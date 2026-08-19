---
date: 2026-02-26
description: Aprenda cómo reanudar y detener tareas en Aspose.Tasks para Java, incluyendo
  el filtrado de tareas por fecha para un control preciso del proyecto.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo reanudar una tarea y detener una tarea en Aspose.Tasks
url: /es/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo reanudar una tarea y detener una tarea en Aspose.Tasks

## Introducción
Si estás construyendo una solución de gestión de proyectos basada en Java, a menudo necesitarás **pausar** una tarea temporalmente y luego **continuarla** más tarde. Aspose.Tasks for Java facilita esto con propiedades integradas para detener y reanudar tareas. En este tutorial descubrirás **cómo reanudar una tarea** y **cómo detener una tarea** programáticamente, y también verás cómo **filtrar tareas por fecha** para trabajar solo con los elementos relevantes en tu cronograma.

## Respuestas rápidas
- **¿Qué significa “stop” (detener) para una tarea?** Establece una fecha de detención, pausando el trabajo después de ese punto.  
- **¿Cómo puedo reanudar una tarea detenida?** Asignando una fecha de reanudación posterior a la fecha de detención.  
- **¿Puedo limitar la operación a un rango de fechas?** Sí – usa una fecha mínima para filtrar tareas.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Tasks for Java (la API permanece estable).  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.

## ¿Qué es “cómo reanudar una tarea” en Aspose.Tasks?
Reanudar una tarea simplemente significa proporcionar una fecha **RESUME** en un objeto `Task`. Cuando el motor del proyecto procesa el cronograma, el trabajo continuará a partir de esa fecha. Esto es especialmente útil para manejar interrupciones como la indisponibilidad de recursos o dependencias externas.

## ¿Por qué usar la función de detener/reanudar?
- **Control sobre los cronogramas:** Pausar el trabajo sin eliminar la tarea.  
- **Informes precisos:** Mostrar fechas de inicio/fin realistas en los diagramas de Gantt.  
- **Automatización fácil:** Combinar con filtros de fechas para actualizar muchas tareas a la vez.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Un sólido dominio de los fundamentos de Java.  
- JDK instalado en tu máquina.  
- La biblioteca Aspose.Tasks for Java añadida a tu proyecto (descárgala desde [here](https://releases.aspose.com/tasks/java/)).  

## Importar paquetes
Primero, trae las clases requeridas al alcance para que puedas trabajar con proyectos y tareas.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Paso 1: Inicializar el proyecto y el recopilador
Crea una instancia de `Project` que apunte a tu archivo MPP y configura un `ChildTasksCollector` para recopilar cada tarea en la jerarquía.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Paso 2: Definir una fecha mínima para el filtrado
Si solo deseas trabajar con tareas que tengan fechas de detención o reanudación significativas, define una **fecha mínima**. Este es el núcleo de la técnica de *filtrar tareas por fecha*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Paso 3: Iterar, comprobar y mostrar los valores de Detener/Reanudar
Ahora recorre las tareas recopiladas, aplica la lógica de **cómo detener una tarea**, y muestra las fechas. El código también demuestra **cómo reanudar una tarea** leyendo la propiedad `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Consejo profesional:** Reemplaza las llamadas a `System.out.println` con tu propia lógica (p. ej., actualizar las fechas, registrar en un archivo o modificar los objetos de tarea) para *detener* o *reanudar* tareas según sea necesario.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | La tarea no tiene una fecha de detención establecida. | Verificar `null` antes de llamar a `.before(minDate)`. |
| Dates appear as `NA` even after setting | La fecha mínima es demasiado reciente. | Utiliza una `minDate` anterior o elimina el filtro. |
| Changes not reflected in the saved MPP | El proyecto no se guardó después de las modificaciones. | Llama a `project.save("output.mpp");` después de actualizar las tareas. |

## Preguntas frecuentes

### ¿Es Aspose.Tasks for Java adecuado para proyectos a gran escala?
¡Absolutamente! Aspose.Tasks for Java está diseñado para manejar proyectos de diferentes tamaños, garantizando eficiencia y fiabilidad.

### ¿Puedo personalizar la fecha para detener y reanudar tareas?
Sí, el ejemplo proporcionado permite flexibilidad al establecer la fecha mínima según los requisitos de tu proyecto.

### ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks for Java?
Visita el [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) para soporte comunitario y discusiones.

### ¿Hay una prueba gratuita disponible para Aspose.Tasks for Java?
Sí, puedes acceder a la [prueba gratuita](https://releases.aspose.com/) para explorar las funciones antes de realizar una compra.

### ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks for Java?
Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para propósitos de prueba.

**Preguntas y respuestas adicionales**

**P: ¿Cómo establezco realmente una nueva fecha de detención para una tarea?**  
R: Usa `tsk.set(Tsk.STOP, new Date(...));` y luego guarda el proyecto.

**P: ¿Puedo filtrar tareas por un rango específico en lugar de solo una fecha mínima?**  
R: Sí—compara tanto `before` como `after` con tus fechas de inicio y fin.

**P: ¿La API recalcula automáticamente el cronograma después de cambiar las fechas de detención/reanudación?**  
R: Después de modificar las fechas, llama a `project.calculateCriticalPath();` para actualizar el cronograma.

## Conclusión
En esta guía cubrimos **cómo reanudar una tarea** y **cómo detener una tarea** usando Aspose.Tasks for Java, junto con un método práctico para **filtrar tareas por fecha**. Al integrar estos fragmentos en tu aplicación, obtienes un control granular sobre los cronogramas del proyecto y puedes automatizar ajustes del cronograma con confianza.

---

**Última actualización:** 2026-02-26  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}