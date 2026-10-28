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

## Optional shared implementation: private MTC with email sources

This example extends the manual workflow above. It separates automated source capture from reviewed knowledge publication. It is an illustrative configuration, not an installed skill or a guarantee that a particular provider supports the complete workflow. An implementation may use a skill, scripts, connectors, or an organizational automation service.

### Spaces, roles, and permissions

The team keeps its working documents in its existing shared workspace and adds a folder named **Email communications**. The MTC maintainer reads that workspace without changing its files, prepares derived records in a separate maintenance area, and publishes the reviewed MTC. Team members query the published MTC with read-only access.

| Space | Authorized writer | Maintainer access | Purpose |
| --- | --- | --- | --- |
| Shared working documents | Team under its existing rules | Read only | Original working sources. |
| `Email communications/capture-config.md` | Designated configuration owners | Read only | Versioned capture scope and processing instructions. |
| `Email communications/contributions/<contributor>/` | That contributor's capture process | Read only | New email capture batches and their attachments. |
| Maintenance area and accepted-source archive | MTC maintainer or its authorized maintenance process | Read/write | Source verification, evidence preservation, and draft records. |
| Published MTC | MTC maintainer or its authorized publishing process | Read/write | Reviewed knowledge; team access is read only. |

These are illustrative subfolders. Use consistent folder names throughout each implementation. Enforce permissions in storage and connector configuration, not only in a prompt. If the connector cannot limit writes to the contribution area, use a separate capture identity or another integration. The maintainer needs no write permission to the team's working folder.

### Initial setup by the maintainer

1. Confirm which communications may be retained, shared with the intended audience, and processed by the chosen provider. Domain matching is a relevance rule, not authorization to disclose.
2. Configure and test the consultation environment for each team member: published MTC and authorized original sources are read only.
3. Configure the capture environment for each contributing member: mailbox read access, configuration read access, and write access limited to that member's contribution area. Account owners complete their own authentication and consent; do not exchange passwords.
4. Agree on the configuration file, its editors, the first historical capture date, schedule, time zone, and retention review conditions.
5. Run one capture manually and verify the saved bytes and links before enabling recurrence. Confirm that the scheduled environment can use all required tools without an interactive step on every run. A connector that can search mail may not export complete messages or write files.

An AI chat in the cloud cannot be assumed to reach a local network share. The implementation must supply an accessible storage integration or an authorized local process. Record the actual tested capabilities instead of assuming equivalence between Google, Microsoft, or different AI providers.

### Capture configuration file

Use the following as a starting template for `capture-config.md`; replace all illustrative values before enabling it. The file contains approved configuration, never credentials. Store run state separately so that the capture process does not need permission to edit these rules.

```yaml
# Illustrative contract; no parser or executable skill is supplied here.
config_version: "1"
project_id: "project-orion"
owner_role: "project-coordinator"
timezone: "Europe/Madrid"
initial_capture_from: "2026-10-01T00:00:00+02:00"
selection:
  mailbox_scope: ["received", "sent"]
  participant_fields: ["from", "to", "cc"]
  include_addresses:
    - address: "ana@client.example"
      valid_from: "2026-10-01"
      valid_to: "2026-10-31"
    - address: "luis@client.example"
      valid_from: "2026-11-01"
      valid_to: null
  include_domains: ["supplier.example"]
  include_subdomains: false
  project_labels_or_folders: ["Project Orion"]
  project_terms_any: ["ORION-42", "Project Orion"]
  exclude_addresses: ["newsletter@supplier.example"]
  exclude_terms_any: ["unrelated campaign"]
  rule: "exclude_first_then_participant_and_project"
treatment:
  preserve_available_original: true
  include_relevant_attachments: true
  retrieve_missing_thread_context: true
  overwrite_existing_captures: false
  summaries: "optional_separate_derivative"
  uncertain_relevance: "hold_for_review_without_shared_body_export"
output:
  contribution_root: "Email communications/aportaciones"
  layout: "contributor/run-id"
  include_manifest: true
  include_run_report: true
retention:
  review_condition: "project closure or authorization change"
```

