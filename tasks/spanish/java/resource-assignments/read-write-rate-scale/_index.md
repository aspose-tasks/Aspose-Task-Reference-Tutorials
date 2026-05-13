---
date: 2026-01-10
description: Aprenda a leer la escala de tarifas y gestionar asignaciones de recursos
  en Aspose.Tasks para Java. Defina recursos materiales, cómo establecer la escala
  y asignar recursos a la tarea.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo leer la escala de tarifas y escribir la escala de tarifas para asignaciones
  de recursos en Aspose.Tasks
url: /es/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer la escala de tarifas y escribir la escala de tarifas para asignaciones de recursos en Aspose.Tasks

En este tutorial descubrirá **cómo leer la escala de tarifas** y ajustarla para las asignaciones de recursos usando Aspose.Tasks para Java. Ya sea que esté creando un programador, una herramienta de informes, o simplemente necesite automatizar actualizaciones de proyectos, dominar la manipulación de la escala de tarifas le brinda un control fino sobre los recursos materiales y de trabajo.

## Respuestas rápidas
- **¿Cuál es la clase principal para el manejo de tarifas?** `ResourceAssignment` con la propiedad `Asn.RATE_SCALE`.  
- **¿Qué enum define las opciones de escala?** `RateScaleType` (Day, Week, Month, etc.).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una licencia de evaluación gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar la escala después de guardar?** Sí – recargue el proyecto y modifique `Asn.RATE_SCALE` como se muestra.  
- **¿IDE compatibles?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, NetBeans) puede compilar el código.

## ¿Qué es la escala de tarifas?
La escala de tarifas determina la unidad de tiempo (día, semana, mes, etc.) a la que se aplica la tarifa de costo de un recurso. Ajustar la escala le permite modelar el consumo de material o el esfuerzo laboral con precisión.

## ¿Por qué leer y escribir la escala de tarifas?
Leer la escala actual le ayuda a auditar los cronogramas existentes, mientras que escribir una nueva escala le permite alinear los recursos con las políticas de facturación o consumo del proyecto. Esto es especialmente útil al **definir recursos materiales** o cuando necesita **establecer la escala** para calendarios de trabajo no estándar.

## Requisitos previos
Antes de comenzar, asegúrese de cumplir los siguientes requisitos:
1. **Entorno de desarrollo Java** – JDK 8 o superior instalado.  
2. **Biblioteca Aspose.Tasks para Java** – Descargue e instale la biblioteca desde [aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importe las clases necesarias de Aspose.Tasks.

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

## Paso 1: Configurar su proyecto Java
Cree un proyecto Maven o Gradle y añada el JAR de Aspose.Tasks a su classpath. Este paso garantiza que el compilador pueda localizar las clases importadas.

## Paso 2: Cargar el archivo de proyecto
Cargue el archivo Microsoft Project existente con el que desea trabajar.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Paso 3: Añadir una tarea
Cree una nueva tarea que más adelante recibirá asignaciones de recursos.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Paso 4: Definir recursos
Aquí **definimos un recurso material** y un recurso de trabajo regular. Observe el uso de `ResourceType.Material` para el recurso de tipo material.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Paso 5: Asignar recursos a la tarea
Ahora **asignamos recursos a la tarea** y especificamos **cómo establecer la escala** usando `RateScaleType.Week`. Esto ilustra tanto la lectura como la escritura de la escala de tarifas.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Paso 6: Guardar el proyecto
Guarde los cambios en un nuevo archivo para que luego podamos verificar la escala de tarifas almacenada.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Paso 7: Recuperar asignaciones de recursos
Recargue el proyecto guardado y **lea la escala de tarifas** para confirmar que se escribió correctamente.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Errores comunes y consejos
- **Desajuste de UID** – Al recuperar asignaciones por UID, asegúrese de que los valores de UID coincidan con los asignados durante la creación.  
- **Tipo de recurso incorrecto** – Usar `ResourceType.Material` para un recurso de trabajo hará que los cálculos de tarifas se comporten de manera inesperada.  
- **Formato de guardado** – Siempre guarde usando `SaveFileFormat.Mpp` (u otro formato compatible) para preservar campos personalizados como la escala de tarifas.

## Conclusión
Gestionar e inspeccionar la escala de tarifas para asignaciones de recursos en Aspose.Tasks para Java es sencillo una vez que conoce las clases y propiedades relevantes. Siguiendo esta guía, podrá **leer la información de tarifas**, **definir objetos de recurso material**, **establecer la escala** y **asignar recursos a la tarea** con confianza.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks para Java con cualquier IDE de Java?**  
A: Sí, Aspose.Tasks para Java es compatible con todos los IDE de Java principales, incluidos IntelliJ IDEA, Eclipse y NetBeans.

**Q: ¿Aspose.Tasks admite otros formatos de archivo además de MPP?**  
A: Sí, Aspose.Tasks admite varios formatos de archivo, incluidos MPP, XML y HTML.

**Q: ¿Aspose.Tasks es adecuado para la gestión de proyectos a nivel empresarial?**  
A: Absolutamente, Aspose.Tasks ofrece funciones integrales para gestionar proyectos de cualquier escala, lo que lo hace adecuado para la gestión de proyectos a nivel empresarial.

**Q: ¿Puedo personalizar más las asignaciones de recursos más allá de la escala de tarifas?**  
A: Sí, Aspose.Tasks brinda amplias capacidades para personalizar las asignaciones de recursos, incluyendo ajustes de costo, trabajo y duración.

**Q: ¿Existe un foro comunitario para soporte de Aspose.Tasks?**  
A: Sí, puede encontrar soporte e interactuar con otros usuarios en el foro de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-01-10  
**Probado con:** Aspose.Tasks para Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}