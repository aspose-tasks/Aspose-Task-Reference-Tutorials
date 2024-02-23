---
title: Administrar las credenciales del servidor de MS Project en Aspose.Tasks
linktitle: Administrar credenciales de Project Server en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a administrar las credenciales de MS Project Server sin problemas con Aspose.Tasks para .NET. Mejorar la eficiencia de la gestión de proyectos.
type: docs
weight: 22
url: /es/net/project-management-integration/project-server-credentials/
---
## Introducción
En el ámbito de la gestión de proyectos, la coordinación eficaz y la comunicación fluida son fundamentales para una ejecución exitosa del proyecto. Aspose.Tasks para .NET proporciona una solución integral para administrar las credenciales de Microsoft Project Server, lo que permite a los usuarios acceder y manipular de forma segura los datos del proyecto. Este tutorial profundiza en el proceso de administración de las credenciales de MS Project Server utilizando Aspose.Tasks para .NET, guiando a los usuarios a través de cada paso para garantizar una experiencia fluida.
## Requisitos previos
Antes de embarcarse en el viaje de administrar las credenciales de MS Project Server con Aspose.Tasks para .NET, asegúrese de que se cumplan los siguientes requisitos previos:
### 1. Instalación de Aspose.Tasks para .NET
 Para comenzar, descargue e instale Aspose.Tasks para .NET desde el archivo proporcionado[enlace de descarga](https://releases.aspose.com/tasks/net/), Siga las instrucciones de instalación para integrar la biblioteca en su entorno .NET sin problemas.
### 2. Credenciales de acceso
Reúna las credenciales necesarias para acceder a MS Project Server. Esto incluye la dirección de dominio de SharePoint, el nombre de usuario y la contraseña asociados con Project Server.

## Importar espacios de nombres
En su proyecto .NET, importe los espacios de nombres necesarios para utilizar las funcionalidades proporcionadas por Aspose.Tasks para .NET de manera eficiente.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Paso 1: Definir la ruta del directorio de documentos
```csharp
String DataDir = "Your Document Directory";
```
## Paso 2: configurar la dirección de dominio, el nombre de usuario y la contraseña de SharePoint
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Paso 3: crear credenciales de Project Server
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Paso 4: cargar el archivo del proyecto
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Paso 5: Inicializar Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Paso 6: crear un nuevo proyecto
```csharp
manager.CreateNewProject(newProject);
```
## Paso 7: recuperar la lista de proyectos
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Paso 8: iterar a través de la lista de proyectos
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Conclusión
La gestión eficaz de las credenciales de MS Project Server es fundamental para optimizar la gestión de proyectos. Aspose.Tasks para .NET simplifica este proceso al proporcionar un sólido conjunto de funcionalidades. Siguiendo la guía paso a paso descrita en este tutorial, los usuarios pueden integrar perfectamente Aspose.Tasks para .NET en sus proyectos, garantizando el acceso seguro y la manipulación de los datos del proyecto.
## Preguntas frecuentes
### P: ¿Aspose.Tasks para .NET es compatible con todas las versiones de Microsoft Project Server?
R: Aspose.Tasks para .NET está diseñado para ser compatible con varias versiones de Microsoft Project Server, lo que garantiza versatilidad y flexibilidad para los usuarios.
### P: ¿Puedo integrar Aspose.Tasks para .NET en mi proyecto .NET existente?
R: Sí, Aspose.Tasks para .NET se puede integrar perfectamente en proyectos .NET existentes, lo que facilita capacidades eficientes de gestión de proyectos.
### P: ¿Aspose.Tasks para .NET proporciona soporte para acceder a los recursos del proyecto?
R: Por supuesto, Aspose.Tasks para .NET ofrece soporte integral para acceder y manipular los recursos del proyecto, mejorando la eficiencia de la gestión de proyectos.
### P: ¿Hay opciones de licencia disponibles para Aspose.Tasks para .NET?
R: Sí, Aspose.Tasks para .NET ofrece opciones de licencia flexibles, incluidas licencias temporales para fines de prueba y licencias completas para uso comercial.
### P: ¿Dónde puedo buscar asistencia o soporte para Aspose.Tasks para .NET?
 R: Para cualquier consulta o ayuda con respecto a Aspose.Tasks para .NET, puede visitar el foro de soporte en[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Código fuente completo