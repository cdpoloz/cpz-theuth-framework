<!-- English section first; Spanish section follows. -->

-------------------------------------

# Retrieval workflow

This workflow guides how a Theuth implementation answers queries using persistent records. Its stages should be visible to the person so they can understand what was consulted, what was verified, and where the limits are. Visibility can be concise and adapted to the interface, but it should not hide an omitted stage.

## Stages

1. **Define the query.** Identify the project or topic, what is being asked, and whether the answer needs current status, a historical state, or the reasons for a decision. If the scope is unclear and would change the answer, ask for clarification.
2. **Locate the entry point.** For a question about a project’s current status, start with its \`project.md\` or equivalent current summary. For a historical or decision-related question, first locate the corresponding record.
3. **Check status and currency.** Review dates, statuses, and relationships such as “replaces” or “was replaced by.” Check whether a record is under review, disputed, or corrected according to the [correction and revision workflow](correction-and-revision.md). Do not treat an old record as current just because it is easy to find. If there are discrepancies, keep them visible; do not silently choose one version.
4. **Trace provenance.** Open the relevant decisions, sources, and specific locators. Check that the cited passage supports the claim and distinguish an original source from a synthesis or derived answer. A synthesis can guide the search but is not independent evidence.
5. **Answer with explicit limits.** Separate supported information, inference, and uncertainty. State what could not be consulted or verified. If the evidence is insufficient or not relevant enough, say so clearly instead of turning a weak match into a confirmed answer.

## What to show the person

During retrieval, briefly communicate progress through the relevant stages, for example:

- scope identified;
- initial summary or record consulted;
- currency and conflicts checked;
- sources or passages compared;
- limits affecting the answer.

Operational details that do not help explain the answer do not need to be shown. Omitted checks, relevant conflicts, and coverage limits should be visible. The final answer should let readers trace its important claims to the corresponding record and source.

## Example: project status

For “What is the current project status?”, retrieval starts with the current summary, checks its date, and follows links to relevant progress and decisions. If the summary is old or contradicts a later record, it says so and looks for original evidence before describing the status. The answer distinguishes confirmed information from pending or outdated items.

## Example: reasons for a decision

For “Why did we make this decision?”, retrieval locates the decision, checks whether it is current or superseded, and reviews its linked sources and turns. It distinguishes reasons stated by the person from LLM recommendations and later inferences. If a reason cannot be confirmed in the source, it is not attributed as a proven motive.

## Implementation independence

The workflow does not prescribe keyword search, a database, indexes, embeddings, or any other specific mechanism. Each implementation may choose its tools and display the stages in a suitable format while maintaining traceability, visibility, and explicit treatment of uncertainty.

-------------------------------------

# Flujo de recuperación

Este flujo orienta cómo una implementación de Theuth responde consultas a partir de registros persistentes. Sus etapas deben ser visibles para la persona, de modo que pueda entender qué se consultó, qué se verificó y dónde quedan límites. La visibilidad puede ser concisa y adaptarse a la interfaz, pero no debe ocultar una etapa omitida.

## Etapas

1. **Delimitar la consulta.** Identifica el proyecto o tema, qué se pregunta y si se necesita el estado vigente, un estado histórico o las razones de una decisión. Si el alcance no está claro y cambia la respuesta, solicita precisión.
2. **Localizar el punto de entrada.** Para una pregunta sobre el estado vigente de un proyecto, empieza por su `project.md` o el resumen actual equivalente. Para una pregunta histórica o decisional, busca primero el registro correspondiente.
3. **Comprobar estado y vigencia.** Revisa fechas, estados y relaciones como “reemplaza a” o “fue reemplazado por”. Comprueba si el registro está en revisión, disputado o corregido según el [flujo de corrección y revisión](correction-and-revision.md). No trates un registro antiguo como vigente solo porque sea fácil de encontrar. Si hay discrepancias, consérvalas visibles y no elijas una versión en silencio.
4. **Seguir la procedencia.** Abre las decisiones, fuentes y localizadores concretos pertinentes. Comprueba que el pasaje citado respalda la afirmación y distingue fuente original de síntesis o respuesta derivada. Una síntesis puede guiar la búsqueda, pero no es evidencia independiente.
5. **Responder con límites explícitos.** Separa lo respaldado, la inferencia y lo incierto. Indica qué no se pudo consultar o verificar. Si la evidencia es insuficiente o poco pertinente, dilo claramente en vez de convertir una coincidencia débil en respuesta confirmada.

## Qué mostrar a la persona

Durante la consulta, comunica de forma breve el avance por las etapas pertinentes, por ejemplo:

- alcance identificado;
- resumen o registro inicial consultado;
- comprobación de vigencia y conflictos;
- fuentes o pasajes contrastados;
- límites que afectan la respuesta.

No es necesario mostrar detalles operativos que no ayuden a entender la respuesta. Sí hay que hacer visibles las comprobaciones omitidas, los conflictos relevantes y las limitaciones de cobertura. La respuesta final debe permitir rastrear sus afirmaciones importantes hasta el registro y la fuente correspondientes.

## Ejemplo: estado de un proyecto

Ante “¿Cuál es el estado actual del proyecto?”, la recuperación comienza por el resumen vigente, revisa su fecha y sigue los enlaces a los avances y decisiones relevantes. Si el resumen es antiguo o contradice un registro posterior, lo señala y busca evidencia original antes de describir el estado. La respuesta distingue lo confirmado de lo pendiente o desactualizado.

## Ejemplo: razones de una decisión

Ante “¿Por qué tomamos esta decisión?”, la recuperación localiza la decisión, comprueba si sigue vigente o fue reemplazada y revisa sus fuentes y turnos enlazados. Distingue las razones expresadas por la persona de las recomendaciones del LLM y de las inferencias posteriores. Si no puede confirmar una razón en la fuente, no la atribuye como motivo probado.

## Independencia de implementación

El flujo no prescribe búsqueda por palabras clave, base de datos, índices, embeddings ni otro mecanismo concreto. Cada implementación puede elegir sus herramientas y mostrar las etapas con el formato adecuado, manteniendo trazabilidad, visibilidad y tratamiento explícito de la incertidumbre.

-------------------------------------
