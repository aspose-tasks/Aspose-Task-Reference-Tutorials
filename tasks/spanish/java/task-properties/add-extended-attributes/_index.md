---
title: Agregue atributos extendidos a las tareas en Aspose.Tasks
linktitle: Agregue atributos extendidos a las tareas en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Explore el poder de Aspose.Tasks Java para personalizar archivos de Microsoft Project con atributos extendidos. Mejore sus capacidades de gestión de proyectos sin esfuerzo.
weight: 11
url: /es/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue atributos extendidos a las tareas en Aspose.Tasks

## Introducción
Mejorar sus capacidades de gestión de proyectos es crucial para un seguimiento de tareas y una gestión de recursos eficientes. Aspose.Tasks para Java proporciona una poderosa solución para que los desarrolladores de Java manipulen archivos de Microsoft Project sin problemas. En este tutorial, exploraremos cómo agregar atributos extendidos a tareas usando Aspose.Tasks para Java, permitiéndole personalizar y organizar los datos de su proyecto de acuerdo con sus requisitos específicos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Tasks para la biblioteca Java instalada. Puedes descargarlo desde el[sitio web](https://releases.aspose.com/tasks/java/).
- Un entorno de desarrollo integrado (IDE) de Java instalado en su sistema.
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para acceder a las funcionalidades de Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Ahora, dividamos cada ejemplo en varios pasos:
## 1. Agregar atributo de texto sin formato
1. Establezca la ruta del directorio de documentos:
```java
String dataDir = "Your Document Directory";
```
2. Crea un nuevo proyecto:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Cree una definición de atributo extendida de tipo Texto1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Agregue la definición a la colección de Atributos extendidos del proyecto:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Agregue una tarea al proyecto:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Cree un atributo extendido a partir de la definición de atributo:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Asigne un valor al Atributo Extendido generado:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Agregue el atributo extendido a la tarea:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Guarde el proyecto:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Agregar atributo de texto con opción de búsqueda
Siga los mismos pasos anteriores, reemplazando Texto1 con Texto2 y personalizando los valores de búsqueda.
## 3. Agregar atributo de duración con la opción de búsqueda
Siga los mismos pasos anteriores, reemplazando Texto1 con Duración2 y personalizando los valores de búsqueda.
## Conclusión
Siguiendo esta guía paso a paso, habrá aprendido cómo aprovechar Aspose.Tasks para Java para agregar atributos extendidos a las tareas en sus archivos de Microsoft Project. Esta personalización le permite adaptar su enfoque de gestión de proyectos, mejorando la flexibilidad y la eficiencia.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para Java con otras bibliotecas de Java?
R: Sí, Aspose.Tasks para Java se puede integrar perfectamente en sus proyectos Java y funciona bien con otras bibliotecas Java.
### P: ¿Aspose.Tasks para Java es adecuado para aplicaciones de gestión de proyectos a gran escala?
R: Por supuesto, Aspose.Tasks para Java está diseñado para manejar proyectos de distintos tamaños, incluidas aplicaciones a gran escala.
### P: ¿Existe alguna consideración de licencia para usar Aspose.Tasks para Java en un proyecto comercial?
 R: Sí, asegúrese de revisar la información de licencia proporcionada en el[Sitio web de Aspose.Tasks](https://purchase.aspose.com/buy).
### P: ¿Cómo puedo obtener soporte o asistencia con Aspose.Tasks para Java?
 R: Visita el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para apoyo y debates de la comunidad.
### P: ¿Puedo probar Aspose.Tasks para Java antes de comprarlo?
 R: Sí, puedes acceder a una versión de prueba gratuita.[aquí](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
