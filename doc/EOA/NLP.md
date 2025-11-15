# Análisis de técnicas de procesamiento de lenguaje natural (NLP)

## Resumen del Estado del Arte en técnicas de Procesamiento de Lenguaje Natural (NLP)

### Tendencias generales

- Modelos fundacionales multimodales y multilingües (p.ej., LLMs tipo Transformer con 10B–>1T parámetros) dominan tareas generales con transferencia cero/pocas tomas.
- Enfoque “instrucción + alineación” (RLHF/DPO, SFT) para utilidad y seguridad.
- Inferencia eficiente: cuantización (INT8/4), podado, LoRA/QLoRA, KV-caching, batching especulativo.
- Razonamiento: cadenas de pensamiento, árboles de pensamiento, verificación iterativa, herramientas externas (RAG, program-of-thought, código).

### Arquitecturas y preentrenamiento

- Transformer y variantes (FlashAttention, RoPE/ALiBi, Mixture-of-Experts, prefix/RMSNorm).
- Preentrenamiento masivo con corpus web filtrado; objetivos: next-token, span-masking, SFT con datos de instrucciones.
- Multimodalidad: encoders de visión/audio acoplados a decoders lingüísticos; grounding con herramientas.

### Adaptación y especialización

Fine-tuning ligero: LoRA/QLoRA, adapters, IA3; afinado por dominios

___

## Resumen del Estado del Arte: procesamiento de prompts para generación de código

### Objetivo del subcampo

- Convertir instrucciones naturales en código correcto, seguro y eficiente.
- Minimizar alucinaciones, ambigüedad y errores de compilación/ejecución.

### Modelos y arquitecturas

- LLMs code-centric: CodeLlama, StarCoder2, DeepSeek-Coder, WizardCoder, Phi-4-code, Qwen2.5-Coder, OpenAI o1/o3-code-like, Mistral-Coder.
- Mezcla de expertos (MoE) para rutas especializadas de sintaxis y APIs.
- Contexto largo con KV cache y atención eficiente; soportan repositorios completos.

### Preentrenamiento y datos

- Corpora enormes de repos públicos, issues/PRs, docstrings, notebooks; deduplicación y filtrado agresivo.
- Objetivos: next-token, fill-in-the-middle (FIM), infilling estructurado (span-masking), ejecución-evaluación en el bucle (self-play).
- Canonicalización de estilos, normalización de imports, mapeo versión-API.

### Instruccionado y alineación para prompts

- SFT con pares instrucción→solución y tareas multi-paso (esqueleto, luego detalles).
