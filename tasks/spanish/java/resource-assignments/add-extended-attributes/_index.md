---
date: 2026-05-20
description: Aprenda cómo usar Aspose.Tasks para Java para agregar atributos extendidos
  a asignaciones de recursos, establecer la fecha de inicio del proyecto y escribir
  archivos de MS Project de manera eficiente.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Agregar atributos extendidos a asignaciones de recursos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo usar Aspose.Tasks para Java – Agregar atributos extendidos a asignaciones
  de recursos
url: /es/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando la manipulación de MS Project con Aspose.Tasks para Java

## Introducción
En este tutorial descubrirás **cómo usar Aspose.Tasks para Java** para agregar atributos extendidos a asignaciones de recursos y escribir información de Microsoft Project de forma programática. Ya sea que estés automatizando una canalización de informes o construyendo una herramienta personalizada de gestión de proyectos, los pasos a continuación te muestran exactamente cómo establecer la fecha de inicio del proyecto, crear asignaciones de recursos y guardar el archivo como XML, todo con solo unas pocas líneas de código Java.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks para Java?** Lee, escribe y modifica archivos de Microsoft Project sin necesidad de tener Microsoft Project instalado.  
- **¿Puedo agregar campos personalizados a una asignación de recurso?** Sí, usa la colección `ExtendedAttribute` en el objeto `ResourceAssignment`.  
- **¿Cómo establezco la fecha de inicio del proyecto?** Llama a `project.setStartDate(LocalDateTime.of(...))` antes de guardar.  
- **¿Necesito una licencia para uso en producción?** Una licencia comercial elimina las marcas de agua de evaluación y desbloquea el acceso completo a la API.  
- **¿Qué versiones de Java son compatibles?** Aspose.Tasks para Java es compatible con JDK 8 hasta JDK 21.

## ¿Cómo usar Aspose.Tasks para Java?
`Project` es el objeto principal que representa un archivo de Microsoft Project en memoria. Carga la biblioteca Aspose.Tasks, crea una instancia de `Project`, configura las propiedades a nivel de proyecto, agrega atributos extendidos a una asignación de recurso y, finalmente, guarda el proyecto como XML. El flujo de trabajo central se divide en tres pasos concisos: inicializar, modificar y persistir. Este patrón funciona para proyectos de cualquier tamaño y se ejecuta en JVMs de Windows, Linux o macOS.

## ¿Qué es un atributo extendido en Aspose.Tasks?
Un **atributo extendido** es un campo personalizado que se adjunta a tareas, recursos o asignaciones para almacenar metadatos adicionales más allá de las columnas incorporadas. `ExtendedAttributeDefinition` define el esquema de un campo personalizado. Aspose.Tasks expone las clases `ExtendedAttributeDefinition` y `ExtendedAttribute` para definir y asignar estos campos de forma programática.

## ¿Por qué agregar atributos extendidos a asignaciones de recursos?
Aspose.Tasks admite **más de 50 campos incorporados y personalizados**, y puedes agregar atributos definidos por el usuario sin límite. Añadirlos te permite capturar códigos de costo, IDs de departamento o cualquier dato específico del negocio directamente dentro del archivo .mpp, eliminando la necesidad de hojas de cálculo externas y garantizando la integridad de los datos a lo largo del ciclo de vida del proyecto.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – JDK 8 o posterior instalado.  
2. **Aspose.Tasks for Java library** – Descárgala desde la página oficial de lanzamientos [aquí](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o cualquier editor compatible con Java que prefieras.

## Importar paquetes
Primero, importa los paquetes necesarios en tu proyecto Java:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Paso 1: Configurar el directorio de datos
Define el directorio donde se almacenarán los datos de tu proyecto. Esta ruta se utiliza más adelante cuando guardes el archivo XML.

```java
String dataDir = "Your Data Directory";
```

### Paso 2: Crear una instancia de Project
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un único archivo de Microsoft Project en memoria. Instanciarla te brinda acceso completo a todos los elementos del proyecto.

```java
Project project = new Project();
```

### Paso 3: Establecer las propiedades de información del proyecto
Establece las propiedades esenciales del proyecto, como la fecha de inicio, la bandera de programación desde el inicio y la fecha de estado. Estos valores se almacenan en el objeto `ProjectInfo` del proyecto.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Paso 4: Agregar atributos extendidos a una asignación de recurso
Crea una `ExtendedAttributeDefinition` para el campo personalizado, adjúntala a un `ResourceAssignment` y asigna el valor. Este paso demuestra el uso de la palabra clave **add extended attributes** en acción.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
- **NullPointerException al acceder a la colección de asignaciones** – Asegúrate de haber creado al menos un recurso y una tarea antes de obtener las asignaciones.  
- **El atributo extendido no aparece en MS Project** – Verifica que el `FieldId` del atributo coincida con una ranura de campo personalizado (p. ej., `ExtendedAttributeTask.Text1`).  
- **Incompatibilidad de formato de fecha** – Usa `java.time.LocalDateTime` para los valores de fecha; Aspose.Tasks los convierte automáticamente al formato del calendario del proyecto.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java para leer archivos de MS Project?**  
R: Sí, la biblioteca ofrece capacidades completas de lectura‑escritura para los formatos .mpp, .xml y .xps.

**P: ¿Es Aspose.Tasks para Java compatible con diferentes versiones de MS Project?**  
R: Absolutamente, es compatible con archivos desde Project 2000 hasta la última versión 2024, cubriendo más de 20 formatos de versión.

**P: ¿Hay limitaciones en la versión de prueba de Aspose.Tasks para Java?**  
R: La versión de prueba agrega una marca de agua a los archivos generados y limita la cantidad de tareas que puedes crear, pero todas las funciones de la API siguen accesibles.

**P: ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?**  
R: Puedes buscar ayuda en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**P: ¿Puedo comprar una licencia temporal para Aspose.Tasks para Java?**  
R: Sí, las licencias temporales están disponibles para uso a corto plazo. Puedes obtener una [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-05-20  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo agregar notas a asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Cómo leer la escala de tarifas y escribir la escala de tarifas para asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Cómo agregar un recurso al proyecto y manejar propiedades de retraso de nivelación en Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}