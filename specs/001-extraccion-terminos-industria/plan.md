# Plan técnico — Spec 001 (Extracción de términos de industria)

> Fase 4 (CÓMO). Sin código. El resultado observable ya está en `spec.md`; aquí se decide la organización interna del proceso de extracción.

## Estructura de módulos
El "sistema" es un procedimiento de extracción documental (no hay binario ejecutable; constitución, principio 1). Componentes lógicos:

- `specs/001-extraccion-terminos-industria/resultado.md` → **Salida**: listado final en categoría única global (RF-8).
- **Inventario** (componente) → recorre el repo en HEAD y aplica inclusiones/exclusiones (RF-1).
- **Extractor** (componente) → lee cada archivo y extrae técnicas/métodos/patrones, incluidos los no nombrados por el autor (RF-2, RF-10).
- **Verificador de fuentes** (componente) → valida cada término contra fuente de industria con URL; descarta propios sin equivalente (RF-4, RF-5).
- **Clasificador/Deduplicador** (componente) → categoría única global + fusión de apariciones (RF-3, RF-7).
- **Citador** (componente) → evidencia `archivo:línea` y marca `[declarado]`/`[inferido]` (RF-6, RF-11).
- **Bloque de seguridad** (componente) → cobertura explícita de defensas anti-inyección/jailbreak/fuga/manipulación (RF-9).
- **Guardián de cifras** (componente) → veta cifras de eficacia sin medición reproducible (RF-12).

## Modelo de datos interno
Esquema de cada entrada del listado (no es salida final, es la unidad de trabajo):

```
Entrada:
  termino_comercial : string        # forma de industria, normalmente en inglés
  categoria         : string        # ÚNICA y global para todo el listado
  fuentes           : [ {tipo: paper|doc-proveedor|doc-framework, url: string} ]  # ≥1
  evidencia         : [ {archivo: string, lineas: "Lx-Ly"|"Lx", origen: declarado|inferido} ]  # ≤3 + resumen
  apariciones_extra : integer       # para "y N archivos más"
  notas             : string?       # ambigüedad de término (opcional)
```

Reglas de integridad:
- `fuentes` ≥ 1 y toda `url` pertenece a paper/arXiv/ACM/IEEE, doc oficial de proveedor o doc oficial de framework (RF-4).
- `evidencia.origen` obligatorio (RF-11).
- Sin cifras (`%`, tasas) en ningún campo salvo medición reproducible citada (RF-12).

## Algoritmos y lógica interna

### A1 — Inventario sobre HEAD (RF-1)
1. Tomar la lista de archivos del último commit (HEAD), no del working tree → reproducibilidad.
2. Excluir: `.git/`, `LICENSE`, binarios (contenido no textual), symlinks (no se siguen), `specs/` y `docs/` (autorreferencia).
3. Incluir por patrón/glob los `[SEGURA] ...` con uno o dos espacios, sin normalizar nombres.
4. Si un archivo no se puede leer como UTF-8, registrar incidencia y continuar.

### A2 — Extracción de técnicas (RF-2, RF-10)
1. Detectar: bloques `;PRIORIDAD - [NOMBRE]`, cabeceras de capa, comentarios que documentan una técnica, y conceptos nombrados en README/paradigma.
2. Descartar: identificadores, nombres de funciones, palabras reservadas del DSL y comentarios no técnicos.
3. Si hay comportamiento técnico sin nombre declarado → nombrarlo con el término comercial correcto, marcándolo `[inferido]` (RF-10).

### A3 — Deduplicación (RF-3, RF-7)
1. Clave = término comercial normalizado (minúsculas, sin puntuación).
2. Fusionar todas las apariciones en una sola entrada; citar todas las ubicaciones (aplicando tope de A4).

### A4 — Citas (RF-6)
1. Rango `archivo:Lx-Ly` si el término ocupa varias líneas; `archivo:Lx` si es una.
2. Patrón transversal → máximo 3 citas representativas + "y N archivos más".
3. Marcar `[declarado]` o `[inferido]` por cita (RF-11).

