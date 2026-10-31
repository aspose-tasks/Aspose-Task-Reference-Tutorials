---
date: 2026-10-31
description: Aprenda cómo guardar proyecto como PDF y leer la base de datos de Microsoft
  Project con Aspose.Tasks para Java, además de conectarse a Project Server, convertir
  el proyecto a HTML y exportar el proyecto a XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Lectura de datos del proyecto desde la base de datos de Microsoft Project
  en Aspose.Tasks
og_description: Guarde proyecto como PDF y lea la base de datos de Microsoft Project
  usando Aspose.Tasks para Java. Aprenda a conectarse a Project Server, exportar a
  HTML, XML y CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Guardar proyecto como PDF y leer la base de datos de Microsoft Project con
  Aspose.Tasks para Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Guardar proyecto como PDF y leer la base de datos de Microsoft Project con
  Aspose.Tasks para Java
url: /es/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar proyecto como PDF y leer la base de datos de Microsoft Project con Aspose.Tasks para Java

## Introducción
En este tutorial descubrirá cómo **leer la base de datos de Microsoft Project** directamente desde un Microsoft Project Server y luego **guardar el proyecto como PDF** usando la API Aspose.Tasks para Java. Ya sea que necesite generar informes imprimibles, migrar datos heredados o incrustar información del proyecto en un portal personalizado, esta guía lo lleva paso a paso—desde la configuración de la conexión JDBC hasta la exportación del proyecto a PDF, XML o HTML. Al final, tendrá una solución lista para producción que se ejecuta en cualquier servidor Java sin instalar Microsoft Project.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks?** Proporciona una API pura de Java para leer, escribir y manipular archivos y bases de datos de Microsoft Project.  
- **¿Necesito Microsoft Project instalado?** No, Aspose.Tasks funciona de forma independiente a Microsoft Project.  
- **¿Qué tipo de base de datos es compatible?** Microsoft SQL Server, el backend de Project Server.  
- **¿Puedo exportar a otros formatos?** Sí—PDF, XML, HTML, CSV, PNG, JPEG y más.  
- **¿Cuáles son los principales requisitos previos?** JDK 8 o superior, la biblioteca Aspose.Tasks para Java, el controlador JDBC de SQL Server y credenciales válidas de Project Server.

## Qué significa “leer la base de datos de Microsoft Project”
Leer una base de datos de Microsoft Project significa conectarse al repositorio SQL Server de Project Server, extraer los datos del proyecto almacenados y cargarlos en un objeto `Project` que Aspose.Tasks puede manipular. Este enfoque es ideal para informes automatizados, migración de datos o análisis personalizados.

## ¿Por qué usar Aspose.Tasks para Java?
Aspose.Tasks para Java le permite trabajar con datos de Microsoft Project sin necesitar la aplicación de escritorio, ofreciendo una solución pura de Java que se ejecuta en cualquier plataforma. Proporciona un modelo de objetos completo para tareas, recursos, calendarios y campos personalizados, y puede manejar proyectos empresariales de gran tamaño de manera eficiente, lo que lo hace ideal para escenarios de informes automatizados, migración e integración.

- **Sin dependencia de Microsoft Project** – se ejecuta en cualquier servidor o entorno CI.  
- **Modelo de objetos rico** – acceda a tareas, recursos, asignaciones, calendarios y campos personalizados programáticamente.  
- **Múltiples opciones de exportación** – Aspose.Tasks soporta exportar a **más de 20 formatos de archivo**, incluidos PDF, XML, HTML, CSV, PNG y JPEG, con una sola llamada a la API.  
- **Alto rendimiento** – la biblioteca puede procesar proyectos con **hasta 10 000 tareas** en menos de un minuto, y transmite datos para evitar cargar todo el archivo en memoria.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. Un entorno de desarrollo Java funcional (JDK 8 o superior).  
2. La biblioteca Aspose.Tasks para Java añadida al classpath de su proyecto.  
3. Credenciales de acceso a la base de datos SQL del Project Server (nombre del servidor, puerto, nombre de la base de datos, usuario, contraseña) para conectarse a Project Server.  
4. El controlador JDBC de Microsoft para SQL Server (p. ej., `sqljdbc4.jar`).  

## Importar paquetes
Primero, importe las clases que necesitará. La lista incluye clases centrales de Aspose.Tasks y utilidades estándar de Java.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Cómo conectarse a Project Server
Establecer una conexión fiable es la base para leer los datos del proyecto. Asegúrese de que la instancia de SQL Server sea accesible desde su host Java y de que el inicio de sesión que use tenga permisos **SELECT** en el esquema de Project Server. También debe verificar la latencia de red y configurar cualquier ajuste SSL necesario para garantizar una comunicación segura.

