---
title: Configuración de la base de datos en Aspose.Tasks
linktitle: Configuración de la base de datos en Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda a importar proyectos desde una base de datos Primavera usando Aspose.Tasks para .NET. Obtenga orientación paso a paso en este tutorial completo.
type: docs
weight: 29
url: /es/net/calendar-scheduling/database-settings/
---
## Introducción

Aspose.Tasks para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con archivos de Microsoft Project en sus aplicaciones .NET. En este tutorial, nos centraremos en importar proyectos desde una base de datos Primavera usando Aspose.Tasks.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Conocimientos básicos del lenguaje de programación C#.
- Visual Studio instalado en su sistema.
-  Aspose.Tasks para la biblioteca .NET instalada. Puedes descargarlo desde[aquí](https://releases.aspose.com/tasks/net/).
- Acceso a una base de datos de Primavera, junto con los permisos necesarios.

## Importar espacios de nombres

Primero, necesita importar los espacios de nombres necesarios a su proyecto C#. Estos espacios de nombres brindan acceso a las clases y métodos necesarios para trabajar con Aspose.Tasks para .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Ahora, dividamos el código de ejemplo proporcionado en varios pasos:

## Paso 1: definir la cadena de conexión

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 En este paso, definimos la cadena de conexión para conectarnos a la base de datos Primavera. Asegúrese de reemplazar`DataDir` con el directorio donde se encuentra su archivo de base de datos.

## Paso 2: crear la configuración de la base de datos

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Aquí creamos una instancia de`PrimaveraDbSettings` clase, pasando la cadena de conexión y el ID del proyecto como parámetros. Ajuste la ID del proyecto según sus necesidades.

## Paso 3: Establecer el nombre invariante del proveedor

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Especifique el nombre invariante del proveedor. En este ejemplo, usamos SQLite, pero puede cambiarlo según su proveedor de base de datos.

## Paso 4: cargar proyecto

```csharp
var project = new Project(settings);
```

 Crear un nuevo`Project` objeto, pasando la configuración de la base de datos como parámetro.

## Paso 5: guardar proyecto

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Finalmente, guarde el proyecto en la ubicación deseada con el formato de archivo especificado.

## Conclusión

En este tutorial, aprendimos cómo importar proyectos desde una base de datos Primavera usando Aspose.Tasks para .NET. Si sigue los pasos proporcionados, puede integrar perfectamente la funcionalidad de importación de proyectos en sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿Puedo importar proyectos de diferentes proveedores de bases de datos usando Aspose.Tasks para .NET?

R1: Sí, puede importar proyectos de varios proveedores de bases de datos ajustando la cadena de conexión y el nombre invariante del proveedor en consecuencia.

### P2: ¿Hay una prueba gratuita disponible para Aspose.Tasks para .NET?

 R2: Sí, puede obtener una prueba gratuita de Aspose.Tasks para .NET desde[aquí](https://releases.aspose.com/).

### P3: ¿Dónde puedo encontrar documentación para Aspose.Tasks para .NET?

 A3: Puedes encontrar la documentación.[aquí](https://reference.aspose.com/tasks/net/).

### P4: ¿Cómo puedo obtener soporte para Aspose.Tasks para .NET?

 R4: Puede obtener soporte en el foro de la comunidad Aspose.Tasks[aquí](https://forum.aspose.com/c/tasks/15).

### P5: ¿Necesito una licencia temporal para usar Aspose.Tasks para .NET?

 R5: Si desea evaluar la funcionalidad completa de la biblioteca, puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).