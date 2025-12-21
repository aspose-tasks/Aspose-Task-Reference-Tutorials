---
date: 2025-12-21
description: Aprenda a personalizar vistas de diagramas de Gantt, gestionar la visualización
  del proyecto y guardar el proyecto como PDF usando Aspose.Tasks para Java. Ajuste
  la cantidad de escala de tiempo sin esfuerzo.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Personalizar diagrama de Gantt – Dominando el recuento de escala de tiempo
  de MS Project en Aspose.Tasks
url: /es/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalizar diagrama de Gantt – Dominando el recuento de escala de tiempo de MS Project en Aspose.Tasks

## Introducción
Si necesita **personalizar el diagrama de Gantt** en Microsoft Project, controlar el recuento de la escala de tiempo es una técnica clave. Con Aspose.Tasks for Java puede establecer programáticamente los niveles inferior y medio de la escala de tiempo, afinar la visibilidad de los ticks y luego **guardar el proyecto como PDF** para compartirlo con los interesados. Este tutorial lo guía a través de todo el proceso, desde la configuración del entorno hasta la generación de un PDF pulido que refleja su vista de Gantt personalizada.

## Respuestas rápidas
- **¿Qué significa “customize Gantt chart”?** Ajustar los niveles de escala de tiempo, colores y diseño para que coincidan con sus necesidades de informes.  
- **¿Qué método de API establece el recuento del nivel inferior?** `view.getBottomTimescaleTier().setCount(int)`.  
- **¿Puedo generar un PDF directamente desde el proyecto?** Sí—utilice `project.save(..., SaveFileFormat.Pdf)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial; hay una versión de prueba gratuita disponible.  
- **¿Qué versión de Java es compatible?** Java 8 o superior funciona con la última biblioteca Aspose.Tasks.

## ¿Qué es “customize Gantt chart” en Aspose.Tasks?
Personalizar un diagrama de Gantt significa alterar programáticamente sus componentes visuales —como intervalos de escala de tiempo, marcas de ticks y barras de tareas— para que el diagrama se alinee con la forma en que desea **gestionar la visualización del proyecto**. Al cambiar el recuento de la escala de tiempo, controla cuántos días, semanas o meses representa cada segmento, haciendo el diagrama más claro para diferentes audiencias.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Entorno de desarrollo Java** – JDK 8 o más reciente instalado.  
2. **Biblioteca Aspose.Tasks for Java** – Descárguela desde [here](https://releases.aspose.com/tasks/java/).  
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

### Paso 1: Establecer el directorio de datos
Defina dónde se leerán y escribirán sus archivos de proyecto:

```java
String dataDir = "Your Data Directory";
```

Reemplace `"Your Data Directory"` con la ruta absoluta en su máquina.

### Paso 2: Crear una nueva instancia de Project
Instancie un objeto `Project` nuevo que contendrá todas las tareas y configuraciones de vista:

```java
Project project = new Project();
```

### Paso 3: Configurar la vista del diagrama de Gantt
Cree un objeto `GanttChartView`; aquí generará el código **generate Gantt view Java** para controlar la apariencia del diagrama:

```java
GanttChartView view = new GanttChartView();
```

### Paso 4: Establecer el recuento de escala de tiempo para el nivel inferior
Ajuste el nivel inferior para mostrar dos intervalos y ocultar las marcas de ticks:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Paso 5: Establecer el recuento de escala de tiempo para el nivel medio
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

El PDF resultante demuestra cómo los niveles inferior y medio de la escala de tiempo han sido **personalizados**, ofreciendo a los interesados una vista clara e imprimible del cronograma.

## Problemas comunes y solución de problemas
- **El PDF está en blanco** – Asegúrese de que la ruta `dataDir` termine con un separador de archivos (`/` o `\`) y de que el directorio exista.  
- **Los ticks siguen apareciendo** – Verifique que `setShowTicks(false)` se haya llamado en ambos niveles.  
- **La duración no se aplicó** – Confirme que está usando `TimeUnitType.Hour` (o la unidad apropiada) al crear duraciones.

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar archivos de proyecto a gran escala?**  
A: Sí, la biblioteca está optimizada para el procesamiento de alto rendimiento de datos de proyecto extensos.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes IDEs de Java?**  
A: Absolutamente — funciona sin problemas con Eclipse, IntelliJ IDEA, NetBeans y otros IDEs populares.

**Q: ¿Puedo personalizar la apariencia de los diagramas de Gantt más allá de la configuración de la escala de tiempo?**  
A: Sí, Aspose.Tasks ofrece amplias opciones de estilo como colores de barras, fuentes y líneas de cuadrícula.

**Q: ¿Existe una versión de prueba disponible para Aspose.Tasks for Java?**  
A: Sí, puede obtener una versión de prueba gratuita desde [here](https://releases.aspose.com/).

**Q: ¿Dónde puedo obtener soporte para Aspose.Tasks for Java?**  
A: Puede encontrar soporte y asistencia en el foro de Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: ¿Cómo cambio programáticamente el color de fondo del diagrama de Gantt?**  
A: Use el método `view.getGanttChartProperties().setBackgroundColor(Color)` después de importar `java.awt.Color`.

## Conclusión
Al seguir estos pasos ha aprendido a **personalizar los niveles de escala de tiempo del diagrama de Gantt**, mejorar la **visualización del proyecto** y **guardar el proyecto como PDF** usando Aspose.Tasks for Java. Este enfoque le brinda control total sobre la salida visual, facilitando la compartición de cronogramas claros y profesionales con su equipo o clientes.

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}