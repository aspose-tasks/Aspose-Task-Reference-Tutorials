---
date: 2026-05-31
description: Aprenda cómo obtener la versión del proyecto y recuperar la fecha de
  la última guardado de archivos MS Project usando Aspose.Tasks para Java. Guía paso
  a paso con ejemplos de código.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Determinar la versión del proyecto con Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo obtener la versión del proyecto – Tutorial de Aspose Tasks para Java
url: /es/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo obtener la versión del proyecto – Tutorial de Aspose Tasks para Java

En este **tutorial de Aspose Tasks para Java** aprenderás **cómo obtener la versión del proyecto** de un archivo Microsoft Project y también cómo **recuperar la fecha de la última guardado** usando la biblioteca Aspose.Tasks para Java. Conocer la versión del archivo y la marca de tiempo de guardado te ayuda a evitar problemas de compatibilidad, aplicar políticas de migración y mantener registros de auditoría precisos. Recorreremos cada paso—desde la configuración del entorno hasta imprimir la versión y la fecha—para que puedas incorporar esta verificación en cualquier aplicación Java con confianza.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Determinar la versión del archivo MS Project y la fecha de última guardado con Aspose.Tasks para Java.  
- **¿Necesito Microsoft Project instalado?** No, Aspose.Tasks funciona de manera independiente de Microsoft Project.  
- **¿Qué formatos de archivo son compatibles?** Los archivos Project basados en XML, como MPP y XML, son totalmente compatibles.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 5‑10 minutos para una verificación básica de versión.  
- **¿Se requiere una licencia?** Una prueba gratuita sirve para evaluación; se requiere una licencia comercial para uso en producción.

## ¿Qué es el tutorial de Aspose Tasks para Java?
El tutorial Java de `Aspose.Tasks` es una guía concisa y práctica que demuestra cómo interactuar con los datos de Microsoft Project de forma programática. Te muestra cómo leer, modificar y analizar la información del proyecto sin necesidad de tener Microsoft Project instalado en el servidor. Además, cubre la carga de archivos, el acceso a propiedades y el guardado de cambios, lo que permite a los desarrolladores automatizar tareas de gestión de proyectos de manera eficiente.

