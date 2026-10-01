# Tarea: Mi prompt avanzado

## Tarea elegida

Generación e identificación de casos de prueba unitarios e integración para un módulo de autenticación y registro de usuarios en un sistema web

## Version 1: prompt basico

```text
Escribe casos de prueba para un sistema de registro de usuarios.
```

## Version 2

```text
Actúa como un QA Automation Lead especializado en seguridad web. 

Diseña una suite de casos de prueba detallada para un formulario de registro de usuarios con los siguientes campos: Nombre, Correo Electrónico y Contraseña. 

Organiza los casos de prueba por categorías (Casos Positivos, Casos Negativos y Seguridad/Borde). Para cada caso de prueba, indica: ID, Nombre, Pasos, Datos de Entrada y Resultado Esperado.
```

## Version 3: prompt final

```text
[ROL Y CONTEXTO]
Actúa como un Principal QA Engineer experto en pruebas de seguridad (OWASP) y backend. Tu objetivo es diseñar la suite de pruebas exhaustiva para la API de Registro de Usuarios.

[RESTRICCIONES Y FORMATO]
Devuelve la respuesta en formato de tabla Markdown con las columnas: | ID | Categoría | Escenario | Datos de Entrada | Pasos | Resultado Esperado |.

[TÉCNICA FEW-SHOT / EJEMPLO]
Sigue este formato de ejemplo para estructurar los casos:
| ID | Categoría | Escenario | Datos de Entrada | Pasos | Resultado Esperado |
| TC-01 | Positivo | Registro exitoso | {email: "user@test.com", pass: "P@ss1234"} | 1. POST /api/register con payload JSON.<br>2. Verificar HTTP status. | HTTP 201 Created y token JWT generado. |

[DESCOMPOSICIÓN Y PASO A PASO (CHAIN OF THOUGHT)]
Antes de generar la tabla, realiza un análisis interno paso a paso:
1. Analiza las reglas del negocio para correo (formato, duplicados) y contraseña (longitud, caracteres especiales).
2. Identifica los riesgos OWASP aplicables (XSS, inyección SQL, bypass de validación).
3. Descompón los escenarios en Positivos, Negativos y de Seguridad.
4. Genera la tabla final con los casos deducidos.

[AUTOCRÍTICA]
Al finalizar la tabla, agrega una sección llamada "Revisión de Cobertura" donde autoevalúes si omitiste algún escenario de límite (boundary values) o caso extremo y justifica su inclusión o descarte.
```

## Tecnicas usadas en el prompt final

| Técnica usada | Parte del Prompt Final correspondiente |
|---------|-------------------------------|
| Role Prompting |Actúa como un Principal QA Engineer experto en pruebas de seguridad (OWASP)... |
| Prompt Estructurado |[ROL Y CONTEXTO], [RESTRICCIONES Y FORMATO] y la indicación de tabla Markdown. |
| Few-Shot Prompting |[TÉCNICA FEW-SHOT / EJEMPLO] con la tabla de ejemplo de TC-01 |
|Chain of Thought / Descomposición |[DESCOMPOSICIÓN Y PASO A PASO (CHAIN OF THOUGHT)] con el proceso analítico del 1 al 4|
|Autocrítica |[AUTOCRÍTICA] pidiendo la sección "Revisión de Cobertura".|

## Evaluacion del resultado

| Criterio de Evaluación | Cumple (Sí / No) |
|---------|-------------------------------|
| ¿El rol definido influyó en la precisión técnica? |si |
| ¿El formato de respuesta se mantuvo estricto al ejemplo? |si|
| ¿El formato de respuesta se mantuvo estricto al ejemplo? |si|
| ¿La autocrítica identificó áreas de mejora relevantes? |si|
|¿Hay algún caso repetido o que no tenga sentido? |si|

## Por que elegi estas tecnicas

Elegí Role Prompting, Few-Shot, Chain of Thought, Prompt Estructurado y Autocrítica porque el diseño de casos de prueba de software requiere tanto precisión analítica como un formato estricto. La combinación de Chain of Thought y Descomposición asegura que el modelo no salte directo a la respuesta omitiendo escenarios de seguridad críticos o valores límite. Asimismo, el patrón Few-Shot junto al Prompt Estructurado garantiza que la salida sea legible y reutilizable directamente en herramientas de gestión de QA como Jira o TestRail. No utilicé técnicas como la generación creativa de texto sin restricciones porque en QA la ambigüedad genera errores en producción.

