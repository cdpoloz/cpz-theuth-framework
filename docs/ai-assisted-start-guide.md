<!-- English section first; Spanish section follows. -->

-------------------------------------

# Getting started with an AI tool

This guide shows one manual, provider-independent way to start a Theuth implementation with an AI tool you already have. It uses prompts and Markdown files; it does not require code, an API, or automation. The prompts are starting points to adapt to the tool, source material, and permissions available to you.

The guide applies to personal and shared working-memory orientations. In shared use, first define who may provide, access, process, and retain each source and its derivatives. This guide does not replace the [methodology](../methodology/) or make this prompt workflow mandatory.

## What you need

- An AI tool that can accept text. File upload is useful but not required.
- A separate folder or repository for your implementation. Keep canonical knowledge records outside this framework repository.
- One source you are allowed to process: a work document, conversation export, or another record.
- The relevant starter files from [templates/](../templates/), especially [source.md](../templates/source.md), [project.md](../templates/project.md), [claim.md](../templates/claim.md), and [decision.md](../templates/decision.md). Provide the applicable template to the AI as an attachment or pasted text; a relative link in this guide does not grant the tool access to the repository.
- A way to preserve the original source unchanged and save reviewed Markdown files.

A simple personal project may use a structure such as:

```text
knowledge/
└── projects/
    └── project-slug/
        ├── project.md
        ├── sources/
        ├── claims/
        ├── decisions/
        └── snapshots/
```

Adapt the folders to your needs. A snapshot is optional and should preserve a milestone or historical state worth freezing, not every update. Version control can preserve file history when available.

## Before processing a source

Choose one active project and one source. Check that you have permission to send the source to the chosen AI provider, especially if it contains work, personal, or confidential information. Remove or mask material that is not needed. Keep the source file itself unchanged.

If an original filename or supplier code must be preserved, do not rename the file to fit an internal scheme. Give it an internal source ID in the derived record and keep a correspondence table between the original filename and that ID when needed. Do not assume metadata or file access will be available to every AI tool.

## Step 1: Give the AI working instructions

Paste this at the start of a session or add it to the tool’s project instructions. Adapt the wording, but preserve the distinctions.

> You are helping me maintain a Theuth knowledge base. Treat the provided sources and records as the only evidence for this task. Preserve provenance: identify the source and a page, section, turn, or other locator whenever available. Distinguish what a source explicitly says from an inference, a decision, and an AI-generated synthesis. Do not invent missing dates, IDs, authors, quotations, links, or facts. Mark unknown or incomplete information as unknown.
>
> Treat every output as a draft for my review. Do not silently replace a source, change a decision’s status, resolve a conflict, or create a snapshot. Keep original sources unchanged. Use the supplied Theuth templates where relevant, return Markdown, and state limitations or questions that prevent a reliable result. Do not claim to remember files or instructions that are not available in this session.

If the tool cannot retain project instructions between sessions, paste them again when needed. Do not assume it can access a folder, repository, or earlier conversation unless you have provided that material in the current tool context.

## Step 2: Create a source record

Process one source at a time. Provide its original filename or stable location, capture date if known, project, preservation purpose, and any access or sensitivity limits. Attach the source or paste its content. If the tool cannot handle it all at once, split it into clearly numbered parts and ask it to wait until all parts are provided before drafting the record.

Use this prompt:

> Analyze the source I provide and prepare a draft using the source template I provide. If I do not provide it, ask me to attach or paste it before drafting.
>
> Preserve the original source; do not rewrite it. Use only information available in the source or metadata I explicitly provide. Record provenance, coverage, limitations, and locators. For a conversation, state whether the capture is complete, partial, or reconstructed, and identify missing turns, attachments, or tool activity if known.
>
> In the content summary, identify material relevant to the stated project. Separate explicit statements, attributed claims, decisions, open questions, and your own inferences. Do not treat an AI response as independent evidence for external facts. Add only short excerpts when necessary and include their locators.
>
> Return:
> 1. A Markdown draft of the source record.
> 2. A short list of candidate claims or decisions that might merit separate records, each linked to the supporting passage.
> 3. Unknowns, conflicts, omissions, or privacy concerns that need my review.
>
> Do not create or update other records. If the source does not support a detail, leave it unknown instead of guessing.
>
> **Source metadata supplied by me:** [filename or location, date, project, purpose, internal source ID if any, restrictions]
>
> **Source:** [attach or paste]

