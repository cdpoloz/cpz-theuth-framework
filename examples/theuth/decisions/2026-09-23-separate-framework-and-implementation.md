<!-- English section first; Spanish section follows. -->

-------------------------------------

# Decision: separate the framework from its personal implementation

- **ID:** decision-2026-09-23-separate-framework-and-implementation
- **Status:** active
- **Date:** 2026-09-23
- **Project:** [Theuth](../project.md)

## Context

The project has two related goals: define a methodology that others can adapt and build a personal knowledge layer that puts it into practice.

## Decision

Keep the methodological framework in one repository and develop the personal implementation as a separate project. The current repository is \`cpz-theuth-framework\`; the final name of the implementation repository remains undecided.

## Reasons and evidence

The design conversation on 2026-09-23 established that the process for others to create their own system should be part of the methodology. Separating the projects keeps the rules and templates reusable without making them depend on a specific application, and allows the implementation to evolve according to personal needs.

## Alternatives considered

- Keep methodology and implementation in one repository: rejected as the initial direction to preserve the framework’s reusability.

## Consequences and conditions

The framework’s examples and templates should describe adaptable patterns. Personal decisions and data should live in the implementation, except for example records deliberately included to explain the method.

## Review

- Review if the framework begins to depend on a specific implementation or if maintaining two projects becomes an unnecessary burden.
- Replaced decision: none.

-------------------------------------

# Decisión: separar el framework de su implementación personal

- **ID:** decision-2026-09-23-separate-framework-and-implementation
- **Estado:** active
- **Fecha:** 2026-09-23
- **Proyecto:** [Theuth](../project.md)

## Contexto

El proyecto tiene dos objetivos relacionados: formular una metodología que otras personas puedan adaptar y construir una capa personal de conocimiento que la ponga en práctica.

## Decisión

Mantener el framework metodológico en un repositorio y desarrollar la implementación personal en otro proyecto separado. El repositorio actual es `cpz-theuth-framework`; el nombre definitivo del repositorio de implementación queda pendiente.

## Razones y evidencia

La conversación de diseño del 23-09-2026 estableció que el flujo para que otras personas creen su propio sistema debía formar parte de la metodología. Separar ambos proyectos permite que las reglas y plantillas sean reutilizables sin hacerlas depender de una aplicación concreta, y permite que la implementación evolucione con necesidades personales.

## Alternativas consideradas

- Mantener metodología e implementación en un solo repositorio: se descartó como dirección inicial para preservar la reutilización del framework.

## Consecuencias y condiciones

Los ejemplos y plantillas del framework deben describir patrones adaptables. Las decisiones personales y los datos propios deberían vivir en la implementación privada, salvo los registros de ejemplo que se incluyan deliberadamente para explicar el método.

## Revisión

- Revisar si el framework pasa a depender de una implementación concreta o si mantener dos proyectos genera una carga innecesaria.
- Decisión reemplazada: ninguna.

-------------------------------------
