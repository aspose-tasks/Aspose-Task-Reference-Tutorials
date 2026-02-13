---
date: 2026-02-13
description: Aprenda a crear una nueva actividad, establecer el directorio de datos
  y guardar el proyecto como MPP en Aspose.Tasks Java. Esta guía paso a paso también
  cubre la personalización de los campos de la tabla.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo crear una nueva actividad y establecer el directorio de datos Aspose.Tasks
url: /es/java/project-configuration/configure-gantt-chart/
weight: 10
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una nueva actividad y establecer el directorio de datos Aspose.Tasks

## Introducción
En este tutorial, aprenderás **cómo establecer el directorio de datos**, cómo **crear una nueva actividad**, y cómo **guardar el proyecto como MPP** mientras configuras la vista de diagrama de Gantt de MS Project en proyectos Aspose.Tasks usando Java. Aspose.Tasks es una API robusta de Java que permite manipular archivos de Microsoft Project programáticamente. Al final de esta guía podrás **personalizar los campos de tabla**, ajustar el directorio de datos y visualizar tu proyecto exactamente como lo necesitas.

## Respuestas rápidas
- **¿Cuál es el primer paso?** Establece la ruta del directorio de datos donde se encuentran tus archivos de proyecto.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (descargable desde el sitio oficial).  
- **¿Puedo agregar atributos personalizados?** Sí, puedes definir atributos extendidos y mostrarlos en el diagrama de Gantt.  
- **¿Necesito una licencia para pruebas?** Una licencia temporal está disponible para propósitos de evaluación.  
- **¿Qué IDE funciona mejor?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, NetBeans) funcionará.

## Qué es “establecer el directorio de datos” y por qué es importante?
Establecer el directorio de datos indica a Aspose.Tasks dónde leer y escribir los archivos de proyecto. Sin una ruta correcta, la API no puede localizar tus archivos `.mpp`, lo que genera errores de FileNotFound. Definir este directorio al inicio de tu código hace que el resto del flujo de trabajo sea limpio y reproducible.

## Por qué personalizar los campos de tabla en un diagrama de Gantt?
Los campos de tabla personalizados te permiten mostrar información adicional —como atributos personalizados, datos de recursos o notas específicas del proyecto— directamente en la vista de Gantt. Esto hace que el diagrama sea más informativo para los interesados y reduce la necesidad de cambiar entre varios informes.

## Cómo crear una nueva actividad?
Crear una nueva actividad (tarea) es una de las operaciones centrales al construir o actualizar un cronograma de proyecto. Al agregar tareas programáticamente puedes automatizar la generación de planes de proyecto complejos, integrar datos de otros sistemas o aplicar cambios masivos sin edición manual.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – cualquier versión reciente (8+).  
2. **Aspose.Tasks Library** – descárgala desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, o cualquier editor compatible con Java que prefieras.

## Importar paquetes
Primero, importa el espacio de nombres de Aspose.Tasks para que puedas trabajar con sus clases:

```java
import com.aspose.tasks.*;
```

## Guía paso a paso

### Paso 1: Configurar el directorio de datos
Define la carpeta que contiene tus archivos de proyecto. Este es el paso de **establecer el directorio de datos** en el que se centra el tutorial.

```java
String dataDir = "Your Data Directory";
```

Reemplaza `"Your Data Directory"` con la ruta absoluta a la carpeta donde se almacena `project.mpp`.

### Paso 2: Cargar el archivo de proyecto
Crea una instancia de `Project` cargando un archivo existente de Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Paso 3: Añadir nueva actividad
Inserta una nueva tarea (actividad) en la raíz del proyecto. Esto demuestra **cómo crear una nueva actividad** programáticamente.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Paso 4: Definir atributo personalizado
Crea una definición de atributo personalizado que podrás adjuntar posteriormente a las tareas.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Paso 5: Añadir atributo personalizado a la tarea
Asigna el atributo recién definido a la tarea que creaste.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Paso 6: Personalizar tabla – **personalizar campos de tabla**
Agrega el atributo personalizado como una columna en la tabla del diagrama de Gantt, especificando ancho, título y alineación.

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### Paso 7: Guardar proyecto
Persiste los cambios en un nuevo archivo que pueda abrirse en Microsoft Project. Este paso **guarda el proyecto como MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **FileNotFoundException** al cargar el proyecto | La ruta **set data directory** es incorrecta o le falta una barra diagonal al final. | Verifica que `dataDir` apunte a la carpeta exacta e incluye el separador de archivos correcto (`/` o `\\`). |
| Atributo personalizado no visible en la vista Gantt | El campo de tabla se añadió en el índice incorrecto o el ancho de la columna es demasiado pequeño. | Asegúrate de que `table.getTableFields().add(3, attrField);` use un índice válido y ajusta `setWidth` según sea necesario. |
| LicenseException al guardar | No se aplicó una licencia válida para uso en producción. | Aplica una licencia temporal o permanente antes de llamar a `project.save()`. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
R: Sí, Aspose.Tasks está disponible para varios lenguajes, incluidos .NET, Java y C++.

**P: ¿Hay una versión de prueba gratuita disponible para Aspose.Tasks?**  
R: Sí, puedes descargar una prueba gratuita desde [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?**  
R: Puedes encontrar soporte y hacer preguntas en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: ¿Cómo puedo comprar una licencia para Aspose.Tasks?**  
R: Puedes comprar una licencia desde [aquí](https://purchase.aspose.com/buy).

**P: ¿Necesito una licencia temporal para propósitos de prueba?**  
R: Sí, puedes obtener una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora sabes cómo **establecer el directorio de datos**, **crear una nueva actividad**, definir y adjuntar un atributo personalizado, y **guardar el proyecto como MPP** mientras **personalizas los campos de tabla** en una vista de diagrama de Gantt usando Aspose.Tasks para Java. Estos pasos te brindan control total sobre cómo se muestra la información del proyecto, haciendo que tus diagramas de Gantt sean más informativos y adaptados a las necesidades de tus interesados.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}