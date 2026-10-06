<!-- English section first; Spanish section follows. -->

-------------------------------------

# Knowledge model

Theuth proposes linkable records without requiring a universal database or taxonomy. The model should serve individuals and teams; capture, access, and governance rules depend on the context of use.

## Conceptual types

| Type | Function |
|---|---|
| Profile | Relatively stable personal preferences and context |
| Project | Goal, status, decisions, and references for a body of work |
| Source | Original material, including conversations and working documents, that provides evidence about its contents |
| Claim | Verifiable or attributed unit with provenance |
| Decision | Choice, reasons, conditions, and consequences |
| Snapshot | Compact representation of current status or a dated checkpoint for a topic |

These are roles, not necessarily separate files. Combine them if their differences remain clear.

## Recommended fields

Adapt the level of detail to each record’s risk and purpose:

- Stable ID or path, title, and content.
- Type and status (for example, active, superseded, archived, or pending review).
- Creation, source, validity, and review dates when applicable.
- Provenance with a reference and specific location within the source.
- Epistemic class: observation, source, inference, or decision.
- Relationships to projects, topics, claims, and prior decisions.
- Uncertainty or limitations affecting interpretation.
- Classification and access restrictions when required by the source or implementation.
- Purpose, review condition, or retention when relevant.

## Sources and derived material

An original conversation or document is a **source**. A note, summary, answer, or synthesis created from that material is **derived** and should retain a link to the source and, when possible, its specific passage or turn. The derivative may aid retrieval and guide work, but does not replace the source or constitute independent evidence of its contents.

Do not automatically add LLM responses to the source collection or evidence index. If a response is preserved because it records a recommendation, decision, or hypothesis, identify it as derived content and record its provenance. Factual claims should point to supporting evidence; a citation or filename alone does not establish support. If sufficient evidence cannot be located, state the limitation and leave the claim unverified rather than presenting a plausible answer as confirmed.

## Usage orientations

Theuth is the shared framework. **TheuthMT** recommends prioritizing continuity in one person’s work; **TheuthMTC** recommends prioritizing knowledge contributed to or accessed by several people. These are advisory and combinable profiles. They do not define exclusive source types: both may use conversations, working documents, and other records according to the goal and applicable authorizations. See [Scope and usage profiles](scope-and-modes.md).

The first planned implementation is personal and has a [setup guide](personal-instance-setup.md). Detailed controls for a shared environment remain to be defined according to its context.

## Framework and implementations

The **cpz-theuth-framework** repository contains reusable methodology, templates, and examples. It is not the canonical home for records in a personal or team implementation.

In a personal implementation, sources are preserved in a common library and linked from one or more projects. One possible starting structure is:

```text
knowledge/
├── sources/
│   └── conversations/
│       └── <source-id>/
│           ├── source.md
│           ├── transcript.jsonl
│           ├── original.<ext>  (if the provider allows an export)
│           └── attachments/    (if needed)
└── projects/
    └── theuth/
        ├── project.md
        ├── decisions/
        │   ├── YYYY-MM-DD-decision-slug.md
        │   └── ...
        └── snapshots/  (optional; only checkpoints worth preserving)
            └── YYYY-MM-DD-topic.md
```

