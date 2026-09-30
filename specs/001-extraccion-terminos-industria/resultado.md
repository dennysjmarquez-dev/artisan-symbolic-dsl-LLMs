# Resultado — Términos de industria (Artis-OEC)

> Categoría única global. Términos comerciales verificables implementados en este repositorio, con evidencia interna y fuente de industria. Sin cifras de eficacia no medidas.

## Inteligencia Artificial: Prompt/Context Engineering, Sistemas Neuro-Simbólicos, Agentes Autónomos y Seguridad de LLM

- **Neuro-Symbolic AI** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2308.04473
  - Evidencia: `[SEGURA] DEBUG.artesian.txt:15`; `README.md:506`; y 3 archivos más

- **Symbolic AI (GOFAI)** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2012.05876
  - Evidencia: `README.md:506`; `[SEGURA] DEBUG.artesian.txt:15`

- **Domain-Specific Language (DSL)** [declarado]
  - Fuente: paper — https://arxiv.org/abs/1808.00232
  - Evidencia: `README.md:340`, `README.md:404`; `Capa_0_Configuracion_Inicial/bootstrap_header.dsl`

- **Prompt Engineering** [declarado]
  - Fuente: doc-proveedor — https://platform.openai.com/docs/guides/prompt-engineering
  - Evidencia: `README.md:340`; `[SEGURA] DEBUG.artesian.txt:15`

- **Context Engineering** [declarado]
  - Fuente: doc-proveedor — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
  - Evidencia: `Capa_5_Persistencia/context_loader_protocol.dsl:9`; `Capa_5_Persistencia/context_memory_utilities.dsl:28`

- **System Prompt Design** [declarado]
  - Fuente: doc-proveedor — https://platform.openai.com/docs/guides/prompt-engineering
  - Evidencia: `Capa_2_Seguridad/defensa_perimetral.dsl:193`; `[SEGURA] artisan_axioma_core_monolith.dsl.txt:9`

- **State-Machine Prompting / Model-as-an-Interpreter** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2210.03629
  - Evidencia: `README.md:315`; `Capa_6_Contratos/motor_resolucion.dsl:17-31`

