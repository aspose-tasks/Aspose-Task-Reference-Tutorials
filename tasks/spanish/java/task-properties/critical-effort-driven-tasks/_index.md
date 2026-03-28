---
date: 2026-01-25
description: Aprende a usar Aspose Tasks Java para la gestión de tareas en Java, manejando
  tareas críticas y basadas en esfuerzo en tus proyectos. Mejora los flujos de trabajo
  del proyecto con esta guía.
linktitle: Aspose Tasks Java – Manage Critical and Effort‑Driven Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – Gestionar tareas críticas y basadas en esfuerzo
url: /es/java/task-properties/critical-effort-driven-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java: Administrar Tareas Críticas y Basadas en Esfuerzo

En la gestión moderna de proyectos, **aspose tasks java** le brinda el poder de identificar y controlar tareas críticas y basadas en esfuerzo directamente desde su código Java. Ya sea que esté creando un programador, una herramienta de informes o un panel personalizado, manejar correctamente estas propiedades de tarea puede significar la diferencia entre un proyecto que se mantiene en el camino y uno que se sale de control. En este tutorial recorreremos todo lo que necesita saber para trabajar con tareas críticas y basadas en esfuerzo usando Aspose Tasks Java.

## Respuestas rápidas
- **¿Qué significa “crítica”?** Una tarea cuyo retraso extenderá la fecha de finalización del proyecto.  
- **¿Qué es “basada en esfuerzo”?** Una tarea que ajusta automáticamente su duración cuando cambia el esfuerzo de trabajo.  
- **¿Qué biblioteca proporciona estas funciones?** Aspose Tasks Java.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita sirve para evaluación; se requiere una licencia para producción.  
- **¿Puedo ejecutarlo en cualquier SO?** Sí – la biblioteca es independiente de la plataforma (Windows, Linux, macOS).

## ¿Qué son las Tareas Críticas y Basadas en Esfuerzo?
Las tareas críticas son aquellas que forman parte del camino crítico del proyecto; cualquier deslizamiento impacta directamente el cronograma general. Las tareas basadas en esfuerzo, por otro lado, recalculan su duración en función de la cantidad de trabajo asignado, lo que las hace ideales para recursos que pueden trabajar horas extra o compartir esfuerzo entre múltiples asignaciones.

## ¿Por qué usar Aspose Tasks Java para esto?
- **API completa al estilo .NET en Java** – No es necesario cambiar de lenguaje.  
- **Alto rendimiento** – Funciona con archivos de proyecto basados en XML grandes sin cargar todo el archivo en memoria.  
- **Conjunto rico de propiedades** – Acceso a `IS_CRITICAL`, `IS_EFFORT_DRIVEN` y muchos más atributos de tarea.  
- **Multiplataforma** – Se ejecuta en cualquier entorno compatible con JVM.

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de contar con los siguientes requisitos:
- Biblioteca Aspose.Tasks para Java: Descargue e instale la biblioteca desde la [documentación de Aspose.Tasks para Java](https://reference.aspose.com/tasks/java/).
- Java Development Kit (JDK): Asegúrese de tener Java instalado en su sistema.
- Entorno de Desarrollo Integrado (IDE): Use su IDE preferido para desarrollo Java.
- Archivo de proyecto: Prepare un archivo de proyecto en formato XML que utilizará para la demostración.

## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para aprovechar las funcionalidades de Aspose.Tasks para Java:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

### Paso 1: Recopilar tareas usando `ChildTasksCollector`
Cree una instancia de `ChildTasksCollector` para recopilar todas las tareas desde la tarea raíz usando `TaskUtils.apply`. Esto garantiza que tenga acceso a cada tarea dentro del proyecto.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
// Create a ChildTasksCollector instance
ChildTasksCollector collector = new ChildTasksCollector();
// Collect all the tasks from RootTask using TaskUtils
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Paso 2: Recorrer las tareas recopiladas
Itere a través de todas las tareas recopiladas usando un bucle `for`. Para cada tarea, determine si es basada en esfuerzo y crítica, luego imprima el estado correspondiente.

```java
// Parse through all the collected tasks
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```

Al seguir estos pasos, podrá gestionar eficazmente tareas críticas y basadas en esfuerzo en sus proyectos usando **aspose tasks java**.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| `NullPointerException` en `tsk.get(Tsk.IS_CRITICAL)` | La tarea no tiene la propiedad establecida (p.ej., una tarea resumen). | Verifique `tsk.get(Tsk.TASK_TYPE)` antes de acceder al indicador, o filtre las tareas resumen. |
| Archivo de proyecto no encontrado | Ruta `dataDir` incorrecta o falta la extensión del archivo. | Use `Paths.get(dataDir, "project.xml").toString()` y verifique que el archivo exista. |
| Licencia no aplicada | La biblioteca se ejecuta en modo de evaluación, limitando funciones. | Cargue su archivo de licencia con `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de crear el objeto `Project`. |

## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para Java tanto en entornos Windows como Linux?
R: Sí, Aspose.Tasks para Java es independiente de la plataforma y puede usarse tanto en Windows como en Linux.

### P: ¿Existe una prueba gratuita disponible para Aspose.Tasks para Java?
R: Sí, puede acceder a una prueba gratuita de Aspose.Tasks para Java [aquí](https://releases.aspose.com/).

### P: ¿Dónde puedo encontrar soporte para Aspose.Tasks para Java?
R: Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener soporte comunitario y discusiones.

### P: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks para Java?
R: Puede adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### P: ¿Dónde puedo comprar Aspose.Tasks para Java?
R: Puede comprar Aspose.Tasks para Java desde la [página de compra](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-01-25  
**Probado con:** Aspose.Tasks Java 24.11 (última disponible al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}