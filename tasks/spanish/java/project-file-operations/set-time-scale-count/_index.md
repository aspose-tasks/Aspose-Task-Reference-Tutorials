---
date: 2026-03-29
description: Aprende a crear archivos PDF de proyectos mientras personalizas el recuento
  de la escala de tiempo del diagrama de Gantt usando Aspose.Tasks para Java. Esta
  guía te muestra paso a paso cómo exportar el Gantt a PDF con control total.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crear PDF del proyecto – Personalizar la escala de tiempo del diagrama de Gantt
url: /es/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PDF de proyecto – Personalizar escala de tiempo del diagrama de Gantt

## Introducción
Si necesita **crear PDF de proyecto** archivos que reflejen un diagrama de Gantt perfectamente ajustado, controlar el recuento de la escala de tiempo es la clave. Con Aspose.Tasks for Java puede establecer programáticamente los niveles inferior y medio de la escala de tiempo, ocultar las marcas de graduación y luego **guardar proyecto como PDF** para una fácil distribución. En este tutorial recorreremos todo lo que necesita, desde configurar el entorno de desarrollo hasta generar un PDF pulido que muestre su vista de Gantt personalizada.

## Respuestas rápidas
- **¿Qué significa “personalizar diagrama de Gantt”?** Ajustar los niveles de la escala de tiempo, colores y diseño para que coincidan con sus necesidades de informes.  
- **¿Qué método de API establece el recuento del nivel inferior?** `view.getBottomTimescaleTier().setCount(int)`.  
- **¿Puedo generar un PDF directamente desde el proyecto?** Sí—utilice `project.save(..., SaveFileFormat.Pdf)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial; hay una versión de prueba gratuita disponible.  
- **¿Qué versión de Java es compatible?** Java 8 o superior funciona con la última biblioteca Aspose.Tasks.

## ¿Qué es “personalizar diagrama de Gantt” en Aspose.Tasks?
Personalizar un diagrama de Gantt significa alterar programáticamente sus componentes visuales —como intervalos de la escala de tiempo, marcas de graduación y barras de tareas— para que el diagrama se ajuste a la forma en que desea **gestionar la visualización del proyecto**. Al cambiar el recuento de la escala de tiempo, controla cuántos días, semanas o meses representa cada segmento, haciendo el diagrama más claro para diferentes audiencias.

## ¿Por qué crear PDF de proyecto con un diagrama de Gantt personalizado?
- **Salida lista para interesados:** El PDF es universalmente visible, asegurando que todos vean el mismo diseño de cronograma.  
- **Amigable para impresión:** El control preciso de los niveles de la escala de tiempo evita impresiones abarrotadas o ambiguas.  
- **Automatización:** Integre la generación de PDF en pipelines CI o servicios de informes para cero esfuerzo manual.  

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Entorno de desarrollo Java** – JDK 8 o superior instalado.  
2. **Biblioteca Aspose.Tasks for Java** – Descárguela desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **Conocimientos básicos de Java** – Familiaridad con la sintaxis de Java y conceptos orientados a objetos.

## Importar paquetes
Importe las clases necesarias en su proyecto Java:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Guía paso a paso

### Paso 1: Establecer directorio de datos
Defina dónde se leerán y escribirán los archivos de su proyecto:

```java
String dataDir = "Your Data Directory";
```

Reemplace `"Your Data Directory"` con la ruta absoluta en su máquina.

### Paso 2: Crear una nueva instancia de Project
Instancie un nuevo objeto `Project` que contendrá todas las tareas y configuraciones de vista:

```java
Project project = new Project();
```

### Paso 3: Configurar la vista del diagrama de Gantt
Cree un objeto `GanttChartView` — aquí **generará código Java de vista Gantt** para controlar la apariencia del diagrama:

```java
GanttChartView view = new GanttChartView();
```

### Paso 4: Establecer el recuento de la escala de tiempo para el nivel inferior
Ajuste el nivel inferior para mostrar dos intervalos y ocultar las marcas de graduación:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Paso 5: Establecer el recuento de la escala de tiempo para el nivel medio
Aplique la misma configuración al nivel medio:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Paso 6: Añadir la vista personalizada al proyecto
Adjunte la vista que acaba de configurar a la instancia `Project`:

```java
project.getViews().add(view);
```

### Paso 7: Añadir tareas de ejemplo (datos de prueba)
Cree un par de tareas con duraciones específicas para ilustrar el diagrama de Gantt personalizado:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Paso 8: Guardar el proyecto como PDF
Finalmente, exporte el proyecto —incluyendo su **diagrama de Gantt personalizado**— a un archivo PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

El PDF resultante muestra cómo los niveles inferior y medio de la escala de tiempo han sido **personalizados**, ofreciendo a los interesados una vista clara e imprimible del cronograma.

## Problemas comunes y solución de problemas
- **El PDF está en blanco** – Asegúrese de que la ruta `dataDir` termine con un separador de archivos (`/` o `\`) y que el directorio exista.  
- **Las marcas siguen apareciendo** – Verifique que `setShowTicks(false)` se llame en ambos niveles.  
- **Duración no aplicada** – Confirme que está usando `TimeUnitType.Hour` (o la unidad apropiada) al crear duraciones.

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks for Java manejar archivos de proyecto a gran escala?**  
R: Sí, la biblioteca está optimizada para el procesamiento de alto rendimiento de datos de proyecto extensos.

**P: ¿Es Aspose.Tasks for Java compatible con diferentes IDEs de Java?**  
R: Absolutamente — funciona sin problemas con Eclipse, IntelliJ IDEA, NetBeans y otros IDEs populares.

**P: ¿Puedo personalizar la apariencia de los diagramas de Gantt más allá de la configuración de la escala de tiempo?**  
R: Sí, Aspose.Tasks ofrece amplias opciones de estilo como colores de barras, fuentes y líneas de cuadrícula.

**P: ¿Hay una versión de prueba disponible para Aspose.Tasks for Java?**  
R: Sí, puede obtener una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks for Java?**  
R: Puede encontrar soporte y asistencia en el foro de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**P: ¿Cómo cambio programáticamente el color de fondo del diagrama de Gantt?**  
R: Use el método `view.getGanttChartProperties().setBackgroundColor(Color)` después de importar `java.awt.Color`.

## Conclusión
Al seguir estos pasos ha aprendido cómo **crear PDF de proyecto** con una escala de tiempo del diagrama de Gantt totalmente personalizada, mejorar la **visualización del proyecto** y **guardar proyecto como PDF** usando Aspose.Tasks for Java. Este enfoque le brinda control total sobre la salida visual, facilitando compartir cronogramas claros y profesionales con su equipo o clientes.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}