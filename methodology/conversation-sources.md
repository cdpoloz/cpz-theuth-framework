<!-- English section first; Spanish section follows. -->

-------------------------------------

# Conversations as Theuth sources

Conversations with LLMs can be valuable sources in different Theuth implementations. Their relevance depends on the goal: in personal memory they often help reconstruct what a person requested, decided, corrected, and left pending; in shared memory they may be useful when capture and handling are authorized. Neither profile is limited to one source type.

Before adding conversations or internal documents to a shared environment, confirm that their use is authorized and that the AI provider may access and process the information. Respect access restrictions in summaries, indexes, and other derivatives as well.

## Evaluate and decide whether to preserve

As an optional workflow, an implementation may offer two separate assisted tools:

1. **Evaluation:** analyze the available conversation and suggest decisions, claims, preferences, requirements, findings, or pending tasks that may be useful to preserve. For each item, explain its relevance and identify the specific turns supporting it. Distinguish what the user said from what the assistant said, and flag uncertainty, contradictions, or sensitive information.
2. **Human review:** the person decides which suggestions to accept, correct, or reject. Evaluation does not create a source or by itself authorize archiving the conversation.
3. **Preservation:** only when requested by the person, another tool prepares the source record and portable representation according to this methodology and the [source template](../templates/source.md). Derived records are prepared only within the approved scope and retain references to specific turns.

Analysis of long conversations should report what content could be reviewed. If the tool could not access the entire conversation, it must identify the scope or missing parts and must not present its findings as an exhaustive assessment. A prior summary of a conversation does not replace the original source for this review.

The framework defines these requirements and the workflow order, not an executable tool format. Specific instructions for skills, commands, or integrations belong to each implementation and provider. Evaluation and preservation may be offered as separate skills, automations, or other tools, while keeping the archiving decision in the person’s hands.

## What a conversation establishes

A conversation is direct evidence of what its participants said within that session. For example, it may support a user preference, an expressed decision, or a recommendation offered by the assistant.

An LLM response is not by itself an independent source for an external claim. If the conversation cites a report, article, or repository, also record that original source when the factual claim will be reused or could affect a decision.

## Which conversations to preserve

At the end of a work session, assess whether it contains decisions, requirements, constraints, findings, accepted changes, or pending items needed to continue a project. The person decides whether to preserve it. Define the scope of archiving and apply it consistently. Conversations without reusable content may be left out; in that case, the system must not be presented as a complete record of every interaction.

Capture the original material before summarizing it or extracting decisions. Derived notes may guide retrieval but do not replace the preserved conversation.

## Preserve the original and support portability

When the provider offers an export, preserve the exported file without editing it. Add a normalized, machine-readable representation so another provider can process the conversation. The normalized representation is a derivative, not the original: record which tool created it, its version, and any content it could not include.

Recommended initial format for the normalized record: JSONL, one turn per line, in order. Include, when available:

- stable source ID and turn number or ID;
- timestamp and time zone;
- participant role (user, assistant, or tool);
- turn content;
- references to attachments, tool results, or omitted items;
- provider, model, and native conversation ID as metadata, not as reading requirements.

Do not invent timestamps, turns, tool calls, or system instructions absent from the export. State whether the capture is complete, partial, or reconstructed. Preserve attachments necessary to interpret the session, with access controls appropriate to their sensitivity.

## Location and naming

A possible initial structure for preserved conversations is:

```text
knowledge/
└── sources/
    └── conversations/
        └── <source-id>/
            ├── source.md
            ├── transcript.jsonl
            ├── original.<ext>       (if the provider allows an export)
            └── attachments/          (if needed to understand the session)
```