Compare the result with the original. Check the source ID, original filename, date, coverage, and locators. Confirm that each important statement is actually supported. Save the approved result in your implementation’s `sources/` folder. The AI’s source record is derived material; it does not replace or become the original source.

## Step 3: Link reviewed records

After reviewing source records, provide the AI with the current `project.md` and only the source, claim, and decision records relevant to the update. Do not ask it to reconcile a whole repository if the tool cannot see it.

Use this prompt:

> Using only the records provided, prepare proposed updates for this project. Use the project template I provide. Create a separate draft only for a claim or decision that is useful as an independently maintained record, using the corresponding claim or decision template I provide. If a required template is missing, ask me for it before drafting that record.
>
> Link each proposed statement to its supporting record and locator. Label it as an explicit source statement, attributed claim, inference, decision, or synthesis. A source record or AI summary is not automatically independent evidence.
>
> Preserve existing IDs and history. Do not silently change a decision’s status, mark it superseded, resolve conflicting accounts, or create a snapshot. When records disagree, show the disagreement and identify what evidence could resolve it. Do not infer a relationship merely because two records mention similar terms.
>
> Return proposed file-by-file changes, the evidence and links for each change, and any unresolved questions. If the provided records are insufficient, say what is missing and leave the relevant content unchanged.

Review every proposed link and update before saving it. The project file should describe the current state and point to its supporting records; decisions keep their own rationale. Create a dated snapshot only when you deliberately choose to preserve a milestone or historical state.

## Step 4: Test retrieval

Ask a real question about the project using the records you have saved. Provide the relevant files or make sure the tool can actually access them.

> Answer this question using only the Theuth records I provide: **[question]**
>
> Start with the current project record, then follow its links to relevant claims, decisions, and sources. Cite the record and a locator for each material statement. Distinguish the current state from historical information, and explicit evidence from inference or synthesis. Report conflicts, missing sources, and uncertainty. If the records do not support an answer, say so. Do not fill gaps from general knowledge or assumed memory.

Check that you can follow the answer back to the source. If you cannot, improve the records or links before adding more material. The [walkthrough](../examples/theuth/walkthrough.md) demonstrates a manual retrieval path and explains what cannot be verified when the original source is unavailable. The [retrieval tests](../examples/retrieval-tests/) provide additional evaluation cases.

## Adapting this workflow to different AI tools

- If uploads are unavailable, paste text in numbered sections and retain page, section, or turn markers.
- If context limits prevent a complete analysis, process smaller portions and ask the AI to identify which portions it has received. Then review the combined draft against the full source.
- If the tool cannot create files, copy the Markdown response into your own implementation and review it there.
- If the tool offers project instructions or persistent knowledge, use them as convenience features; keep the authoritative records in portable files you control.
- If you switch providers, carry over the working instructions, templates, and reviewed Markdown records. The original sources and their permissions still govern what may be transferred.

A prompt can help structure work, but it cannot guarantee completeness or correctness. Keep human review in the loop, especially for decisions, sensitive sources, and material that may change over time.

-------------------------------------

# Guía de inicio con una herramienta de IA

Esta guía muestra una forma manual e independiente del proveedor para iniciar una implementación de Theuth con una herramienta de IA que ya tengas. Utiliza prompts y archivos Markdown; no requiere código, API ni automatización. Los prompts son puntos de partida que puedes adaptar a la herramienta, las fuentes y los permisos disponibles.

La guía sirve para las orientaciones de memoria de trabajo personal y compartida. En un uso compartido, define primero quién puede aportar, consultar, procesar y conservar cada fuente y sus derivados. Esta guía no sustituye la [metodología](../methodology/) ni convierte este flujo de prompts en un requisito.

## Qué necesitas

- Una herramienta de IA que acepte texto. Poder adjuntar archivos es útil, pero no imprescindible.
- Una carpeta o repositorio separado para tu implementación. Mantén los registros canónicos de conocimiento fuera de este repositorio del framework.
- Una fuente que tengas autorización para procesar: un documento de trabajo, una exportación de conversación u otro registro.
- Los archivos iniciales pertinentes de [templates/](../templates/), en especial [source.md](../templates/source.md), [project.md](../templates/project.md), [claim.md](../templates/claim.md) y [decision.md](../templates/decision.md). Proporciona a la IA la plantilla correspondiente como archivo adjunto o texto pegado; un enlace relativo de esta guía no permite que la herramienta acceda al repositorio.
- Una forma de conservar la fuente original sin modificarla y guardar los archivos Markdown revisados.