The \`project.md\` file is the compact, current project summary. Update it when its status changes; Git preserves earlier versions. Important decisions have their own files when their rationale, validity, or review cycle may change independently.

## Current status, history, and snapshots

The knowledge base distinguishes three related but different queries:

- **What is considered current now:** consult the current project summary and linked active records.
- **What changed and why:** reconstruct it from Git history and, when a record’s meaning or validity changes, from an explicit note or relationship explaining the change and pointing to evidence.
- **Which state should be preserved as a checkpoint:** consult a dated snapshot created for a milestone or version worth recovering.

A snapshot is not a chronological record of every edit or a substitute for Git, decisions, or sources. Snapshots need not be created every session. Update the current summary incrementally and leave a semantic explanation when something relevant changes; use snapshots only to freeze useful historical states. Git history alone may show which lines changed without showing why.

In a personal profile, work conversations may be valuable sources for reconstructing what the person requested, decided, or corrected and what response they received. Preserve the original export without editing it when available, along with a portable representation for use with other providers. Decisions and claims should link to the conversation ID and specific turns. The [capture methodology](conversation-sources.md) defines the workflow and its limits.

In a shared profile, documents, conversations, and their derivatives must respect applicable access restrictions. Before processing a source with an AI provider, confirm authorization for its handling and processing. The specific controls depend on the implementation.

A conversation records what was said; it does not by itself validate an LLM’s factual claim. Preserve the original external source if that claim is reused or could affect a decision.

Records under \`examples/theuth/\` demonstrate how to apply the format. Although they are based on the author’s real project and were included with authorization, they are not the canonical source for the personal knowledge base. When the implementation exists, canonical records will live there; the example can be kept in summarized form, anonymized, or removed.

## Separate a source from a claim

A **source** identifies the material consulted; a **claim** expresses a specific idea and retains its link to supporting evidence. One source may support several claims, and a claim may be checked against different sources. This separation makes it possible to review a conclusion without duplicating the original material’s record.

Both records are not always necessary. For a brief or one-time note, a reference next to the claim may be sufficient. Use separate files when a source or claim will be reused, has its own limitations, may change status, or needs independent review. The initial templates are [source](../templates/source.md) and [claim](../templates/claim.md).

## Correction and evolution

When a source or interpretation changes, preserve the original source, create or update the derived record, and link the previous one to the new one with a relationship such as \`reviews\`, \`corrects\`, or \`supersedes\`. State what changed, why, when, and on what evidence when meaning, status, or currency changes. Identify records and decisions that depended on the affected content and mark them for review; do not invalidate or update them automatically. The [correction and revision workflow](correction-and-revision.md) distinguishes errors from legitimate changes in currency and explains how to trace dependencies.

To review access, retention, or removal of a source, consult the [privacy, retention, and removal workflow](privacy-retention-and-removal.md). Deleting a visible file does not guarantee that its history, synchronized copies, or backups will disappear.

During the initial phase, paths may serve as identifiers. If moving files breaks too many links, consider immutable IDs.

-------------------------------------

# Modelo de conocimiento

Theuth propone registros enlazables sin imponer una base de datos o taxonomía universal. El modelo debe servir tanto a una persona como a un equipo; las reglas de captura, acceso y gobernanza dependen del contexto de uso.

## Tipos conceptuales

| Tipo | Función |
|---|---|
| Perfil | Preferencias y contexto personal relativamente estable |
| Proyecto | Objetivo, estado, decisiones y referencias de un trabajo |
| Fuente | Material original, incluidas conversaciones y documentos de trabajo, que aporta evidencia sobre su contenido |
| Afirmación | Unidad verificable o atribuida, con procedencia |
| Decisión | Elección, razones, condiciones y consecuencias |
| Snapshot | Representación compacta del estado actual o checkpoint fechado de un tema |

Son roles, no necesariamente archivos separados. Combínalos si sus diferencias siguen claras.

## Campos recomendados

Adapta el detalle al riesgo y al propósito de cada registro:

- ID o ruta estable, título y contenido.
- Tipo y estado (por ejemplo, activo, reemplazado, archivado o pendiente de revisión).
- Fechas de creación, fuente, vigencia y revisión cuando apliquen.
- Procedencia con referencia y ubicación concreta dentro de la fuente.
- Clase epistémica: observación, fuente, inferencia o decisión.
- Relaciones con proyectos, temas, afirmaciones y decisiones previas.
- Incertidumbres o limitaciones que afecten su interpretación.
- Clasificación y restricciones de acceso cuando la fuente o la implementación las requieran.
- Propósito, condición de revisión o retención cuando sea pertinente.

## Fuentes y material derivado

Una conversación o documento original es una **fuente**. Una nota, resumen, respuesta o síntesis generada a partir de ese material es **derivado** y debe mantener el enlace a la fuente y, cuando sea posible, a su pasaje o turno concreto. El derivado puede facilitar la recuperación y orientar el trabajo, pero no sustituye la fuente ni constituye evidencia independiente de lo que esta contiene.

No incorpores automáticamente respuestas del LLM al conjunto de fuentes o al índice de evidencia. Si una respuesta se conserva porque registra una recomendación, decisión o hipótesis, identifícala como contenido derivado y registra su procedencia. Las afirmaciones factuales deben apuntar a evidencia que las respalde; una cita o un nombre de archivo por sí solos no demuestran el respaldo. Si no se localiza evidencia suficiente, declara la limitación y deja la afirmación sin verificar en vez de presentar una respuesta plausible como confirmada.

## Orientaciones de uso

Theuth es el framework común. **TheuthMT** recomienda priorizar la continuidad del trabajo de una persona; **TheuthMTC** recomienda priorizar una memoria a la que contribuyen o acceden varias personas. Son perfiles orientativos y combinables. No determinan un tipo exclusivo de fuente: ambos pueden utilizar conversaciones, documentos de trabajo y otros registros, según el objetivo y las autorizaciones aplicables. Consulta [Alcance y perfiles de uso](scope-and-modes.md).

La primera implementación prevista es personal y cuenta con una [guía de inicio](personal-instance-setup.md). Los controles detallados para un entorno compartido quedan pendientes de definición según su contexto.

## Framework e implementaciones

El repositorio **cpz-theuth-framework** contiene metodología, plantillas y ejemplos reutilizables. No es la ubicación canónica de los registros de una implementación personal o de equipo.

En una implementación personal, las fuentes se conservan en una biblioteca común y se enlazan desde uno o más proyectos. Una estructura inicial posible es:

```text
knowledge/
├── sources/
│   └── conversations/
│       └── <source-id>/
│           ├── source.md
│           ├── transcript.jsonl
│           ├── original.<ext>  (si el proveedor permite exportarlo)
│           └── attachments/    (si son necesarios)
└── projects/
    └── theuth/
        ├── project.md
        ├── decisions/
        │   ├── YYYY-MM-DD-decision-slug.md
        │   └── ...
        └── snapshots/  (opcional; solo checkpoints que valga la pena conservar)
            └── YYYY-MM-DD-topic.md
