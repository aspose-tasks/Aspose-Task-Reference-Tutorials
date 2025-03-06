---
title: Recuperar códigos de esquema de MS Project en Aspose.Tasks
linktitle: Recuperar códigos de esquema en Aspose.Tasks
second_title: Aspose.Tasks API de Java
description: Aprenda a recuperar códigos de esquema de Microsoft Project mediante programación utilizando Aspose.Tasks para Java. Mejore sus capacidades de gestión de proyectos.
weight: 15
url: /es/java/project-file-operations/retrieve-outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar códigos de esquema de MS Project en Aspose.Tasks

## Introducción
En este tutorial, aprenderemos cómo recuperar códigos de esquema de Microsoft Project usando Aspose.Tasks para Java. Los códigos de esquema en MS Project proporcionan una forma estructurada de categorizar y organizar las tareas, los recursos y las asignaciones del proyecto. Aspose.Tasks es una poderosa biblioteca de Java que permite a los desarrolladores manipular y administrar archivos de Microsoft Project mediante programación.
## Requisitos previos
Antes de comenzar, asegúrese de tener configurados los siguientes requisitos previos:
### 1. Entorno de desarrollo Java
Asegúrese de tener instalado el kit de desarrollo de Java (JDK) en su sistema. Puede descargar e instalar JDK desde el sitio web de Oracle.
### 2. Biblioteca Aspose.Tasks
 Descargue e incluya la biblioteca Aspose.Tasks en su proyecto Java. Puedes descargar la biblioteca desde[Página de descarga de Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).
## Importar paquetes
Primero, importe los paquetes necesarios desde Aspose.Tasks en su código Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Ahora dividamos el código de ejemplo proporcionado en varios pasos:
## Paso 1: cargar el proyecto
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 En este paso, cargamos el archivo de Microsoft Project en un`Project` objeto utilizando el nombre de archivo proporcionado.
## Paso 2: recuperar códigos de esquema
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Repetimos cada definición de código de esquema en el proyecto.
## Paso 3: Acceda a las propiedades del código de esquema
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperamos e imprimimos varias propiedades de la definición del código de esquema, como Alias, ID de campo y Nombre de campo.
## Paso 4: Verifique el código personalizado empresarial
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verificamos si el código de esquema es un código personalizado empresarial e imprimimos el resultado en consecuencia.
## Paso 5: Mostrar máscaras de código de esquema
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Repetimos cada máscara asociada con el código de esquema e imprimimos su nivel y valor de máscara.
## Paso 6: Mostrar los valores del código de esquema
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Repetimos cada valor de código de esquema e imprimimos su descripción, ID de valor, valor y tipo.
## Conclusión
En este tutorial, hemos aprendido cómo recuperar códigos de esquema de MS Project usando Aspose.Tasks para Java. Si sigue los pasos proporcionados, podrá acceder y manipular códigos de esquema en sus aplicaciones Java de manera efectiva, lo que permitirá capacidades avanzadas de gestión de proyectos.
## Preguntas frecuentes
### P1: ¿Puedo usar Aspose.Tasks para Java para modificar códigos de esquema en un archivo de proyecto?
R: Sí, Aspose.Tasks para Java proporciona API para modificar códigos de esquema en archivos de MS Project mediante programación.
### P2: ¿Existe una versión de prueba disponible para Aspose.Tasks para Java?
 R: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks para Java desde[Sitio web de Aspose.Tasks](https://releases.aspose.com/).
### P3: ¿Cómo puedo obtener soporte técnico para Aspose.Tasks para Java?
 R: Puede obtener soporte técnico visitando el[Foro Aspose.Tasks](https://forum.aspose.com/c/tasks/15) y publicar allí sus consultas.
### P4: ¿Puedo comprar una licencia temporal de Aspose.Tasks para Java?
 R: Sí, puede comprar una licencia temporal de Aspose.Tasks para Java desde el[pagina de compra](https://purchase.aspose.com/temporary-license/).
### P5: ¿Dónde puedo encontrar la documentación completa de Aspose.Tasks para Java?
 R: Puedes consultar el[documentación](https://reference.aspose.com/tasks/java/) para obtener información detallada sobre el uso de Aspose.Tasks para Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
