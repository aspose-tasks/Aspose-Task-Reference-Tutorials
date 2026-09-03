---
date: 2026-06-05
description: Aprenda cómo crear resource assignment con Aspose.Tasks para Java, añadir
  recursos a un proyecto y gestionar leveling delay properties.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Manejar Leveling Delay Properties para Resource Assignments en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Crear Resource Assignment con Aspose.Tasks para Java
url: /es/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear asignación de recursos con Aspose.Tasks para Java

En esta guía completa aprenderás **cómo crear asignación de recursos aspotasks** usando la biblioteca Aspose.Tasks para Java. Ya sea que estés construyendo un motor de programación personalizado, automatizando actualizaciones masivas de proyectos, o simplemente necesites manipular archivos de Microsoft Project sin la aplicación de escritorio, dominar estos pasos te permite mantener tus datos de proyecto precisos y totalmente controlables.

## Respuestas rápidas
- **¿Qué significa “add resource to project”?** Crea una nueva entrada de recurso que luego puede asignarse a tareas.  
- **¿Puedo establecer un retraso de nivelación después de la asignación?** Sí, usando los campos `Asn.DELAY` o `Asn.LEVELING_DELAY`.  
- **¿Necesito una licencia para ejecutar este código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia paga para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o posterior.  
- **¿Es compatible con todos los formatos de archivo de MS Project?** Aspose.Tasks admite más de 12 formatos, incluidos .MPP, .XML, .XER, .CSV, .PDF y más.

## Qué es “add resource to project” en Aspose.Tasks?
Agregar un recurso a un proyecto significa crear un objeto `Resource` dentro del modelo `Project`. Este objeto puede enlazarse posteriormente a tareas mediante `ResourceAssignment`, lo que te permite rastrear trabajo, costos y configuraciones de nivelación. Al insertar un recurso le das al planificador algo que asignar, y luego puedes consultar o modificar sus propiedades como disponibilidad, tarifas y asignaciones de calendario.

## Por qué manejar las propiedades de retraso de nivelación?
El retraso de nivelación indica al planificador que posponga el inicio de una asignación sobre‑asignada, distribuyendo el trabajo de manera más uniforme a lo largo de la línea de tiempo. Al configurar este retraso evitas fechas de inicio poco realistas, reduces las advertencias de sobreasignación y produces un cronograma que refleja las limitaciones reales de recursos. Ajustar el retraso también te brinda un control granular sobre cuánto margen puede insertar el motor, ayudándote a cumplir los plazos del proyecto respetando los límites de recursos.

