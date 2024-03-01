---
title: Administre los valores del esquema del proyecto MS con Aspose.Tasks
linktitle: Colección de valores de esquema en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar valores de esquema en archivos de Microsoft Project usando Aspose.Tasks para .NET. Tutorial paso a paso con ejemplos de código.
type: docs
weight: 17
url: /es/net/outline-code-page-settings/outline-value-collection/
---
## Introducción
Aspose.Tasks para .NET proporciona un conjunto completo de funciones para interactuar con archivos de Microsoft Project. Una de esas características es la capacidad de gestionar valores de esquema dentro de un proyecto. En este tutorial, exploraremos cómo recopilar y manipular valores de esquema usando Aspose.Tasks para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Aspose.Tasks para .NET: puede descargar la biblioteca desde[aquí](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: asegúrese de tener instalado un IDE adecuado, como Visual Studio.
3. Conocimientos básicos de C#: será beneficiosa la familiaridad con el lenguaje de programación C#.
## Importar espacios de nombres
En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos de Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Dividamos el ejemplo proporcionado en varios pasos:
## Paso 1: cargar un archivo de proyecto
 En primer lugar, inicialice un`Project` objeto cargando un archivo de Microsoft Project existente:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Paso 2: borrar los valores de esquema existentes
A continuación, borre los valores de esquema existentes del proyecto:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Paso 3: definir un nuevo código de esquema
Ahora, defina un nuevo código de esquema con una descripción y un valor:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Paso 4: actualizar el valor del esquema
Actualice el valor del código de esquema:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Paso 5: iterar sobre los valores del esquema
Repita los valores del esquema e imprima sus detalles:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Paso 6: manipular los valores del esquema
Realice operaciones como eliminar, insertar y copiar valores de esquema según sea necesario:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Conclusión
En este tutorial, aprendimos cómo trabajar con valores de esquema en archivos de Microsoft Project usando Aspose.Tasks para .NET. Si sigue los pasos proporcionados, puede administrar de manera eficiente los valores del esquema dentro de sus proyectos, lo que permite un mayor control y flexibilidad.
## Preguntas frecuentes
### P: ¿Puedo manipular varios códigos de esquema simultáneamente?
R: Sí, puedes definir y manipular múltiples códigos de esquema dentro de un proyecto usando Aspose.Tasks.
### P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?
R: Sí, Aspose.Tasks admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP y XML.
### P: ¿Cómo puedo manejar los errores mientras trabajo con valores de esquema?
R: Puede implementar mecanismos de manejo de errores, como bloques try-catch, para administrar las excepciones de manera elegante.
### P: ¿Puedo personalizar la apariencia de los valores del esquema en mi proyecto?
R: Sí, Aspose.Tasks proporciona API completas para personalizar la apariencia y el comportamiento de los valores de esquema según sus requisitos.
### P: ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Tasks?
 R: Puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener apoyo de la comunidad y explorar[documentación](https://reference.aspose.com/tasks/net/) para obtener información detallada sobre API y funciones.