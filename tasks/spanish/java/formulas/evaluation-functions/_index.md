---
date: 2026-10-10
description: Aprenda cómo agregar un atributo extendido en Aspose.Tasks, usar funciones
  de evaluación y generar informes de proyecto con esta biblioteca de gestión de proyectos
  Java.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Soporte de funciones de evaluación en fórmulas de Aspose.Tasks
og_description: Aprenda cómo agregar un atributo extendido en Aspose.Tasks, usar funciones
  de evaluación y generar informes de proyecto con esta biblioteca de gestión de proyectos
  Java.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Cómo agregar un atributo extendido en fórmulas de Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Cómo agregar un atributo extendido en fórmulas de Aspose.Tasks
url: /es/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un atributo extendido en fórmulas de Aspose.Tasks

## Introducción
Aspose.Tasks for Java es una **biblioteca de gestión de proyectos Java** que le permite generar informes de proyecto creando un objeto `Project` en Java y evaluando funciones de Microsoft Project directamente dentro de su código. Al incrustar estas fórmulas, puede ejecutar cálculos sofisticados, generar informes personalizados y automatizar el análisis de proyectos sin salir de su entorno de desarrollo. En este tutorial recorreremos la creación de un objeto de proyecto, la adición de un atributo extendido y el uso de funciones de evaluación para **agregar datos de tarea de campo personalizado**.

## Respuestas rápidas
- **¿Qué significa “create project object java”?** Crea una instancia de `Project` en memoria que puede manipular programáticamente.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (descárguela desde el sitio oficial).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa de Aspose.Tasks para uso en producción; hay una versión de prueba gratuita disponible.  
- **¿Puedo usar campos personalizados?** Sí, puede **agregar un atributo extendido** a las tareas y tratarlos como campos personalizados.  
- **¿Es compatible con todos los formatos de archivo de Project?** Aspose.Tasks admite 3 formatos principales (MPP, MPT, XML) y más de 50 formatos adicionales de entrada/salida.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Entorno de desarrollo Java** – JDK 8+ y un IDE como IntelliJ IDEA o Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Descargue e incluya la biblioteca desde la [página de descarga de Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Agregue el espacio de nombres de Aspose.Tasks a su clase Java para poder trabajar con proyectos, tareas y atributos extendidos:

```java
import com.aspose.tasks.*;
```

## Generar informe del proyecto – crear objeto de proyecto java
La clase `Project` representa un archivo de Microsoft Project en memoria, exponiendo tareas, recursos y datos personalizados. Instanciar esta clase le brinda un contenedor para todos los elementos del proyecto que definirá.

```java
Project project = new Project();
```

La línea anterior **crea un objeto de proyecto java** que comienza vacío y listo para personalizarse.

## Cómo agregar un atributo extendido
La clase `ExtendedAttributeDefinition` define un campo personalizado que puede adjuntarse a las tareas. Para agregar un atributo extendido, cree una instancia de esta clase con tipo `Number`, asígnele un alias como “Sine”, añádalo a la colección `ExtendedAttributes` del proyecto y luego vincúlelo a cada tarea que requiera el campo personalizado.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aquí **agregamos un atributo extendido** de tipo `Number` llamado “Sine” y lo asociamos con las tareas.

## Agregar el atributo extendido al proyecto
Registre la definición del atributo en el proyecto para que cada tarea pueda referenciarlo.

```java
project.getExtendedAttributes().add(attr);
```

## Crear una nueva tarea
`Task` representa un elemento de trabajo en el proyecto y puede contener campos personalizados.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Agregar tarea de campo personalizado al proyecto
Vincule el atributo extendido definido previamente a la tarea recién creada, proporcionando a la tarea un campo personalizado “Sine” que puede usar en fórmulas o cálculos.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ahora la tarea contiene un campo personalizado “Sine” que puede usar en fórmulas o cálculos. Así es también como **agrega datos de tarea de campo personalizado** de forma programática.

## ¿Por qué usar funciones de evaluación?
Las funciones de evaluación le permiten incrustar fórmulas nativas de Microsoft Project (p. ej., `Sin([Start])`) directamente en Aspose.Tasks, habilitando cálculos en tiempo real sin procesamiento externo. Esto mantiene toda la lógica del proyecto en un solo lugar, reduce errores de sincronización de datos y acelera la generación de informes. Aspose.Tasks soporta la evaluación de más de 100 funciones de MS Project, proporcionando un motor de cálculo completo dentro de Java.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **La fórmula devuelve `NaN`** | Verifique que el tipo de campo personalizado coincida con el tipo numérico esperado. |
| **Atributo extendido no visible** | Asegúrese de que la definición del atributo se añada al proyecto **antes** de crear las tareas. |
| **Excepción de licencia** | Instale una licencia temporal o completa de **Aspose.Tasks**; el modo de prueba puede limitar ciertas funciones. |
| **Licencia temporal faltante** | Obtenga una **licencia temporal de Aspose** desde el sitio web de Aspose. |

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar fórmulas complejas de MS Project?**  
A: Sí, Aspose.Tasks for Java soporta la evaluación de una amplia gama de funciones de MS Project, permitiendo cálculos complejos dentro de aplicaciones Java.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de archivos de Microsoft Project?**  
A: Sí, Aspose.Tasks for Java admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.

**Q: ¿Puedo probar Aspose.Tasks for Java antes de comprar?**  
A: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks for Java desde la página [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?**  
A: Puede obtener soporte en el foro de la comunidad de Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: ¿Existe una licencia temporal disponible para Aspose.Tasks for Java?**  
A: Sí, puede obtener una licencia temporal para pruebas desde la página de Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Conclusión
Al seguir estos pasos ha aprendido a **crear un objeto de proyecto**, **agregar un atributo extendido** y aprovechar las funciones de evaluación para **generar informes de proyecto** automáticamente. Ahora puede ampliar esta base para crear análisis de proyecto más avanzados, paneles personalizados o herramientas de programación automatizada, todo impulsado por Aspose.Tasks for Java.

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## Tutoriales relacionados

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}