### A5 — Verificación de fuentes (RF-4, RF-5)
1. Para cada término, buscar fuente de industria.
2. Aceptar solo: paper (arXiv/ACM/IEEE/revista), doc oficial de proveedor (OpenAI, Anthropic, Google, etc.) o doc oficial de framework conocido. Blogs y agregadores = rechazo.
3. Si no hay equivalente comercial verificable → excluir el término (RF-5).

### A6 — Seguridad (RF-9)
1. Identificar en el repo las defensas implementadas contra: prompt injection (directa e indirecta), jailbreak, prompt leakage y manipulación conversacional/ingeniería social.
2. Solo se incluye lo que el repo implementa como DEFENSA, con evidencia; no se incluye la amenaza como logro.

### A7 — Cifras (RF-12)
1. Antes de publicar, barrer el listado: cualquier `%`/tasa sin medición reproducible en el repo se elimina.

## Decisiones técnicas y arquitectura
- **Decisión**: categoría única global para todo el listado.
  - **Alternativa descartada**: múltiples categorías.
  - **Por qué**: pedido explícito del usuario raíz; simplifica el "Acerca de".
  - **Restricción de constitución**: principio 5 (idioma español).
- **Decisión**: escanear HEAD.
  - **Alternativa descartada**: working tree.
  - **Por qué**: reproducibilidad ante estado Git sucio.
  - **Restricción de constitución**: principio 4 (datos versionados por Git).
- **Decisión**: separar el resultado en `resultado.md`.
  - **Alternativa descartada**: escribir en `spec.md`.
  - **Por qué**: RF-8; la spec no se contamina con resultados.
  - **Restricción de constitución**: principio 1 (todo texto plano .md).
- **Decisión**: tope de 3 citas + "N más".
  - **Alternativa descartada**: citar todas las apariciones.
  - **Por qué**: control de volumen; el detalle completo no cabe en LinkedIn.
  - **Restricción de constitución**: —.
- **Decisión**: fuentes con URL obligatoria.
  - **Alternativa descartada**: fuente sin URL.
  - **Por qué**: verificabilidad observable (RF-4).
  - **Restricción de constitución**: —.
- **Decisión**: marcar `[declarado]`/`[inferido]`.
  - **Alternativa descartada**: evidencia sin origen.
  - **Por qué**: RF-11; separa lo que el autor nombró de lo deducido del código.
  - **Restricción de constitución**: principio 6 (trazabilidad).

## Contrato de interfaces externas
Entregable único: `specs/001-extraccion-terminos-industria/resultado.md`.

Formato:
```markdown
# Resultado — Términos de industria (Artis-OEC)

## IA
- **<Término comercial>** [declarado|inferido]
  - Fuente: <paper|doc-proveedor|doc-framework> — <URL>
  - Evidencia: archivo:Lx-Ly; archivo:Lz; y N archivos más
...
```
- Idioma: español; términos comerciales en su forma inglesa original.
- Sin cifras de eficacia no medidas.

## Estrategia de tests
Manual/observable (constitución, principio 1: sin dependencias ejecutables).

- Unitarios por término:
  - ≥1 fuente con URL válida (RF-4).
  - Evidencia `archivo:línea` presente (RF-6).
  - Origen `[declarado]`/`[inferido]` presente (RF-11).
- Integración:
  - Recorrido completo sin omitir carpetas/versiones (RF-1).
  - Dedup correcto: un término una sola vez (RF-7).
  - Bloque de seguridad presente (RF-9).
  - Ausencia de cifras no medidas (RF-12).
  - Archivos vacíos/malformados reportados como incidencia sin abortar.

## Cobertura RF → plan
- RF-1 → A1
- RF-2 → A2
- RF-3 → A3, Decisión categoría única
- RF-4 → A5
- RF-5 → A5
- RF-6 → A4
- RF-7 → A3, A4
- RF-8 → Salida / Contrato
- RF-9 → A6
- RF-10 → A2
- RF-11 → A4
- RF-12 → A7