## Paso 1: configurar la conexión a la base de datos
La clase `MspDbSettings` encapsula los detalles de conexión JDBC requeridos para acceder a una base de datos de Microsoft Project Server. Cree una instancia de `MspDbSettings` que contenga la cadena de conexión JDBC. Reemplace los valores de marcador de posición con los detalles reales de su servidor.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Consejo profesional:** Almacene la cadena de conexión en un archivo de configuración seguro o en una variable de entorno en lugar de codificar las credenciales directamente.

## Paso 2: agregar el controlador JDBC
Cargue el controlador JDBC de Microsoft SQL Server en tiempo de ejecución para que la JVM pueda comunicarse con la base de datos.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Advertencia:** Asegúrese de que la versión del controlador coincida con la versión de su SQL Server. Usar un controlador incompatible puede provocar fallos de conexión.

## Paso 3: leer datos del proyecto
La clase `Project` representa un archivo de Microsoft Project cargado en memoria, exponiendo tareas, recursos y asignaciones. Instancie un objeto `Project` pasando el `MspDbSettings`. Aspose.Tasks obtendrá los datos del proyecto de la base de datos automáticamente.

```java
Project project = new Project(settings);
```

En este punto puede explorar el objeto `project`: listar tareas, recursos o modificar campos según sea necesario.

## Paso 4: guardar el proyecto como PDF
La enumeración `SaveFileFormat` define el formato de salida para el método `Project.save`, como PDF, XML o HTML. Exporte el proyecto cargado al formato que prefiera. El ejemplo a continuación guarda el proyecto como **PDF**, ideal para informes imprimibles. También puede **exportar el proyecto a XML** o **convertir el proyecto a HTML** cambiando la enumeración `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Si prefiere XML, simplemente reemplace `SaveFileFormat.Pdf` por `SaveFileFormat.Xml`. Para salida HTML, use `SaveFileFormat.Html`.

## Problemas comunes y soluciones
| Problema | Causa típica | Solución |
|----------|--------------|----------|
| **Tiempo de espera de conexión** | Servidor/puerto incorrecto o firewall bloqueando | Verifique la dirección del servidor, abra el puerto 1433 y pruebe la conectividad con un programa de prueba JDBC simple. |
| **Error de autenticación** | Nombre de usuario/contraseña inválidos o SQL Server no configurado para autenticación SQL | Utilice un inicio de sesión SQL válido o habilite la autenticación de modo mixto en el servidor. |
| **Controlador no encontrado** | JAR JDBC no está en el classpath | Asegúrese de que `addJDBCDriver` apunte al archivo `.jar` correcto y que la ruta use doble barra invertida (`\\`). |
| **Proyecto vacío después de cargar** | Permisos insuficientes para leer las tablas de Project Server | Conceda al inicio de sesión derechos SELECT en el esquema de la base de datos de Project Server. |

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks usarse para leer datos de proyecto de otras bases de datos además de Microsoft Project?**  
A: Sí, Aspose.Tasks soporta leer datos de proyecto de archivos XML, bases de datos Primavera y otros formatos estándar de proyecto.

**Q: ¿Es Aspose.Tasks compatible con diferentes versiones de Microsoft Project?**  
A: Sí, la biblioteca funciona con Microsoft Project 2007 hasta las últimas versiones 2024, garantizando una integración sin problemas entre versiones.

**Q: ¿Puedo manipular los datos del proyecto antes de guardarlos?**  
A: Absolutamente, puede agregar, actualizar o eliminar tareas, recursos y campos personalizados usando la rica API antes de exportar.

**Q: ¿Aspose.Tasks soporta varios formatos de salida?**  
A: Sí, puede guardar proyectos como PDF, XML, HTML, CSV, PNG, JPEG y más—más de 20 formatos en total.

**Q: ¿Dónde puedo encontrar más soporte o asistencia con Aspose.Tasks?**  
A: Para ayuda adicional, visite el foro de Aspose.Tasks o explore la documentación disponible en el sitio web [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusión
Al seguir esta guía paso a paso, ahora sabe cómo **leer la base de datos de Microsoft Project**, **guardar el proyecto como PDF** y exportar a otros formatos usando Aspose.Tasks para Java. Este enfoque elimina la dependencia de Microsoft Project, simplifica los informes automatizados y abre la puerta a poderosas integraciones personalizadas.

---

**Última actualización:** 2026-10-31  
**Probado con:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo guardar proyecto como PDF con Aspose.Tasks – Guía de exportación](/tasks/java/project-file-operations/save-as-pdf/)
- [Guardar proyecto como PDF – Renderizar hoja de tareas con Aspose.Tasks para Java](/tasks/java/task-properties/render-task-sheet/)
- [Exportar proyecto a PDF y reducir la brecha entre la lista de tareas y el pie de página en Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}