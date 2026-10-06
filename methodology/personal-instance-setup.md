<!-- English section first; Spanish section follows. -->

-------------------------------------

# Create a personal implementation

This guide turns Theuth methodology into a knowledge base that one person can maintain. The framework repository serves as a reference and source of templates; the personal implementation preserves its owner’s canonical records.

## 1. Choose where the knowledge base will live

Create a workspace separate from the \`cpz-theuth-framework\` repository. It may be a local folder or its own Git repository. If it will sync to a remote service, decide who can access it before adding personal information.

Use a private repository when the content is not public. Do not store passwords, API keys, or credentials in records. Add temporary files, exports, or data you do not want versioned to \`.gitignore\`.

## 2. Start with a minimal structure

Create only the folders you will use. An initial knowledge base may look like this:

```text
personal-knowledge/
└── knowledge/
    ├── profile.md
    ├── sources/
    │   └── conversations/
    │       └── <source-id>/
    │           ├── source.md
    │           ├── transcript.jsonl
    │           └── original.<ext>  (if available)
    └── projects/
        └── project-slug/
            ├── project.md
            └── decisions/
```

For Theuth, the planned project record is \`knowledge/projects/theuth/project.md\`, and its canonical decisions go in \`knowledge/projects/theuth/decisions/\`. The \`project.md\` file maintains a compact summary of current status.

Store work conversations under \`knowledge/sources/conversations/\`: one session may cover several projects, so a single original source can be preserved and linked from all of them. At the end of a session with reusable content, save the export without editing it when available and generate the portable transcript; the [capture methodology](conversation-sources.md) defines the format and its limits. Casual conversations without work material do not need to be archived. Add \`snapshots/\` only when you want to preserve dated milestone checkpoints; Git already keeps prior versions of \`project.md\`.

## 3. Copy and adapt the templates

Take the templates you need from the framework repository:

- \`profile.md\` for relevant preferences and personal context;
- \`project.md\` for purpose, status, links, and next steps;
- \`decision.md\` for choices with reasons, provenance, and conditions;
- \`source.md\` for references, conversation metadata, and notes on the original material;
- \`claim.md\` for atomic claims with evidence, limits, and validity;
- \`snapshot.md\` for a dated checkpoint worth preserving, not as a replacement for the project’s current summary.

Remove sections that add no value and keep those that help interpret or retrieve information. A template is a starting point, not a required form. A separate claim note is not needed for every fact: use one when the claim will be reused, may be disputed, or can change independently of its source.

## 4. Add a small amount of knowledge

Start with one active project and a few items you already know you will consult. First preserve the work conversations that contain this knowledge; then create derived records. For each record:

1. write one central idea and the minimum context needed;
2. note its provenance and date when they affect interpretation;
3. distinguish what the source said from your inference or decision;
4. link it from the project file and, if appropriate, to the turn ID in the preserved conversation;
5. mark uncertainty, currency, or a review condition when relevant.

Do not automatically import your entire personal history. Selection and context are often more useful than a large collection of unreviewed notes.

## 5. Test retrieval

Ask a real question about the project. For a question about current status, start with \`project.md\`; follow links to the decision or source supporting the answer. Consult a dated snapshot when asking about the state at an earlier milestone.

If you cannot explain why an answer is considered current or where it came from, improve the links and metadata before adding more content.

## 6. Maintain the knowledge base

Update \`project.md\` when status changes. Record important decisions separately when they can be reviewed independently. Keep dated snapshots only when you need to freeze a milestone; you do not need to create them every session or after every change. Git tracks file history.

Before syncing changes, check again that you have not added secrets or unnecessary sensitive information. Periodically review whether temporary data remains current and mark superseded records without erasing their provenance.

-------------------------------------

# Crear una implementación personal

Esta guía convierte la metodología de Theuth en una base de conocimiento que una persona pueda mantener. El repositorio del framework sirve como referencia y fuente de plantillas; la implementación personal conserva los registros canónicos de su propietario.

## 1. Elige dónde vivirá la base

Crea un espacio de trabajo separado del repositorio `cpz-theuth-framework`. Puede ser una carpeta local o un repositorio Git propio. Si se sincronizará con un servicio remoto, decide quién podrá acceder antes de añadir información personal.

Usa un repositorio privado cuando el contenido no sea público. No guardes contraseñas, claves de API ni credenciales en los registros. Añade a `.gitignore` archivos temporales, exportaciones o datos que no quieras versionar.

## 2. Empieza con una estructura mínima

Crea solo las carpetas que vayas a utilizar. Una base inicial puede tener esta forma:

```text
personal-knowledge/
└── knowledge/
    ├── profile.md
    ├── sources/
    │   └── conversations/
    │       └── <source-id>/
    │           ├── source.md
    │           ├── transcript.jsonl
    │           └── original.<ext>  (si está disponible)
    └── projects/
        └── project-slug/
            ├── project.md
            └── decisions/
