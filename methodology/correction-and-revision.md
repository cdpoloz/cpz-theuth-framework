<!-- English section first; Spanish section follows. -->

-------------------------------------

# Correction and revision of knowledge

This workflow makes it possible to correct a record without erasing history or leaving earlier summaries appearing current. It applies to claims, decisions, summaries, and other derived records. Original sources are preserved; if a source contains an error, record the correction separately and link it to the source.

## Distinguish what changed

Before editing, identify the situation:

- **Error in a derived record:** the source has not changed, but a claim, quotation, summary, or decision misinterpreted it or recorded an incorrect fact.
- **Change in available information:** a new source, measurement, or passage of time changes what is considered current. The previous record may have been correct at the time; do not automatically describe it as an error.
- **Transcription or extraction error:** the transcript, OCR, or other derived representation does not match the original source. Correct or replace the derivative and review records that depended on it.
- **Original source questioned or corrected:** preserve the captured original and record the correction, erratum, or new version as linked additional material. Do not silently overwrite the earlier capture.

## Incremental updates

Update only affected parts and preserve what remains supported. For any change that alters meaning, status, or currency:

- record the date of the change and what was modified;
- explain the reason and link the source and locator supporting the change;
- state whether the earlier record remains valid for another period or scope, is disputed, or has been superseded;
- link dependent records that need review.

A separate record is not needed for a style or formatting edit that does not change meaning. Git can preserve that edit, but for semantic changes Git does not replace an explanation of the reason or a link to evidence.

## Correction workflow