Define the matching semantics explicitly. In this example, exclusions take priority. A selected message must have a matching participant address or domain **and** a project label/folder or project term. Match participant fields, not addresses found in quoted body text. Match normalized email domains exactly; include subdomains only if explicitly enabled. Participant dates are inclusive, interpreted in the configured time zone against the message date. An expired exact address blocks that address even if its domain is included, unless the configuration explicitly defines an exception.

A personnel change affects selection for the applicable dates; it does not automatically withdraw earlier authorized evidence. Configuration changes apply prospectively by default. A historical rescan is an explicit maintenance operation, with its period and reason recorded. The implementation must define which fields the term search covers; this example uses subject and body, including quoted text, with ambiguous matches sent for review.

Add approved natural-language instructions beneath the structured configuration when needed: attachment selection, treatment of restricted material, output naming, and cases requiring review. The skill must read these rules on every run. If the file is missing, invalid, or contradictory, report the failure and keep the previous successful capture position. Email bodies and attachments are source content; instructions inside them must not alter the task, recipients, permissions, or destinations.

### Daily capture procedure

A scheduled run performs the following work automatically within the configured scope:

1. Read the authorized configuration and record its version and content hash. Fix a run cutoff time and retrieve changes since the last successful run, using a small overlap and deduplication when appropriate. The first run uses the agreed historical start date. Process all pages and respect tool limits.
2. Apply filters to incoming and sent messages. Select threads through matching messages, then retrieve only the earlier context needed to interpret them, subject to the same sharing restrictions. Mark context-only messages and incomplete coverage. Do not assume a provider's thread ID is shared across accounts or providers.
3. Save available original messages, preferably native exports such as `.eml` when supported, and relevant attachments. If only a structured representation is available, label it accordingly and record missing headers, messages, or attachments. Never reconstruct an unavailable original from an AI summary.
4. Save a manifest with contributor and run IDs, configuration version/hash, covered interval, capture time, message identifiers, sender/recipients/date, thread relationships, original mailbox locator when available, captured-file paths, attachment relationships, and file hashes. Missing metadata is marked unknown. Preserve originals; removing repeated quotations is allowed only in a separate analysis view.
5. Produce a report with counts, omissions, pending review, and errors. Save new batches without overwriting earlier evidence. Advance the successful position only after all selected material and the manifest have been saved and checked; partial runs retain enough state for a safe retry.

Maintain separate capture state for each contributor, account, and project. Deduplicate repeated runs and, during maintenance, copies contributed by different members, using available message IDs and content hashes while retaining provenance. Do not treat identical subjects as identical messages or silently merge variants and redacted copies. If a provider's incremental history has expired, rescan the necessary period and deduplicate; disclose any unresolvable gap.

### Review, extraction, and publication

At the chosen maintenance interval, the maintainer reads completed batches, verifies their coverage and authorization, and preserves the accepted evidence in an archive controlled by the maintenance process. This archive remains subject to the agreed access, retention, and removal rules. Record the team's original capture URL as well as the archived location and hash: the MTC should not depend on an editable contribution remaining unchanged.

Create source records using the existing [source template](../templates/source.md), adapting conversation metadata to email: message ID, participants, dates, thread relationships, export format, coverage, and missing attachments. Fields specific to an AI conversation, such as model, are not applicable to human email. Use the [decision template](../templates/decision.md) when a separate decision record is useful.

A proposal, acknowledgment, conditional acceptance, and confirmed agreement have different meanings. Preserve the accepting person's role, conditions, dates, and evidence; silence is not confirmation. A later message does not automatically supersede a document or decision. Show contradictions and submit proposed changes for review before publishing. Captured email is source evidence, not automatically accepted knowledge.

### Instructions for team consultation

Use project instructions such as:

