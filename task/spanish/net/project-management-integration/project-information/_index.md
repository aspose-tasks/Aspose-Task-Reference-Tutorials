---
title: Extraiga información del proyecto MS en Aspose.Tasks
linktitle: Extracción de información del proyecto en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a extraer información de MS Project sin esfuerzo utilizando Aspose.Tasks para .NET. Sumérgete en nuestro completo tutorial.
type: docs
weight: 20
url: /es/net/project-management-integration/project-information/
---
## Introducción
¿Está buscando extraer información de manera eficiente de archivos de Microsoft Project usando Aspose.Tasks para .NET? En este tutorial, lo guiaremos a través del proceso paso a paso. Pero antes de profundizar en los detalles de implementación, primero asegurémonos de que tiene todo lo que necesita.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
### 1. Aspose.Tareas para .NET
 Asegúrese de haber instalado la biblioteca Aspose.Tasks para .NET. Si aún no lo has hecho, puedes descargarlo desde[Aspose.Tasks para el sitio web .NET](https://releases.aspose.com/tasks/net/).
### 2. Credenciales para SharePoint
Necesitará las credenciales para acceder a SharePoint donde están almacenados sus archivos de MS Project. Asegúrese de tener la siguiente información:
- Dirección de dominio de SharePoint
- Nombre de usuario
- Contraseña
## Importando espacios de nombres
Una vez que haya resuelto sus requisitos previos, es hora de importar los espacios de nombres necesarios a su proyecto.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Ahora dividamos el proceso de extracción de información de MS Project en varios pasos.
## Paso 1: proporcionar credenciales
Primero, debe proporcionar sus credenciales de SharePoint para acceder a Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Paso 2: Inicializar Project Server Manager
 A continuación, inicialice un`ProjectServerManager` instancia con las credenciales proporcionadas.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Paso 3: recuperar la lista de proyectos
Ahora puede recuperar la lista de proyectos del Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Paso 4: imprimir la información del proyecto
Finalmente, recorra la lista de proyectos e imprima su información.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo extraer información de MS Project usando Aspose.Tasks para .NET. Con este conocimiento, ahora puede integrar esta funcionalidad en sus aplicaciones .NET sin problemas.
## Preguntas frecuentes
### P1: ¿Puedo usar Aspose.Tasks para .NET con cualquier versión de Microsoft Project?
R: Sí, Aspose.Tasks para .NET admite varias versiones de Microsoft Project, incluidas 2003, 2007, 2010, 2013, 2016 y 2019.
### P2: ¿Aspose.Tasks para .NET es compatible con las plataformas Windows y Linux?
R: Sí, Aspose.Tasks para .NET es compatible con plataformas Windows y Linux, lo que lo hace versátil para diferentes entornos de desarrollo.
### P3: ¿Puedo extraer dependencias de tareas usando Aspose.Tasks para .NET?
R: ¡Absolutamente! Aspose.Tasks para .NET proporciona una funcionalidad sólida para extraer no solo información básica del proyecto sino también dependencias de tareas y otros detalles complejos.
### P4: ¿Aspose.Tasks para .NET ofrece soporte técnico?
 R: Sí, puede obtener soporte técnico para Aspose.Tasks para .NET a través de[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15), donde puede hacer preguntas y buscar ayuda de expertos.
### P5: ¿Puedo probar Aspose.Tasks para .NET antes de comprarlo?
 R: ¡Ciertamente! Puede aprovechar una prueba gratuita de Aspose.Tasks para .NET desde el[página de lanzamientos](https://releases.aspose.com/), permitiéndole explorar sus características antes de tomar una decisión de compra.