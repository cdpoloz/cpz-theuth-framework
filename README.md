<!-- Bilingual README: English section followed by Spanish section. -->
-------------------------------------

# Theuth

Theuth is a methodological framework for creating knowledge layers that help individuals and teams continue their work with one or more LLMs, including when changing providers. It organizes sources, decisions, claims, and context in portable, version-controlled formats.

As an initial guide, Theuth includes two usage profiles:

- **TheuthMT (personal working memory):** prioritizes the context and continuity of one person’s work.
- **TheuthMTC (shared working memory):** prioritizes knowledge contributed to or accessed by multiple people under shared agreements and permissions.

These are recommendations for adapting Theuth to the goal and context of use, not rigid categories or separate systems. Sources can overlap: either profile may use conversations, working documents, and other records, depending on what is useful and authorized. In shared use, permissions and the AI provider’s access must be defined.

## Why Theuth?

The name refers to **Theuth**, whom Plato presents in the *Phaedrus* as the inventor of writing. In the dialogue, writing supports memory and consultation, but does not replace living understanding. This tension expresses the project’s purpose: using external records to support memory and thought without confusing the archive with knowledge itself.

## Related work

Theuth is developed in dialogue with related proposals, but it is not an implementation of any of them and does not automatically adopt their technical decisions.

### Ideas and provenance approaches

