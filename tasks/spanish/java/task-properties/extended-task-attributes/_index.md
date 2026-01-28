---
date: 2026-01-28
description: Aprenda a leer atributos de tarea extendidos usando Aspose.Tasks para
  Java y cambie el tipo de campo personalizado de manera eficiente.
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Leer atributos de tarea extendidos con Aspose.Tasks para Java
url: /es/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer atributos de tarea extendidos con Aspose.Tasks para Java

## Introducción
En este tutorial completo descubrirás cómo **leer atributos de tarea extendidos** de archivos Microsoft Project usando la biblioteca Aspose.Tasks para Java. Ya sea que estés creando una herramienta de informes, sincronizando datos o simplemente necesites una visión más profunda de los campos personalizados, dominar esta funcionalidad te permitirá extraer toda la información almacenada en un proyecto. Recorreremos la configuración requerida, te mostraremos cómo cambiar el tipo de campo personalizado al procesar atributos y te daremos consejos prácticos para evitar errores comunes.

## Respuestas rápidas
- **¿Qué significa “leer atributos de tarea extendidos”?** Se refiere a extraer los valores de campos personalizados que van más allá de las propiedades de tarea predeterminadas en un archivo Project.  
- **¿Qué clase proporciona acceso a estos atributos?** La clase `ExtendedAttribute` en Aspose.Tasks.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar el tipo de atributo en tiempo de ejecución?** Sí – usa la instrucción `switch` para **cambiar el tipo de campo personalizado** basado en `CustomFieldType`.  
- **¿Es compatible con Java 8 y versiones posteriores?** Absolutamente, la API soporta JDK 8+.

## ¿Qué son los atributos de tarea extendidos?
Los atributos de tarea extendidos son campos definidos por el usuario (texto, fecha, número, bandera, etc.) que complementan las propiedades estándar de tarea en Microsoft Project. Aspose.Tasks los expone a través de la colección `ExtendedAttribute` adjunta a cada objeto `Task`, permitiéndote leer o modificar sus valores programáticamente.

## ¿Por qué leer los atributos de tarea extendidos?
- **Visibilidad total:** Obtén información sobre los datos personalizados que los interesados han añadido al cronograma.  
- **Automatización:** Poblá tableros, genera informes personalizados o migra datos a otros sistemas sin exportación manual.  
- **Flexibilidad:** Trabaja con cualquier tipo de campo personalizado—texto, fecha, duración, costo, bandera—manejando cada caso de forma adecuada.

## Requisitos previos
Antes de comenzar, asegúrate de tener:
- Conocimientos básicos de programación en Java.  
- Java Development Kit (JDK) instalado en tu máquina.  
- Un IDE como IntelliJ IDEA o Eclipse.  

## Importar paquetes
Comienza importando las clases necesarias para el proyecto Aspose.Tasks:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Paso 1: Acceder a la tarea y a los atributos extendidos
Carga un archivo Project e itera a través de cada tarea para alcanzar sus atributos extendidos:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Paso 2: Recuperar el ID del campo y el GUID del valor
Imprime los identificadores internos que te ayudan a entender con qué campo personalizado estás trabajando:

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Paso 3: Cómo cambiar el tipo de campo personalizado al leer los atributos de tarea extendidos
Utiliza una instrucción `switch` sobre `CustomFieldType` para manejar correctamente cada posible tipo de dato:

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

Repite estos pasos para cada tarea en tu proyecto para explorar y manipular cada atributo de tarea extendido.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Valores nulos devueltos** | Verifica que el campo personalizado esté realmente poblado en el archivo .mpp de origen. |
| **Tipo incorrecto mostrado** | Asegúrate de estar usando el `CustomFieldType` correcto en la instrucción `switch`; los tipos no coincidentes producirán valores predeterminados. |
| **Ralentización del rendimiento en proyectos grandes** | Procesa las tareas en lotes o filtra solo las tareas que necesitas usando `project.getRootTask().getChildren().stream()` con los predicados apropiados. |

## Preguntas frecuentes
### ¿Puedo modificar los atributos de tarea extendidos programáticamente?
Sí, puedes modificar los atributos de tarea extendidos usando Aspose.Tasks para Java. Consulta la documentación para obtener instrucciones detalladas.

### ¿Hay una versión de prueba disponible?
Sí, puedes acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte para Aspose.Tasks para Java?
Para soporte, visita el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### ¿Cómo puedo obtener una licencia temporal?
Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo comprar la versión completa de Aspose.Tasks para Java?
Puedes comprar la versión completa [aquí](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-01-28  
**Probado con:** Aspose.Tasks Java API (última versión estable)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}