## Cómo crear asignación de recursos aspotasks?
Carga tu objeto `Project`, agrega una tarea, crea un recurso y luego vincúlalos con un `ResourceAssignment`. Este flujo de extremo a extremo te permite construir programáticamente una estructura completa de proyecto y controlar inmediatamente el retraso de nivelación en la asignación. El proceso demuestra el flujo de trabajo central: inicialización del proyecto, definición de tareas, creación de recursos, enlace de asignaciones y, finalmente, aplicación de parámetros de programación como el retraso de nivelación.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Java Development Kit (JDK): Asegúrate de tener el JDK de Java instalado en tu sistema. Puedes descargarlo e instalarlo desde el [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Biblioteca Aspose.Tasks para Java: Descarga la biblioteca Aspose.Tasks para Java desde la [download page](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Las siguientes importaciones traen las clases centrales de Aspose.Tasks necesarias para la manipulación de proyectos.  
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

## Cómo crear asignación de recursos aspotasks?
Carga tu objeto `Project`, agrega una tarea, crea un recurso y luego vincúlalos con un `ResourceAssignment`. Este flujo de extremo a extremo te permite construir programáticamente una estructura completa de proyecto y controlar inmediatamente el retraso de nivelación en la asignación. El proceso demuestra el flujo de trabajo central: inicialización del proyecto, definición de tareas, creación de recursos, enlace de asignaciones y, finalmente, aplicación de parámetros de programación como el retraso de nivelación.

## Paso 1: Crear un objeto Project
La clase `Project` es el contenedor de nivel superior de Aspose.Tasks que representa un archivo de proyecto completo en memoria. Instanciarla te brinda una hoja en blanco para agregar tareas, recursos y asignaciones.
```java
Project prj = new Project();
```

## Paso 2: Crear una tarea
La clase `Task` representa un único elemento de trabajo en el cronograma. Agregar una tarea demuestra **cómo agregar tarea** programáticamente y proporciona un objetivo para la próxima asignación de recurso.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Paso 3: Establecer la fecha de inicio y la duración de la tarea
Define cuándo comienza la tarea y cuánto tiempo se ejecutará. Las fechas de inicio correctas son esenciales porque los cálculos de nivelación las usan como base para cualquier retraso que especifiques más adelante.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Paso 4: Añadir un recurso
Ahora **add resource to project** creando una nueva entrada `Resource`. La clase `Resource` representa a una persona, equipo o material que puede asignarse a tareas.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Paso 5: Crear una asignación de recurso
`ResourceAssignment` enlaza un `Task` y un `Resource`. Esta asociación te permite registrar trabajo, costo y detalles de nivelación para un recurso específico en una tarea específica.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Paso 6: Establecer el retraso de nivelación
Configura el retraso de nivelación para la asignación. Establecerlo en cero significa que no hay retraso adicional, pero puedes ajustar el valor según sea necesario. El campo `Asn.DELAY` contiene el retraso en minutos; `Asn.LEVELING_DELAY` es un alias que funciona de la misma manera.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Paso 7: Mostrar resultados
Imprime las propiedades importantes para verificar que todo se haya configurado correctamente. Este paso te ayuda a confirmar que el recurso, la tarea y los valores de retraso son exactamente lo que esperas antes de guardar el archivo.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Errores comunes y consejos
- **Error:** Olvidar establecer la fecha de inicio de la tarea puede hacer que la asignación se predetermine al inicio del proyecto.  
- **Consejo:** Usa `prj.getDuration(value, TimeUnitType.Day)` para controlar la granularidad del retraso.  
- **Consejo:** Después de agregar varios recursos, llama a `prj.updateResourceAssignments()` para que el planificador recalcule la nivelación.  
- **Consejo profesional:** Para proyectos grandes (más de 10 000 tareas) habilita `prj.setAutoCalculate(false)` antes de actualizaciones masivas, luego llama a `prj.calculate()` una sola vez al final para mejorar el rendimiento.

## Preguntas frecuentes

**Q:** ¿Puedo usar Aspose.Tasks con otras bibliotecas Java?  
**A:** Sí, Aspose.Tasks se integra sin problemas con bibliotecas como Jackson para el manejo de JSON o Apache POI para operaciones adicionales de hojas de cálculo, lo que te permite crear soluciones de gestión de proyectos más completas.

**Q:** ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?  
**A:** Aspose.Tasks admite más de 12 formatos, incluidos .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML y .MPP12, garantizando una edición bidireccional sin problemas en todas las versiones principales de Project.

**Q:** ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks?  
**A:** Puedes encontrar soporte y discusiones de la comunidad en el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q:** ¿Puedo probar Aspose.Tasks antes de comprar?  
**A:** Sí, una prueba gratuita totalmente funcional está disponible en la [página de lanzamientos](https://releases.aspose.com/).

**Q:** ¿Cómo puedo obtener una licencia temporal para evaluación?  
**A:** Solicita una licencia temporal en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/) para ejecutar la biblioteca sin restricciones de evaluación.

---

**Última actualización:** 2026-06-05  
**Probado con:** Aspose.Tasks para Java 24.11  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Administrar presupuesto de asignación Java usando Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [Cómo detener una asignación y reanudar asignaciones de recursos en Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}