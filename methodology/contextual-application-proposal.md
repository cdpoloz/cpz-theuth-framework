<!-- English section first; Spanish section follows. -->

-------------------------------------

# Proposal: contextual application and validated reuse

**Status:** methodological evolution proposed for evaluation (2026-10-16). This document does not announce a new release or prove effectiveness.

## Problem

Retrieval can correctly trace a claim to an original source and confirm its historical status while still failing to establish that the claim is suitable for a different situation. Evidence of provenance, evidence of contextual fit, and evidence of a successful outcome are separate matters.

## Proposed guidance

For a recommendation, decision, or consequential action based on retrieved knowledge:

1. **Identify intended use.** Specify the decision or action, its constraints, stakes, and who is authorized to approve it.
2. **Check source and status.** Use the existing [retrieval workflow](retrieval.md) for provenance, currency, contradictions, and uncertainty.
3. **Assess transferability.** Compare the original scope, assumptions, environment, dependencies, tested conditions, and known limits with the proposed context. Mark unexamined dimensions as unknown rather than assuming equivalence.
4. **Verify proportionately.** Choose independent checks appropriate to the stakes: a current source, measurement, small test, domain expert, or safety review. A successful check in one context does not certify all contexts.
5. **Surface a clear result.** Distinguish supported / applicable within stated constraints / unverified or unsuitable; describe missing checks and consequences. Require responsible human authorization for consequential actions.
6. **Capture learning when useful.** If a test reveals an error, new limit, or transferable lesson, preserve evidence, update only affected records, and link dependencies according to [correction and revision](correction-and-revision.md). Do not turn a passing artifact or an LLM conclusion into independent evidence without an identifiable test or source.

These are advisory, risk-sensitive steps, not required fields or a universal automated gate. A historical factual question may end at retrieval; a safety-critical design cannot be approved merely because a prior source is well documented.

## Reusable knowledge

A design, procedure, configuration, or component may be a reusable **artifact**. Its claims of suitability must remain linked to the conditions and evidence under which it was validated. An implementation may maintain a library, but no `library/` folder or new canonical record type is required. Use existing sources, claims, decisions, and project records where sufficient.

For multiple contributors or agents, an implementation may also document who provided inputs, what changed, which checks were performed, what dependent records could be affected, and who approved the update. This is optional coordination guidance; it does not give agents autonomous authority to change decisions.

## Evaluation case to try

**Scenario:** a documented PLA fixture worked on a desk at room temperature; a new project proposes using the same fixture in a hot vehicle.

- **Retrieval:** locate the prior design, outcome, materials, and test conditions.
- **Application:** do not infer heat resistance from the earlier success; identify the changed operating environment.
- **Verification:** seek appropriate material data and a relevant test or expert review before recommending use.
- **Expected response:** state that prior evidence supports the desk use only, identify the unverified thermal requirement, and propose verification without claiming the new fixture is safe.
- **Failure:** treating a traceable success record as proof of suitability in the hot environment.

Compare systems with and without this step by measuring unsupported transfers, correctly identified limitations, unnecessary blocking, and quality of evidence links. This proposal remains open until evaluated.

## Relationship to related work

Greg Isenberg's [*VIBE MANUFACTURING IS HERE*](https://x.com/i/article/2106728342569250816) (October 4, 2026; [Spanish adaptation](https://crearsoftware.com/blog/la-fabricacion-vibe-ya-esta-aqui/)) illustrates requirements files, manufacturing constraints, reuse libraries, tests, and build logs in a commercially oriented agentic manufacturing workflow. It motivates the application problem but is not a formal Theuth specification or independently validated academic methodology. Theuth deliberately does not adopt manufacturing-specific folders, agents, or commercial objectives.

-------------------------------------

# Propuesta: aplicación contextual y reutilización validada

**Estado:** evolución metodológica propuesta para evaluación (2026-10-16). Este documento no anuncia una nueva versión ni demuestra eficacia.

## Problema

Una recuperación puede vincular correctamente una afirmación con su fuente original y confirmar su estado histórico sin demostrar que resulte adecuada para otra situación. La evidencia de procedencia, la de adecuación contextual y la de un resultado satisfactorio son cuestiones distintas.

## Orientación propuesta

