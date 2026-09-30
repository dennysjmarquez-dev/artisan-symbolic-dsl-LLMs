# Tareas — Spec 001

## T1: Inventario sobre HEAD
- **RF cubiertos**: RF-1
- **Descripción**: Listar archivos del último commit (HEAD) y aplicar inclusiones/exclusiones.
- **Hecho cuando**:
  - [ ] Lista incluye `[SEGURA] ...` (1 o 2 espacios) sin normalizar nombres
  - [ ] Excluye `.git/`, `LICENSE`, binarios, symlinks, `specs/`, `docs/`
  - [ ] Archivo no-UTF8 se reporta como incidencia y el escaneo continúa
  - [ ] **Estado**: pendiente

---

## T2: Extracción de técnicas
- **RF cubiertos**: RF-2, RF-10
- **Descripción**: Extraer técnicas/métodos/patrones del texto; nombrar con término comercial lo no declarado.
- **Hecho cuando**:
  - [ ] Se detectan bloques `;PRIORIDAD - [NOMBRE]`, cabeceras de capa y comentarios técnicos
  - [ ] Se descartan identificadores, funciones, palabras reservadas y comentarios no técnicos
  - [ ] Comportamiento sin nombre declarado queda marcado `[inferido]`
  - [ ] **Estado**: pendiente

---

## T3: Verificación de fuentes de industria
- **RF cubiertos**: RF-4, RF-5
- **Descripción**: Validar cada término contra paper/doc oficial de proveedor/framework con URL.
- **Hecho cuando**:
  - [ ] Toda entrada tiene ≥1 fuente con URL (paper/arXiv/ACM/IEEE o doc oficial)
  - [ ] Blogs y agregadores son rechazados
  - [ ] Término propio sin equivalente comercial es excluido
  - [ ] **Estado**: pendiente

---

## T4: Deduplicación y categoría única
- **RF cubiertos**: RF-3, RF-7
- **Descripción**: Fusionar apariciones por término normalizado en una categoría global única.
- **Hecho cuando**:
  - [ ] Un término aparece una sola vez aunque esté en varias capas
  - [ ] Todas sus ubicaciones quedan citadas en la misma entrada
  - [ ] **Estado**: pendiente

---

## T5: Citado y marca de origen
- **RF cubiertos**: RF-6, RF-11
- **Descripción**: Asociar evidencia `archivo:Lx-Ly` y marcar `[declarado]`/`[inferido]`.
- **Hecho cuando**:
  - [ ] Rango correcto para términos multilínea; línea única cuando aplica
  - [ ] Patrón transversal: ≤3 citas + "y N archivos más"
  - [ ] Cada cita tiene `[declarado]` o `[inferido]`
  - [ ] **Estado**: pendiente

---

## T6: Bloque de seguridad
- **RF cubiertos**: RF-9
- **Descripción**: Cubrir defensas anti prompt injection (directa/indirecta), jailbreak, fuga y manipulación.
- **Hecho cuando**:
  - [ ] Cada defensa incluida tiene evidencia `archivo:línea`
  - [ ] Amenazas no implementadas como defensa no se listan como logro
  - [ ] **Estado**: pendiente

---

## T7: Guardián de cifras
- **RF cubiertos**: RF-12
- **Descripción**: Vetar cifras de eficacia sin medición reproducible.
- **Hecho cuando**:
  - [ ] Ningún `%`/tasa aparece sin medición reproducible citada
  - [ ] **Estado**: pendiente

---

## T8: Ensamblado y validación de resultado.md
- **RF cubiertos**: RF-8
- **Descripción**: Escribir el listado final en `resultado.md` y validar cobertura global.
- **Hecho cuando**:
  - [ ] `resultado.md` existe con categoría única y formato acordado
  - [ ] Todos los RF-1..RF-12 verificables de forma observable
  - [ ] **Estado**: pendiente

---

## Cobertura de requisitos
| RF | Cubierto por |
|----|-------------|
| RF-1 | T1 |
| RF-2 | T2 |
| RF-3 | T4 |
| RF-4 | T3 |
| RF-5 | T3 |
| RF-6 | T5 |
| RF-7 | T4 |
| RF-8 | T8 |
| RF-9 | T6 |
| RF-10 | T2 |
| RF-11 | T5 |
| RF-12 | T7 |