- [LLM Wiki, by Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): an idea for an LLM to maintain a personal knowledge base from sources.
- [The Provenance-First Wiki, by Able Varghese](https://github.com/AbleVarghese/Provenance-First-Wiki): an analysis and proposal that puts verifiable evidence traceability at the center of an LLM-managed wiki.

### LLM-assisted knowledge frameworks and projects

- [Funes](https://github.com/ulyssestenn/funes): a Git-based framework for organizing sources in a linked Markdown library and producing referenced answers and documents.
- [Personal Knowledge Wiki](https://github.com/ZLHad/personal-knowledge-wiki): an LLM-assisted personal wiki with workflows and skills for Claude Code, inspired by Karpathy’s pattern.

### Persistent memory for agents

- [Agent Zero Memory](https://arxiv.org/abs/2608.29606): research on agent memory with sources, temporal context, and evidence-linked answers.
- [Letta](https://github.com/letta-ai/letta): a platform for agents with persistent memory.
- [Mem0](https://github.com/mem0ai/mem0): memory infrastructure for AI applications and agents.
- [Graphiti](https://github.com/getzep/graphiti): a framework for temporal context graphs with provenance.

These works cover parts of the design space at different levels: idea, method, memory system, or implementation tool. Theuth aims to define a portable and adaptable methodology connecting capture, provenance, retrieval, correction, and retention, while keeping people in control of the knowledge that is retained.

## Initial principles

- Preserve provenance and distinguish original sources, derived material, inferences, and decisions.
- Link each important claim to locatable evidence; a synthesis does not automatically become evidence or an independent source.
- Record changes in meaning or validity incrementally, explaining what changed, why, and based on what evidence; preserve history without silent rewrites.
- Distinguish current state from history: the project summary describes the present, while Git, linked decisions, and optional snapshots help reconstruct changes and past states.
- Save context and purpose instead of accumulating information without criteria.
- Keep records small and linkable.
- Use progressive retrieval and show how an answer was reached.
- Use readable files, portable formats, and version control.
- Minimize sensitive data and protect privacy.
- Respect authorization and access restrictions that apply to sources and their derivatives.

## Repository structure

- `methodology/`: principles, knowledge model, usage profiles, lifecycle, conversation capture, retrieval, correction, and privacy/retention.
- `templates/`: reusable starter formats.
- `examples/`: demonstration cases, fictional or explicitly authorized, including retrieval evaluation cases.
- `docs/`: release scope and the relationship between the framework and a reference implementation.

This repository defines the framework. Canonical records belong in a separate implementation. See [the principles](methodology/principles.md), [scope and usage profiles](methodology/scope-and-modes.md), [the v0.1.0 release scope](docs/release-scope.md), [the reference implementation note](docs/reference-implementation.md), the [knowledge model](methodology/knowledge-model.md), the [conversation source guide](methodology/conversation-sources.md), the [retrieval workflow](methodology/retrieval.md), the [correction and revision workflow](methodology/correction-and-revision.md), and the [privacy, retention, and removal guide](methodology/privacy-retention-and-removal.md).

## Getting started

1. Read [the principles](methodology/principles.md), [scope and usage profiles](methodology/scope-and-modes.md), and the [knowledge model](methodology/knowledge-model.md).
2. If your goal is personal memory, follow the [personal instance setup guide](methodology/personal-instance-setup.md).
3. Adapt the templates and recommendations to your context; you do not need to use all of them.
4. Test retrieval with a real question and check that you can trace the answer to the records and sources that support it. You can start with the [first evaluation case](examples/retrieval-tests/01-theuth-current-framework-status.md).

The v0.1.0 scope is described in [docs/release-scope.md](docs/release-scope.md). This is a starting point, not a closed standard. The first planned reference implementation will apply Theuth in the TheuthMT personal orientation and will be maintained separately; see [docs/reference-implementation.md](docs/reference-implementation.md).

## Author

**Carlos Polo Zamora**  
GitHub: https://github.com/cdpoloz  
Alias: CPZ / cepezeta / cdpoloz

## License

Unless otherwise stated, the documentation, templates, and examples created for Theuth in this repository are licensed under **CC BY-SA 4.0**. If you share an adaptation of material covered by this license, you must provide attribution, indicate changes, and license it under CC BY-SA 4.0 or a compatible license permitted by its terms. See [LICENSE](LICENSE), the [official legal code](https://creativecommons.org/licenses/by-sa/4.0/legalcode.en), and the [Spanish deed](https://creativecommons.org/licenses/by-sa/4.0/deed.es).

The license covers copyrightable expression included in the repository; it does not grant rights over third-party material or exclusive rights over ideas or methods as such.

-------------------------------------

# Theuth

Theuth es un framework metodológico para crear capas de conocimiento que ayuden a personas o equipos a continuar su trabajo con uno o varios LLM, incluso al cambiar de proveedor. Organiza `sources`, `decisions`, `claims` y contexto en formatos portables y con control de versiones.

Como orientación inicial, Theuth incluye dos perfiles de uso:

- **TheuthMT (memoria de trabajo personal):** prioriza el contexto y la continuidad del trabajo de una persona.
- **TheuthMTC (memoria de trabajo compartida):** prioriza el conocimiento al que contribuyen o acceden varias personas bajo acuerdos y permisos comunes.

Son recomendaciones para adaptar Theuth al objetivo y al contexto de uso, no categorías rígidas ni sistemas separados. Las `sources` pueden solaparse: cualquiera de los perfiles puede utilizar conversaciones, documentos de trabajo y otros registros, según lo que resulte útil y esté autorizado. En un uso compartido deben definirse los permisos y el acceso del proveedor de IA.

## ¿Por qué Theuth?

El nombre alude a **Theuth**, figura que Platón presenta en el *Fedro* como inventor de la escritura. En el diálogo, la escritura sirve de apoyo para recordar y consultar, aunque no sustituye la comprensión viva. Esta tensión expresa el propósito del proyecto: utilizar registros externos para sostener la memoria y el pensamiento sin confundir el archivo con el conocimiento mismo.

## Trabajos relacionados

Theuth se desarrolla en diálogo con propuestas cercanas, pero no es una implementación de ninguna de ellas ni adopta automáticamente sus decisiones técnicas.

### Ideas y enfoques de provenance

- [LLM Wiki, de Andrej Karpathy](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f): idea para que un LLM mantenga una base personal de conocimiento a partir de `sources`.
- [The Provenance-First Wiki, de Able Varghese](https://github.com/AbleVarghese/Provenance-First-Wiki): análisis y propuesta que sitúa la trazabilidad verificable de la evidencia en el centro de una wiki gestionada por LLM.

### Frameworks y proyectos de conocimiento asistido por LLM

- [Funes](https://github.com/ulyssestenn/funes): framework basado en Git para organizar `sources` en una biblioteca Markdown enlazada y producir respuestas y documentos con referencias.
- [Personal Knowledge Wiki](https://github.com/ZLHad/personal-knowledge-wiki): wiki personal asistida por LLM, con workflows y skills para Claude Code, inspirada en el patrón de Karpathy.

### Memoria persistente para agentes

- [Agent Zero Memory](https://arxiv.org/abs/2608.29606): investigación sobre memoria de agentes con `sources`, contexto temporal y respuestas vinculadas a evidencia.
- [Letta](https://github.com/letta-ai/letta): plataforma para agentes con memoria persistente.
- [Mem0](https://github.com/mem0ai/mem0): infraestructura de memoria para aplicaciones y agentes de IA.
- [Graphiti](https://github.com/getzep/graphiti): framework para grafos temporales de contexto con `provenance`.

Estos trabajos cubren partes del espacio de diseño en distintos niveles: idea, método, sistema de memoria o herramienta de implementación. Theuth busca definir una metodología portable y adaptable que conecte `capture`, `provenance`, `retrieval`, `correction` y `retention`, manteniendo a las personas al mando del conocimiento que se conserva.

## Principios iniciales

- Conservar la `provenance` y distinguir `original sources`, `derived material`, `inferences` y `decisions`.
- Enlazar cada `claim` importante con evidencia localizable; una síntesis no se convierte automáticamente en evidencia ni en una fuente independiente.
- Registrar los cambios de significado o vigencia de forma incremental, explicando qué cambió, por qué y con qué evidencia; conservar el historial sin reescrituras silenciosas.
- Distinguir el estado actual del historial: el resumen del proyecto describe el presente, mientras Git, las `decisions` enlazadas y los `snapshots` opcionales permiten reconstruir cambios y estados pasados.
- Guardar contexto y propósito en lugar de acumular información sin criterio.
- Mantener los registros pequeños y enlazables.
- Utilizar `progressive retrieval` y mostrar cómo se llegó a una respuesta.
- Utilizar archivos legibles, formatos portables y control de versiones.
- Minimizar los datos sensibles y proteger la privacidad.
- Respetar las autorizaciones y restricciones de acceso aplicables a las `sources` y sus derivados.

## Estructura del repositorio

- `methodology/`: principios, modelo de conocimiento, perfiles de uso, ciclo de vida, captura de conversaciones, `retrieval`, corrección y privacidad/retención.
- `templates/`: formatos iniciales reutilizables.
- `examples/`: casos de demostración, ficticios o expresamente autorizados, incluidos casos de evaluación de `retrieval`.
- `docs/`: alcance de la versión y relación entre el framework y una implementación de referencia.

Este repositorio define el framework. Los registros canónicos pertenecen a una implementación separada. Consulta [los principios](methodology/principles.md), [el alcance y los perfiles de uso](methodology/scope-and-modes.md), [el alcance de v0.1.0](docs/release-scope.md), [la nota sobre implementación de referencia](docs/reference-implementation.md), el [modelo de conocimiento](methodology/knowledge-model.md), la guía de [captura de conversaciones](methodology/conversation-sources.md), el [workflow de retrieval](methodology/retrieval.md), el [workflow de correction and revision](methodology/correction-and-revision.md) y la guía de [privacy, retention and removal](methodology/privacy-retention-and-removal.md).

## Cómo empezar

1. Lee [los principios](methodology/principles.md), [el alcance y los perfiles de uso](methodology/scope-and-modes.md) y el [modelo de conocimiento](methodology/knowledge-model.md).
2. Si tu objetivo es la memoria personal, sigue la [guía de configuración de una personal instance](methodology/personal-instance-setup.md).
3. Adapta las plantillas y recomendaciones a tu contexto; no es necesario utilizarlas todas.
4. Prueba `retrieval` con una pregunta real y comprueba que puedes rastrear la respuesta hasta los registros y `sources` que la respaldan. Puedes empezar con el [primer caso de evaluación](examples/retrieval-tests/01-theuth-current-framework-status.md).

El alcance de v0.1.0 está descrito en [docs/release-scope.md](docs/release-scope.md). Es una base de trabajo, no un estándar cerrado. La primera implementación de referencia prevista aplicará Theuth en la orientación personal TheuthMT y se mantendrá por separado; consulta [docs/reference-implementation.md](docs/reference-implementation.md).

## Author

**Carlos Polo Zamora**  
GitHub: https://github.com/cdpoloz  
Alias: CPZ / cepezeta / cdpoloz

## License

Salvo que se indique lo contrario, la documentación, las plantillas y los ejemplos creados para Theuth en este repositorio se ofrecen bajo **CC BY-SA 4.0**. Si compartes una adaptación de material cubierto por esta licencia, debes dar atribución, indicar los cambios y licenciarla bajo CC BY-SA 4.0 o una licencia compatible permitida por sus términos. Consulta [LICENSE](LICENSE), el [código legal oficial](https://creativecommons.org/licenses/by-sa/4.0/legalcode.en) y el [resumen en español](https://creativecommons.org/licenses/by-sa/4.0/deed.es).

La licencia cubre la expresión protegible incluida en el repositorio; no concede derechos sobre materiales de terceros ni derechos exclusivos sobre ideas o métodos como tales.

-------------------------------------