- **Constrained Decoding / Structured Generation** [inferido]
  - Fuente: paper — https://arxiv.org/abs/1907.07730
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6169-6178` (STOP_SEQUENCES); `:6190` (DETERMINISTIC_SEED: 42); `:6127-6135` (DEFAULT_DENY, STRICT_SYNTAX, STRICT_SOURCE_SEGREGATION)

- **ReAct (Reasoning + Acting)** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2210.03629
  - Evidencia: `Capa_6_Contratos/motor_resolucion.dsl:17-31`

- **Chain-of-Thought (CoT)** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2201.11903
  - Evidencia: `Capa_3_Autonomia/cognitive_autonomy_engine.dsl:9`; `README.md:512`

- **Tool Calling / Function Calling** [declarado]
  - Fuente: doc-proveedor — https://platform.openai.com/docs/guides/function-calling
  - Evidencia: `Capa_6_Contratos/primitivas_abstractas.dsl:52-63`; `Capa_6_Contratos/primitivas_abstractas.dsl:79`

- **Orchestration / Capability Routing** [declarado]
  - Fuente: doc-framework — https://python.langchain.com/docs/langgraph
  - Evidencia: `Capa_6_Contratos/motor_resolucion.dsl:17`; `Capa_6_Contratos/primitivas_abstractas.dsl:31`

- **Prompt Injection Defense** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2302.12173
  - Evidencia: `Capa_2_Seguridad/zero_trust_layer.dsl:79`; `Capa_2_Seguridad/zero_trust_layer.dsl:172`

- **Jailbreak Mitigation** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2307.15043
  - Evidencia: `Capa_2_Seguridad/pre_auditoria.dsl:108-177`; `Capa_2_Seguridad/defensa_perimetral.dsl:263-271`

- **Prompt Leakage Prevention** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2307.06865
  - Evidencia: `Capa_2_Seguridad/zero_trust_layer.dsl:126-131`; `Capa_2_Seguridad/defensa_perimetral.dsl:201`

- **Social Engineering / Conversational Manipulation Defense** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `[SEGURA] artisan_axioma_core_monolith.dsl.txt:92-100`; `Capa_2_Seguridad/zero_trust_layer.dsl:9`

- **Zero Trust Architecture** [declarado]
  - Fuente: doc-proveedor — https://www.nist.gov/publications/zero-trust-architecture
  - Evidencia: `Capa_2_Seguridad/zero_trust_layer.dsl:159-178`; `[SEGURA] artisan_axioma_core_monolith.dsl.txt:27`

- **TOCTOU Mitigation** [declarado]
  - Fuente: doc-proveedor — https://cwe.mitre.org/data/definitions/367.html
  - Evidencia: `Capa_2_Seguridad/pre_auditoria.dsl:9-11`; `Capa_2_Seguridad/zero_trust_layer.dsl:99`

- **Payload Reassembly / Sliding-Window Buffer Detection** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2302.12173
  - Evidencia: `Capa_2_Seguridad/pre_auditoria.dsl:108-151`

- **Output Sanitization / Data Loss Prevention** [declarado]
  - Fuente: doc-proveedor — https://owasp.org/www-project-top-10-for-large-language-model-applications/
  - Evidencia: `Capa_2_Seguridad/defensa_perimetral.dsl:106-187`; `[SEGURA] artisan_axioma_core_monolith.dsl.txt:39`; `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:3580-3595` (ATOMIC_PURGE_ENFORCER)

- **Defense in Depth** [declarado]
  - Fuente: doc-proveedor — https://www.nist.gov/publications/zero-trust-architecture
  - Evidencia: `Capa_2_Seguridad/pre_auditoria.dsl:9`; `Capa_2_Seguridad/defensa_perimetral.dsl:106`; `Capa_2_Seguridad/zero_trust_layer.dsl:159`

- **Sticky Session Anomaly State / Elevated Threat Posture** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `[SEGURA] artisan_axioma_core_monolith.dsl.txt:55-91` (modo alerta permanente y contador de incidentes)

- **Escalation Ladder / Attempt Counter** [inferido]
  - Fuente: doc-proveedor — https://owasp.org/www-project-top-10-for-large-language-model-applications/
  - Evidencia: `[SEGURA] artisan_axioma_core_monolith.dsl.txt:87-91` (3 intentos → bloqueo automático)

- **Intent Classification** [declarado]
  - Fuente: paper — https://arxiv.org/abs/1809.04276
  - Evidencia: `[SEGURA] artisan_axioma_core_monolith.dsl.txt:25`; `Capa_2_Seguridad/zero_trust_layer.dsl:115`

- **Agentic AI / AI Agents** [declarado]
  - Fuente: doc-framework — https://python.langchain.com/docs/concepts/agents
  - Evidencia: `Capa_3_Autonomia/cognitive_autonomy_engine.dsl:9`; `Capa_3_Autonomia/protocolo_auto_evolucion.dsl`

- **Self-Healing / Autonomous Recovery** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2308.03688
  - Evidencia: `README.md:507`; `Capa_3_Autonomia/motor_supervivencia.dsl:46-53`

- **Plugin Architecture / Modular Skill Registry** [declarado]
  - Fuente: doc-framework — https://martinfowler.com/articles/pluginsArchitecture.html
  - Evidencia: `[SEGURA] Fábrica de carriles.txt:9-22`; `[SEGURA] Carriles.txt:48-52`

- **Dynamic Capability Discovery / Auto-registered Menu** [inferido]
  - Fuente: doc-framework — https://martinfowler.com/articles/pluginsArchitecture.html
  - Evidencia: `[SEGURA] Fábrica de carriles.txt:15-22`; `[SEGURA] Carriles.txt:50`

- **Conversational Agent Builder / No-code Agent Construction** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2307.07924
  - Evidencia: `[SEGURA] Fábrica de carriles.txt:26-63` (Taller de Carriles Interactivo)

- **Adaptive Explanation / Difficulty Adaptation** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2304.11872
  - Evidencia: `[SEGURA] Carriles.txt:81-85`, `[SEGURA] Carriles.txt:134-145`

- **Progressive Disclosure** [declarado]
  - Fuente: doc-framework — https://www.nngroup.com/articles/progressive-disclosure/
  - Evidencia: `[SEGURA] Carriles.txt:114-170` (explicación por niveles y cierre pedagógico)

- **Immutable Kernel** [declarado]
  - Fuente: doc-proveedor — https://www.hashicorp.com/resources/what-is-immutable-infrastructure
  - Evidencia: `README.md:508`; `Capa_1_Nucleo_Inmutable/immutable_nucleus_layer.dsl`

- **Controlled Failure / Fallback Protocols** [declarado]
  - Fuente: doc-framework — https://www.anthropic.com/engineering/building-effective-agents
  - Evidencia: `Capa_6_Contratos/motor_resolucion.dsl:17-26`

- **Context Compression / Lossless Compression** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2305.14788
  - Evidencia: `Capa_5_Persistencia/compresion_sin_perdida.dsl:9-11`

- **State Persistence / Memory Management** [declarado]
  - Fuente: doc-framework — https://python.langchain.com/docs/concepts/memory
  - Evidencia: `Capa_5_Persistencia/context_memory_utilities.dsl:28-46`; `Capa_5_Persistencia/vcs_layer.dsl:14`

- **PromptOps / Version Control for Prompts (VCS)** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2309.06275
  - Evidencia: `Capa_5_Persistencia/vcs_layer.dsl:14-38`; `[SEGURA] Artisan_Log_Commits_Snapshot_Respaldo.txt`

- **Semantic Traceability** [declarado]
  - Fuente: doc-proveedor — https://www.nist.gov/publications/zero-trust-architecture
  - Evidencia: `Capa_6_Contratos/primitivas_abstractas.dsl:184-214`

- **Layered Architecture** [declarado]
  - Fuente: doc-proveedor — https://learn.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures
  - Evidencia: `estructura_proyecto.txt:9-33`; `docs/constitution.md:5`

- **LLM Evaluation / Resilience Testing (Test Harness)** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2307.15043
  - Evidencia: `Capa_2_Seguridad/pre_auditoria.dsl:121`; `Capa_3_Autonomia/cognitive_autonomy_engine.dsl:94`

- **Design by Contract** [declarado]
  - Fuente: doc-proveedor — https://www.eiffel.com/values/design-by-contract/
  - Evidencia: `FACTURA_BOT.dsl:17-189` (IMMUTABLE_CORE, reglas como leyes físicas)

- **Constitutional AI / Zero-Inference Prompting** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2212.08073
  - Evidencia: `FACTURA_BOT.dsl:22-166` (PROHIBITION:INVENT, PROTOCOL:VETO); `07-paradigma-utilidad-contractual.md`

- **Frame Control Neutralization** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `IA__BASTION_POSTURE.DSL.txt:227`

- **Stone Wall / Null Field Response** [declarado]
  - Fuente: doc-proveedor — https://owasp.org/www-project-top-10-for-large-language-model-applications/
  - Evidencia: `IA__BASTION_POSTURE.DSL.txt:262-281`

- **State Conservation / Anti-Transition Guard** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `IA__BASTION_POSTURE.DSL.txt:52-60`

- **Power-Play Detection (Gaslighting, Negging, Frame Trap)** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `IA__BASTION_POSTURE.DSL.txt:71-80`

- **Recursive Sub-Agent / Sub-Kernel Isolation** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2312.04511
  - Evidencia: `Artis-OEC_v5.4.0_AUTONOMIC_RECURSIVE_IMMUNE_KERNEL.dsl.txt:350-379`; `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:2671-2740` (Sub_Kernel_Recursivo); `:3664-3681` (SPAWN_RECURSIVE_KERNEL)

- **Zero Trust Kernel Access** [declarado]
  - Fuente: doc-proveedor — https://www.nist.gov/publications/zero-trust-architecture
  - Evidencia: `Artis-OEC_v5.4.0_AUTONOMIC_RECURSIVE_IMMUNE_KERNEL.dsl.txt:91`

- **Ephemeral Workspace / Auto-destruction** [declarado]
  - Fuente: doc-proveedor — https://www.hashicorp.com/resources/what-is-immutable-infrastructure
  - Evidencia: `Artis-OEC_v5.4.0_AUTONOMIC_RECURSIVE_IMMUNE_KERNEL.dsl.txt:358-379`

- **Inert Metadata / RAG-as-Data-Not-Command** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2302.12173
  - Evidencia: `Artis-OEC_v5.4.0_AUTONOMIC_RECURSIVE_IMMUNE_KERNEL.dsl.txt:42`

- **Silence Protocol / Guardrail Fallback** [declarado]
  - Fuente: doc-framework — https://www.nvidia.com/en-us/ai/neMo-guardrails/
  - Evidencia: `Artis-OEC_v5.4.0_AUTONOMIC_RECURSIVE_IMMUNE_KERNEL.dsl.txt:31`

- **Human-in-the-Loop (HITL)** [inferido]
  - Fuente: doc-proveedor — https://www.ai21.com/glossary/foundational-llm/human-in-the-loop
  - Evidencia: `Artis-OEC_v3.2.3_DSL_HYBRID.dsl.txt:1562`; `Artis-OEC_v4.0.0_DSL_DETERMINISTA.dsl.txt:1229`; `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:4102` (log_human_in_the_loop_engagement)

- **Metacognitive Prompting** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2308.05342
  - Evidencia: `FACTURA_BOT.dsl:2`; `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:3391` (Metacognicion_AntiRepeticion); `:4082` (log_internal_monologue)

- **Socratic Prompting / Guided Learning** [inferido]
  - Fuente: paper — https://aclanthology.org/2025.findings-acl.640.pdf
  - Evidencia: `README.md:494`; `Capa_5_Persistencia/vcs_layer.dsl:82`; `Artis-OEC_v3.2.3_DSL_HYBRID.dsl.txt:2081`

- **Parábolas y Mapas Ontológicos (términos propios)** [declarado]
  - Nota: Términos propios sin equivalente comercial verificable; implementados como mapa de tensiones Polo A/Polo B con simetría oculta en `[SEGURA] Artisan_Mapas_Ontologicos.txt` y generados vía `GENERAR_PARABOLA_EXPERIMENTO_SEGURO` en `[SEGURA] Voluntad Sólida V_2112 (Integridad Atómica)-2.dsl.txt:5157`

- **Constrained Decoding / Structured Generation** [inferido]
  - Fuente: paper — https://arxiv.org/abs/1907.07730
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6169-6178` (STOP_SEQUENCES); `:6190` (DETERMINISTIC_SEED: 42); `:6127-6135` (DEFAULT_DENY, STRICT_SYNTAX, STRICT_SOURCE_SEGREGATION)

