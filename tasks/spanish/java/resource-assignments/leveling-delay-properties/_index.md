---
date: 2026-01-07
description: Aprenda cómo agregar recursos a un proyecto y manejar las propiedades
  de retraso de nivelación para asignaciones de recursos usando Aspose.Tasks para
  Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo agregar un recurso al proyecto y manejar las propiedades de retraso de
  nivelación en Aspose.Tasks
url: /es/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar recurso al proyecto y manejar propiedades de retraso de nivelación en Aspose.Tasks

## Introducción
En este tutorial, aprenderás **cómo agregar recurso al proyecto** mientras también gestionas las propiedades de retraso de nivelación para asignaciones de recursos con Aspose.Tasks para Java. Ya sea que estés construyendo un motor de programación o automatizando actualizaciones de proyectos, dominar estos pasos te permite mantener tus datos de proyecto precisos sin necesidad de tener Microsoft Project instalado.

## Respuestas rápidas
- **¿Qué significa “add resource to project”?** Crea una nueva entrada de recurso que puede asignarse a tareas.  
- **¿Puedo establecer un retraso de nivelación después de la asignación?** Sí, usando los campos `Asn.DELAY` o `Asn.LEVELING_DELAY`.  
- **¿Necesito una licencia para ejecutar este código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia de pago para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o posterior.  
- **¿Es compatible con todos los formatos de archivo de MS Project?** Aspose.Tasks admite .MPP, .XML, .XER y más.

## ¿Qué es “add resource to project” en Aspose.Tasks?
Agregar un recurso a un proyecto significa crear un objeto `Resource` dentro del modelo `Project`. Este objeto puede enlazarse posteriormente a tareas mediante `ResourceAssignment`, lo que te permite rastrear trabajo, costos y configuraciones de nivelación.

## ¿Por qué manejar las propiedades de retraso de nivelación?
El retraso de nivelación ayuda al planificador a distribuir el trabajo cuando los recursos están sobreasignados. Al establecer un retraso, le indicas al motor que posponga el inicio de una asignación, evitando conflictos y manteniendo el proyecto realista.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Java Development Kit (JDK): Asegúrate de tener instalado Java JDK en tu sistema. Puedes descargarlo e instalarlo desde el [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Descarga la biblioteca Aspose.Tasks for Java desde la [download page](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importa los paquetes necesarios en tu proyecto Java para usar las funcionalidades de Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Paso 1: Crear un objeto Project
Instancia un objeto `Project`, que servirá como contenedor para todas las tareas, recursos y asignaciones:
```java
Project prj = new Project();
```

## Paso 2: Crear una tarea
Agrega una tarea al proyecto. Esto demuestra **cómo agregar tarea** de forma programática:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Paso 3: Establecer la fecha de inicio y la duración de la tarea
Define cuándo comienza la tarea y cuánto tiempo se ejecutará:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Paso 4: Agregar un recurso
Ahora **agregamos recurso al proyecto** creando una nueva entrada `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Paso 5: Crear una asignación de recurso
Enlaza la tarea y el recurso recién agregado:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Paso 6: Establecer el retraso de nivelación
Configura el retraso de nivelación para la asignación. Establecerlo en cero significa que no hay retraso adicional, pero puedes ajustar el valor según sea necesario:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Paso 7: Mostrar resultados
Imprime las propiedades importantes para verificar que todo se haya configurado correctamente:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Problemas comunes y consejos
- **Problema:** Olvidar establecer la fecha de inicio de la tarea puede hacer que la asignación se establezca por defecto al inicio del proyecto.  
- **Consejo:** Usa `prj.getDuration(value, TimeUnitType.Day)` para controlar la granularidad del retraso.  
- **Consejo:** Después de agregar varios recursos, llama a `prj.updateResourceAssignments()` para que el planificador recalcule la nivelación.

## Conclusión
Al seguir estos pasos, ahora sabes **cómo agregar recurso al proyecto**, asignarlo a una tarea y gestionar las propiedades de retraso de nivelación usando Aspose.Tasks para Java. Este conocimiento te permite crear soluciones robustas de automatización de proyectos que se mantengan en sintonía con las limitaciones reales de recursos.

## Preguntas frecuentes
### Q: ¿Puedo usar Aspose.Tasks con otras bibliotecas Java?
A: Sí, Aspose.Tasks puede integrarse con otras bibliotecas Java para mejorar las capacidades de gestión de proyectos.

### Q: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?
A: Sí, Aspose.Tasks admite varias versiones de archivos de Microsoft Project, garantizando compatibilidad en diferentes entornos.

### Q: ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks?
A: Puedes encontrar soporte y recursos en el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q: ¿Puedo probar Aspose.Tasks antes de comprar?
A: Sí, puedes obtener una prueba gratuita de Aspose.Tasks desde la [releases page](https://releases.aspose.com/).

### Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks?
A: Puedes solicitar una licencia temporal en la [temporary license page](https://purchase.aspose.com/temporary-license/) para propósitos de evaluación.

## Preguntas frecuentes adicionales

**Q:** ¿Qué ocurre si establezco un retraso de nivelación distinto de cero?  
**A:** El planificador pospondrá el inicio de la asignación por la duración especificada, ayudando a resolver sobreasignaciones.

**Q:** ¿Puedo recuperar el retraso de nivelación después de guardar el proyecto?  
**A:** Sí, puedes volver a abrir el archivo del proyecto y leer la propiedad `Asn.DELAY` de la asignación.

**Q:** ¿Existe una forma de aplicar el retraso de nivelación a todas las asignaciones a la vez?  
**A:** Puedes iterar a través de `prj.getResourceAssignments()` y establecer el retraso para cada asignación en un bucle.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}