A conversation may refer to more than one project; therefore, sources can be stored in a common location and linked from the relevant projects. The project, decision, or claim record should point to a specific turn, for example \`source-id#turn-0042\`, in addition to the file.

## Capture workflow

1. The person chooses a conversation for evaluation or directly requests its preservation.
2. If an evaluation is performed, the person reviews and selects the suggestions to preserve; they may skip the evaluation if they already know which conversation they want to save.
3. Preserve the export or original material within the approved scope, without editing it when available.
4. Create the normalized transcript and source record with source metadata, integrity, coverage, and limitations.
5. Record approved decisions, claims, or pending items separately and link them to turn IDs.
6. Version the files and check that links resolve.

Do not store credentials or secrets in the knowledge history. If sensitive material should not enter the repository, exclude it from capture or store it in a protected location, and note the limitation without copying the sensitive content.

## Resume work with another provider

A new provider should be able to read the neutral format, starting with the usage guide, current project status, and active decisions. Then retrieve only the turns and sources relevant to the task. The complete historical archive remains available for verification; it is not loaded in full for every query.

Provider-specific adapters may change. Theuth IDs, roles, turns, projects, and references should remain stable when changing tools.

## Verification limits

A reference to a conversation establishes what was said, not whether a factual claim expressed there is true. For fact-checking, follow the link to the original external source or mark the claim as pending or unverified.

If the original conversation cannot be exported or is no longer available, keep a record describing that limitation. Do not present a paraphrase or snapshot as if it were the original record.

-------------------------------------

# Conversaciones como fuentes de Theuth

Las conversaciones con LLM pueden ser fuentes valiosas en distintas implementaciones de Theuth. Su relevancia depende del objetivo: en una memoria personal suelen ayudar a reconstruir lo que la persona pidió, decidió, corrigió y dejó pendiente; en una memoria compartida pueden ser útiles si la captura y el tratamiento están autorizados. Ningún perfil queda limitado a un tipo de fuente.

Antes de incorporar conversaciones o documentos internos a un entorno compartido, confirma que el uso está autorizado y que el proveedor de IA puede acceder y procesar esa información. Respeta las restricciones de acceso también en los resúmenes, índices y demás derivados.

## Evaluar y decidir si conservar

Como flujo opcional, la implementación puede ofrecer dos herramientas asistidas y separadas:

1. **Evaluación:** analiza la conversación disponible y propone decisiones, afirmaciones, preferencias, requisitos, hallazgos o tareas pendientes que podrían ser útiles para conservar. Para cada elemento, explica su relevancia y señala los turnos concretos que lo sustentan. Distingue lo dicho por el usuario de lo dicho por el asistente y marca incertidumbres, contradicciones o información sensible.
2. **Revisión de la persona:** la persona decide qué propuestas acepta, corrige o descarta. La evaluación no crea una fuente ni autoriza por sí sola el archivo de la conversación.
3. **Conservación:** solo cuando la persona lo solicite, otra herramienta prepara la ficha de fuente y la representación portable según esta metodología y la [plantilla de fuente](../templates/source.md). Los registros derivados se preparan únicamente dentro del alcance aprobado y conservan referencias a turnos concretos.

El análisis de conversaciones extensas debe informar qué contenido pudo revisar. Si la herramienta no tuvo acceso a la conversación completa, debe identificar el alcance o las partes faltantes y no presentar sus hallazgos como una evaluación exhaustiva. Una conversación previa resumida no sustituye la fuente original para esta revisión.

El framework define estos requisitos y el orden del flujo, no el formato ejecutable de una herramienta. Las instrucciones concretas de skills, comandos o integraciones corresponden a cada implementación y proveedor. La evaluación y la conservación pueden ofrecerse como skills separados, automatizaciones u otras herramientas, siempre manteniendo la decisión de archivo en manos de la persona.

## Qué prueba una conversación

Una conversación es evidencia directa de lo que sus participantes dijeron dentro de esa sesión. Por ejemplo, puede respaldar una preferencia del usuario, una decisión expresada o una recomendación que el asistente ofreció.

La respuesta de un LLM no constituye por sí sola una fuente independiente para una afirmación externa. Si la conversación cita un informe, un artículo o un repositorio, registra también esa fuente original cuando la afirmación factual vaya a ser reutilizada o pueda afectar una decisión.

## Qué conversaciones conservar

Al cerrar una sesión de trabajo, puede evaluarse si contiene decisiones, requisitos, restricciones, hallazgos, cambios aceptados o pendientes necesarios para continuar un proyecto. La decisión de conservarla corresponde a la persona. Define el alcance del archivo y aplícalo de forma constante. Las charlas sin contenido reutilizable pueden quedar fuera; en ese caso, el sistema no debe presentarse como un registro completo de toda interacción.

Captura el material original antes de resumirlo o extraer decisiones. Las notas derivadas pueden orientar consultas, pero no reemplazan la conversación conservada.

## Conservar el original y permitir la portabilidad

Cuando el proveedor ofrezca una exportación, conserva el archivo exportado sin editarlo. Añade una representación normalizada y legible por máquina para que un proveedor distinto pueda procesar la conversación. La representación normalizada es una derivación, no el original: registra qué herramienta la generó, su versión y qué contenido no pudo incluir.

Formato inicial recomendado para el registro normalizado: JSONL, un turno por línea, en orden. Incluye, cuando estén disponibles:

- ID estable del origen y número o ID de turno;
- marca temporal y zona horaria;
- rol del participante (usuario, asistente o herramienta);
- contenido del turno;
- referencias a adjuntos, resultados de herramientas o elementos omitidos;
- proveedor, modelo y ID nativo de conversación como metadatos, no como requisito de lectura.

No inventes marcas temporales, turnos, llamadas a herramientas ni instrucciones de sistema que la exportación no contenga. Indica si la captura es completa, parcial o reconstruida. Conserva los adjuntos que sean necesarios para interpretar la sesión, con controles de acceso acordes a su sensibilidad.

## Ubicación y nombres

Una estructura inicial posible para conversaciones conservadas es:

```text
knowledge/
└── sources/
    └── conversations/
        └── <source-id>/
            ├── source.md
            ├── transcript.jsonl
            ├── original.<ext>       (si el proveedor permite exportarlo)
            └── attachments/          (si son necesarios para entender la sesión)