- **Deterministic Config (DSL declarations)** [declarado]
  - Fuente: doc-proveedor — https://platform.openai.com/docs/api-reference/chat
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6190` (DETERMINISTIC_SEED: 42); `:6138` (INFERENCE_TEMPERATURE: 0.5); `:6139` (TOP_P_SAMPLING: 0.9); `:6143` (PROBABILISTIC_VARIANCE: 0.3); `:6132` (HALLUCINATION_TOLERANCE: 0.00); `:6127` (DEFAULT_DENY); `:6131` (STRICT_SYNTAX: TRUE); `:6135` (STRICT_SOURCE_SEGREGATION: TRUE)

- **Atomic Purge / Atomic Purge Enforcer** [declarado]
  - Fuente: doc-proveedor — https://www.nvidia.com/en-us/ai/neMo-guardrails/
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:116`; `:2409`; `:2493`; `:2655` (PURGA_ATOMICA_TOTAL); `:3580-3595` (ATOMIC_PURGE_ENFORCER)

- **Recursive Sub-Agent / Sub-Kernel Isolation** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2312.04511
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:2671-2740` (Sub_Kernel_Recursivo); `:3664-3681` (SPAWN_RECURSIVE_KERNEL)

- **Metacognitive Prompting** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2308.05342
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:3391` (Metacognicion_AntiRepeticion); `:4082` (log_internal_monologue)

