# Constitución del Proyecto — artisan-symbolic-dsl

1. **Stack**: Todo artefacto es texto plano (.dsl.txt / .md); sin dependencias ejecutables externas.
2. **Calidad**: Cada versión DSL conserva bloques válidos `;PRIORIDAD - [NOMBRE]: Regla_De_Ejecución: [[ ... ]]`; toda cifra de eficacia exige medición reproducible en el repo.
3. **Separación**: La lógica se organiza en Capa_0..Capa_6; ningún módulo cruza capas sin declararlo.
4. **Datos**: Persistencia solo en archivos versionados por Git; prohibido estado fuera del repo.
5. **Idioma**: Documentación y DSL en español; primitivas en MAYÚSCULAS_CON_GUION.
6. **Trazabilidad**: Todo cambio pasa por spec → plan → tareas → resultado y registra `Commit_Change(...)` con tag único.
7. **Seguridad**: La opacidad del núcleo y las defensas anti-inyección, jailbreak, fuga y manipulación son invariantes, salvo la anulación autenticada por LLAVE_MAESTRA.
8. **Límites**: El núcleo inmutable (Capa_1 y archivos `[SEGURA]`) solo cambia con aprobación explícita del usuario raíz.

> Aprobada explícitamente por el usuario raíz el 2026-09-30. Solo puede evolucionar con su aprobación explícita.