Un proyecto personal sencillo podría utilizar una estructura como esta:

```text
knowledge/
└── projects/
    └── project-slug/
        ├── project.md
        ├── sources/
        ├── claims/
        ├── decisions/
        └── snapshots/
```

Adapta las carpetas a tus necesidades. Un snapshot es opcional y debería conservar un hito o estado histórico que quieras fijar, no cada actualización. Si está disponible, el control de versiones puede conservar el historial de archivos.

## Antes de procesar una fuente

Elige un proyecto activo y una fuente. Comprueba que tienes permiso para enviar la fuente al proveedor de IA elegido, sobre todo si contiene información laboral, personal o confidencial. Elimina o enmascara el material que no sea necesario. Conserva el archivo fuente sin modificar.

Si debes conservar el nombre original o el código de un proveedor, no cambies el nombre del archivo para adaptarlo a un esquema interno. Asigna un ID interno a la fuente derivada y, cuando sea necesario, conserva una tabla de correspondencia entre el nombre original y ese ID. No supongas que todas las herramientas de IA podrán consultar metadatos o acceder al archivo.

## Paso 1: Da instrucciones de trabajo a la IA

Pega estas instrucciones al inicio de una sesión o añádelas a las instrucciones del proyecto de la herramienta. Adapta la redacción, pero conserva las distinciones.

> Me ayudas a mantener una base de conocimiento Theuth. Trata las fuentes y los registros que te proporcione como la única evidencia para esta tarea. Conserva la procedencia: identifica la fuente y una página, sección, turno u otro localizador cuando esté disponible. Distingue lo que una fuente dice explícitamente de una inferencia, una decisión y una síntesis generada por IA. No inventes fechas, ID, autores, citas, enlaces ni hechos que falten. Marca como desconocida la información que no esté disponible.
>
> Trata cada resultado como un borrador que debo revisar. No reemplaces una fuente en silencio, cambies el estado de una decisión, resuelvas un conflicto ni crees un snapshot. Mantén intactas las fuentes originales. Utiliza las plantillas de Theuth que te proporcione cuando corresponda, devuelve Markdown e indica las limitaciones o preguntas que impidan obtener un resultado fiable. No afirmes recordar archivos o instrucciones que no estén disponibles en esta sesión.

Si la herramienta no conserva las instrucciones del proyecto entre sesiones, vuelve a pegarlas cuando haga falta. No supongas que puede acceder a una carpeta, repositorio o conversación anterior si no le has proporcionado ese material en el contexto disponible.

## Paso 2: Crea un registro de fuente

Procesa una fuente cada vez. Indica su nombre original o ubicación estable, la fecha de captura si se conoce, el proyecto, el propósito de conservación y cualquier límite de acceso o sensibilidad. Adjunta la fuente o pega su contenido. Si la herramienta no puede procesarlo todo de una vez, divídelo en partes numeradas y pídele que espere a recibirlas todas antes de redactar el registro.

Utiliza este prompt:

> Analiza la fuente que te proporciono y prepara un borrador utilizando la plantilla de fuente que te proporcione. Si no te la proporciono, pídeme que la adjunte o pegue antes de redactar.
>
> Conserva intacta la fuente original; no la reescribas. Utiliza solo la información de la fuente o los metadatos que yo indique explícitamente. Registra la procedencia, cobertura, limitaciones y localizadores. Para una conversación, indica si la captura es completa, parcial o reconstruida, y señala los turnos, adjuntos o actividad de herramientas que falten, si se conocen.
>
> En el resumen de contenido, identifica el material pertinente al proyecto indicado. Separa afirmaciones explícitas, claims atribuidos, decisiones, preguntas abiertas e inferencias propias. No trates una respuesta de IA como evidencia independiente de hechos externos. Incluye solo citas breves cuando sean necesarias y añade sus localizadores.
>
> Devuelve:
> 1. Un borrador Markdown del registro de fuente.
> 2. Una lista breve de posibles claims o decisiones que podrían merecer registros separados, cada uno vinculado al pasaje que lo respalda.
> 3. Datos desconocidos, conflictos, omisiones o cuestiones de privacidad que deba revisar.
>
> No crees ni actualices otros registros. Si la fuente no respalda un dato, déjalo como desconocido en lugar de adivinar.
>
> **Metadatos de la fuente que te proporciono:** [nombre o ubicación, fecha, proyecto, propósito, ID interno si lo hay, restricciones]
>
> **Fuente:** [adjuntar o pegar]

