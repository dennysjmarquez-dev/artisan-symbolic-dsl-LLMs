# Spec 001 — Extracción de términos de industria desde el repositorio

## Contexto y objetivo
El repositorio contiene años de trabajo autodidacta en un DSL simbólico propio (Artis-OEC) donde el autor descubrió y nombró con términos propios técnicas que en la industria ya existen con nombres comerciales. El objetivo es escanear la totalidad del repositorio, detectar cada técnica/método/metodología implementada, incluso cuando el autor no le haya dado un nombre propio y solo exista como código/implementación, y producir un listado de términos **comerciales reales y verificables** en una única categoría global, para ser usado por el autor en la sección "Acerca de" de LinkedIn.

## Usuarios / actores
- **Autor raíz**: dueño del repositorio y destinatario del listado; lo copia a LinkedIn.
- **Reclutadores / pares de IA**: lectores finales del listado (consumidores indirectos).

## Historias de usuario
- H1: Como autor raíz quiero un listado de términos comerciales de IA en una única categoría global para publicarlos en LinkedIn como evidencia de mis competencias.
- H2: Como autor raíz quiero que cada término esté respaldado por la ubicación exacta en mi repositorio para poder demostrar que lo implementé.

## Requisitos funcionales (criterios de aceptación en EARS)
- RF-1: EL SISTEMA escaneará todos los archivos del repositorio, incluidos los archivos `[SEGURA] ...` y todas las versiones `Artis-OEC_v*`, EXCEPTO `.git/`, `LICENSE`, binarios y symlinks (no se siguen). Se excluyen del escaneo `specs/` y `docs/` (autorreferencia).
- RF-2: EL SISTEMA extraerá de cada archivo toda técnica, método, patrón o arquitectura con nombre conceptual. Se excluyen identificadores, nombres de funciones, palabras reservadas del DSL y comentarios, salvo que el comentario documente una técnica.
- RF-3: EL SISTEMA clasificará todos los hallazgos en UNA sola categoría global con un solo título, y listará dentro sus términos separados por comas o viñetas. Regla de deduplicación: si un término aparece en varios archivos, se lista una sola vez con todas sus citas.
- RF-4: EL SISTEMA incluirá en el listado únicamente términos que puedan citarse con fuente de industria reconocida: paper (arXiv, revista, ACM, IEEE), documentación oficial de proveedor (OpenAI, Anthropic, Google, etc.) o documentación oficial de un framework conocido. Blogs y agregadores NO cuentan. Mínimo 1 fuente por término, con URL.
- RF-5: SI un término propio no tiene equivalente comercial verificable, ENTONCES EL SISTEMA lo excluirá del listado.
- RF-6: EL SISTEMA asociará a cada término comercial la evidencia interna en formato `archivo:línea`. Término en varias líneas = rango `archivo:Lx-Ly`. Patrón transversal = máximo 3 citas representativas + "y N archivos más".
- RF-7: CUANDO un mismo término aparezca en varios archivos, EL SISTEMA lo listará una sola vez y citará todas las ubicaciones donde aparece (aplicando RF-6).
- RF-8: EL SISTEMA escribirá el listado final en un archivo NUEVO: `specs/001-extraccion-terminos-industria/resultado.md` (no en `spec.md`).
- RF-9: EL SISTEMA dedicará cobertura explícita a los métodos usados como DEFENSA para prompt injection (directa e indirecta), jailbreak, fuga de prompt (prompt leakage) y manipulación conversacional/ingeniería social. Solo se incluye lo que el repo implementa como defensa, con evidencia.
- RF-10: CUANDO una técnica esté implementada en el código sin un término propio declarado, EL SISTEMA la nombrará y citará con el término comercial correcto de industria.
- RF-11: EL SISTEMA distinguirá en la evidencia si el término fue declarado explícitamente por el autor o si fue inferido por el sistema. `[declarado]` = el autor lo nombra en README, en el documento del paradigma o en un comentario/cabecera del DSL; `[inferido]` = se deduce del comportamiento del código.
- RF-12: NINGUNA cifra de eficacia (%, tasas) entrará al listado si no existe una medición reproducible en el repositorio.

## Requisitos no funcionales
- Idioma del listado: español (los términos comerciales pueden quedar en su forma inglesa original).
- Todo artefacto es texto plano Markdown; sin dependencias ejecutables externas.
- Cada término debe ser verificable de forma observable mediante su fuente de industria citada.
- El escaneo cubre la totalidad del repositorio (según RF-1), sin omisión de carpetas ni versiones.
- El "Acerca de" de LinkedIn respeta el límite de caracteres vigente de LinkedIn (verificar el límite actual antes de publicar).

## Casos límite
- Archivos `[SEGURA] ...` con espacios dobles o nombres no estándar: no se normalizan; se leen por patrón/glob con uno o dos espacios.
- Versiones `Artis-OEC_v*` duplicadas o superpuestas entre sí.
- Términos propios repetidos a lo largo de múltiples capas (`Capa_0..Capa_6`): se aplica deduplicación (RF-3/RF-7).
- Archivos no-DSL (`.md`, `estructura_proyecto.txt`, `basteaon_temp.datosdeentrenamiento.md`).
- Términos propios sin equivalente comercial (deben quedar fuera).
- Técnicas implementadas sin ningún término asociado en el texto (solo deducibles del código).
- Implementaciones ambiguas que admitan más de un término comercial posible.
- Archivos vacíos o DSL malformado: se reportan como incidencia y el escaneo continúa.
- Estado Git sucio: se escanea el último commit (HEAD) para que sea reproducible.
- Volumen: la lista completa va en `resultado.md`; el "Acerca de" de LinkedIn respeta el límite de caracteres vigente.
- Codificación: se asume UTF-8; si falla la lectura de un archivo, se reporta.

## Fuera de alcance
- No modificar ningún archivo del repositorio salvo crear `resultado.md` dentro de `specs/001-extraccion-terminos-industria/`.
- Reescribir o refactorizar el DSL.
- Implementar código ejecutable o scripts automatizados de extracción.
- Traducir el listado a otros idiomas distintos del español.
- Publicar directamente en LinkedIn.
- Mapear términos propios sin equivalente comercial.
- Inventar términos comerciales que no existan en la industria para implementaciones sin equivalente real.

## Criterios de finalización
- El listado completo vive en `specs/001-extraccion-terminos-industria/resultado.md`.
- Todos los RF-1..RF-12 se cumplen de forma observable.
- Cada término del listado tiene fuente de industria (con URL) y evidencia interna `archivo:línea`.
- Aprobación explícita del usuario raíz antes de pasar a la fase de Plan técnico.

## Resultado esperado
> [PENDIENTE DE EJECUCIÓN — se completa en `specs/001-extraccion-terminos-industria/resultado.md` tras el escaneo total del repositorio en la fase de implementación.]

## Dudas abiertas
- Ninguna. El listado se entrega completo sin límite de categorías ni de términos.
