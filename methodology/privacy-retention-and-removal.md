<!-- English section first; Spanish section follows. -->

-------------------------------------

# Privacy, retention, and source removal

This guide sets general methodological criteria. It does not determine legal deadlines, organizational permissions, or a universal deletion procedure: each implementation must adapt them to its purpose, information type, authorizations, and storage and provider capabilities.

## Before adding a source

Assess and document, in proportion to the risk:

- **Purpose and need:** what work it helps remember, understand, or continue. Do not add information that does not provide sufficient value.
- **Authorization:** whether the person adding the material may retain it and whether processing by the AI provider is authorized for that information type and use.
- **Minimization:** whether unnecessary personal or sensitive data can be excluded while noting what was omitted.
- **Sensitivity and access:** who may consult the original and what restrictions must also apply to transcripts, excerpts, indexes, and derivatives.
- **Planned retention:** the agreed period or condition that will trigger review, archiving, or removal.

Do not copy sensitive content into control notes when it is sufficient to record its category, restriction, or reason for exclusion. Do not store secrets or credentials in the knowledge base.

## Reviewing retention

There is no single period appropriate for every source. Set a review date or condition according to its purpose, sensitivity, currency, and applicable obligations. Review sooner if authorization changes, the purpose expires, information becomes invalid, or someone requests removal.

During review, decide whether to retain, restrict access, update derivatives, archive, or remove. Record the result and reason when doing so does not reproduce content being removed. Git makes it possible to consult versions, but it is not by itself a complete retention policy and does not guarantee deletion of copies.

## Removing a source and reviewing its derivatives

When a source is requested or decided to be removed:

1. **Identify it and define the reason.** Locate the record and original material, and determine whether the reason is expiry, lack of authorization, capture error, removal request, or something else.
2. **Trace dependencies.** Search for claims, decisions, project summaries, snapshots, transcripts, attachments, indexes, caches, and other derivatives that depend on the source. Note which repositories and systems could be reviewed.
3. **Assess each derivative.** Decide whether it should be removed, corrected, replaced, or retained under restrictions for a valid and authorized reason. Do not assume all derivatives receive the same treatment.
4. **Agree on the scope of action.** Explain what will be deleted, what will be restricted, what may remain in history or backups, and which systems are inaccessible. For irreversible actions, present the scope before executing them and obtain an explicit instruction.
5. **Apply removal within available capabilities.** Consider original and normalized files, excerpts, attachments, synchronized copies, indexes, caches, backups, and repository history. If a location cannot be changed from the implementation, explain the pending step and who must handle it.
6. **Check the result.** Verify that accessible records no longer expose removed content or present claims as supported when their evidence has been removed. Review locatable dependencies and state the limits of that search.
7. **Keep a minimal record.** When appropriate and authorized, retain the source identifier, date, general reason, and removal result, without reproducing the removed material.

Do not promise complete erasure if the system retains history, replicas, or backups beyond the implementation’s reach. Removing a working copy does not necessarily purge every repository version or provider copy.

## Possible assisted tool

An implementation may provide a skill or other tool to assist with reviews and removals. It may locate references and dependencies, flag restrictions or review dates, and prepare a list of actions and reviewed locations. The responsible person decides the scope; the tool must not remove sources or derivatives on its own.

The tool should state which repositories, versions, indexes, and backups it could inspect and what is outside its reach. Deletion or permission changes are carried out only when the person explicitly authorizes them and the implementation can perform them. The executable format and integration with each storage system belong to the implementation; Theuth defines the criteria and expected behavior.

## Implementation records

The [source template](../templates/source.md) supports recording access, privacy, and review. Details about the legal basis for authorization, specific deadlines, exceptions, and procedures must be defined in the implementation according to its context and applicable rules.

-------------------------------------

# Privacidad, retención y retirada de fuentes

Esta guía establece criterios metodológicos generales. No determina plazos legales, permisos organizacionales ni un procedimiento universal de borrado: cada implementación debe adaptarlos al propósito, al tipo de información, a sus autorizaciones y a las capacidades de su almacenamiento y proveedor.

## Antes de incorporar una fuente

Evalúa y documenta, en el grado adecuado al riesgo:

