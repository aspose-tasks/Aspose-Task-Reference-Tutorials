---
date: 2026-03-03
description: Aprenda a renumerar WBS en Aspose.Tasks para Java, gestione la descomposición
  del trabajo y personalice los códigos WBS de manera eficiente con ejemplos paso
  a paso.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo renumerar WBS en Aspose.Tasks para Java
url: /es/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo renumerar WBS en Aspose.Tasks para Java

## Introducción
Si necesitas **cómo renumerar WBS** en un archivo de Microsoft Project usando Aspose.Tasks para Java, estás en el lugar correcto. Este tutorial te guía a través de la lectura de los códigos WBS existentes, su personalización y luego la renumeración de la jerarquía para que tu proyecto permanezca organizado. Ya sea que estés limpiando un cronograma heredado o construyendo uno nuevo desde cero, dominar estos pasos te ayudará a **gestionar estructuras de desglose de trabajo** con confianza.

## Respuestas rápidas
- **¿Qué hace la renumeración de WBS?** Recalcula la numeración jerárquica de las tareas para reflejar cualquier cambio estructural.  
- **¿Qué clase realiza la renumeración?** `Project.renumberWBSCode`.  
- **¿Necesito una licencia para ejecutar el código?** Se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo personalizar el formato WBS?** Sí—usa `Task.set(Tsk.WBS, "...")` para asignar cualquier cadena que desees.  
- **¿Cuáles son los requisitos principales?** Java JDK, la biblioteca Aspose.Tasks para Java y un archivo de proyecto válido (.mpp).

## ¿Qué es una Estructura de Desglose del Trabajo (WBS)?
Una Estructura de Desglose del Trabajo (WBS) es una representación jerárquica de los entregables y tareas de un proyecto. Cada tarea recibe un código (p. ej., 1.2.3) que refleja su posición en la jerarquía. La renumeración se vuelve esencial cuando se añaden, eliminan o reordenan tareas, garantizando que los códigos permanezcan lógicos y fáciles de leer.

## ¿Por qué gestionar el desglose del trabajo y personalizar los códigos WBS?
- **Claridad:** Los códigos WBS claros facilitan a los interesados localizar tareas.  
- **Informes:** Muchas herramientas de generación de informes dependen de una numeración consistente.  
- **Flexibilidad:** Los códigos personalizados te permiten alinear la estructura del proyecto con los estándares internos.  

## Requisitos previos
Antes de sumergirnos en el código, confirma que tienes lo siguiente:

- Java Development Kit (JDK) instalado en tu máquina.  
- Biblioteca Aspose.Tasks para Java añadida a tu proyecto. Puedes obtenerla [aquí](https://releases.aspose.com/tasks/java/).  

## Importar paquetes
Asegúrate de importar los paquetes necesarios para iniciar tu proyecto:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Leer códigos WBS
Primero, leeremos los códigos WBS existentes para que puedas ver con qué estás trabajando.

### Paso 1: Cargar el proyecto
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Paso 2: Recopilar tareas
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Paso 3: Analizar y personalizar
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

El fragmento anterior imprime el WBS y nivel actuales de cada tarea, y luego muestra cómo **personalizar códigos WBS** asignando una nueva cadena.

## Renumerar códigos WBS de tareas
Ahora vamos a renumerar realmente la jerarquía WBS.

### Paso 1: Cargar el proyecto (Ejemplo de renumeración)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Paso 2: Seleccionar todas las tareas
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Paso 3: Mostrar códigos WBS iniciales
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Paso 4: Renumerar códigos WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Paso 5: Mostrar códigos WBS actualizados
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Al seguir estos pasos, podrás **renumerar WBS** de manera efectiva para cualquier conjunto de tareas en tu archivo de proyecto.

## Problemas comunes y soluciones
- **WBS no cambia después de la llamada `set`:** Asegúrate de estar trabajando con la instancia de tarea correcta y de que el proyecto se guarde después de las modificaciones.  
- **`renumberWBSCode` lanza una excepción:** Verifica que la lista de IDs coincida con el número de tareas de nivel superior; de lo contrario el método no podrá asignar los nuevos números correctamente.  
- **Faltan valores WBS:** Algunas tareas pueden tener un WBS `null` si fueron importadas de un archivo que no definía uno. Usa un valor alternativo antes de imprimir.  

## Preguntas frecuentes

**P: ¿Dónde puedo encontrar la documentación de Aspose.Tasks para Java?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/tasks/java/).

**P: ¿Cómo puedo descargar Aspose.Tasks para Java?**  
R: Puedes descargarlo [aquí](https://releases.aspose.com/tasks/java/).

**P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
R: Sí, puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?**  
R: Visita el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener soporte.

**P: ¿Puedo obtener una licencia temporal para Aspose.Tasks para Java?**  
R: Sí, obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Puedo renombrar el formato WBS después de la renumeración?**  
R: Por supuesto. Después de llamar a `renumberWBSCode`, puedes iterar sobre las tareas y aplicar `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` para adaptarlo a tus convenciones de nombres.

**P: ¿La renumeración afecta las dependencias de tareas?**  
R: No. El método solo actualiza la cadena WBS; los enlaces y restricciones de tareas permanecen sin cambios.

---

**Última actualización:** 2026-03-03  
**Probado con:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}