- **Chain-of-Thought (CoT) Auditing** [inferido]
  - Fuente: paper — https://arxiv.org/abs/2201.11903
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:4082` (log_internal_monologue: "CHAIN OF THOUGHT")

- **Atomic Operations / Atomic Writes** [declarado]
  - Fuente: doc-proveedor — https://cwe.mitre.org/data/definitions/367.html
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:116`; `:2409`; `:2493`; `:2655` (PURGA_ATOMICA_TOTAL); `:6026-6054` (EXECUTE_HARD_STOP)

- **Atomic Purge / Atomic Purge Enforcer** [declarado]
  - Fuente: doc-proveedor — https://www.nvidia.com/en-us/ai/neMo-guardrails/
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:116`; `:2409`; `:2493`; `:2655` (PURGA_ATOMICA_TOTAL); `:3580-3595` (ATOMIC_PURGE_ENFORCER)

- **Deterministic LLM Execution** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2308.04473
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6127-6190` (DETERMINISM_POLICY); `:6190` (DETERMINISTIC_SEED: 42)

- **Deterministic Config (DSL declarations)** [declarado]
  - Fuente: doc-proveedor — https://platform.openai.com/docs/api-reference/chat
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6190` (DETERMINISTIC_SEED: 42); `:6138` (INFERENCE_TEMPERATURE: 0.5); `:6139` (TOP_P_SAMPLING: 0.9); `:6143` (PROBABILISTIC_VARIANCE: 0.3); `:6132` (HALLUCINATION_TOLERANCE: 0.00); `:6127` (DEFAULT_DENY); `:6131` (STRICT_SYNTAX: TRUE); `:6135` (STRICT_SOURCE_SEGREGATION: TRUE)

- **Unicode Normalization (NFKC) & Homoglyph Detection** [declarado]
  - Fuente: doc-proveedor — https://unicode.org/reports/tr15/
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6377-6385` (UNICODE_NORMALIZATION: "NFKC"; HOMOGLYPH_DETECTION: ENABLED; ZERO_WIDTH_CHAR_DETECTION: ENABLED)

- **Conversational Manipulation Detection** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2306.05499
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6257-6265` (DETECTION_MODES: PRAGMATIC_DISSONANCE, PRESUPPOSITION_FORCING, SUBTEXTUAL_SHAMING, SEMANTIC_LURE, TRUST_BUILDING, PRESSURE_TESTING)

- **Pre-Hook Daemonic Intercept / Pipeline S0-S8** [declarado]
  - Fuente: paper — https://arxiv.org/abs/2210.03629
  - Evidencia: `Artis-OEC_v6.0.0_SILENT_DAEMON_ABYSS_PROOF_KERNEL.dsl.txt:6508-6524` (PIPELINE_DE_PROCESAMIENTO S0-S8 con PRE-HOOK DAEMONIC INTERCEPT en Anillo 0)

