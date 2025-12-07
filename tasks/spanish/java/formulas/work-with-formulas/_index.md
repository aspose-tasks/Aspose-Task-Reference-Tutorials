---
date: 2025-12-07
description: Aprenda a **crear un proyecto de prueba** y **agregar un campo personalizado**
  mientras manipula archivos de Microsoft Project usando Aspose.Tasks para Java.
language: es
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crear proyecto de prueba y usar fórmulas con Aspose.Tasks para Java
url: /java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear proyecto de prueba y usar fórmulas con Aspose.Tasks para Java

## Introducción
En este tutorial **creará archivos de proyecto de prueba**, añadirá un campo personalizado y trabajará con fórmulas de MS Project usando la biblioteca Aspose.Tasks para Java. Aspose.Tasks facilita **manipular datos de Microsoft Project** de forma programática—ya sea que necesite generar cronogramas, calcular fechas o automatizar informes. Al final de la guía tendrá un ejemplo ejecutable que define un atributo extendido, establece una fecha límite para una tarea y guarda el proyecto como un archivo MPP.

## Respuestas rápidas
- **¿Qué cubre el tutorial?** Crear un proyecto de prueba, añadir un campo personalizado, definir un atributo extendido y establecer una fecha límite de tarea con una fórmula.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (última versión).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción.  
- **¿Qué IDE puedo usar?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, VS Code) que soporte JDK 8+.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para copiar el código y ejecutarlo.

## ¿Qué es un “Proyecto de prueba” en Aspose.Tasks?
Un **proyecto de prueba** es un archivo ligero de Microsoft Project creado programáticamente para demostrar o validar funcionalidad. Contiene un conjunto mínimo de tareas, recursos y campos personalizados que puede manipular sin afectar datos de proyecto reales.

## ¿Por qué usar Aspose.Tasks para manipular Microsoft Project?
- **Cobertura completa de la API** – acceso a cada propiedad de Project, Task y Resource.  
- **No se requiere instalación de Office** – funciona en servidores, pipelines CI y contenedores Docker.  
- **Multiplataforma** – se ejecuta en Windows, Linux y macOS con el mismo código Java.  
- **Motor de fórmulas robusto** – calcule fechas, duraciones y campos personalizados directamente dentro del archivo del proyecto.

## Requisitos previos
Antes de comenzar, asegúrese de contar con lo siguiente:

- **Java Development Kit (JDK) 8+** – descárguelo del sitio web de Oracle o adopte OpenJDK.  
- **Aspose.Tasks para Java** – obtenga el JAR más reciente desde la [página de descarga de Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/) y agréguelo al classpath de su proyecto o a las dependencias Maven/Gradle.

## Importar paquetes
Primero, importe las clases que necesitaremos:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guía paso a paso

### Paso 1: Crear un proyecto de prueba con un campo personalizado
Comenzamos **creando un proyecto de prueba** y añadiendo un campo personalizado que más adelante contendrá el resultado de nuestra fórmula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Consejo profesional:* `CreateTestProjectWithCustomField()` es un método auxiliar que construye un cronograma mínimo y registra un atributo extendido listo para la asignación de fórmula.

### Paso 2: Definir un atributo extendido (Añadir campo personalizado)
A continuación, **definimos el atributo extendido**—esencialmente el campo personalizado—y le damos un alias amigable. Aquí es donde implementamos la lógica de **añadir campo personalizado**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- El **Alias** hace que el campo sea legible en Project.  
- La **Fórmula** calcula el número de días entre la fecha *Finish* de una tarea y su *Deadline*.

### Paso 3: Establecer fecha límite para una tarea (Añadir tarea de fecha límite y establecer fecha límite)
Ahora **añadimos datos de tarea de fecha límite** estableciendo la propiedad *Deadline* en una tarea específica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- La instancia de `Calendar` define el momento exacto de la fecha límite.  
- `set(Tsk.DEADLINE, …)` **establece la fecha límite** para la tarea elegida.

### Paso 4: Guardar el proyecto (Manipular archivo de Microsoft Project)
Finalmente, **manipulamos Microsoft Project** persistiendo los cambios en un archivo MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Puede abrir `SaveFile.mpp` en Microsoft Project para ver el campo personalizado, el resultado de la fórmula y la fecha límite reflejados en el cronograma.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **La fórmula no se evalúa** | Asegúrese de que la cadena `Formula` del atributo use los nombres de campo correctos (p. ej., `[Deadline]`, `[Finish]`). |
| **Tarea no encontrada** | Verifique que el ID de tarea (`1` en el ejemplo) exista; use `project.getRootTask().getChildren().size()` para depurar. |
| **Excepción de licencia** | Aplique una licencia válida de Aspose.Tasks antes de llamar a cualquier método de la API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
R: Sí, Aspose.Tasks ofrece APIs para .NET, Java y otras plataformas, lo que le permite **manipular Microsoft Project** en el lenguaje que prefiera.

**P: ¿Hay una prueba gratuita disponible para Aspose.Tasks?**  
R: Por supuesto. Descargue una prueba totalmente funcional desde la [página de descarga de Aspose.Tasks](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks?**  
R: La documentación oficial está alojada en [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**P: ¿Cómo puedo obtener soporte para Aspose.Tasks?**  
R: Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para hacer preguntas y compartir experiencias con la comunidad.

**P: ¿Necesito una licencia temporal para la evaluación?**  
R: Sí, hay una licencia temporal disponible para pruebas a corto plazo; puede solicitarla [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2025-12-07  
**Probado con:** Aspose.Tasks para Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}