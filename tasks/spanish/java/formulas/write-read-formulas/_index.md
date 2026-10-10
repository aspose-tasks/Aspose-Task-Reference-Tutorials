---
date: 2026-10-10
description: Aprenda cómo crear un campo personalizado aspose en Java, aplicar una
  fórmula de costo doble de tarea y guardar el project file usando Aspose.Tasks. Incluye
  la lectura de fórmulas de MS Project.
keywords:
- create custom field aspose
- double task cost formula
- add custom field formula
- calculate task cost
lastmod: 2026-10-10
linktitle: Ejemplo de fórmula de campo personalizado – Guardar project file
og_description: Aprenda cómo crear un campo personalizado aspose en Java, aplicar
  una fórmula de costo doble de tarea y guardar el project file usando Aspose.Tasks.
  Incluye la lectura de fórmulas de MS Project.
og_image_alt: 'Guide: create custom field aspose and save project file with Aspose.Tasks
  Java'
og_title: Cómo crear un campo personalizado aspose y guardar el project file
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  headline: How to create custom field aspose and save project file
  type: TechArticle
- description: Learn how to create custom field aspose in Java, apply a double task
    cost formula, and save the project file using Aspose.Tasks. Includes reading MS
    Project formulas.
  name: How to create custom field aspose and save project file
  steps:
  - name: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
    text: '**Java Development Kit (JDK)** – Java 8 or higher installed on your machine.'
  - name: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download and install from [Aspose.Tasks Java
      download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
    text: '**Integrated Development Environment (IDE)** – Choose your preferred IDE
      for Java development (IntelliJ IDEA, Eclipse, VS Code, etc.).'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of MS Project versions, from older
      .mpp formats to the latest releases, covering over 30 file format variations.
    question: Is Aspose.Tasks compatible with all versions of MS Project?
  - answer: Absolutely. The API is designed for seamless integration; just add the
      Aspose.Tasks JAR to your project’s classpath and start using the `Project` class.
    question: Can I integrate Aspose.Tasks into my existing Java project?
  - answer: The library supports most native MS Project formula syntax, including
      arithmetic, logical, and built‑in functions. Complex custom functions may require
      workarounds, but common calculations like **double task cost formula** work
      out of the box.
    question: Are there any limitations to the types of formulas I can create?
  - answer: Yes, the library runs on any platform that supports Java, including Windows,
      Linux, and macOS, and can handle projects up to 2 GB without loading the entire
      file into memory.
    question: Does Aspose.Tasks support multi‑platform deployment?
  - answer: Visit the [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)
      for community help, or open a support ticket if you have a commercial license.
    question: How can I get technical support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- custom field
- Aspose.Tasks
- Java project automation
title: Cómo crear un campo personalizado aspose y guardar el project file
url: /es/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un campo personalizado aspose y guardar el archivo de proyecto

## Introducción
En este tutorial verá un **custom field formula example** que muestra cómo **save project file**, escribir y leer fórmulas de MS Project, y aplicar una **double task cost formula** usando Aspose.Tasks para Java. Al final entenderá por qué los campos personalizados son poderosos, cómo incrustar cálculos directamente en un proyecto, y cómo conservar esos cambios para informes posteriores. El enfoque principal está en **create custom field aspose** para que pueda automatizar los cálculos de costos en cualquier flujo de trabajo basado en MS Project‑based workflow.

## Respuestas rápidas
- **¿Qué hace “save project file”?** Escribe todos los cambios en memoria de vuelta a un archivo .mpp en el disco.  
- **¿Puedo agregar fórmulas de campo personalizado?** Sí, puede crear un campo personalizado y asignar una fórmula como “double task cost”.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué IDE funciona mejor?** Cualquier IDE Java (IntelliJ IDEA, Eclipse, VS Code) compilará el ejemplo.  
- **¿Es la API compatible con la última versión de MS Project?** Aspose.Tasks admite todos los formatos .mpp recientes.

## Qué es “save project file” en Aspose.Tasks?
Guardar un archivo de proyecto significa preservar el estado actual del objeto `Project`, incluidos tareas, recursos y cualquier fórmula personalizada, en un archivo físico de Microsoft Project (`.mpp`). Esta operación es esencial después de modificar datos, como agregar un campo personalizado o cambiar los costos de tareas. La llamada `save` escribe la estructura completa del proyecto en el disco, haciendo que los cambios estén disponibles para herramientas de informes posteriores.

## ¿Por qué agregar un campo personalizado y crear una fórmula de campo personalizado?
Agrega un campo personalizado cuando necesita almacenar información que los campos incorporados no cubren. Adjuntar una fórmula—como una que **double task cost**—automatiza los cálculos, elimina actualizaciones manuales y garantiza que cada vez que el costo base cambie, el valor derivado se actualice instantáneamente. Este enfoque reduce errores y mantiene los datos de su cronograma consistentes entre los equipos.

## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de contar con los siguientes requisitos:

1. **Java Development Kit (JDK)** – Java 8 o superior instalado en su máquina.  
2. **Aspose.Tasks for Java** – Descargue e instale desde [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **Integrated Development Environment (IDE)** – Elija su IDE preferido para desarrollo Java (IntelliJ IDEA, Eclipse, VS Code, etc.).  

## Importando paquetes
Las clases `Project`, `ExtendedAttribute` y relacionadas se encuentran en el espacio de nombres `com.aspose.tasks`. Impórtalas al inicio de su archivo fuente para que el compilador pueda resolver los tipos.

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Paso 1: configurar el directorio de datos
Defina la carpeta donde se encuentran sus archivos MS Project. Aquí cargará el archivo fuente y luego **save project file**.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Paso 2: cargar el archivo de proyecto
La clase `Project` representa un archivo Microsoft Project en memoria, proporcionando acceso a tareas, recursos y campos personalizados. Cargar el archivo le brinda un modelo de objetos manipulable.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Paso 3: agregar campo personalizado y crear fórmula de campo personalizado
En este paso **agregamos un campo personalizado** “Double Costs” y **creamos una fórmula de campo personalizado** que multiplica el `[Cost]` de la tarea por 2, implementando efectivamente una **double task cost formula**. El método `setFormula` incrusta el cálculo directamente en el archivo del proyecto.

```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```

## Paso 4: agregar tarea y establecer costo
Cree una nueva tarea y luego asigne un costo base de `100`. Cuando el proyecto se guarde, el campo personalizado mostrará automáticamente `200` debido a la fórmula definida anteriormente.

```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```

## Paso 5: guardar el archivo de proyecto
El método `save` escribe el proyecto actualizado, incluido el nuevo campo personalizado y sus valores calculados, en `saved.mpp`. Esto conserva los cambios de **create custom field aspose** para cualquier consumidor posterior.

```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Fórmula no aplicada** | El campo personalizado no se agregó a la colección `ExtendedAttributes` del proyecto. | Asegúrese de que `project.getExtendedAttributes().add(attr);` se ejecute antes de guardar. |
| **Archivo no encontrado** | Ruta `dataDir` incorrecta. | Verifique que la cadena del directorio termine con un separador de ruta (`/` o `\\`). |
| **El costo aparece como 0** | El costo de la tarea no se estableció antes de guardar. | Llame a `task.set(Tsk.COST, ...)` antes de `project.save`. |

## Preguntas frecuentes
**P: ¿Es Aspose.Tasks compatible con todas las versiones de MS Project?**  
R: Sí, Aspose.Tasks admite una amplia gama de versiones de MS Project, desde formatos .mpp antiguos hasta las últimas versiones, cubriendo más de 30 variaciones de formato de archivo.

**P: ¿Puedo integrar Aspose.Tasks en mi proyecto Java existente?**  
R: Por supuesto. La API está diseñada para una integración sin problemas; simplemente añada el JAR de Aspose.Tasks al classpath de su proyecto y comience a usar la clase `Project`.

**P: ¿Existen limitaciones en los tipos de fórmulas que puedo crear?**  
R: La biblioteca admite la mayor parte de la sintaxis de fórmulas nativas de MS Project, incluyendo aritmética, lógica y funciones incorporadas. Las funciones personalizadas complejas pueden requerir soluciones alternativas, pero cálculos comunes como **double task cost formula** funcionan directamente.

**P: ¿Aspose.Tasks admite despliegue multiplataforma?**  
R: Sí, la biblioteca se ejecuta en cualquier plataforma que soporte Java, incluyendo Windows, Linux y macOS, y puede manejar proyectos de hasta 2 GB sin cargar todo el archivo en memoria.

**P: ¿Cómo puedo obtener soporte técnico para Aspose.Tasks?**  
R: Visite el [foro de la comunidad de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener ayuda de la comunidad, o abra un ticket de soporte si tiene una licencia comercial.

## Conclusión
En este **custom field formula example** cubrimos cómo **save project file**, **agregar un campo personalizado**, y **crear una double task cost formula** que duplica automáticamente el costo de la tarea. Al seguir estos pasos puede automatizar cálculos, enriquecer los datos de su proyecto y garantizar que todos los cambios se conserven para futuros informes y análisis. La técnica **create custom field aspose** es una forma poderosa de ampliar MS Project sin trabajo manual de hojas de cálculo.

---

**Última actualización:** 2026-10-10  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear archivo MPP – Crear y guardar proyecto vacío en formato MPP con Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Cómo crear proyecto aspose.tasks – Establecer atributos de nuevas tareas](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Leer atributos de tarea extendidos con Aspose.Tasks para Java](/tasks/java/task-properties/extended-task-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}