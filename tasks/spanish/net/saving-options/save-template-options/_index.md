---
title: Guarde archivos de MS Project como plantillas con Aspose.Tasks
linktitle: Guardar opciones de plantilla para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar archivos de Microsoft Project como plantillas usando Aspose.Tasks para .NET. Personalice la configuración de la plantilla para una gestión de proyectos optimizada.
weight: 18
url: /es/net/saving-options/save-template-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guarde archivos de MS Project como plantillas con Aspose.Tasks

## Introducción
En este tutorial, recorreremos el proceso de guardar una plantilla usando Aspose.Tasks para .NET. Las plantillas son útiles para estandarizar las estructuras y configuraciones del proyecto para uso futuro. Demostraremos cómo guardar un proyecto como plantilla y ajustaremos sus propiedades a lo largo del camino.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Aspose.Tasks para la biblioteca .NET: asegúrese de tener instalada la biblioteca Aspose.Tasks para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
2. Conocimiento de programación C#: se requieren conocimientos básicos de programación C# para comprender e implementar los fragmentos de código proporcionados.
3. Archivo de Microsoft Project: tenga listo un archivo de Microsoft Project (formato MPP) que desee guardar como plantilla.

## Importar espacios de nombres
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Paso 1: cargar proyecto
Primero, necesitamos cargar el archivo de Microsoft Project (.mpp) que queremos guardar como plantilla.
```csharp
// La ruta al directorio de documentos.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Paso 2: obtener información del archivo del proyecto
Recupere información sobre el archivo del proyecto cargado, como su formato.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Paso 3: configurar las opciones para guardar plantilla
Cree opciones para guardar plantillas y configure sus propiedades según sus requisitos. Estas opciones le permiten personalizar qué datos deben eliminarse de la plantilla.
```csharp
var options = new SaveTemplateOptions
{
	// Eliminar todos los costos fijos de la plantilla del proyecto
	RemoveFixedCosts = true,
	// Eliminar todos los valores reales de la plantilla del proyecto
	RemoveActualValues = true,
	// Eliminar tarifas de recursos de la plantilla del proyecto
	RemoveResourceRates = true,
	// Eliminar todos los valores de referencia de la plantilla del proyecto
	RemoveBaselineValues = true
};
```
## Paso 4: guardar el proyecto como plantilla
Guarde el proyecto como una plantilla con las opciones especificadas.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Paso 5: Obtener información del archivo de plantilla
Recupere información sobre el archivo de plantilla guardado, como su formato.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
¡Felicidades! Ha guardado exitosamente una plantilla usando Aspose.Tasks para .NET, personalizando sus propiedades según sea necesario.

## Conclusión
En este tutorial, exploramos cómo guardar un archivo de Microsoft Project como plantilla usando Aspose.Tasks para .NET. Las plantillas son valiosas para estandarizar las estructuras y configuraciones de los proyectos, agilizando las creaciones futuras de proyectos.
## Preguntas frecuentes
### P: ¿Puedo personalizar qué datos eliminar de la plantilla?
R: Sí, puede configurar las opciones de Guardar plantilla para eliminar datos específicos como costos fijos, valores reales, tasas de recursos y valores de referencia.
### P: ¿Aspose.Tasks para .NET es compatible con todas las versiones de Microsoft Project?
R: Aspose.Tasks para .NET proporciona una amplia compatibilidad con varias versiones de Microsoft Project, lo que garantiza una integración y funcionalidad perfectas.
### P: ¿Puedo aplicar plantillas a proyectos existentes?
R: Sí, puede aplicar plantillas a proyectos existentes cargando el archivo de plantilla y combinándolo con su proyecto actual según sea necesario.
### P: ¿Aspose.Tasks para .NET admite el desarrollo multiplataforma?
R: Aspose.Tasks para .NET está diseñado principalmente para aplicaciones de .NET framework que se ejecutan en plataformas Windows.
### P: ¿Hay soporte técnico disponible para Aspose.Tasks para .NET?
 R: Sí, puede buscar asistencia técnica y orientación de la comunidad Aspose.Tasks[foros](https://forum.aspose.com/c/tasks/15) comuníquese con su equipo de soporte directamente.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
