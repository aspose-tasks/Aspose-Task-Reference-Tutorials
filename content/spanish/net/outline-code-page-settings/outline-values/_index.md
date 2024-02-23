---
title: Dominar los valores del esquema de MS Project con Aspose.Tasks
linktitle: Gestión de valores de esquema en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar los valores de esquema de MS Project de manera eficiente usando Aspose.Tasks para .NET. Personalice los esquemas del proyecto con facilidad.
type: docs
weight: 16
url: /es/net/outline-code-page-settings/outline-values/
---
## Introducción
En este tutorial, exploraremos cómo administrar los valores de esquema de Microsoft Project utilizando la biblioteca Aspose.Tasks para .NET. Con Aspose.Tasks, puede manipular fácilmente códigos de esquema, crear nuevos valores de esquema y personalizar esquemas de proyecto según sus requisitos.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1.  Instalación de Aspose.Tasks para .NET: Descargue e instale la biblioteca Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/tasks/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo, como Visual Studio, con compatibilidad con .NET Framework.
3. Comprensión básica de la programación C#: familiarícese con los conceptos básicos del lenguaje de programación C#, ya que usaremos C# para trabajar con la biblioteca Aspose.Tasks.

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su código C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Paso 1: cargue el archivo del proyecto
```csharp
// La ruta al directorio de documentos.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Este paso inicializa un nuevo objeto de Proyecto y carga el archivo de Microsoft Project desde el directorio especificado.
## Paso 2: Definir las definiciones del código de esquema
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Aquí, definimos dos objetos OutlineCodeDefinition y los agregamos a la colección OutlineCodes del proyecto.
## Paso 3: definir la máscara de contorno
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
Este paso configura una OutlineMask para la definición del código de esquema.
## Paso 4: crear valores de esquema
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
En este paso, creamos dos objetos OutlineValue y configuramos sus propiedades, como valor, ID de valor, tipo, descripción y estado de colapso.

## Conclusión
Administrar los valores del esquema de MS Project usando Aspose.Tasks para .NET es sencillo con las funcionalidades proporcionadas. Si sigue los pasos descritos en este tutorial, podrá manipular de manera eficiente los códigos y valores de los esquemas para personalizar los esquemas del proyecto según sus necesidades.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks con otros frameworks .NET?
R: Sí, Aspose.Tasks es compatible con varios marcos .NET, lo que garantiza flexibilidad en su entorno de desarrollo.
### P: ¿Existe una versión de prueba disponible para Aspose.Tasks?
 R: Sí, puede acceder a una versión de prueba gratuita de Aspose.Tasks desde[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks?
 R: Para obtener soporte y asistencia, puede visitar el foro Aspose.Tasks.[aquí](https://forum.aspose.com/c/tasks/15).
### P: ¿Puedo comprar una licencia temporal para Aspose.Tasks?
 R: Sí, puede comprar una licencia temporal para Aspose.Tasks en[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Dónde puedo encontrar documentación detallada para Aspose.Tasks?
 R: Puede consultar la documentación completa disponible[aquí](https://reference.aspose.com/tasks/net/).