## ¿Por qué usar Aspose.Tasks para determinar la versión del proyecto?
Aspose.Tasks proporciona **metadatos de versión exactos** y **marcas de tiempo de la última guardada** mientras se ejecuta en cualquier SO que soporte Java. Procesa archivos de hasta **500 páginas en menos de 2 segundos** en una CPU estándar de 2.5 GHz, lo que lo hace ideal para automatización por lotes y escenarios de migración a gran escala.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – versión 8 o superior.  
2. **Aspose.Tasks for Java JAR** – descárgalo desde el [website](https://releases.aspose.com/tasks/java/) y agrégalo al classpath de tu proyecto.  
3. **Archivo MS Project** – un archivo Project basado en XML (p. ej., `input.xml`) que deseas inspeccionar.  

> **Consejo profesional:** Almacena el archivo Project en una carpeta `data` dedicada para mantener las rutas ordenadas y evitar sobrescrituras accidentales.

## Importar paquetes
Primero, importa las clases esenciales de Aspose.Tasks:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Cómo configurar el directorio del proyecto
Para localizar correctamente tus archivos de proyecto, crea un directorio dedicado dentro de la estructura de tu aplicación y almacena allí todos los archivos de entrada. Esto mantiene el código limpio y evita errores relacionados con rutas al cargar archivos. Usa un nombre de variable claro para la ruta del directorio, que puede ser absoluta o relativa a la raíz del proyecto.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Reemplaza `"Your Data Directory"` con la ruta absoluta o relativa donde reside `input.xml`.

## Cómo cargar el proyecto
`Project` es el objeto principal de Aspose.Tasks que representa un archivo Microsoft Project en memoria, dándote acceso a todas las propiedades y colecciones del proyecto. Después de crear la instancia `Project`, puedes consultar sus campos, iterar sobre tareas o modificar datos antes de guardar el archivo de nuevo en disco.

```java
Project project = new Project(dataDir + "input.xml");
```

Si tu archivo tiene un nombre diferente, ajusta `"input.xml"` en consecuencia.

## Cómo determinar la versión del proyecto
`Prj.SAVE_VERSION` es una propiedad que indica el número de versión de Microsoft Project que guardó el archivo. `Prj.LAST_SAVED` es una propiedad que almacena la fecha y hora en que el archivo se guardó por última vez. `Prj.SAVE_VERSION` devuelve la versión numérica de la aplicación Microsoft Project que guardó el archivo (p. ej., 12 para Project 2010). `Prj.LAST_SAVED` proporciona la fecha y hora exactas de la operación de guardado más reciente.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Estos valores te permiten aplicar programáticamente reglas de negocio específicas por versión o generar informes de auditoría.

## Cómo mostrar el resultado
Después de recuperar la versión y la información de la última guardada, normalmente querrás mostrarlos en la consola o en un archivo de registro. Usa `System.out.println` para imprimir los valores, formateando la fecha según sea necesario. Esto confirma que la extracción tuvo éxito y brinda retroalimentación inmediata durante el desarrollo o en scripts automatizados.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` on `project.get(...)` | Archivo no encontrado o ruta incorrecta | Verifica `dataDir` y el nombre del archivo; usa una ruta absoluta para pruebas. |
| Número de versión inesperado (p. ej., 0) | Cargando un archivo XML que no es de Project | Asegúrate de que el archivo sea un archivo Microsoft Project válido (MPP/XML). |
| Excepción de licencia | Usar la versión de prueba sin una licencia válida en producción | Aplica tu licencia de Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
A: Sí, Aspose.Tasks soporta .NET, Java y C++ entre otros.

**Q: ¿Es Aspose.Tasks adecuado para proyectos a gran escala?**  
A: Absolutamente; puede procesar proyectos de cientos de páginas en segundos sin cargar todo el archivo en memoria.

**Q: ¿Puedo personalizar los datos del proyecto usando Aspose.Tasks?**  
A: Sí, puedes modificar tareas, recursos, calendarios y cualquier otro elemento del proyecto a través de la API.

**Q: ¿Aspose.Tasks requiere la instalación de Microsoft Project?**  
A: No, la biblioteca funciona de manera independiente y no necesita Microsoft Project en la máquina host.

**Q: ¿Hay soporte técnico disponible para Aspose.Tasks?**  
A: Sí, puedes obtener ayuda en el foro de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**Preguntas y respuestas adicionales**

**Q: ¿Cómo recupero otras propiedades del proyecto (p. ej., autor, empresa)?**  
A: Usa `project.get(Prj.AUTHOR)` o `project.get(Prj.COMPANY)` de la misma manera que recuperas la versión.

**Q: ¿Puedo comprobar la versión de un archivo MPP (binario)?**  
A: Sí, Aspose.Tasks carga archivos `.mpp` directamente; la propiedad `Prj.SAVE_VERSION` funciona también para formatos binarios.

**Q: ¿Existe una forma de actualizar programáticamente un archivo de proyecto antiguo a una versión más reciente?**  
A: Carga el archivo antiguo, luego guárdalo con `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks escribe el archivo en el formato más reciente por defecto.

## Conclusión
Ahora dominas **cómo obtener la versión del proyecto** y **recuperar la fecha de la última guardada** de los archivos MS Project usando Aspose.Tasks para Java. Incorpora estos fragmentos en pipelines de automatización, herramientas de informes o utilidades de migración para garantizar que siempre conozcas la versión exacta del Project que estás manejando.

---

**Última actualización:** 2026-05-31  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Establecer la fecha de inicio del proyecto en MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)
- [Leer la base de datos de Microsoft Project con Aspose.Tasks para Java](/tasks/java/project-data-reading/read-project-database/)
- [Guardar el proyecto como plantilla, CSV y texto con Aspose.Tasks para Java](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}