- **Propósito y necesidad:** qué trabajo ayuda a recordar, comprender o continuar. No incorpores información que no aporte valor suficiente.
- **Autorización:** si quien incorpora el material puede conservarlo y si su tratamiento por el proveedor de IA está autorizado para ese tipo de información y ese uso.
- **Minimización:** si pueden excluirse datos personales o sensibles que no hagan falta, manteniendo constancia de las partes omitidas.
- **Sensibilidad y acceso:** quién puede consultar el original y qué restricciones deben aplicarse también a transcripciones, extractos, índices y derivados.
- **Retención prevista:** el periodo acordado o la condición que hará que la fuente deba revisarse, archivarse o retirarse.

No copies contenido sensible a notas de control si basta con registrar su categoría, restricción o motivo de exclusión. No guardes secretos o credenciales en la base de conocimiento.

## Revisar la retención

No existe un plazo único adecuado para todas las fuentes. Define una fecha o condición de revisión según su propósito, sensibilidad, vigencia y obligaciones aplicables. Revisa antes si cambia la autorización, vence el propósito, la información deja de ser válida o una persona solicita su retirada.

En la revisión, decide si conservar, limitar el acceso, actualizar los derivados, archivar o retirar. Registra el resultado y el motivo cuando hacerlo no reproduzca contenido que se intenta retirar. Git permite consultar versiones, pero por sí solo no constituye una política completa de retención ni garantiza la eliminación de copias.

## Retirar una fuente y revisar sus derivados

Cuando se solicita o decide retirar una fuente:

1. **Identificarla y delimitar el motivo.** Localiza el registro y el material original, y determina si el motivo es caducidad, falta de autorización, error de captura, solicitud de retirada u otro.
2. **Rastrear dependencias.** Busca afirmaciones, decisiones, resúmenes de proyecto, snapshots, transcripciones, adjuntos, índices, cachés y otros derivados que dependan de la fuente. Anota qué repositorios y sistemas se pudieron revisar.
3. **Evaluar cada derivado.** Decide si debe retirarse, corregirse, sustituirse o conservarse con restricciones por una razón válida y autorizada. No asumas que todos los derivados tienen el mismo tratamiento.
4. **Acordar el alcance de la acción.** Expón qué se eliminará, qué se restringirá, qué podría permanecer en historial o respaldos y qué sistemas no son accesibles. Para acciones irreversibles, presenta el alcance antes de ejecutarlas y obtén una instrucción explícita.
5. **Aplicar la retirada según las capacidades disponibles.** Considera archivos originales y normalizados, extractos, adjuntos, copias sincronizadas, índices, cachés, respaldos e historial del repositorio. Si una ubicación no puede modificarse desde la implementación, explica el paso pendiente y quién debe gestionarlo.
6. **Comprobar el resultado.** Verifica que los registros accesibles ya no expongan contenido retirado ni presenten como respaldadas afirmaciones que perdieron su evidencia. Revisa las dependencias localizables y declara los límites de esa búsqueda.
7. **Dejar una constancia mínima.** Cuando sea apropiado y esté autorizado, conserva el identificador de la fuente, la fecha, el motivo general y el resultado de la retirada, sin reproducir el material retirado.

No prometas un borrado completo si el sistema conserva historial, réplicas o respaldos fuera del alcance de la implementación. La eliminación de una copia de trabajo no implica necesariamente purgar todas las versiones del repositorio o las copias del proveedor.

## Posible herramienta asistida

Una implementación puede ofrecer un skill u otra herramienta para asistir en revisiones y retiradas. Puede localizar referencias y dependencias, señalar restricciones o fechas de revisión, y preparar una lista de acciones y ubicaciones revisadas. La persona responsable decide el alcance; la herramienta no debe retirar fuentes ni derivados por iniciativa propia.

La herramienta debe declarar qué repositorios, versiones, índices y respaldos pudo inspeccionar y qué queda fuera de su alcance. Las acciones de borrado o cambio de permisos solo se ejecutan cuando la persona las autoriza explícitamente y la implementación puede realizarlas. El formato ejecutable y la integración con cada almacenamiento corresponden a la implementación; Theuth define los criterios y el comportamiento esperado.

## Registros de implementación

La plantilla de [fuente](../templates/source.md) permite anotar acceso, privacidad y revisión. Los detalles sobre base de autorización, plazos concretos, excepciones y procedimientos deben definirse en la implementación conforme a su contexto y reglas aplicables.

-------------------------------------