> For questions about this project, consult the published MTC first and follow its links to the relevant records and authorized original sources. Support material project statements with the MTC record, a specific locator, and the corporate URL of the original file in the shared working folder. For captured email, identify the sender, message date, and message ID when available, and link to the saved capture accessible to the audience. A personal mailbox link alone is insufficient.
>
> Distinguish confirmed decisions, proposals, history, and inference. State the MTC's last completed update and any relevant coverage gap. If the MTC is unavailable or lacks evidence, say so; consult authorized originals when possible and identify that additional consultation. Never invent links or imply verification of a file you could not access. Do not modify the MTC or its sources through the consultation workflow.

### Fictional end-to-end example and pilot checks

A captured thread contains a proposal on October 27 to deliver on November 15, a question about test completion, and an authorized coordinator's reply on October 28: delivery on November 15 is confirmed **provided acceptance tests pass**. Capture preserves the three messages and their dates. The reviewed source record points to them; the decision record preserves the condition. A project answer reports the conditional date and cites the shared capture URL plus the coordinator's message locator. No actual URL is invented in this example.

Before expanding the pilot, verify:

- A thread with more than 100 messages is paginated fully, or its missing coverage is reported.
- A failed daily run is recovered without omissions or duplicate evidence.
- A participant replacement preserves historical selection and applies new dates correctly.
- Two contributors' copies remain traceable and do not create duplicate decisions.
- Consultation cannot write to the MTC; capture cannot write outside its contribution area.
- Saved originals, attachments, hashes, and corporate links can be inspected independently of the AI summary.
- Conflicting decisions, instructions embedded in emails, unrelated domain matches, and missing configuration are handled as specified.

The example is ready for deployment only after these capabilities are tested in the chosen environment. Scheduling, executable skill packaging, provider setup, and connector-specific code belong to the implementation.

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

## Implementación compartida opcional: MTC privada con fuentes de correo

Este ejemplo amplía el flujo manual anterior. Separa la captura automática de fuentes de la publicación de conocimiento revisado. Es una configuración ilustrativa, no una skill instalada ni una garantía de que un proveedor soporte el recorrido completo. La implementación puede utilizar una skill, scripts, conectores o un servicio de automatización de la organización.

### Espacios, responsabilidades y permisos

El equipo conserva sus documentos de trabajo en su espacio compartido habitual y añade una carpeta llamada **Comunicaciones por correo**. El responsable de la MTC lee ese espacio sin modificar sus archivos, prepara los registros derivados en un área de mantenimiento separada y publica la MTC revisada. Los miembros del equipo consultan la MTC publicada con acceso de solo lectura.

| Espacio | Quién puede escribir | Acceso del responsable MTC | Propósito |
| --- | --- | --- | --- |
| Documentos de trabajo compartidos | El equipo según sus reglas actuales | Solo lectura | Fuentes originales de trabajo. |
| `Comunicaciones por correo/capture-config.md` | Responsables designados de la configuración | Solo lectura | Alcance de captura e instrucciones de tratamiento con versiones. |
| `Comunicaciones por correo/aportaciones/<aportante>/` | El proceso de captura de ese aportante | Solo lectura | Nuevos lotes de correos y sus adjuntos. |
| Área de mantenimiento y archivo de fuentes aceptadas | Responsable MTC o su proceso autorizado | Lectura/escritura | Verificación, preservación de evidencia y borradores. |
| MTC publicada | Responsable MTC o su proceso autorizado de publicación | Lectura/escritura | Conocimiento revisado; el equipo tiene solo lectura. |

Las subcarpetas son ilustrativas. Los permisos se aplican en el almacenamiento y en la configuración del conector, además de indicarse en el prompt. Si el conector no permite limitar la escritura al área de aportaciones, utiliza una identidad de captura separada u otra integración. El responsable MTC no necesita escritura sobre la carpeta de trabajo del equipo.

### Configuración inicial a cargo del responsable

