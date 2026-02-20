---
date: 2026-02-20
description: Explora cómo agregar una tarea a un proyecto y gestionar duraciones con
  Aspose.Tasks para Java. Aprende cómo establecer la duración y cómo convertirla fácilmente.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Agregar tarea al proyecto y gestionar duraciones con Aspose.Tasks
url: /es/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar Tarea al Proyecto y Gestionar Duraciones con Aspose.Tasks

## Introducción
En este tutorial aprenderá **cómo agregar una tarea al proyecto** y controlar su duración usando Aspose.Tasks para Java. Ya sea que esté creando una nueva herramienta de planificación de proyectos o ampliando una solución existente, dominar el manejo de la duración de tareas es esencial para una programación y generación de informes precisas.

## Respuestas rápidas
- **¿Qué significa “add task to project”?** Crea un nuevo objeto Task bajo la raíz del proyecto o bajo una tarea resumen específica.  
- **¿Qué clase representa una duración?** `com.aspose.tasks.Duration`.  
- **¿Cómo establecer la duración?** Use `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **¿Puedo convertir una duración a otra unidad?** Sí, llame a `duration.convert(TimeUnitType.Hour)` o cualquier otro `TimeUnitType`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.Tasks para uso comercial.

## ¿Qué es “add task to project”?
Agregar una tarea a un proyecto significa crear un objeto `Task` y adjuntarlo a la jerarquía de tareas del proyecto. Esta operación es el primer paso antes de que pueda definir trabajo, recursos o duración para esa tarea.

## ¿Por qué gestionar las duraciones de las tareas?
Las duraciones precisas impulsan cronogramas realistas, asignación de recursos y análisis de la ruta crítica. Con Aspose.Tasks puede establecer, leer, convertir y ajustar duraciones programáticamente, dándole control total sobre los horarios del proyecto.

## Requisitos previos
Antes de comenzar, asegúrese de contar con lo siguiente:

- Java Development Kit (JDK): Asegúrese de que tiene Java instalado en su máquina. Puede descargarlo [aquí](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteca Aspose.Tasks: Descargue e incluya la biblioteca Aspose.Tasks en su proyecto. Puede encontrar la biblioteca [aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para trabajar con Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Paso 1: Configurar su proyecto
```java
// Create a new project
Project project = new Project();
```

## Paso 2: Agregar una nueva tarea (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Cómo establecer la duración
Ahora que la tarea existe, puede definir su longitud. Por defecto, las duraciones se expresan en días.

## Paso 3: Obtener y convertir la duración de la tarea
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Cómo convertir la duración
El método `convert` le permite traducir un `Duration` de un `TimeUnitType` a otro (p. ej., días → horas, semanas → días).

## Paso 4: Actualizar la duración de la tarea a 1 semana
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Paso 5: Disminuir la duración de la tarea
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Al seguir estos pasos, ha **agregado una tarea a un proyecto** y gestionado su duración usando Aspose.Tasks para Java.

## Problemas comunes y consejos
- **Problema:** Olvidar convertir la duración antes de realizar operaciones aritméticas puede producir resultados incorrectos. Siempre verifique la unidad con `duration.getTimeUnit()`.
- **Consejo:** Use `project.getDuration(value, TimeUnitType)` para crear duraciones en la unidad deseada en lugar de convertirlas después.
- **Problema:** Establecer una duración negativa lanzará una excepción. Asegúrese de validar los valores de entrada.

## Conclusión
En esta guía cubrimos cómo **agregar una tarea al proyecto**, leer su duración predeterminada, **establecer la duración** y **convertir la duración** a diferentes unidades de tiempo. Ahora puede integrar estas técnicas en aplicaciones de programación más amplias para una planificación de proyectos precisa.

## Preguntas frecuentes
### ¿Es Aspose.Tasks compatible con todas las versiones de Java?
Aspose.Tasks es compatible con Java 6 y versiones posteriores.

### ¿Puedo usar Aspose.Tasks para proyectos comerciales?
Sí, puede usar Aspose.Tasks tanto para proyectos personales como comerciales. Visite [aquí](https://purchase.aspose.com/buy) para obtener detalles de la licencia.

### ¿Dónde puedo encontrar soporte y recursos adicionales?
Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener soporte de la comunidad y discusiones.

### ¿Cómo puedo obtener una licencia temporal para propósitos de prueba?
Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/) para pruebas y evaluación.

### ¿Hay una prueba gratuita disponible para Aspose.Tasks?
Sí, puede acceder a la prueba gratuita [aquí](https://releases.aspose.com/) para explorar Aspose.Tasks antes de realizar una compra.

## Preguntas frecuentes

**Q: ¿Cómo cambio la duración de una tarea después de haberla establecido?**  
A: Recupere la duración actual con `task.get(Tsk.DURATION)`, modifíquela (p. ej., `add`, `subtract` o `convert`) y luego restablézcala usando `task.set(Tsk.DURATION, newDuration)`.

**Q: ¿Puedo establecer una duración en minutos?**  
A: Sí, use `TimeUnitType.Minute` al llamar a `project.getDuration(value, TimeUnitType.Minute)`.

**Q: ¿Cambiar la duración actualiza automáticamente las fechas de inicio y fin de la tarea?**  
A: Solo si el modo de programación del proyecto está configurado como automático. De lo contrario, es posible que deba recalcular el cronograma con `project.calculateCriticalPath()`.

**Q: ¿Es posible obtener la duración como un número bruto?**  
A: Llame a `duration.getTimeSpan()` para obtener el valor numérico en la unidad de tiempo actual.

**Q: ¿Qué ocurre si resto más que la duración actual?**  
A: La API lanzará una `ArgumentOutOfRangeException`. Siempre valide que la duración resultante siga siendo positiva.

---

**Última actualización:** 2026-02-20  
**Probado con:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}