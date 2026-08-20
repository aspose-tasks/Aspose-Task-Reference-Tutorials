---
date: 2026-03-14
description: Aprenda cómo especificar el esquema de base de datos para una base de
  datos de Microsoft Project usando Aspose.Tasks y cómo importar datos de proyecto
  en aplicaciones .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Especificar el esquema de la base de datos para Project DB con Aspose.Tasks
url: /es/net/advanced-concepts/msp-database-settings/
weight: 19
---

 >}}

# Settings for Microsoft Project Database in Aspose.Tasks

Translate title: "Configuración de la base de datos de Microsoft Project en Aspose.Tasks". Keep heading level.

Proceed.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configuración de la base de datos de Microsoft Project en Aspose.Tasks

## Introducción

Si trabajas con bases de datos de Microsoft Project en tus aplicaciones .NET usando Aspose.Tasks, necesitarás **especificar el esquema de la base de datos** y configurar los ajustes necesarios para **importar datos del proyecto** de manera fluida. Este tutorial te guiará paso a paso, mostrándote **cómo configurar los detalles de conexión**, **crear la cadena de conexión .NET**, y finalmente **guardar el proyecto como MPP**.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Especificar el esquema de la base de datos e importar una base de datos de Project a una aplicación .NET.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para .NET.  
- **¿Cómo me conecto a Project Server?** Construyendo una cadena de conexión SQL adecuada y usando `MspDbSettings`.  
- **¿Qué formato de archivo se genera?** Un archivo MPP guardado con `SaveFileFormat.Mpp`.  
- **¿Puedo cambiar el nombre del esquema?** Sí, establece la propiedad `Schema` en `MspDbSettings`.

## Cómo especificar el esquema de la base de datos para Project DB

Entender por qué podrías necesitar **especificar el esquema de la base de datos** es esencial. En muchos entornos empresariales la base de datos de Project Server reside bajo un esquema personalizado (p. ej., `dbo`, `psdata`). Al establecer explícitamente el esquema, garantizas que Aspose.Tasks consulte las tablas correctas, evitando errores en tiempo de ejecución y asegurando una importación de datos precisa.

## Requisitos previos

Antes de comenzar, asegúrate de contar con lo siguiente:

1. Aspose.Tasks para .NET: Descarga e instala la biblioteca Aspose.Tasks desde [aquí](https://releases.aspose.com/tasks/net/).  
2. Acceso a una base de datos de Microsoft Project: Debes disponer de acceso a una base de datos de Microsoft Project desde la cual importar datos.  

## Importar espacios de nombres

Primero, asegúrate de importar los espacios de nombres necesarios en tu proyecto:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Paso 1: Crear la cadena de conexión

Construye la cadena de conexión a tu base de datos de Microsoft Project. Aquí es donde **creas la cadena de conexión .NET** y también defines cómo **conectarte a Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Consejo profesional:** Verifica dos veces los valores de `DataSource` y `InitialCatalog`; deben coincidir con la dirección de tu servidor y el nombre de la base de datos publicada.

## Paso 2: Configurar MspDbSettings

Crea una instancia de `MspDbSettings`, pasa la cadena de conexión y **especifica el esquema de la base de datos** estableciendo la propiedad `Schema`. Esto indica a Aspose.Tasks qué esquema consultar.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Aquí también proporcionamos el GUID del proyecto que identifica el proyecto específico que deseas cargar.

## Paso 3: Cargar datos del proyecto

Instancia un objeto `Project` usando la configuración configurada. Este paso efectivamente **importa datos del proyecto** desde la base de datos a un objeto .NET.

```csharp
var project = new Project(settings);
```

## Paso 4: Guardar los datos del proyecto

Finalmente, persiste el proyecto cargado en un archivo MPP en disco. Esto demuestra **guardar el proyecto como MPP** usando la API de Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Después de ejecutar el código, encontrarás el archivo `ImportProjectDataFromDatabase_out.mpp` en el directorio de salida, listo para abrirse en Microsoft Project.

## Conclusión

En este tutorial, has aprendido cómo **especificar el esquema de la base de datos** para una base de datos de Microsoft Project, **configurar la conexión**, **importar datos del proyecto** y **guardar el proyecto como MPP** usando Aspose.Tasks para .NET. Estos pasos permiten una integración fluida de los datos de Project Server en tus aplicaciones personalizadas, ayudándote a crear soluciones robustas de gestión de proyectos.

## Preguntas frecuentes

### Q1: ¿Puedo usar Aspose.Tasks con diferentes versiones de bases de datos de Microsoft Project?
A1: Sí, Aspose.Tasks admite varias versiones de bases de datos de Microsoft Project, lo que brinda flexibilidad en la integración.

### Q2: ¿Cómo puedo solucionar problemas de conexión con la base de datos?
A2: Asegúrate de que tu cadena de conexión esté configurada correctamente con las credenciales y los detalles de la base de datos apropiados. También puedes consultar la documentación o buscar ayuda en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: ¿Existe una versión de prueba disponible para Aspose.Tasks?
A3: Sí, puedes acceder a una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

### Q4: ¿Puedo personalizar el esquema para la interacción con la base de datos?
A4: Sí, puedes especificar el esquema para el objeto `MspDbSettings` según la estructura de tu base de datos.

### Q5: ¿Dónde puedo encontrar documentación más detallada sobre el uso de Aspose.Tasks?
A5: Puedes explorar la documentación completa [aquí](https://reference.aspose.com/tasks/net/) para obtener información detallada sobre las funcionalidades de Aspose.Tasks.

**P: ¿Este enfoque funciona con bases de datos Azure SQL?**  
R: Absolutamente. Solo ajusta el `DataSource` al nombre de tu servidor Azure y asegúrate de que las configuraciones TLS/SSL estén habilitadas.

**P: ¿Cómo manejo bases de datos de Project muy grandes sin que se agote el tiempo de espera?**  
R: Incrementa el valor de `ConnectTimeout` en la cadena de conexión y considera cargar los proyectos por lotes si es necesario.

---

**Última actualización:** 2026-03-14  
**Probado con:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}