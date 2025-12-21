---
date: 2025-12-21
description: Aprenda cómo guardar el proyecto como plantilla, exportar MPP a CSV y
  convertir MPP a texto usando Aspose.Tasks para Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Guardar proyecto como plantilla, CSV y texto con Aspose.Tasks para Java
url: /es/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar proyecto como plantilla, CSV y texto con Aspise.Tasks

## Introducción
En este tutorial, descubrirás **cómo guardar un proyecto como plantilla** y también cómo exportar tus archivos Microsoft Project (MPP) a formatos CSV y texto plano usando la biblioteca Aspose.Tasks para Java. Ya sea que necesites crear una plantilla de proyecto reutilizable, generar informes CSV para análisis, o producir extractos de texto simples para integración, estos pasos te guiarán rápidamente y de manera eficiente.

## Respuestas rápidas
- **¿Puedo exportar MPP a CSV?** Sí – usa `project.save(..., SaveFileFormat.CSV)`.  
- **¿Cómo exportar texto?** Guarda con `SaveFileFormat.TEXT`.  
- **¿Qué hace “guardar proyecto como plantilla”?** Crea un archivo `.mpt` que elimina los valores reales y de línea base, listo para reutilizar.  
- **¿Necesito una licencia?** Hay una versión de prueba disponible; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java se necesita?** Se admite Java 8+.

## ¿Qué es “guardar proyecto como plantilla”?
Guardar un proyecto como plantilla (`.mpt`) captura la estructura, la jerarquía de tareas y las asignaciones de recursos mientras elimina las fechas reales de inicio/fin y los datos de línea base. Esto hace que la plantilla sea ideal para reutilizar un diseño estándar de proyecto en múltiples proyectos nuevos.

## ¿Por qué usar Aspose.Tasks para Java?
Aspose.Tasks te permite manipular archivos Microsoft Project sin instalar Microsoft Project. Soporta **cómo exportar MPP**, **cómo exportar texto** y **convertir MPP a CSV**, todo desde código Java puro, lo que es perfecto para automatización del lado del servidor, pipelines CI o utilidades de escritorio.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. Java Development Kit (JDK) 8 o superior instalado.  
2. Biblioteca Aspose.Tasks para Java añadida a tu proyecto. Descárgala desde [aquí](https://releases.aspose.com/tasks/java/).  
3. Familiaridad básica con la sintaxis de Java y la configuración de proyectos Maven/Gradle.

## Importar paquetes
Primero, importa las clases necesarias en tu archivo fuente Java:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Guardar proyecto como CSV (Exportar MPP a CSV)
Exportar un archivo MPP a CSV es útil para el análisis de datos en Excel o herramientas de BI.

### Paso 1: Cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Paso 2: Guardar como CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Guardar proyecto como texto (Cómo exportar texto)
Si necesitas una representación en texto plano de tareas, recursos o asignaciones, guarda el proyecto como un archivo de texto.

### Paso 1: Cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Paso 2: Guardar como texto
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Guardar proyecto como plantilla (Crear plantilla de proyecto Java)
Crear una plantilla reutilizable elimina las fechas reales y las líneas base, dejando un esqueleto limpio para nuevos proyectos.

### Paso 1: Cargar el proyecto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Paso 2: Configurar opciones de plantilla
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Paso 3: Guardar como plantilla
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Problemas comunes y consejos
- **Archivo no encontrado:** Asegúrate de que la ruta a `YourProject.mpp` sea correcta o usa una ruta absoluta.  
- **Excepciones de licencia:** Sin una licencia válida, la biblioteca se ejecuta en modo de evaluación y puede añadir marcas de agua. Aplica tu licencia al inicio del código (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Proyectos grandes:** Para archivos MPP muy grandes, considera aumentar el tamaño del heap de JVM (`-Xmx2g`) para evitar `OutOfMemoryError`.

## Conclusión
Hemos cubierto **cómo guardar un proyecto como plantilla**, así como cómo **exportar MPP a CSV** y **convertir MPP a texto** usando Aspose.Tasks para Java. Estas capacidades te permiten automatizar la gestión de datos de proyectos, generar plantillas reutilizables e integrar información de proyectos en otros sistemas, todo sin necesidad de instalar Microsoft Project.

## Preguntas frecuentes
### P: ¿Puede Aspose.Tasks para Java manejar archivos de proyecto complejos?
R: ¡Absolutamente! Aspose.Tasks para Java puede manejar proyectos de diversa complejidad con facilidad, proporcionando soporte integral para los formatos de archivo de Microsoft Project.  
### P: ¿Hay una versión de prueba disponible para Aspose.Tasks para Java?
R: Sí, puedes obtener una prueba gratuita de Aspose.Tasks para Java desde [aquí](https://releases.aspose.com/).  
### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks para Java?
R: Puedes visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para cualquier asistencia o consulta relacionada con Aspose.Tasks para Java.  
### P: ¿Puedo comprar una licencia temporal para Aspose.Tasks para Java?
R: Sí, puedes adquirir una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/), lo que te permite evaluar todo el potencial de la biblioteca.  
### P: ¿Aspose.Tasks para Java es compatible con diferentes sistemas operativos?
R: Sí, Aspose.Tasks para Java es compatible con varios sistemas operativos, incluidos Windows, macOS y Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose  

---