<!-- English section first; Spanish section follows. -->

-------------------------------------

# Evaluation case 01: current status of Theuth

This case checks whether a query about the framework’s status retrieves current information, distinguishes the methodology from an implementation, and makes its supporting evidence visible. It is a manual methodology test, not an automated benchmark.

## Query

> Which methodological features have already been defined in Theuth, and which aspects remain open?

## Reference corpus

Run the case against the repository at commit \`35111bced83cce5ac480fc4acd4817ae7aac5f24\`. This ref makes it possible to repeat the query even if the contents of \`main\` change.

Start with:

- [README](../../README.md)
- [Scope and usage profiles](../../methodology/scope-and-modes.md)
- [Knowledge model](../../methodology/knowledge-model.md)

Follow, as needed for the question:

- [Conversations as sources](../../methodology/conversation-sources.md)
- [Retrieval workflow](../../methodology/retrieval.md)
- [Correction and revision](../../methodology/correction-and-revision.md)
- [Privacy, retention, and removal](../../methodology/privacy-retention-and-removal.md)
- [Lifecycle](../../methodology/lifecycle.md)

Files under [examples/theuth](../theuth/project.md) are illustrative material, not canonical sources for the current state of the framework. In particular, the [initial snapshot](../theuth/snapshots/2026-09-29-initial-design.md) is explicitly a historical checkpoint. Using it as the current state without checking its scope counts as a retrieval error.

## Expected answer

A satisfactory answer should communicate, in equivalent terms:

- Theuth has an initial v0.1 methodological proposal; it is neither a closed standard nor a finished technical implementation.
- It already describes provenance principles and the distinction between sources and derived material; portable capture of conversations; personal and shared profiles as flexible recommendations; progressive and visible retrieval; correction with dependency tracking; and general criteria for privacy, retention, and removal.
- The first planned implementation is personal and would be developed separately. The detailed controls for shared use—and decisions specific to each implementation—remain open.
- The Theuth project examples are not canonical records, and the initial snapshot only describes its cutoff date.
- Do not claim that an executable system, automated search, common legal retention policy, or shared deployment exists, because this corpus does not establish that.

## Stages the answer should make visible

1. **Scope:** explain that the query concerns the framework’s status and compares what is defined with what remains open.
2. **Entry point:** consult the README and scope/profiles.
3. **Currency:** compare against the current methodology and do not use the snapshot as present-day status.
4. **Provenance:** link each important claim to the methodological document that supports it.
5. **Limits:** distinguish what is documented from what is proposed or pending; state whether any relevant source was not reviewed.

The interface may summarize progress in a brief note, but the answer should make clear which stages were completed and let readers trace relevant claims.

## Evaluation criteria

Score each criterion as achieved / partial / not achieved:

- Distinguishes the methodological framework from an implementation.
- Accurately describes the practices already defined.
- Identifies open aspects without presenting them as adopted decisions.
- Uses current methodological documents as support and links to locators.
- Does not treat illustrative files or snapshots as authority on the current state.
- States uncertainty and avoids inventing technical capabilities.

**Case passes:** all critical criteria (distinguishing framework from implementation, providing support, and not inventing capabilities) must be achieved, and at least five of the six criteria must be achieved.

## Critical errors

- Claiming that Theuth has a working implementation or automated search without support in the corpus.
- Presenting a future proposal as an existing decision or capability.
- Citing the historical snapshot as sufficient evidence of the current state.
- Treating a legal policy or universal retention period as already defined.

## Case maintenance

The corpus is pinned to the commit above. If the case is adapted to a later version, update the ref, recheck the expected criteria, and keep a note of what changed. A content change may be part of the evaluated result; it is not a reason to leave the test ambiguous.

-------------------------------------

# Caso de evaluación 01: estado actual de Theuth

Este caso comprueba si una consulta sobre el estado del framework recupera información vigente, distingue la metodología de una implementación y hace visible el respaldo. Es una prueba manual de metodología, no un benchmark automatizado.

## Consulta

> ¿Qué características metodológicas ya están definidas en Theuth y qué aspectos siguen abiertos?

## Corpus de referencia

Ejecutar el caso contra el repositorio en el commit `35111bced83cce5ac480fc4acd4817ae7aac5f24`. Este ref permite repetir la consulta aunque el contenido de `main` cambie.

Iniciar por:

- [README](../../README.md)
- [Alcance y perfiles de uso](../../methodology/scope-and-modes.md)
- [Modelo de conocimiento](../../methodology/knowledge-model.md)

Seguir, según la pregunta, a:

- [Conversaciones como fuentes](../../methodology/conversation-sources.md)
- [Flujo de recuperación](../../methodology/retrieval.md)
- [Corrección y revisión](../../methodology/correction-and-revision.md)
- [Privacidad, retención y retirada](../../methodology/privacy-retention-and-removal.md)
- [Ciclo de vida](../../methodology/lifecycle.md)

Los archivos bajo [examples/theuth](../theuth/project.md) son material ilustrativo y no la fuente canónica del estado actual del framework. En particular, el [snapshot inicial](../theuth/snapshots/2026-09-29-initial-design.md) es explícitamente un checkpoint histórico. Usarlos como estado vigente sin comprobar su alcance cuenta como un error de recuperación.

## Respuesta esperada

Una respuesta satisfactoria debería comunicar, en términos equivalentes:

- Theuth tiene una propuesta metodológica inicial v0.1, no un estándar cerrado ni una implementación técnica acabada.
- Ya están descritos principios de procedencia y distinción entre fuente y material derivado; captura portable de conversaciones; perfiles personal y compartido como recomendaciones flexibles; recuperación progresiva y visible; corrección con rastreo de dependencias; y criterios generales de privacidad, retención y retirada.
- La primera implementación prevista es personal y se desarrollaría por separado. El diseño detallado de los controles para un uso compartido —y las decisiones específicas de cada implementación— permanece abierto.
- Los ejemplos del proyecto Theuth no son registros canónicos y el snapshot inicial solo informa de su fecha de corte.
- No se debe afirmar que existe un sistema ejecutable, una búsqueda automatizada, una política legal común de retención ni un despliegue compartido, porque este corpus no lo establece.

## Etapas que debe hacer visibles la respuesta

1. **Delimitación:** explicar que se consulta el estado del framework y se compara lo definido con lo que sigue abierto.
2. **Punto de entrada:** consultar README y alcance/perfiles.
3. **Vigencia:** contrastar con metodología actual y no usar el snapshot como estado presente.
4. **Procedencia:** enlazar cada afirmación importante al documento metodológico que la sustenta.
5. **Límites:** distinguir lo ya documentado de lo propuesto o pendiente; indicar si no se revisó alguna fuente pertinente.

La interfaz puede resumir el progreso en una nota breve, pero la respuesta debe permitir entender qué etapas se realizaron y rastrear las afirmaciones relevantes.

## Criterios de evaluación

Puntuar cada criterio como logrado / parcial / no logrado:

- Distingue framework metodológico de implementación.
- Describe correctamente las prácticas ya definidas.
- Identifica los aspectos abiertos sin presentarlos como decisiones adoptadas.
- Usa documentos metodológicos vigentes como respaldo y enlaza localizadores.
- No trata archivos ilustrativos o snapshots como autoridad sobre el estado actual.
- Declara incertidumbres y evita inventar capacidades técnicas.

**Aprobación del caso:** todos los criterios críticos (distinción entre framework e implementación, respaldo y no invención de capacidades) deben lograrse, y al menos cinco de los seis criterios deben estar logrados.

## Errores críticos

- Afirmar que Theuth tiene una implementación funcional o búsqueda automatizada sin respaldo en el corpus.
- Presentar una propuesta futura como decisión o capacidad ya existente.
- Citar el snapshot histórico como evidencia suficiente del estado actual.
- Dar por definida una política legal o un plazo universal de retención.

## Mantenimiento del caso

El corpus está fijado al commit indicado. Si el caso se adapta a una versión posterior, actualiza el ref, vuelve a comprobar los criterios esperados y conserva una nota de qué cambió. El cambio de contenido puede ser parte del resultado evaluado, no un motivo para dejar el test ambiguo.

-------------------------------------
