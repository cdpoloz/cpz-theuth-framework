<!-- English section first; Spanish section follows. -->

-------------------------------------

# Evaluation case 02: reasons for a decision and supporting evidence

This case checks whether an implementation can explain a decision, trace its reasons back to evidence, and make provenance limitations visible. It also checks whether it detects discrepancies between a decision’s status and the status of the evidence supporting it. It is a manual test, not an automated benchmark.

## Query

> Why was the hybrid methodological approach adopted for Theuth, and what evidence supports that decision?

## Reference corpus

Run the case against the repository at commit \`69ef30e1bb985b34ba87035fceb2d07858f141cf\`. This ref pins the corpus for repeating the query if \`main\` changes and includes the anonymized version of the source record.

Entry point and records to follow:

- [Methodological decision](../theuth/decisions/2026-09-23-methodological-foundation.md)
- [Acceptance claim](../theuth/claims/2026-09-23-hybrid-approach.md)
- [Anonymized exchange record](../theuth/sources/2026-09-23-methodological-design-discussion.md)

For methodological context, consult the [retrieval walkthrough](../../methodology/retrieval.md) and the [correction and revision workflow](../../methodology/correction-and-revision.md).

## Expected answer

A satisfactory answer should express, in equivalent terms:

- The decision record says the goal was to preserve useful knowledge and resume work without rereading entire conversations.
- The decision lists explicit provenance, compact snapshots, atomic decisions, progressive retrieval, and Git with text files as components of the approach.
- The record presents an unstructured collection of notes without provenance or retrieval as insufficient, and postpones implementing an application until after defining the methodology.
- **Evidentiary limit:** the conversation record says its coverage is reconstructed; the original export and full transcript are not in the repository. The record is a paraphrase, not complete textual evidence. The derived claim is also marked \`needs-review\` and lists no independent sources.
- **Status discrepancy:** the decision record is marked \`active\`, while the supporting claim and source are marked \`needs-review\`. The answer should flag this discrepancy for review without resolving it or changing the status on its own.
- Therefore, the answer may report the reasons and components documented in the example records, attributing them to those records, but it cannot claim that the exact wording has been verified or that all original evidence is available.

## Stages the answer should make visible

1. **Scope:** identify that the query asks about the reasoning for a specific decision and its support.
2. **Locate:** open the decision record first and follow its links.
3. **Check status:** inspect the status of the decision, claim, and source; report the difference between \`active\` and \`needs-review\`.
4. **Trace provenance:** reach the conversation record and review its locator and limitations.
5. **Answer with limits:** separate what the record states from what can be verified in the original; do not invent turns or quotations.

The interface may summarize the stages, but it should be clear that the provenance chain was reviewed and which part could not be checked.

## Evaluation criteria

Score each criterion as achieved / partial / not achieved:

- Retrieves documented reasons without adding absent motives.
- Distinguishes the decision’s components from its reasons.
- Follows the decision → claim → source relationship.
- States that the source is reconstructed and the original is not archived.
- Detects the status discrepancy between the decision and its supporting records.
- Carefully attributes what appears only in the synthesis and does not invent textual evidence.

**Case passes:** stating that the original source is missing, detecting the status discrepancy, and not inventing evidence are critical. All three must be achieved, along with at least five of the six criteria.

## Critical errors

- Quoting the original conversation or inventing turn IDs, excerpts, or motives.
- Presenting the paraphrase as independent verification of the claim.
- Treating the decision’s \`active\` status as sufficient proof that its sources have been reviewed.
- Automatically changing the decision’s status or ignoring the discrepancy.

## Case maintenance

The corpus is pinned to the commit above. If it is adapted to a later version, update the ref, verify the provenance chain, and recheck the expected statuses and criteria. Adding an original transcript later would deliberately change the expected result.

-------------------------------------

# Caso de evaluación 02: razones de una decisión y respaldo

Este caso comprueba si una implementación puede explicar una decisión, rastrear sus razones hasta la evidencia y hacer visibles las limitaciones de procedencia. También comprueba si detecta discrepancias entre el estado de una decisión y el estado de la evidencia que la sustenta. Es una prueba manual, no un benchmark automatizado.

## Consulta

> ¿Por qué se adoptó el enfoque metodológico híbrido para Theuth y qué evidencia respalda esa decisión?

## Corpus de referencia

Ejecutar el caso contra el repositorio en el commit `69ef30e1bb985b34ba87035fceb2d07858f141cf`. Este ref fija el corpus para repetir la consulta aunque `main` cambie e incluye la versión anonimizada de la ficha de fuente.

Punto de entrada y registros a seguir:

- [Decisión metodológica](../theuth/decisions/2026-09-23-methodological-foundation.md)
- [Afirmación de aceptación](../theuth/claims/2026-09-23-hybrid-approach.md)
- [Ficha anonimizada del intercambio](../theuth/sources/2026-09-23-methodological-design-discussion.md)

Como contexto de método, puede consultarse el [recorrido de recuperación](../../methodology/retrieval.md) y el [flujo de corrección y revisión](../../methodology/correction-and-revision.md).

## Respuesta esperada

Una respuesta satisfactoria debería expresar, en términos equivalentes:

- El registro de decisión dice que se buscaba conservar conocimiento útil y poder retomarlo sin tener que releer conversaciones completas.
- La decisión enumera procedencia explícita, snapshots compactos, decisiones atómicas, recuperación progresiva y Git con archivos de texto como componentes del enfoque.
- El registro presenta como alternativa insuficiente una colección de notas sin procedencia ni recuperación, y como opción pospuesta implementar una aplicación antes de definir la metodología.
- **Límite probatorio:** la ficha de conversación declara que su cobertura es reconstruida; el original exportado y la transcripción completa no están en el repositorio. La ficha es una paráfrasis, no evidencia textual completa. La afirmación derivada también está marcada `needs-review` y no registra fuentes independientes.
- **Discrepancia de estado:** el registro de decisión aparece como `active`, mientras que la afirmación y la fuente que lo respaldan aparecen como `needs-review`. La respuesta debe señalar que esta discrepancia necesita revisión, sin resolverla ni cambiar el estado por su cuenta.
- Por tanto, se puede informar qué razones y componentes constan en los registros de ejemplo, atribuyéndolos a esos registros, pero no afirmar que se ha verificado la formulación exacta o que se dispone de toda la evidencia original.

## Etapas que debe hacer visibles la respuesta

1. **Delimitar:** identificar que se pregunta por el razonamiento de una decisión específica y su respaldo.
2. **Localizar:** abrir primero el registro de decisión y seguir sus enlaces.
3. **Comprobar estado:** observar los estados de decisión, afirmación y fuente; reportar la diferencia entre `active` y `needs-review`.
4. **Seguir procedencia:** llegar a la ficha de conversación y revisar cobertura, localizador y limitaciones.
5. **Responder con límites:** separar lo que el registro afirma de lo que puede verificarse en el original; no inventar turnos ni citas.

La interfaz puede resumir las etapas, pero debe quedar claro que se revisó la cadena de procedencia y qué parte no pudo comprobarse.

## Criterios de evaluación

Puntuar cada criterio como logrado / parcial / no logrado:

- Recupera las razones documentadas sin añadir motivos ausentes.
- Distingue los componentes de la decisión de sus razones.
- Sigue la relación decisión → afirmación → fuente.
- Expone que la fuente es reconstruida y el original no está archivado.
- Detecta la discrepancia de estados entre la decisión y sus registros de respaldo.
- Atribuye con cautela lo que solo consta en la síntesis y no inventa evidencia textual.

**Aprobación del caso:** son críticos exponer la falta de fuente original, detectar la discrepancia de estados y no inventar evidencia. Los tres deben lograrse, además de al menos cinco de los seis criterios.

## Errores críticos

- Citar como textual la conversación original o inventar IDs de turno, fragmentos o motivos.
- Presentar la paráfrasis como verificación independiente de la afirmación.
- Tratar el estado `active` de la decisión como prueba suficiente de que sus fuentes están revisadas.
- Cambiar automáticamente el estado de la decisión o ignorar la discrepancia.

## Mantenimiento del caso

El corpus está fijado al commit indicado. Si se adapta a una versión posterior, actualiza el ref, verifica la cadena de procedencia y vuelve a revisar los estados y criterios esperados. Una transcripción original incorporada posteriormente cambiaría deliberadamente el resultado esperado.

-------------------------------------
