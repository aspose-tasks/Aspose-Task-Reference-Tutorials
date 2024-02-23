---
title: Opciones de guardado de MS Project en el servidor para Aspose.Tasks
linktitle: Opciones de guardado de Project Server para Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a guardar las opciones de Microsoft Project para Aspose.Tasks mediante la integración de Project Server. Mejore los flujos de trabajo de gestión de proyectos.
type: docs
weight: 16
url: /es/net/saving-options/project-server-save-options/
---
## Introducción
En este tutorial, profundizaremos en cómo guardar las opciones de Microsoft Project para Aspose.Tasks usando Project Server. Aspose.Tasks es una potente API .NET que permite a los desarrolladores trabajar con archivos de Microsoft Project mediante programación. Aprovechando las capacidades de Project Server, podemos integrar perfectamente Aspose.Tasks en nuestros flujos de trabajo de gestión de proyectos. Este tutorial lo guiará a través del proceso paso a paso.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  Aspose.Tasks para .NET: Instale Aspose.Tasks para .NET desde el[enlace de descarga](https://releases.aspose.com/tasks/net/).
   
2. Acceso a Project Server: necesitará las credenciales de acceso y la URL de su instancia de Project Server. Si no tienes uno, puedes obtener una prueba gratuita en[aquí](https://releases.aspose.com/).
3. Archivo de Microsoft Project: prepare el archivo de Microsoft Project (.mpp) que desea guardar usando Aspose.Tasks.

## Importar espacios de nombres
Primero, necesitas importar los espacios de nombres necesarios en tu proyecto:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    
```
## Paso 1: inicializar el proyecto y las credenciales
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
 Asegúrese de reemplazar`"Your Document Directory"`, `URL`, `Domain`, `UserName` ,y`Password` con sus valores reales.
## Paso 2: crear el administrador de Project Server
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Paso 3: definir opciones de guardar
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
 Ajustar el`ProjectGuid`, `ProjectName`, `Timeout` ,y`PollingInterval` según sus requisitos.
## Paso 4: guardar el proyecto en el servidor
```csharp
manager.CreateNewProject(project, options);
```
Esto guardará el proyecto en Project Server con las opciones especificadas.

## Conclusión
En este tutorial, aprendimos cómo guardar las opciones de Microsoft Project para Aspose.Tasks mediante la integración de Project Server. Si sigue estos pasos, podrá incorporar Aspose.Tasks sin problemas en sus flujos de trabajo de gestión de proyectos, mejorando la eficiencia y la productividad.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks con diferentes versiones de Microsoft Project?
R: Sí, Aspose.Tasks admite varias versiones de Microsoft Project, lo que garantiza la compatibilidad entre diferentes entornos.
### P: ¿Existe una versión de prueba disponible para Aspose.Tasks?
 R: Sí, puede obtener una versión de prueba gratuita de Aspose.Tasks en[aquí](https://releases.aspose.com/).
### P: ¿Aspose.Tasks admite subprocesos múltiples?
R: Sí, Aspose.Tasks está diseñado para ser seguro para subprocesos, lo que permite el acceso simultáneo a los datos del proyecto.
### P: ¿Puedo personalizar las opciones de guardado cuando uso la integración de Project Server?
R: Sí, puede personalizar las opciones de guardado, como el nombre del proyecto, el tiempo de espera y el intervalo de sondeo, para adaptarlas a sus necesidades.
### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?
 R: Puede encontrar soporte y asistencia en el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).