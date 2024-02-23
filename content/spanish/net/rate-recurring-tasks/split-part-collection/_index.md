---
title: Recopile MS Project de piezas divididas en Aspose.Tasks
linktitle: Colección de partes divididas en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a recopilar partes divididas en MS Project usando Aspose.Tasks para .NET. Este completo tutorial le guiará paso a paso a través del proceso.
type: docs
weight: 19
url: /es/net/rate-recurring-tasks/split-part-collection/
---
## Introducción
En este tutorial, profundizaremos en cómo recopilar partes divididas en MS Project usando Aspose.Tasks para .NET. Dividir tareas en partes puede ser un aspecto crucial de la gestión de proyectos y Aspose.Tasks proporciona métodos convenientes para manejar esto de manera eficiente.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Instalación de Aspose.Tasks para .NET: asegúrese de haber instalado Aspose.Tasks para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Conocimiento básico de C#: la familiaridad con el lenguaje de programación C# será beneficiosa ya que escribiremos fragmentos de código en C#.

## Importar espacios de nombres
En su proyecto C#, incluya los espacios de nombres necesarios:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Paso 1: configura tu proyecto
Primero, cree un nuevo proyecto en su IDE preferido y asegúrese de que se haga referencia correctamente a Aspose.Tasks para .NET.
## Paso 2: Inicializar el objeto del proyecto
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inicialice un nuevo objeto de Proyecto con la ruta a su archivo de MS Project.
## Paso 3: recuperar la tarea e iterar sobre partes divididas
```csharp
var task = project.RootTask.Children.GetById(1);
// Iterar sobre partes divididas
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Recupere la tarea del proyecto e itere sobre sus partes divididas, imprimiendo sus fechas de inicio y finalización.
## Paso 4: Divida la parte por índice
```csharp
// Obtener la pieza por índice
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Recupere una pieza dividida específica por índice e imprima su fecha de inicio.

## Conclusión
La gestión de partes divididas en archivos de MS Project puede mejorar significativamente la eficiencia de la gestión de proyectos. Aspose.Tasks para .NET simplifica este proceso al proporcionar API intuitivas para manejar tareas divididas sin problemas.
## Preguntas frecuentes
### P: ¿Puedo dividir tareas dinámicamente durante el tiempo de ejecución?
R: Sí, puede dividir tareas mediante programación usando Aspose.Tasks para .NET.
### P: ¿Aspose.Tasks admite todas las versiones de archivos de MS Project?
R: Aspose.Tasks admite varias versiones de archivos de MS Project, lo que garantiza la compatibilidad entre diferentes plataformas.
### P: ¿Existe una versión de prueba disponible para realizar pruebas?
 R: Sí, puede obtener una versión de prueba gratuita en[aquí](https://releases.aspose.com/) Para evaluar.
### P: ¿Cómo puedo obtener licencias temporales para mis proyectos?
 R: Las licencias temporales se pueden adquirir en[aquí](https://purchase.aspose.com/temporary-license/) para uso a corto plazo.
### P: ¿Dónde puedo buscar ayuda o soporte con respecto a Aspose.Tasks?
 R: Puedes visitar el foro de Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15) buscar ayuda de la comunidad o del equipo de soporte de Aspose.