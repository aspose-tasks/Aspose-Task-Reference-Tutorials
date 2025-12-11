---
date: 2025-12-09
description: Aprenda cómo crear un objeto de proyecto en Java y admitir funciones
  de evaluación en fórmulas de Aspose.Tasks usando Java. Descubra cómo crear un atributo
  extendido para tareas.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Crear objeto de proyecto Java – Soporte de funciones de evaluación en Aspose.Tasks
url: /es/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Soporte de Funciones de Evaluación en Fórmulas de Aspose.Tasks

## Introducción
Aspose.Tasks for Java le permite **create project object java** instancias y evaluar funciones de Microsoft Project directamente dentro de su código Java. Al incrustar estas fórmulas, puede ejecutar cálculos sofisticados, generar informes personalizados y automatizar el análisis de proyectos sin salir de su entorno de desarrollo. Este tutorial le guía a través de todo el proceso—desde la configuración del objeto de proyecto hasta la adición de un atributo extendido que puede contener datos personalizados.

## Respuestas Rápidas
- **¿Qué significa “create project object java”?** Crea una instancia `Project` en memoria que puede manipular programáticamente.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (descargue del sitio oficial).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción; hay disponible una prueba gratuita.  
- **¿Puedo usar campos personalizados?** Sí – puede definir y adjuntar atributos extendidos a las tareas.  
- **¿Es compatible con todos los formatos de archivo de Project?** Aspose.Tasks admite los formatos MPP, MPT y XML.

## Requisitos Previos
Antes de comenzar, asegúrese de tener:

1. **Entorno de Desarrollo Java** – JDK 8+ y un IDE como IntelliJ IDEA o Eclipse.  
2. **Biblioteca Aspose.Tasks for Java** – Descargue e incluya la biblioteca desde la [página de descarga de Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importar Paquetes
Agregue el espacio de nombres Aspose.Tasks a su clase Java para que pueda trabajar con proyectos, tareas y atributos extendidos:

```java
import com.aspose.tasks.*;
```

## Paso 1: Crear Project Object Java
Instancie un nuevo objeto `Project`. Este servirá como contenedor para todas las tareas, recursos y datos personalizados que definirá.

```java
Project project = new Project();
```

La línea anterior **creates project object java** que comienza vacío y listo para personalizar.

## Paso 2: Cómo Crear un Atributo Extendido
Defina un atributo extendido que almacenará datos numéricos personalizados (p. ej., un valor de seno) para cada tarea.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Aquí **create extended attribute** de tipo `Number` llamado “Sine” y lo asociamos con las tareas.

## Paso 3: Añadir el Atributo Extendido al Proyecto
Registre la definición del atributo en el proyecto para que cada tarea pueda referenciarlo.

```java
project.getExtendedAttributes().add(attr);
```

## Paso 4: Crear una Nueva Tarea
Añada una tarea simple llamada “Task” bajo la tarea raíz del proyecto.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Paso 5: Asociar el Atributo Extendido con la Tarea
Vincule el atributo extendido definido previamente a la tarea recién creada.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Ahora la tarea contiene un campo personalizado “Sine” que puede usar en fórmulas o cálculos.

## ¿Por Qué Usar Funciones de Evaluación?
Incrustar funciones de MS Project en fórmulas de Aspose.Tasks le permite:

- Realizar cálculos en tiempo real (p. ej., `Sin([Start])`) sin herramientas externas.  
- Mantener toda la lógica del proyecto dentro de una única base de código mantenible.  
- Generar informes dinámicos que reflejen cambios de datos en tiempo real.

## Problemas Comunes y Soluciones
| Problema | Solución |
|----------|----------|
| **La fórmula devuelve `NaN`** | Verifique que el tipo de campo personalizado coincida con el tipo numérico esperado. |
| **Atributo extendido no visible** | Asegúrese de que la definición del atributo se añada al proyecto **antes** de crear tareas. |
| **Excepción de licencia** | Instale una licencia temporal o completa; el modo de prueba puede limitar ciertas funciones. |

## Preguntas Frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar fórmulas complejas de MS Project?**  
**A:** Sí, Aspose.Tasks for Java admite la evaluación de una amplia gama de funciones de MS Project, lo que permite cálculos complejos dentro de aplicaciones Java.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de archivos de Microsoft Project?**  
**A:** Sí, Aspose.Tasks for Java admite varias versiones de archivos de Microsoft Project, incluidos los formatos MPP, MPT y XML.

**Q: ¿Puedo probar Aspose.Tasks for Java antes de comprar?**  
**A:** Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks for Java desde el sitio web [aquí](https://purchase.aspose.com/buy).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks for Java?**  
**A:** Puede obtener soporte en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**Q: ¿Hay una licencia temporal disponible para Aspose.Tasks for Java?**  
**A:** Sí, puede obtener una licencia temporal para propósitos de prueba en el sitio web de Aspose [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2025-12-09  
**Probado con:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}