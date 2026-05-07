---
date: 2026-02-23
description: Aprenda a gestionar el tiempo extra en tareas de proyecto usando Aspose.Tasks
  para Java, incluyendo cómo calcular el costo del tiempo extra y simplificar el seguimiento
  de recursos.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo gestionar el tiempo extra en tareas con Aspose.Tasks
url: /es/java/task-properties/overtimes-in-tasks/
weight: 23
---

 unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo gestionar el tiempo extra en tareas con Aspose.Tasks

## Introduction
Si está buscando **cómo gestionar el tiempo extra** en un archivo de Microsoft Project, ha llegado al lugar correcto. En este tutorial le mostraremos cómo Aspose.Tasks para Java le permite leer, modificar e informar las propiedades relacionadas con el tiempo extra de cada tarea, para que pueda mantener su cronograma y presupuesto precisos.  

## Quick Answers
- **¿Qué significa “tiempo extra” en un proyecto?** Horas de trabajo adicionales más allá de la capacidad regular de un recurso.  
- **¿Qué clase de API proporciona los datos de tiempo extra?** `Task` con la colección de campos `Tsk` (p.ej., `Tsk.OVERTIME_COST`).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Sí, se requiere una licencia temporal o completa de Aspose.Tasks para uso en producción.  
- **¿Puedo calcular el costo del tiempo extra automáticamente?** Absolutamente – recupere `Tsk.OVERTIME_COST` y aplique su lógica de tarifa de costos.  
- **¿Es compatible con Java 17?** Sí, Aspose.Tasks para Java soporta Java 8 y versiones posteriores.

## What is Overtime Management in Project Tasks?
La gestión del tiempo extra significa rastrear el trabajo adicional y el costo que ocurre cuando los recursos superan su tiempo de trabajo normal. Capturar estos datos con precisión le ayuda a pronosticar presupuestos, ajustar cronogramas y reportar la salud real del proyecto.

## Why Use Aspose.Tasks for Overtime?
* **No se requiere Microsoft Project** – trabaje directamente con archivos .MPP.  
* **Acceso completo a los campos de tiempo extra** – los valores de costo, trabajo y porcentaje completado están expuestos a través de la enumeración `Tsk`.  
* **Control programático** – puede leer, modificar o calcular el costo del tiempo extra sin pasos manuales en la UI.

## Prerequisites
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
- Entorno de desarrollo Java: Asegúrese de tener un entorno de desarrollo Java configurado en su máquina.  
- Aspose.Tasks para Java: Descargue e instale la biblioteca Aspose.Tasks. Puede encontrar la biblioteca y su documentación [aquí](https://reference.aspose.com/tasks/java/).  
- Archivo de proyecto: Prepare un archivo de proyecto (p. ej., TaskOvertimes.mpp) para trabajar durante el tutorial.

## Import Packages
En su proyecto Java, importe los paquetes necesarios de Aspose.Tasks para aprovechar sus funcionalidades. Añada las siguientes declaraciones de importación:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
Crear un nuevo proyecto (o cargar uno existente) es el primer paso para cualquier análisis. Esto también satisface la palabra clave secundaria **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
Ahora recorreremos cada tarea de nivel superior, mostraremos su información de tiempo extra y demostraremos cómo **calcular el costo del tiempo extra** leyendo el campo `OVERTIME_COST`.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **Consejo:** El valor `OVERTIME_COST` ya es calculado por Aspose.Tasks basándose en la tarifa de tiempo extra del recurso. Si necesita un cálculo personalizado, multiplique `OVERTIME_WORK` por su propia tarifa y actualice el campo con `tsk.set(Tsk.OVERTIME_COST, yourValue);`.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Valores nulos para los campos de tiempo extra** | Asegúrese de que el archivo .MPP de origen realmente contenga datos de tiempo extra; de lo contrario los campos devuelven `null`. |
| **Costo incorrecto después de la modificación** | Después de cambiar el trabajo o costo de tiempo extra, llame a `project.save()` para persistir los cambios. |
| **Licencia no encontrada** | Coloque su archivo `Aspose.Tasks.lic` en la raíz del proyecto o establezca la licencia programáticamente antes de cargar el proyecto. |

## Frequently Asked Questions

**P: ¿Es Aspose.Tasks adecuado para la gestión de proyectos a gran escala?**  
R: Sí, Aspose.Tasks está diseñado para manejar proyectos de varios tamaños, desde pequeñas iniciativas hasta programas grandes y complejos.

**P: ¿Puedo integrar Aspose.Tasks con otros frameworks Java?**  
R: ¡Absolutamente! Aspose.Tasks se integra sin problemas con Spring, Jakarta EE y otros ecosistemas Java, lo que mejora su versatilidad.

**P: ¿Existen consideraciones de licencia para usar Aspose.Tasks?**  
R: Sí, puede encontrar los detalles de licencia y obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo buscar asistencia o discutir consultas relacionadas con Aspose.Tasks?**  
R: Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para interactuar con la comunidad y buscar soporte.

**P: ¿Hay una versión de prueba gratuita disponible para Aspose.Tasks?**  
R: Sí, puede acceder a la versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo calculo el costo del tiempo extra para un recurso específico?**  
R: Recupere la tarifa de tiempo extra del recurso, multiplíquela por `OVERTIME_WORK` (en horas) y establezca el resultado de nuevo en `OVERTIME_COST` si necesita un cálculo personalizado.

## Conclusion
Aspose.Tasks para Java simplifica **cómo gestionar el tiempo extra** en tareas de proyecto, brindando a los desarrolladores acceso programático directo a métricas de costo, trabajo y progreso del tiempo extra. Siguiendo esta guía podrá cargar un proyecto, leer los detalles de tiempo extra, ajustar porcentajes e incluso calcular costos personalizados de tiempo extra, todo sin abrir Microsoft Project.

---

**Última actualización:** 2026-02-23  
**Probado con:** Aspose.Tasks for Java (última versión)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}