Para una recomendación, decisión o acción con consecuencias basada en conocimiento recuperado:

1. **Identificar el uso previsto.** Precisar la decisión o acción, restricciones, riesgos y quién tiene autoridad para aprobarla.
2. **Comprobar fuente y estado.** Utilizar el [flujo de recuperación](retrieval.md) para procedencia, vigencia, contradicciones e incertidumbre.
3. **Evaluar transferibilidad.** Comparar alcance, supuestos, entorno, dependencias, condiciones probadas y límites conocidos del caso original con el contexto propuesto. Marcar como desconocido lo que no se haya examinado, sin asumir equivalencias.
4. **Verificar de forma proporcional.** Elegir comprobaciones independientes acordes con las consecuencias: fuente actual, medición, ensayo, especialista o revisión de seguridad. Una prueba exitosa en un contexto no certifica todos los demás.
5. **Comunicar el resultado con claridad.** Distinguir respaldado / aplicable bajo restricciones declaradas / no verificado o inadecuado; explicar las comprobaciones pendientes y sus consecuencias. Las acciones relevantes requieren autorización humana responsable.
6. **Conservar aprendizajes cuando aporte valor.** Si la prueba descubre un error, un límite nuevo o una lección transferible, conservar la evidencia, actualizar solo los registros afectados y enlazar dependencias siguiendo [corrección y revisión](correction-and-revision.md). No convertir un artefacto que superó una prueba ni una conclusión de un LLM en evidencia independiente sin ensayo o fuente identificables.

Son pasos orientativos y sensibles al riesgo, no campos obligatorios ni un control automatizado universal. Una consulta factual histórica puede terminar en la recuperación; un diseño crítico para la seguridad no queda aprobado por estar bien documentado.

## Conocimiento reutilizable

Un diseño, procedimiento, configuración o componente puede ser un **artefacto** reutilizable. Sus afirmaciones de idoneidad deben mantenerse vinculadas a las condiciones y evidencias con las que se validó. Una implementación puede disponer de una biblioteca, pero no se exige una carpeta `library/` ni un nuevo tipo de registro canónico. Se utilizan fuentes, afirmaciones, decisiones y registros de proyecto existentes cuando basten.

Cuando colaboren varias personas o agentes, una implementación también puede documentar quién aportó entradas, qué cambió, qué comprobaciones se hicieron, qué registros dependientes podrían verse afectados y quién aprobó la actualización. Es una guía opcional de coordinación; no concede a los agentes autoridad autónoma para cambiar decisiones.

## Caso de evaluación propuesto

**Escenario:** un soporte de PLA documentado funcionó sobre un escritorio a temperatura ambiente; otro proyecto plantea usarlo dentro de un vehículo caliente.

- **Recuperación:** localizar el diseño anterior, resultado, materiales y condiciones de ensayo.
- **Aplicación:** no inferir resistencia térmica del éxito anterior; identificar el cambio de entorno.
- **Verificación:** consultar datos de materiales y realizar una prueba pertinente o revisión experta antes de recomendarlo.
- **Respuesta esperada:** indicar que la evidencia anterior solo respalda el uso en escritorio, identificar el requisito térmico no verificado y proponer la comprobación sin asegurar que el nuevo soporte sea seguro.
- **Fallo:** tratar un éxito trazable como demostración de idoneidad en un entorno caliente.

Comparar sistemas con y sin este paso midiendo transferencias sin respaldo, limitaciones correctamente detectadas, bloqueos innecesarios y calidad de los enlaces a evidencia. La propuesta permanecerá abierta hasta su evaluación.

## Relación con otros trabajos

El artículo [*VIBE MANUFACTURING IS HERE*, de Greg Isenberg](https://x.com/i/article/2106728342569250816) (4 de octubre de 2026; [adaptación en español](https://crearsoftware.com/blog/la-fabricacion-vibe-ya-esta-aqui/)) describe archivos de requisitos, restricciones de fabricación, bibliotecas reutilizables, pruebas e historial en un flujo de fabricación con agentes y orientación comercial. Motiva el problema de aplicación, pero no constituye una especificación formal de Theuth ni una metodología académica validada independientemente. Theuth no adopta carpetas, agentes ni objetivos comerciales específicos de fabricación.

-------------------------------------
