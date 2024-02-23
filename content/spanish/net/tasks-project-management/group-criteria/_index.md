---
title: Manipulación de los criterios del grupo de proyectos de MS en Aspose.Tasks
linktitle: Criterios de grupo en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Explore cómo manipular archivos de MS Project mediante programación en .NET usando Aspose.Tasks. Recuperar ejemplos paso a paso de información de criterios y grupos de tareas.
type: docs
weight: 27
url: /es/net/tasks-project-management/group-criteria/
---
## Introducción
Aspose.Tasks para .NET es una potente API que facilita el trabajo con archivos de Microsoft Project en sus aplicaciones .NET. Ya sea que esté desarrollando software de gestión de proyectos o necesite manipular datos del proyecto mediante programación, Aspose.Tasks ofrece un conjunto completo de funciones para satisfacer sus necesidades.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
### 1. Conocimiento de C# y .NET Framework
La familiaridad con el lenguaje de programación C# y .NET Framework es esencial para comprender e implementar los ejemplos proporcionados en este tutorial.
### 2. Instalación de Aspose.Tasks para .NET
 Asegúrese de tener Aspose.Tasks para .NET instalado en su entorno de desarrollo. Puedes descargar la biblioteca desde[aquí](https://releases.aspose.com/tasks/net/) y siga las instrucciones de instalación proporcionadas.
### 3. Entorno de desarrollo integrado (IDE)
Tenga un IDE como Visual Studio instalado en su sistema para escribir y ejecutar código C#.

## Importar espacios de nombres
Para comenzar, importe los espacios de nombres necesarios en su código C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Paso 1: cargue un archivo de Microsoft Project
Primero, especifique la ruta a su archivo de Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 reemplazar`"Your Document Directory"` con la ruta al archivo de su proyecto.
## Paso 2: recuperar información de grupos de tareas
A continuación, recupere información sobre los grupos de tareas del proyecto:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Este fragmento de código imprime el recuento total de grupos de tareas, recupera el segundo grupo de tareas, su nombre y el recuento de criterios que contiene.
## Paso 3: recuperar la información de criterios del grupo de trabajo
Ahora, profundicemos en los detalles de un criterio específico dentro del grupo de tareas:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Este segmento muestra varias propiedades del criterio, como su índice, campo, información de agrupación, color de celda, color de fuente, intervalo de grupo y punto de partida.
## Paso 4: recuperar la información de fuente de Criterion
Por último, obtenga detalles del criterio relacionados con la fuente:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Este paso imprime el nombre de la fuente, el tamaño, el estilo y si el criterio está ordenado en orden ascendente o descendente.

## Conclusión
En este tutorial, exploramos cómo usar Aspose.Tasks para .NET para recuperar información sobre grupos de tareas y criterios de un archivo de Microsoft Project. Si sigue la guía paso a paso, podrá trabajar de manera eficiente con los datos del proyecto mediante programación en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puede Aspose.Tasks manejar archivos grandes de Microsoft Project?
Aspose.Tasks está optimizado para manejar archivos de proyectos grandes de manera eficiente, garantizando un alto rendimiento y confiabilidad.
### ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?
Sí, Aspose.Tasks admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad entre diferentes formatos de archivo.
### ¿Puedo manipular datos del proyecto usando Aspose.Tasks?
Por supuesto, Aspose.Tasks proporciona amplias funcionalidades para manipular los datos del proyecto, incluidas tareas, recursos, calendarios y más.
### ¿Aspose.Tasks ofrece soporte para diferentes plataformas .NET?
Sí, Aspose.Tasks admite múltiples plataformas .NET, incluidas .NET Framework, .NET Core y .NET Standard.
### ¿Existe un foro comunitario para Aspose.Tasks donde pueda buscar ayuda?
 Sí, puedes visitar el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para hacer preguntas, compartir conocimientos y colaborar con otros usuarios.