```

El archivo `project.md` es el resumen compacto y vigente del proyecto. Se actualiza cuando cambia su estado; Git conserva sus versiones anteriores. Las decisiones importantes tienen sus propios archivos cuando su razonamiento, vigencia o ciclo de revisión puede cambiar independientemente.

## Estado vigente, historial y snapshots

La base distingue tres consultas relacionadas, pero distintas:

- **Qué se considera vigente ahora:** se consulta en el resumen actual del proyecto y en los registros activos enlazados.
- **Qué cambió y por qué:** se reconstruye con el historial de Git y, cuando el significado o la vigencia de un registro cambia, con una nota o relación explícita que explique el cambio y apunte a su evidencia.
- **Qué estado se quiere conservar como checkpoint:** se consulta en un snapshot fechado creado para un hito o una versión que valga la pena recuperar.

Un snapshot no es el registro cronológico de cada edición ni un sustituto de Git, de las decisiones o de las fuentes. No es necesario crear snapshots en cada sesión. Actualiza el resumen vigente de forma incremental y deja una explicación semántica cuando cambie algo relevante; usa snapshots solo para congelar estados históricos útiles. El historial técnico de Git, por sí solo, puede mostrar qué líneas cambiaron, pero no necesariamente por qué.

En un perfil personal, las conversaciones de trabajo pueden ser fuentes valiosas para reconstruir qué pidió, decidió o corrigió la persona y qué respuesta recibió. Conserva la exportación original sin editarla cuando esté disponible y una representación portable para consultar desde otros proveedores. Las decisiones y afirmaciones deben enlazar al ID de la conversación y a turnos concretos. La [metodología de captura](conversation-sources.md) define el flujo y sus límites.

En un perfil compartido, documentos, conversaciones y sus derivados deben respetar las restricciones de acceso aplicables. Antes de procesar una fuente con un proveedor de IA, confirma la autorización para su manejo y para ese procesamiento. El diseño concreto de los controles depende de la implementación.

Una conversación registra lo que se dijo; no valida por sí sola una afirmación factual del LLM. Conserva la fuente externa original si esa afirmación se reutiliza o puede afectar una decisión.

Los registros en `examples/theuth/` son una demostración de cómo aplicar el formato. Aunque estén basados en el proyecto real del autor y se hayan incluido con su autorización, no son la fuente canónica de la base personal. Cuando exista la implementación, los registros canónicos vivirán allí; el ejemplo se podrá mantener de forma resumida, anonimizar o retirar.

## Separar una fuente de una afirmación

Una **fuente** identifica el material consultado; una **afirmación** expresa una idea concreta y conserva el vínculo con la evidencia que la respalda. Una fuente puede sustentar varias afirmaciones, y una afirmación puede contrastarse con fuentes distintas. Esta separación facilita revisar una conclusión sin duplicar la ficha del material original.

No siempre hace falta crear ambos registros. Para una nota breve o de uso único, basta con indicar la referencia junto a la afirmación. Usa archivos separados cuando la fuente o la afirmación se vaya a reutilizar, tenga límites propios, pueda cambiar de estado o necesite revisión independiente. Las plantillas iniciales son [fuente](../templates/source.md) y [afirmación](../templates/claim.md).

## Corrección y evolución

Cuando una fuente o interpretación cambia, conserva la fuente original, crea o actualiza el registro derivado y enlaza el anterior con el nuevo mediante una relación como `reviews`, `corrects` o `supersedes`. Indica qué cambió, por qué, cuándo y con qué evidencia cuando el cambio afecte el significado, el estado o la vigencia. Identifica los registros y decisiones que dependían del contenido afectado y márcalos para revisión; no los invalides ni actualices automáticamente. El [flujo de corrección y revisión](correction-and-revision.md) distingue errores de cambios legítimos de vigencia y explica cómo rastrear dependencias.

Para revisar acceso, retención o retirada de una fuente, consulta el [flujo de privacidad, retención y retirada](privacy-retention-and-removal.md). El borrado de un archivo visible no garantiza que desaparezcan su historial, copias sincronizadas o respaldos.

En la fase inicial las rutas pueden funcionar como identificadores. Si mover archivos rompe demasiados enlaces, considera IDs inmutables.

-------------------------------------