1. **Record the finding.** State which record appears incorrect or outdated, how it was identified, and when. If the cause is not yet known, mark the record for review.
2. **Return to the evidence.** Consult the original source and its locator. Distinguish a demonstrable error from an unresolved contradiction or information that has simply changed.
3. **Locate dependencies.** Find records that link to the affected item and records that declare dependence on it: claims, decisions, project summaries, and related snapshots. The search may miss dependencies if links are incomplete; state this limit.
4. **Assess each affected derivative.** Determine whether it remains supported, needs updating, should remain disputed, or has been superseded. Do not assume that a correction automatically invalidates every related conclusion.
5. **Update without erasing history.** Make the smallest sufficient change. For changes in meaning, preserve the previous record and its historical status, create or revise the current record, and link them with relationships such as \`corrects\` or \`supersedes\`. State the reason, date, and evidence. Minor edits may remain in the same record with Git history.
6. **Review decisions and summaries.** Identify decisions whose rationale depends on the corrected information and summaries that repeat it. Mark potentially affected decisions for review; do not revoke or change them automatically.
7. **Communicate the result.** Explain what was corrected, which records were reviewed, what remains pending, and what limits applied when tracing dependencies. Keep unresolved conflicts visible.

## Current state and history

The project summary and linked active records express the state considered current. Git history preserves file versions; relationships between records and change notes explain why one version replaced or revised another. A snapshot may preserve a dated checkpoint worth consulting, but it is not an exhaustive chronology or a source of current status.

Do not update all historical snapshots to make them appear current: preserve what they described at their cutoff date. If a correction affects historical interpretation, link a correction or review note without silently changing the original content; also follow applicable privacy, retention, and removal rules.

## Statuses and links

Recommended statuses distinguish pending work from current knowledge:

- **active:** reviewed and current for the stated scope;
- **needs-review:** a change or finding may affect it, but has not been resolved;
- **disputed:** evidence or interpretation conflicts;
- **superseded:** another record replaces it for the stated scope or period;
- **unverified:** sufficient support has not been found.

When relevant, record links such as **reviews**, **corrects**, **supersedes**, or **depends on**. Include the date, reason, source, and locator for the correction. Exact field names may be adapted to the implementation; the relationship should remain understandable and searchable.

## Automation and control

A tool may detect incoming links and propose a review list. It must not delete sources, change decisions, or mark an entire chain as corrected automatically. The responsible person reviews the effects and accepts updates for the context.

If a dependency cannot be located, do not claim that the correction propagated throughout the database. Identify the records reviewed and state that the search may have been incomplete.

-------------------------------------

# Corrección y revisión de conocimiento

Este flujo permite corregir un registro sin borrar la historia ni hacer que las síntesis anteriores sigan apareciendo como vigentes. Se aplica a afirmaciones, decisiones, resúmenes y otros registros derivados. Las fuentes originales se preservan; si una fuente contiene un error, la corrección se registra aparte y se enlaza a ella.

## Distinguir qué cambió

Antes de editar, identifica el caso:

- **Error en un registro derivado:** la fuente no cambió, pero una afirmación, cita, resumen o decisión la interpretó mal o registró un dato incorrecto.
- **Cambio en la información disponible:** una fuente nueva, una nueva medición o el paso del tiempo modifica lo que se considera vigente. El registro anterior pudo ser correcto para su momento; no debe describirse automáticamente como un error.
- **Error de transcripción o extracción:** el transcript, OCR u otra representación derivada no coincide con la fuente original. Corrige o reemplaza la derivación y revisa los registros que dependían de ella.
- **Fuente original cuestionada o corregida:** conserva el original capturado y registra la corrección, errata o versión nueva como material adicional enlazado. No sobrescribas silenciosamente la captura anterior.

## Actualización incremental

Actualiza solo las partes afectadas y conserva las que siguen respaldadas. Para todo cambio que altere significado, estado o vigencia:

- registra la fecha del cambio y qué se modificó;
- explica el motivo y enlaza la fuente y el localizador que justifican el cambio;
- indica si el registro anterior sigue siendo válido para otro periodo o alcance, queda disputado o ha sido sustituido;
- enlaza registros dependientes que deban revisarse.

No hace falta crear un registro independiente para una edición de estilo o formato que no cambie el sentido. Git puede conservar esa edición, pero para los cambios semánticos Git no sustituye la explicación del motivo ni el enlace con la evidencia.

## Flujo de corrección

1. **Registrar el hallazgo.** Indica qué registro parece incorrecto o desactualizado, cómo se detectó y cuándo. Si la causa aún no se conoce, marca el registro como pendiente de revisión.
2. **Volver a la evidencia.** Consulta la fuente original y su localizador. Distingue un error demostrable de una contradicción no resuelta o de información que simplemente ha cambiado.
3. **Localizar dependencias.** Busca los registros que enlazan con el elemento afectado y los que declaran depender de él: afirmaciones, decisiones, resúmenes de proyecto y snapshots relacionados. La búsqueda puede no encontrar dependencias si los enlaces estaban incompletos; declara ese límite.
4. **Evaluar cada derivado afectado.** Determina si sigue respaldado, requiere actualización, debe quedar en disputa o ha sido reemplazado. No supongas que una corrección invalida automáticamente todas las conclusiones relacionadas.
5. **Actualizar sin borrar la historia.** Aplica el cambio mínimo suficiente. Para cambios de significado, conserva el registro previo y su estado histórico, crea o revisa el registro vigente y enlázalos con relaciones como `corrige` o `sustituye`. Indica motivo, fecha y evidencia. Las ediciones menores pueden permanecer en el mismo registro con el historial de Git.
6. **Revisar decisiones y resúmenes.** Señala las decisiones cuyo razonamiento dependa de la información corregida y los resúmenes que la repitan. Una decisión que pueda verse afectada pasa a revisión; no se revoca ni cambia automáticamente.
7. **Comunicar el resultado.** Explica qué se corrigió, qué registros fueron revisados, qué queda pendiente y qué limitaciones hubo al rastrear dependencias. Mantén visibles los conflictos sin resolver.

## Estado vigente e historia

El resumen de proyecto y los registros activos enlazados expresan el estado que se considera vigente. La historia de Git conserva versiones de archivos; las relaciones entre registros y las notas de cambio explican por qué una versión reemplazó o revisó otra. Un snapshot puede conservar un checkpoint fechado que merezca consulta, pero no se usa como cronología exhaustiva ni como fuente del estado actual.

No actualices todos los snapshots históricos para que parezcan reflejar el presente: conserva lo que describían en su fecha de corte. Si una corrección afecta la interpretación histórica, enlaza una nota de corrección o revisión sin alterar silenciosamente el contenido original; respeta además las reglas de privacidad, retención y retirada aplicables.

## Estados y enlaces

Los estados recomendados permiten distinguir el trabajo pendiente del conocimiento vigente:

- **active:** revisado y vigente para el alcance indicado;
- **needs-review:** hay un cambio o hallazgo que puede afectarlo, pero aún no se ha resuelto;
- **disputed:** existe evidencia o interpretación en conflicto;
- **superseded:** otro registro lo sustituye para el alcance o periodo indicado;
- **unverified:** no se ha encontrado respaldo suficiente.

Cuando sea pertinente, registra enlaces como `reviews`, `corrects`, `supersedes` o `depends on`. Incluye fecha, motivo, fuente y localizador de la corrección. Los nombres exactos de campos pueden adaptarse a la implementación; la relación debe poder entenderse y consultarse.

## Automatización y control

Una herramienta puede detectar enlaces entrantes y proponer una lista de revisión. No debe borrar fuentes, cambiar decisiones ni marcar toda la cadena como corregida automáticamente. La persona responsable revisa los efectos y acepta las actualizaciones según el contexto.

Si una dependencia no puede localizarse, no afirmes que la corrección se propagó por toda la base. Identifica los registros revisados y deja constancia de que la búsqueda pudo ser incompleta.

-------------------------------------