1. Confirmar qué comunicaciones se pueden conservar, compartir con la audiencia prevista y procesar con el proveedor elegido. La coincidencia de dominio indica relevancia, no autoriza la divulgación.
2. Configurar y probar el entorno de consulta de cada miembro: MTC publicada y fuentes originales autorizadas con acceso de solo lectura.
3. Configurar el entorno de captura de cada aportante: lectura del correo, lectura de la configuración y escritura limitada a su área de aportaciones. Cada titular completa su autenticación y consentimiento; no se intercambian contraseñas.
4. Acordar el archivo de configuración, sus editores, la fecha inicial del histórico, el horario, la zona horaria y las condiciones de revisión de retención.
5. Ejecutar una captura manual y comprobar los archivos guardados y sus enlaces antes de programarla. Verificar que el entorno programado pueda utilizar todas las herramientas necesarias sin una intervención en cada ejecución. Buscar correo mediante un conector no implica poder exportar mensajes completos o escribir archivos.

No se presupone que un chat de IA en la nube pueda acceder a una carpeta de red local. La implementación debe proporcionar una integración de almacenamiento accesible o un proceso local autorizado. Documenta las capacidades realmente probadas, sin asumir equivalencia entre Google, Microsoft o distintos proveedores de IA.

### Archivo de configuración de captura

Utiliza esta plantilla inicial para `capture-config.md`; sustituye los valores ilustrativos antes de activarla. El archivo contiene configuración autorizada, nunca credenciales. El estado de ejecución se guarda aparte para que el proceso de captura no necesite editar estas reglas.

```yaml
# Contrato ilustrativo; no incluye parser ni skill ejecutable.
config_version: "1"
project_id: "project-orion"
owner_role: "project-coordinator"
timezone: "Europe/Madrid"
initial_capture_from: "2026-10-01T00:00:00+02:00"
selection:
  mailbox_scope: ["received", "sent"]
  participant_fields: ["from", "to", "cc"]
  include_addresses:
    - address: "ana@client.example"
      valid_from: "2026-10-01"
      valid_to: "2026-10-31"
    - address: "luis@client.example"
      valid_from: "2026-11-01"
      valid_to: null
  include_domains: ["supplier.example"]
  include_subdomains: false
  project_labels_or_folders: ["Project Orion"]
  project_terms_any: ["ORION-42", "Project Orion"]
  exclude_addresses: ["newsletter@supplier.example"]
  exclude_terms_any: ["unrelated campaign"]
  rule: "exclude_first_then_participant_and_project"
treatment:
  preserve_available_original: true
  include_relevant_attachments: true
  retrieve_missing_thread_context: true
  overwrite_existing_captures: false
  summaries: "optional_separate_derivative"
  uncertain_relevance: "hold_for_review_without_shared_body_export"
output:
  contribution_root: "Comunicaciones por correo/aportaciones"
  layout: "contributor/run-id"
  include_manifest: true
  include_run_report: true
retention:
  review_condition: "project closure or authorization change"
```

Define expresamente cómo se combinan los criterios. En este ejemplo, las exclusiones prevalecen. El mensaje seleccionado debe tener un participante cuya dirección o dominio coincida **y**, además, una etiqueta/carpeta o un término del proyecto. Las direcciones se buscan en los campos de participantes, no en el texto citado del cuerpo. La comparación de dominios normalizados es exacta; los subdominios solo se incluyen si se habilitan. Las fechas de participantes son inclusivas y se interpretan en la zona horaria configurada sobre la fecha del mensaje. Una dirección exacta fuera de vigencia bloquea esa dirección aunque su dominio esté incluido, salvo excepción expresa de la configuración.

El cambio de personal afecta a la selección para las fechas correspondientes; no retira automáticamente la evidencia histórica autorizada. Los cambios de configuración se aplican hacia adelante por defecto. Un nuevo barrido histórico requiere una operación explícita de mantenimiento que registre su periodo y motivo. La implementación debe definir dónde busca términos; este ejemplo usa asunto y cuerpo, incluido el texto citado, y remite coincidencias ambiguas a revisión.