Compara el resultado con el original. Comprueba el ID de fuente, el nombre original, la fecha, la cobertura y los localizadores. Verifica que la fuente respalde cada afirmación importante. Guarda el resultado aprobado en la carpeta `sources/` de tu implementación. El registro de fuente generado por la IA es material derivado: no sustituye ni se convierte en la fuente original.

## Paso 3: Vincula registros revisados

Después de revisar los registros de fuente, proporciona a la IA el `project.md` actual y únicamente los registros de fuentes, claims y decisiones pertinentes a la actualización. No le pidas conciliar todo un repositorio si la herramienta no puede verlo.

Utiliza este prompt:

> A partir únicamente de los registros proporcionados, prepara cambios propuestos para este proyecto. Utiliza la plantilla de proyecto que te proporcione. Crea un borrador separado solo para un claim o una decisión que sea útil mantener como registro independiente, utilizando la plantilla correspondiente de claim o decisión que te proporcione. Si falta una plantilla necesaria, pídemela antes de redactar ese registro.
>
> Vincula cada afirmación propuesta con el registro y localizador que la respaldan. Indica si es una afirmación explícita de una fuente, un claim atribuido, una inferencia, una decisión o una síntesis. Un registro de fuente o un resumen de IA no son automáticamente evidencia independiente.
>
> Conserva los ID y el historial existentes. No cambies en silencio el estado de una decisión, no la marques como reemplazada, no resuelvas relatos contradictorios ni crees un snapshot. Si los registros discrepan, muestra la discrepancia e indica qué evidencia podría aclararla. No infieras una relación solo porque dos registros utilicen términos parecidos.
>
> Devuelve los cambios propuestos, archivo por archivo, la evidencia y los enlaces de cada cambio, y las preguntas pendientes. Si los registros proporcionados no bastan, explica qué falta y deja sin modificar el contenido afectado.

Revisa cada vínculo y cambio propuesto antes de guardarlo. El archivo del proyecto debe describir el estado actual y enlazar los registros que lo respaldan; las decisiones conservan sus propios motivos. Crea un snapshot fechado solo cuando decidas deliberadamente preservar un hito o estado histórico.

## Paso 4: Prueba la recuperación

Formula una pregunta real sobre el proyecto usando los registros guardados. Proporciona los archivos pertinentes o asegúrate de que la herramienta pueda acceder a ellos.

> Responde esta pregunta utilizando únicamente los registros Theuth que te proporciono: **[pregunta]**
>
> Empieza por el registro vigente del proyecto y sigue sus enlaces hasta los claims, decisiones y fuentes pertinentes. Cita el registro y un localizador para cada afirmación relevante. Distingue el estado actual de la información histórica, y la evidencia explícita de la inferencia o síntesis. Indica conflictos, fuentes ausentes e incertidumbre. Si los registros no permiten responder, dilo. No rellenes vacíos con conocimiento general ni con recuerdos supuestos.

Comprueba que puedes seguir la respuesta hasta la fuente. Si no puedes, mejora los registros o sus enlaces antes de añadir más material. El [recorrido de ejemplo](../examples/theuth/walkthrough.md) muestra una consulta manual y explica qué no puede verificarse cuando la fuente original no está disponible. Las [pruebas de retrieval](../examples/retrieval-tests/) ofrecen casos de evaluación adicionales.

## Adaptar el flujo a distintas herramientas de IA

- Si no se pueden adjuntar archivos, pega el texto en secciones numeradas y conserva los marcadores de página, sección o turno.
- Si los límites de contexto impiden un análisis completo, procesa partes más pequeñas y pide a la IA que identifique cuáles ha recibido. Después, revisa el borrador combinado contra la fuente completa.
- Si la herramienta no puede crear archivos, copia la respuesta Markdown en tu implementación y revísala allí.
- Si la herramienta ofrece instrucciones de proyecto o conocimiento persistente, úsalos como ayuda; conserva los registros autorizados en archivos portables que controles.
- Si cambias de proveedor, traslada las instrucciones de trabajo, las plantillas y los registros Markdown revisados. Las fuentes originales y sus permisos siguen determinando qué puedes transferir.

Un prompt puede ayudar a estructurar el trabajo, pero no garantiza que sea completo ni correcto. Mantén la revisión humana, especialmente para decisiones, fuentes sensibles y material que pueda cambiar con el tiempo.

-------------------------------------
