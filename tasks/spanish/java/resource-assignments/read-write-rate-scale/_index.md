---
date: 2026-06-10
description: Aprenda cómo leer la tarifa y cómo escribir Rate Scale para asignaciones
  de recursos usando Aspose.Tasks para Java. Soporta recursos materiales, múltiples
  formatos y proyectos grandes.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Leer y escribir Rate Scale para asignaciones de recursos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo leer Rate Scale y escribir Rate Scale para asignaciones de recursos en
  Aspose.Tasks
url: /es/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer la escala de tarifas y escribir la escala de tarifas para asignaciones de recursos en Aspose.Tasks

En este tutorial descubrirás **cómo leer la escala de tarifas** y ajustarla para asignaciones de recursos usando Aspose.Tasks para Java. Ya sea que estés construyendo un programador, una herramienta de informes, o simplemente necesites automatizar actualizaciones de proyectos, dominar la manipulación de la escala de tarifas te brinda un control detallado sobre los recursos materiales y de trabajo.

## Respuestas rápidas
`ResourceAssignment` vincula una tarea a un recurso y contiene datos específicos de la asignación.  
`Asn` contiene constantes para los campos de asignación, incluido `RATE_SCALE`.  
`RateScaleType` enum enumera posibles unidades de tiempo para la escala de tarifas.  

- **¿Cuál es la clase principal para el manejo de tarifas?** `ResourceAssignment` con la propiedad `Asn.RATE_SCALE`.  
- **¿Qué enum define las opciones de escala?** `RateScaleType` (Day, Week, Month, etc.).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una licencia de evaluación gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar la escala después de guardar?** Sí – recarga el proyecto y modifica `Asn.RATE_SCALE` como se muestra.  
- **¿IDEs compatibles?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, NetBeans) puede compilar el código.

## Cómo leer la escala de tarifas para asignaciones de recursos?

Carga el proyecto, localiza la `ResourceAssignment` deseada y llama a `getRateScale()` – esto devuelve un valor `RateScaleType` que indica si la tarifa se aplica por día, semana, mes u otra unidad. La respuesta es inmediata y requiere solo dos llamadas a la API, lo que lo hace ideal para scripts de auditoría o visualizaciones en la UI.

## Cómo escribir la escala de tarifas para asignaciones de recursos?

Crea o recupera un objeto `ResourceAssignment`, establece su propiedad `Asn.RATE_SCALE` al `RateScaleType` deseado (p. ej., `RateScaleType.Week`), y luego guarda el proyecto. Este único cambio de propiedad actualiza automáticamente los cálculos de costos y se mantiene en todos los formatos de archivo compatibles. Después de establecer la escala, también puede ser necesario ajustar la tarifa estándar o la tarifa de horas extra del recurso para reflejar la nueva unidad de tiempo, garantizando que los cálculos de costos sigan siendo precisos.

## Qué es la escala de tarifas?

La escala de tarifas determina la unidad de tiempo (día, semana, mes, etc.) a la que se aplica la tarifa de costo de un recurso. Ajustar la escala permite modelar con precisión el consumo de material o el esfuerzo laboral. Por ejemplo, establecer la escala a Week significa que la tarifa de costo se interpreta como costo por semana, y el costo total de una tarea se calcula en función del número de semanas que el recurso está asignado.

## Por qué leer y escribir la escala de tarifas?

Leer la escala actual te ayuda a auditar los cronogramas existentes, mientras que escribir una nueva escala te permite alinear los recursos con las políticas de facturación o consumo del proyecto. Esto es especialmente útil al **definir costos de recursos materiales** o cuando necesitas **establecer la escala** para calendarios de trabajo no estándar.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. **Entorno de desarrollo Java** – JDK 8 o superior instalado.  
2. **Biblioteca Aspose.Tasks para Java** – Descarga e instala la biblioteca desde [aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
La clase `ResourceAssignment` representa un vínculo entre una tarea y un recurso, mientras que `RateScaleType` enumera las posibles unidades de tiempo para una tarifa. Importa las clases necesarias de Aspose.Tasks antes de comenzar a programar.

`Project` es el objeto principal que carga y guarda archivos de Microsoft Project.  
`Resource` define un recurso del proyecto, como trabajo o material.  
`ResourceType` enum especifica si un recurso es de trabajo o material.  
`Task` representa un elemento de trabajo en el cronograma del proyecto.  
`SaveFileFormat` enum define el formato de salida para guardar un proyecto.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Paso 1: Configura tu proyecto Java
Crea un proyecto Maven o Gradle y agrega el JAR de Aspose.Tasks a tu classpath. Este paso asegura que el compilador pueda localizar las clases importadas.

## Paso 2: Cargar el archivo del proyecto
Carga el archivo de Microsoft Project existente con el que deseas trabajar.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Paso 3: Añadir una tarea
Crea una nueva tarea que luego recibirá asignaciones de recursos.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Paso 4: Definir recursos
Aquí **definimos un recurso material** y un recurso de trabajo regular. Observa el uso de `ResourceType.Material` para el recurso de tipo material.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Paso 5: Asignar recursos a la tarea
Ahora **asignamos recursos a la tarea** y especificamos el **cómo establecer la escala** usando `RateScaleType.Week`. Esto ilustra tanto la lectura como la escritura de la escala de tarifas.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Paso 6: Guardar el proyecto
Persistir los cambios en un nuevo archivo para que luego podamos verificar la escala de tarifas almacenada.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Paso 7: Recuperar asignaciones de recursos
Recarga el proyecto guardado y **lee la escala de tarifas** para confirmar que se escribió correctamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Errores comunes y consejos
- **Desajuste de UID** – Al recuperar asignaciones por UID, asegúrate de que los valores de UID coincidan con los asignados durante la creación.  
- **Tipo de recurso incorrecto** – Usar `ResourceType.Material` para un recurso de trabajo hará que los cálculos de tarifas se comporten de manera inesperada.  
- **Formato de guardado** – Siempre guarda usando `SaveFileFormat.Mpp` (u otro formato compatible) para preservar campos personalizados como la escala de tarifas.  
- **Proyectos grandes** – Aspose.Tasks puede procesar archivos con **más de 500 páginas** sin cargar todo el documento en memoria, gracias a su arquitectura de streaming.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java con cualquier IDE de Java?**  
R: Sí, Aspose.Tasks para Java es compatible con todos los IDEs principales de Java, incluidos IntelliJ IDEA, Eclipse y NetBeans.

**P: ¿Aspose.Tasks admite otros formatos de archivo además de MPP?**  
R: Sí, Aspose.Tasks admite varios formatos de archivo, incluidos MPP, XML y HTML.

**P: ¿Aspose.Tasks es adecuado para la gestión de proyectos a nivel empresarial?**  
R: Absolutamente, Aspose.Tasks ofrece funciones integrales para gestionar proyectos de cualquier escala, lo que lo hace adecuado para la gestión de proyectos a nivel empresarial.

**P: ¿Puedo personalizar más las asignaciones de recursos más allá de la escala de tarifas?**  
R: Sí, Aspose.Tasks brinda amplias capacidades para personalizar las asignaciones de recursos, incluidos ajustes de costo, trabajo y duración.

**P: ¿Existe un foro comunitario para soporte de Aspose.Tasks?**  
R: Sí, puedes encontrar soporte e interactuar con otros usuarios en el foro de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-06-10  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Cómo modificar asignaciones – Leer recursos compartidos con Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [Cómo agregar notas a asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}