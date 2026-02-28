---
date: 2026-02-28
description: Aprende a usar Aspose.Tasks para Java para gestionar datos de tareas
  por fases temporales, descarga la biblioteca, pruébala gratis y agiliza el seguimiento
  de proyectos.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo usar Aspose.Tasks para gestionar datos de tareas por fases de tiempo (Java)
url: /es/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar Aspose.Tasks para datos de tiempo de tareas

## Introducción
Si buscas **cómo usar Aspose** para mantener un control estricto sobre el cronograma de tu proyecto, has llegado al lugar correcto. El seguimiento preciso de los datos de tiempo de tareas es una piedra angular de la gestión de proyectos exitosa, y Aspose.Tasks for Java te brinda las herramientas necesarias para automatizar ese proceso. En este tutorial recorreremos un ejemplo completo, de extremo a extremo, que muestra cómo usar Aspose.Tasks para crear un proyecto, asignar recursos, establecer líneas base y, finalmente, recuperar y mostrar los datos de tiempo.

## Respuestas rápidas
- **¿Qué significa “timephased data”?** Son datos desglosados por intervalos de tiempo (días, semanas, meses) que muestran el trabajo, el costo o el trabajo restante a lo largo de la línea de tiempo del proyecto.  
- **¿Qué biblioteca proporciona esta capacidad?** Aspose.Tasks for Java.  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o superior.  
- **¿Puedo exportar los resultados a Excel?** Sí – puedes iterar la colección `TimephasedData` y escribir los valores en cualquier formato que necesites.

## ¿Qué son los datos de tiempo de tareas?
Los datos de tiempo de tareas representan la cantidad de trabajo (o costo) programada para una tarea durante cada segmento de tiempo del calendario del proyecto. Permiten ver cómo se distribuye el trabajo, detectar sobreasignación y comparar el progreso planificado con el real.

## ¿Por qué usar Aspose.Tasks para gestionar datos de tiempo?
- **Control total** – crear, modificar y consultar información de tiempo de forma programática sin abrir Microsoft Project.  
- **Multiplataforma** – funciona en cualquier SO que soporte Java.  
- **Sin dependencias COM** – ideal para automatización del lado del servidor.  
- **API rica** – admite líneas base, contornos de trabajo y campos personalizados de forma nativa.

## Requisitos previos
- **Entorno de desarrollo Java** – JDK 8+ instalado y `JAVA_HOME` configurado.  
- **Biblioteca Aspose.Tasks for Java** – Descarga e incluye la biblioteca Aspose.Tasks en tu proyecto. Puedes encontrar la biblioteca [aquí](https://releases.aspose.com/tasks/java/).  
- **Directorio de documentos** – Una carpeta en tu máquina donde se leerá y escribirá el archivo de proyecto de ejemplo (`project.xml`).

## Importar paquetes
En tu proyecto Java, importa las clases necesarias de Aspose.Tasks:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Paso 1: Establecer la fecha de inicio del proyecto
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explicación:* Creamos una instancia `Project`, inicializamos un `Calendar` con la fecha de inicio deseada y lo asignamos a la propiedad `START_DATE` del proyecto.

## Paso 2: Definir tarea y recurso
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explicación:* Se añade una nueva tarea llamada **Task** bajo la tarea raíz. También creamos un recurso llamado **Rsc** y establecemos sus tarifas estándar y de horas extra.

## Paso 3: Establecer la duración de la tarea
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explicación:* La tarea se programa con una duración de **6 días**.

## Paso 4: Asignar recurso a la tarea
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explicación:* El recurso definido previamente se enlaza a la tarea mediante un `ResourceAssignment`.

## Paso 5: Configurar la asignación de recurso
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explicación:* Establecemos las fechas de detención y reanudación de la asignación (usando un valor de marcador) y aplicamos un contorno de trabajo **Back‑Loaded**, que desplaza más trabajo hacia el final de la asignación.

## Paso 6: Establecer la línea base
```java
project.setBaseline(BaselineType.Baseline);
```
*Explicación:* Capturar una línea base te permite comparar los valores planificados con los reales más adelante.

## Paso 7: Actualizar el progreso de la tarea
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explicación:* La tarea se marca como **50 % completada**, lo que afectará los cálculos del trabajo restante.

## Paso 8: Recuperar datos de tiempo
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explicación:* Esta llamada extrae el **trabajo restante** de la asignación, desglosado por los intervalos de tiempo del proyecto.

## Paso 9: Mostrar datos de tiempo
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explicación:* Simplemente imprimimos el número de entradas de tiempo y el valor de la primera entrada. En un escenario real, iterarías la lista y exportarías los datos a un informe o interfaz de usuario.

## Problemas comunes y soluciones
- **NullPointerException en `getTimephasedData`** – Asegúrate de que las fechas `START` y `FINISH` de la asignación estén establecidas antes de llamar al método.  
- **Contorno de trabajo incorrecto** – Verifica que el `WorkContourType` que elijas coincida con tu estrategia de programación; `BackLoaded` es solo una de varias opciones.  
- **La línea base no refleja los cambios** – Recuerda llamar a `project.setBaseline` *después* de haber definido tareas, recursos y asignaciones.

## Preguntas frecuentes
### Q: ¿Puedo usar Aspose.Tasks for Java en cualquier proyecto Java?
A: Sí, Aspose.Tasks for Java es compatible con cualquier proyecto basado en Java.

### Q: ¿Dónde puedo encontrar soporte adicional para Aspose.Tasks for Java?
A: Visita el [Foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para soporte y discusiones.

### Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks for Java?
A: Sí, puedes explorar una prueba gratuita [aquí](https://releases.aspose.com/).

### Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks for Java?
A: Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Q: ¿Dónde puedo comprar Aspose.Tasks for Java?
A: Puedes comprar Aspose.Tasks for Java [aquí](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-02-28  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}