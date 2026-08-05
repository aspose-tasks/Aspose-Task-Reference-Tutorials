---
date: 2026-02-13
description: Aprende a generar un informe de proyecto creando un objeto de proyecto
  en Java, añadiendo atributos extendidos y utilizando funciones de evaluación con
  Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Generar informe del proyecto – Crear objeto de proyecto Java
url: /es/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Funciones de Evaluación de Soporte en Fórmulas de Aspose.Tasks

## Introducción
Aspose.Tasks for Java te permite **generar informes de proyecto** creando un **objeto de proyecto** en Java y evaluando funciones de Microsoft Project directamente dentro de tu código. Al incrustar estas fórmulas, puedes ejecutar cálculos sofisticados, generar informes personalizados y automatizar el análisis de proyectos sin salir de tu entorno de desarrollo. En este tutorial recorreremos la creación de un objeto de proyecto, la adición de un atributo extendido y el uso de funciones de evaluación para **añadir datos de campo personalizado a tareas**.

## Respuestas Rápidas
- **¿Qué significa “create project object java”?** Crea una instancia de `Project` en memoria que puedes manipular programáticamente.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (descárgala desde el sitio oficial).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa de Aspose.Tasks para uso en producción; hay una versión de prueba gratuita disponible.  
- **¿Puedo usar campos personalizados?** Sí – puedes **añadir un atributo extendido** a las tareas y tratarlos como campos personalizados.  
- **¿Es compatible con todos los formatos de archivo de Project?** Aspose.Tasks soporta los formatos MPP, MPT y XML.

## Requisitos Previos
Antes de comenzar, asegúrate de tener:

1. **Entorno de Desarrollo Java** – JDK 8+ y un IDE como IntelliJ IDEA o Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Descarga e incluye la biblioteca desde la [página de descarga de Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar Paquetes
Añade el espacio de nombres de Aspose.Tasks a tu clase Java para que puedas trabajar con proyectos, tareas y atributos extendidos:

```java
import com.aspose.tasks.*;
```

## Generar Informe de Proyecto – Crear Objeto de Proyecto Java
Instancia un nuevo objeto `Project`. Este servirá como contenedor para todas las tareas, recursos y datos personalizados que definirás.

```java
Project project = new Project();
```

La línea anterior **creates project object java** que comienza vacío y listo para personalizar.

## Cómo Añadir un Atributo Extendido
Define un atributo extendido que almacenará datos numéricos personalizados (p. ej., un valor de seno) para cada tarea.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aquí **add extended attribute** de tipo `Number` llamado “Sine” y lo asociamos con las tareas.

## Añadir el Atributo Extendido al Proyecto
Registra la definición del atributo en el proyecto para que cada tarea pueda referenciarlo.

```java
project.getExtendedAttributes().add(attr);
```

## Crear una Nueva Tarea
Añade una tarea simple llamada “Task” bajo la tarea raíz del proyecto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Asociar el Atributo Extendido con la Tarea
Vincula el atributo extendido previamente definido con la tarea recién creada.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ahora la tarea contiene un campo personalizado “Sine” que puedes usar en fórmulas o cálculos. Así es también como **add custom field task** datos de forma programática.

## ¿Por Qué Usar Funciones de Evaluación?
Incrustar funciones de MS Project en fórmulas de Aspose.Tasks te permite:

- Realizar cálculos sobre la marcha (p. ej., `Sin([Start])`) sin herramientas externas.  
- Mantener toda la lógica del proyecto dentro de una única base de código mantenible.  
- Generar informes dinámicos que reflejen cambios de datos en tiempo real, ayudándote a **generar informes de proyecto** automáticamente.

## Problemas Comunes y Soluciones
| Problema | Solución |
|----------|----------|
| **La fórmula devuelve `NaN`** | Verifique que el tipo de campo personalizado coincida con el tipo numérico esperado. |
| **Atributo extendido no visible** | Asegúrese de que la definición del atributo se añada al proyecto **antes** de crear tareas. |
| **Excepción de licencia** | Instale una licencia temporal o completa de **Aspose.Tasks**; el modo de prueba puede limitar ciertas funciones. |
| **Licencia temporal faltante** | Obtenga una **licencia temporal de Aspose** desde el sitio web de Aspose. |

## Preguntas Frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar fórmulas complejas de MS Project?**  
A: Sí, Aspose.Tasks for Java soporta la evaluación de una amplia gama de funciones de MS Project, permitiendo cálculos complejos dentro de aplicaciones Java.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de archivos de Microsoft Project?**  
A: Sí, Aspose.Tasks for Java soporta varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.

**Q: ¿Puedo probar Aspose.Tasks for Java antes de comprar?**  
A: Sí, puedes descargar una versión de prueba gratuita de Aspose.Tasks for Java desde el sitio web [aquí](https://purchase.aspose.com/buy).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?**  
A: Puedes obtener soporte en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**Q: ¿Existe una licencia temporal disponible para Aspose.Tasks for Java?**  
A: Sí, puedes obtener una licencia temporal para propósitos de prueba desde el sitio web de Aspose [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Al seguir estos pasos has aprendido cómo **create project object**, **add extended attribute** y aprovechar las funciones de evaluación para **generar informes de proyecto** automáticamente. Ahora puedes ampliar esta base para crear análisis de proyecto más avanzados, paneles personalizados o herramientas de programación automatizada, todo impulsado por Aspose.Tasks for Java.

---

**Última actualización:** 2026-02-13  
**Probado con:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}