```

Para Theuth, el registro de proyecto previsto es `knowledge/projects/theuth/project.md`, y sus decisiones canónicas van en `knowledge/projects/theuth/decisions/`. El archivo `project.md` mantiene el resumen compacto del estado actual.

Guarda las conversaciones de trabajo en `knowledge/sources/conversations/`: una sesión puede abarcar varios proyectos y así se conserva una sola fuente original que todos pueden enlazar. Al cerrar una sesión con contenido reutilizable, guarda la exportación sin editarla cuando exista y genera el transcript portable; la [metodología de captura](conversation-sources.md) define el formato y sus límites. No es necesario archivar conversaciones casuales sin material de trabajo. Añade `snapshots/` solo si quieres conservar checkpoints fechados de hitos; Git ya conserva las versiones anteriores de `project.md`.

## 3. Copia y adapta las plantillas

Toma del repositorio del framework las plantillas que necesitas:

- `profile.md` para preferencias y contexto personal relevante;
- `project.md` para propósito, estado, enlaces y siguientes pasos;
- `decision.md` para elecciones con razones, procedencia y condiciones;
- `source.md` para conservar referencias, metadatos de conversación y notas sobre el material original;
- `claim.md` para afirmaciones atómicas con evidencia, límites y vigencia;
- `snapshot.md` para un checkpoint fechado que convenga conservar, no para reemplazar el resumen vigente del proyecto.

Quita las secciones que no aporten valor y conserva las que ayuden a interpretar o recuperar la información. Una plantilla es un punto de partida, no un formulario obligatorio. No hace falta crear una nota de afirmación separada para cada dato: úsala cuando la afirmación vaya a reutilizarse, pueda discutirse o cambie independientemente de su fuente.

## 4. Añade una cantidad pequeña de conocimiento

Empieza con un proyecto activo y unas pocas piezas que ya sepas que consultarás. Conserva primero las conversaciones de trabajo que contienen ese conocimiento; después crea los registros derivados. Para cada registro:

1. escribe una idea central y el contexto mínimo;
2. anota su procedencia y fecha cuando afecten a la interpretación;
3. distingue lo que dijo la fuente de tu inferencia o decisión;
4. enlázalo desde el archivo del proyecto y, si procede, con el ID de turno de la conversación conservada;
5. marca incertidumbres, vigencia o una condición de revisión cuando sea relevante.

No importes automáticamente todo el historial personal. La selección y el contexto suelen ser más útiles que una gran colección de notas sin revisar.

## 5. Prueba la recuperación

Formula una pregunta real sobre el proyecto. Para una pregunta sobre el estado vigente, empieza por `project.md`; sigue los enlaces hasta la decisión o fuente que sustenta la respuesta. Consulta un snapshot fechado cuando preguntes por el estado en un hito anterior.

Si no puedes explicar por qué una respuesta se considera vigente o de dónde procede, mejora los enlaces y metadatos antes de añadir más contenido.

## 6. Mantén la base

Actualiza `project.md` cuando cambie el estado. Registra por separado las decisiones importantes que puedan revisarse de forma independiente. Conserva snapshots fechados solo cuando necesites congelar un hito; no es necesario producirlos en cada sesión ni cambio. Git mantiene la evolución de los archivos.

Antes de sincronizar cambios, vuelve a comprobar que no has añadido secretos o información sensible innecesaria. Revisa periódicamente si los datos temporales siguen vigentes y marca los registros reemplazados sin borrar su procedencia.

-------------------------------------
