---
title: MS Project con opciones de hoja de cálculo 2003 para Aspose.Tasks
linktitle: Opciones de guardado de hoja de cálculo 2003 para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Hoja de cálculo maestra 2003 Guarde las opciones de MS Project con Aspose.Tasks para .NET. Personalice y guarde sin problemas archivos de MS Project mediante programación.
weight: 19
url: /es/net/saving-options/spreadsheet-2003-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project con opciones de hoja de cálculo 2003 para Aspose.Tasks

## Introducción
En este tutorial, profundizaremos en cómo aprovechar Aspose.Tasks para .NET para utilizar las opciones de Guardar MS Project de Spreadsheet 2003. Esta poderosa herramienta permite la manipulación y personalización perfecta de archivos de MS Project en el entorno .NET. Analicemos el proceso paso a paso.
## Requisitos previos
Antes de embarcarnos en este tutorial, asegúrese de tener los siguientes requisitos previos:
1.  Instalación de Aspose.Tasks para .NET: Descargue e instale la biblioteca Aspose.Tasks para .NET desde[enlace de descarga](https://releases.aspose.com/tasks/net/).
2. Familiaridad con la programación C#: Es necesario un conocimiento básico del lenguaje de programación C# para comprender los conceptos tratados en este tutorial.

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su proyecto C#:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Estos espacios de nombres brindan acceso a las funcionalidades necesarias para guardar archivos de MS Project usando el formato de hoja de cálculo 2003 y personalizar las opciones de visualización.
## Paso 1: cargar el proyecto
En primer lugar, cargue el archivo de MS Project usando Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 Reemplazar`"Your Document Directory"`con la ruta del directorio real donde se encuentra su archivo de MS Project.
## Paso 2: definir opciones de guardar
 Defina las opciones de guardar de Spreadsheet 2003 creando una instancia de`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Paso 3: personalizar las columnas de vista
Personalice las columnas de vista para el diagrama de Gantt, la vista de Recursos y la vista de Asignaciones:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Estos pasos agregan columnas personalizadas a las vistas respectivas, mejorando las capacidades de visualización y análisis del archivo de MS Project.
## Paso 4: guarde el proyecto
Finalmente, guarde el proyecto con las opciones especificadas:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Este comando guarda el proyecto modificado con formato de hoja de cálculo 2003 y las columnas de vista personalizadas.

## Conclusión
El uso de Aspose.Tasks para .NET, específicamente las opciones para guardar MS Project de hoja de cálculo 2003, permite a los desarrolladores administrar y personalizar de manera eficiente archivos de MS Project mediante programación. Si sigue la guía paso a paso descrita en este tutorial, podrá integrar perfectamente estas capacidades en sus aplicaciones .NET, mejorando la productividad y la flexibilidad.

## Preguntas frecuentes
### P: ¿Se puede utilizar Aspose.Tasks para .NET en aplicaciones web y de escritorio?
R: Sí, Aspose.Tasks para .NET se puede integrar perfectamente en aplicaciones web y de escritorio, proporcionando una funcionalidad consistente en todas las plataformas.
### P: ¿Existe una versión de prueba disponible de Aspose.Tasks para .NET?
R: Sí, puede acceder a una prueba gratuita de Aspose.Tasks para .NET desde[sitio web](https://releases.aspose.com/), permitiéndole explorar sus características antes de realizar una compra.
### P: ¿Existe alguna limitación para personalizar las columnas de vista usando Aspose.Tasks para .NET?
R: Aspose.Tasks para .NET ofrece amplias opciones de personalización para las columnas de vista, con limitaciones mínimas. Sin embargo, las personalizaciones complejas pueden requerir conocimientos avanzados de la biblioteca.
### P: ¿Puedo buscar ayuda si tengo problemas al utilizar Aspose.Tasks para .NET?
 R: ¡Absolutamente! Puede encontrar soporte y recursos completos en el foro Aspose.Tasks en[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), donde expertos y miembros de la comunidad están disponibles para ayudar a resolver cualquier consulta o desafío que pueda enfrentar.
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Tasks para .NET?
 R: Puede adquirir una licencia temporal de Aspose.Tasks para .NET desde el[pagina de compra](https://purchase.aspose.com/temporary-license/), permitiéndole evaluar todas las capacidades de la biblioteca.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