```

Una conversación puede referirse a más de un proyecto; por eso las fuentes se pueden guardar en un archivo común y enlazar desde los proyectos correspondientes. El registro de proyecto, la decisión o la afirmación debe apuntar a un turno concreto, por ejemplo `source-id#turn-0042`, además del archivo.

## Flujo de captura

1. La persona elige una conversación para evaluar o solicita directamente su conservación.
2. Si se realiza una evaluación, la persona revisa y selecciona las propuestas que desea conservar; puede saltarse la evaluación si ya sabe qué conversación quiere guardar.
3. Conserva la exportación o material original dentro del alcance aprobado, sin editarlo cuando esté disponible.
4. Crea el transcript normalizado y la ficha de fuente con metadatos de origen, integridad, cobertura y limitaciones.
5. Registra las decisiones, afirmaciones o pendientes aprobados por separado, enlazándolos a IDs de turno.
6. Versiona los archivos y revisa que los enlaces resuelvan.

No guardes credenciales ni secretos en el historial de conocimiento. Si un material sensible no debe entrar en el repositorio, exclúyelo de la captura o almacénalo en una ubicación protegida y deja constancia de esa limitación sin copiar el contenido sensible.

## Recuperar el trabajo con otro proveedor

Un proveedor nuevo debe poder leer el formato neutral, empezando por la guía de uso, el estado actual del proyecto y sus decisiones vigentes. Después se recuperan solo los turnos y fuentes pertinentes a la tarea. El archivo histórico completo queda disponible para verificación; no se carga entero en cada consulta.

Los adaptadores de cada proveedor pueden cambiar. Los IDs, roles, turnos, proyectos y referencias de Theuth deben permanecer estables al cambiar de herramienta.

## Límites de verificación

Una referencia a una conversación prueba qué se dijo, no que una afirmación factual expresada allí sea verdadera. Para esa verificación, sigue el enlace a la fuente externa original o marca la afirmación como pendiente o no verificada.

Si la conversación original no puede exportarse o ya no está disponible, conserva una ficha que describa la limitación. No presentes una paráfrasis o snapshot como si fuera el registro original.

-------------------------------------