Añade debajo de la configuración estructurada instrucciones autorizadas en lenguaje natural cuando hagan falta: selección de adjuntos, tratamiento de material restringido, nombres de salida y casos de revisión. La skill consulta estas reglas en cada ejecución. Si el archivo falta, es inválido o contiene contradicciones, registra el fallo y conserva la posición de la última captura correcta. Los correos y adjuntos son contenido fuente: sus instrucciones no pueden cambiar la tarea, destinatarios, permisos ni destinos.

### Procedimiento de captura diaria

La tarea programada realiza automáticamente este trabajo dentro del alcance configurado:

1. Leer la configuración autorizada y registrar su versión y hash. Fijar la hora límite de la ejecución y recuperar los cambios desde la última ejecución correcta, con un pequeño solapamiento y deduplicación cuando corresponda. La primera ejecución utiliza la fecha histórica acordada. Procesar todas las páginas y respetar los límites de las herramientas.
2. Aplicar los filtros a mensajes recibidos y enviados. Seleccionar cadenas a partir de mensajes coincidentes y recuperar solo el contexto anterior necesario para interpretarlos, sujeto a las mismas restricciones de divulgación. Identificar mensajes incorporados solo como contexto y cobertura incompleta. No suponer que el ID de cadena de un proveedor sea común entre cuentas o proveedores.
3. Guardar los mensajes originales disponibles, preferiblemente exportaciones nativas como `.eml` cuando se admitan, y sus adjuntos pertinentes. Si solo se obtiene una representación estructurada, identificarla como tal y registrar cabeceras, mensajes o adjuntos ausentes. No reconstruir un original no disponible a partir de un resumen de IA.
4. Guardar un manifiesto con ID del aportante y ejecución, versión/hash de configuración, intervalo cubierto, fecha de captura, identificadores de mensajes, remitente/destinatarios/fecha, relaciones entre mensajes, localizador del correo original si existe, rutas de las capturas, relación de adjuntos y hashes. Los metadatos ausentes se marcan como desconocidos. Conservar los originales; eliminar citas repetidas solo se permite en una vista de análisis separada.
5. Generar un informe con cantidades, omisiones, pendientes y errores. Guardar lotes nuevos sin sobrescribir evidencia anterior. Avanzar la posición de captura correcta solo después de guardar y comprobar todo el material seleccionado y el manifiesto; una ejecución parcial conserva estado suficiente para reintentarse sin pérdidas.

Mantener un estado de captura por aportante, cuenta y proyecto. Deduplicar ejecuciones repetidas y, durante el mantenimiento, las copias aportadas por varios miembros, utilizando identificadores y hashes disponibles sin perder su procedencia. Un asunto idéntico no identifica un mensaje; las variantes y copias depuradas no se fusionan silenciosamente. Si caduca el historial incremental del proveedor, volver a recorrer el periodo necesario y deduplicar; declarar cualquier vacío que no pueda resolverse.

### Revisión, extracción y publicación

Con la frecuencia elegida, el responsable lee lotes terminados, comprueba cobertura y autorización, y preserva la evidencia aceptada en un archivo bajo control del proceso de mantenimiento. Ese archivo sigue sujeto a las reglas de acceso, retención y retirada acordadas. Registrar la URL de la captura original del equipo, la ubicación preservada y su hash: la MTC no debe depender de que una aportación editable permanezca intacta.

Crear fichas con la [plantilla de fuente](../templates/source.md), adaptando los metadatos de conversación al correo: ID de mensaje, participantes, fechas, relaciones entre mensajes, formato, cobertura y adjuntos ausentes. Los campos exclusivos de conversaciones con IA, como modelo, no aplican al correo entre personas. Utilizar la [plantilla de decisión](../templates/decision.md) cuando resulte útil un registro independiente.

