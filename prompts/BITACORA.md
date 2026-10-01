# Bitacora de tecnicas avanzadas

Laboratorio 07: Tecnicas Avanzadas de Prompting.
Herramienta de IA usada: (escribe aqui cual usaste)

## Ejercicio 2: Zero-shot, one-shot y few-shot

| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) |
|------|-----------------|-------------------------|------------------------------------|
| Zero-shot |positivo,negativo,neutral,negativo,positivo |en una tabla|si|
| One-shot |positivo,negativo,neutral,negativo,positivo |texto -> etiqueta |si |
| Few-shot |positivo,negativo,neutral,negativo,positivo |texto -> etiqueta|si |


## Ejercicio 3: Chain of Thought

| Pedido | Respuesta de la IA | Muestra los pasos (Si/No) | Correcta (Si/No) |
|--------|--------------------|---------------------------|------------------|
| Directo |318.60 |no|si |
| Paso a paso |318.60 |si|si |


## Ejercicio 4: Role prompting

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas |
|---------|-------------------------------|-----------------------|----------------------|
| A. Sin rol |sencillo|no|cualquier persona |
| B. Rol docente |sencillo|si|principiantes |
| C. Rol senior |tecnico|no|desarrolladores con experiencia |


## Ejercicio 5: Descomposicion

Paso 1 (Requisitos): Una lista resumida con los 5 requisitos principales (CRUD de productos, control de stock, registro de ventas, persistencia de datos y reportes básicos).

Paso 2 (Diseño de clases): El diseño conceptual de las clases de modelo (Producto, Categoria, Venta, DetalleVenta, MovimientoInventario), enumeraciones y servicios con sus atributos y tipos de datos.

Paso 3 (Código en Java): Un mensaje de disculpa/limitación donde la IA no pudo entregar el código Java solicitado para la clase Producto.

Paso 4 (Mejoras): Tres propuestas de mejora técnica concretas (validaciones en setters, métodos de dominio helper y sobrescritura de equals/hashCode/toString).

Al solicitar el sistema de una sola vez ("Crea un sistema de inventario para una tienda"), la IA entregó directamente en un solo mensaje la arquitectura de base de datos, los módulos funcionales, un script de código ejecutable completo en Python con SQLite y métodos de gestión operativa.

## Ejercicio 6: Prompt estructurado y autocritica


| Qué revisar | Cumple (Sí / No) |
|---------|-------------------------------|
| ¿Tiene las 4 columnas pedidas? |si |
| ¿Incluye el bloqueo después de 3 intentos?|si|
| ¿Incluye casos con campos vacíos? |si|
|¿Indica qué casos agregó en la autocrítica? |si|
|¿Hay algún caso repetido o que no tenga sentido? |no|

```text
<rol>Actua como analista de pruebas de software.</rol>
<contexto>Login web con correo y contrasena. La cuenta se bloquea
despues de 3 intentos fallidos.</contexto>
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea>
<formato>Tabla con las columnas: ID, escenario, datos de entrada,
resultado esperado.</formato>
```
