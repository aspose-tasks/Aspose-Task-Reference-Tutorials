---
date: 2026-01-05
description: Aprenda cómo establecer la fecha de inicio del proyecto y guardar XML
  de MS Project usando Aspose.Tasks para Java. Guía paso a paso para desarrolladores
  Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Establecer la fecha de inicio del proyecto con Aspose.Tasks para Java
url: /es/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer la fecha de inicio del proyecto con Aspose.Tasks para Java

## Introducción
En este tutorial aprenderá **cómo establecer la fecha de inicio del proyecto** en un archivo de Microsoft Project y luego **guardar MS Project XML** usando la biblioteca Aspose.Tasks para Java. Ya sea que esté automatizando una canalización de informes o construyendo una herramienta personalizada de gestión de proyectos, dominar esta tarea le ahorrará tiempo y eliminará errores manuales.

## Respuestas rápidas
- **¿Cuál es el método principal para establecer una fecha de inicio?** Use `project.set(Prj.START_DATE, …)`.
- **¿Qué formato debo usar para exportar el archivo?** Guárdelo como XML con `SaveFileFormat.Xml`.
- **¿Necesito una licencia para esta operación?** Una versión de prueba funciona, pero una licencia completa elimina las marcas de agua.
- **¿Puedo cambiar la fecha de inicio después de crear tareas?** Sí, actualice la propiedad del proyecto antes de añadir tareas.
- **¿Es compatible con todas las versiones de MS Project?** Aspose.Tasks admite XML, MPP y más.

## ¿Qué es “Establecer la fecha de inicio del proyecto”?
Establecer la fecha de inicio del proyecto define el calendario base a partir del cual comienzan todos los cálculos de programación de tareas. Es el primer paso para construir programáticamente un cronograma de proyecto fiable.

## ¿Por qué usar Aspose.Tasks para Java?
Aspose.Tasks proporciona una API pura de Java que funciona en cualquier plataforma sin requerir la instalación de Microsoft Project. Le permite crear, modificar y exportar datos de proyecto rápidamente, lo que lo hace ideal para la automatización del lado del servidor.

## Requisitos previos
1. **Java Development Kit (JDK)** – cualquier versión reciente del JDK.  
2. **Aspose.Tasks para Java** – descárguelo desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o su IDE Java preferido.

## Importar paquetes
Primero, importe las clases necesarias:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Paso 1: Configurar el directorio de datos
Defina dónde se almacenarán los archivos generados.

```java
String dataDir = "Your Data Directory";
```

### Paso 2: Crear una instancia de Project
Instancie un proyecto nuevo y vacío.

```java
Project project = new Project();
```

### Paso 3: Establecer propiedades de información del proyecto
Aquí **establecemos la fecha de inicio del proyecto** y las propiedades de programación relacionadas.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Paso 4: Guardar MS Project XML
Exporte el proyecto configurado a un archivo XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
- **Formato de fecha incorrecto:** Asegúrese de usar `java.util.Calendar` y llamar a `getTime()` antes de asignar.
- **Archivo no guardado:** Verifique que `dataDir` apunte a una carpeta existente y con permisos de escritura.
- **Advertencias de licencia:** La versión de prueba agrega marcas de agua; aplique una licencia válida para eliminarlas.

## Preguntas frecuentes

### P: ¿Puedo usar Aspose.Tasks para Java para leer archivos de MS Project?  
**R:** Sí, Aspose.Tasks para Java ofrece funcionalidades robustas tanto para leer como para escribir archivos de MS Project.

### P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de MS Project?  
**R:** Absolutamente, Aspose.Tasks para Java soporta varios formatos de MS Project, garantizando una amplia compatibilidad.

### P: ¿Existen limitaciones en la versión de prueba de Aspose.Tasks para Java?  
**R:** La versión de prueba le permite explorar la biblioteca pero agrega marcas de agua a los archivos de salida.

### P: ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?  
**R:** Puede buscar asistencia en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

### P: ¿Puedo comprar una licencia temporal para Aspose.Tasks para Java?  
**R:** Sí, las licencias temporales están disponibles para usos a corto plazo. Obtenga una [aquí](https://purchase.aspose.com/temporary-license/).

### P: ¿Al guardar como XML se conservan los campos personalizados?  
**R:** Sí, al guardar usando `SaveFileFormat.Xml`, todos los atributos personalizados y campos extendidos se mantienen.

### P: ¿Puedo cambiar la fecha de inicio después de añadir tareas?  
**R:** Puede actualizar la fecha de inicio en cualquier momento antes de guardar; simplemente llame nuevamente a `project.set(Prj.START_DATE, …)`.

---

**Última actualización:** 2026-01-05  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}