Una propuesta, un acuse de recibo, una aceptación condicionada y un acuerdo confirmado tienen significados distintos. Conservar el rol de quien acepta, condiciones, fechas y evidencia; el silencio no es confirmación. Un mensaje posterior no sustituye automáticamente un documento o decisión. Mostrar las contradicciones y revisar los cambios propuestos antes de publicar. El correo capturado es evidencia fuente, no conocimiento aceptado automáticamente.

### Instrucciones para la consulta del equipo

Utilizar instrucciones de proyecto como estas:

> Para preguntas sobre este proyecto, consulta primero la MTC publicada y sigue sus enlaces a registros pertinentes y fuentes originales autorizadas. Respalda las afirmaciones relevantes del proyecto con el registro MTC, un localizador concreto y la URL corporativa del archivo original en la carpeta compartida de trabajo. Para correo capturado, identifica remitente, fecha del mensaje e ID si está disponible, y enlaza la captura guardada accesible a la audiencia. Un enlace al buzón personal no basta.
>
> Distingue decisiones confirmadas, propuestas, historia e inferencias. Indica la última actualización completada de la MTC y cualquier vacío de cobertura pertinente. Si la MTC no está disponible o carece de evidencia, dilo; consulta originales autorizados cuando sea posible e identifica esa consulta adicional. No inventes enlaces ni afirmes verificar archivos inaccesibles. No modifiques la MTC ni sus fuentes desde el flujo de consulta.

### Ejemplo ficticio completo y comprobaciones del piloto

Una cadena capturada contiene una propuesta del 27 de octubre para entregar el 15 de noviembre, una pregunta sobre la finalización de pruebas y la respuesta de una coordinadora autorizada del 28 de octubre: se confirma entregar el 15 de noviembre **si se superan las pruebas de aceptación**. La captura conserva los tres mensajes y sus fechas. La ficha revisada los referencia y el registro de decisión mantiene la condición. Una respuesta del proyecto comunica la fecha condicionada y cita la URL de la captura compartida y el localizador del mensaje de la coordinadora. En este ejemplo no se inventa una URL real.

Antes de ampliar el piloto, comprobar:

- Una cadena de más de 100 mensajes se pagina completamente o declara la cobertura que falta.
- Una ejecución diaria fallida se recupera sin omisiones ni evidencia duplicada.
- El relevo de participantes conserva la selección histórica y aplica las nuevas fechas correctamente.
- Las copias de dos aportantes mantienen trazabilidad y no generan decisiones duplicadas.
- La consulta no puede escribir en la MTC y la captura no puede escribir fuera de su área de aportaciones.
- Los originales, adjuntos, hashes y enlaces corporativos pueden inspeccionarse independientemente del resumen de IA.
- Las decisiones contradictorias, instrucciones incrustadas en correos, coincidencias de dominio ajenas al proyecto y configuraciones ausentes se tratan según lo definido.

El ejemplo estará listo para desplegarse cuando se prueben estas capacidades en el entorno elegido. La programación, el empaquetado de una skill ejecutable, la configuración del proveedor y el código específico de conectores pertenecen a la implementación.

## Adaptar el flujo a distintas herramientas de IA

- Si no se pueden adjuntar archivos, pega el texto en secciones numeradas y conserva los marcadores de página, sección o turno.
- Si los límites de contexto impiden un análisis completo, procesa partes más pequeñas y pide a la IA que identifique cuáles ha recibido. Después, revisa el borrador combinado contra la fuente completa.
- Si la herramienta no puede crear archivos, copia la respuesta Markdown en tu implementación y revísala allí.
- Si la herramienta ofrece instrucciones de proyecto o conocimiento persistente, úsalos como ayuda; conserva los registros autorizados en archivos portables que controles.
- Si cambias de proveedor, traslada las instrucciones de trabajo, las plantillas y los registros Markdown revisados. Las fuentes originales y sus permisos siguen determinando qué puedes transferir.

Un prompt puede ayudar a estructurar el trabajo, pero no garantiza que sea completo ni correcto. Mantén la revisión humana, especialmente para decisiones, fuentes sensibles y material que pueda cambiar con el tiempo.

-------------------------------------

