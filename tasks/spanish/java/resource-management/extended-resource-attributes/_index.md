---
date: 2026-06-10
description: Aprenda cómo crear un atributo extendido en Java, cargar un archivo de
  Microsoft Project, establecer valores numéricos y guardar el proyecto como XML usando
  Aspose.Tasks para Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Manejar atributos de recursos extendidos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Cómo crear un atributo extendido en Java con Aspose.Tasks
url: /es/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un atributo extendido en Java con Aspose.Tasks

## Introducción
En esta guía práctica **creará un atributo extendido en Java** para un archivo Microsoft Project usando Aspose.Tasks. Recorreremos la carga de un proyecto existente, la definición de un nuevo atributo numérico, la asignación de un valor a un recurso y, finalmente, la persistencia de los cambios como un archivo XML. Al final tendrá un patrón de código reutilizable que puede incorporarse a cualquier solución de gestión de proyectos basada en Java.

## Respuestas rápidas
- **¿Qué es un atributo extendido?**  
  Un campo definido por el usuario (p. ej., Edad, Nivel de habilidad) que almacena datos adicionales para recursos o tareas.  
- **¿Qué API lo crea?**  
  Aspose.Tasks para Java proporciona la clase `ExtendedAttributeDefinition` para definir y gestionar atributos personalizados.  
- **¿Necesito una licencia?**  
  Una licencia de evaluación temporal funciona para desarrollo; se requiere una licencia completa para implementaciones en producción.  
- **¿Puedo almacenar números?**  
  Sí – use `setNumericValue(BigDecimal)` para asignar valores decimales precisos.  
- **¿Cómo persisto los cambios?**  
  Llame a `project.save("output.xml", SaveFileFormat.Xml)` para escribir el proyecto actualizado en formato XML.

## ¿Qué es un atributo personalizado?
Un **atributo personalizado** (también conocido como atributo extendido) es una columna adicional que puede agregar a recursos o tareas en Microsoft Project. Le permite capturar datos que no están cubiertos por los campos incorporados, como la edad del empleado, el nivel de certificación o cualquier métrica específica del negocio.

## ¿Por qué crear un atributo extendido en Java?
Crear un atributo extendido en Java le permite enriquecer programáticamente los datos del proyecto, garantizando consistencia entre archivos y habilitando informes automatizados. Al definir el atributo una vez, puede aplicarlo a cualquier número de recursos o tareas sin entrada manual, ahorrando tiempo y reduciendo errores.

- **Adaptar los datos a su organización** – almacene cualquier métrica que le importe sin soluciones manuales en Excel.  
- **Habilitar informes más ricos** – consulte el campo personalizado más tarde para paneles o análisis.  
- **Mantener la consistencia** – aplique programáticamente la misma definición en decenas de proyectos, eliminando errores humanos.  
- **Probado en rendimiento** – Aspose.Tasks procesa proyectos con hasta 10 000 tareas y 5 000 recursos sin cargar todo el archivo en memoria, según los benchmarks del producto.

## Requisitos previos
Antes de comenzar, asegúrese de contar con:

1. **Java Development Kit** – JDK 8 o superior instalado.  
2. **Aspose.Tasks for Java** – descargue la última versión desde [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA o cualquier entorno de desarrollo compatible con Java.  

## ¿Cómo crear un atributo extendido en Java?
Cargue su proyecto, defina el atributo, asígnelo a un recurso y guarde el archivo – todo en unos pocos pasos sencillos. Las siguientes secciones desglosan cada paso con una explicación concisa seguida del marcador de posición donde irá su código real.

### Guía paso a paso

#### Importar paquetes
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` y clases relacionadas se encuentran en el espacio de nombres `com.aspose.tasks`. Importe estas clases al inicio de su archivo Java.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Paso 1: Definir el directorio de datos
`Paths` es una clase de utilidad que proporciona métodos para obtener una ruta del sistema de archivos de forma independiente de la plataforma.

```java
String dataDir = "Your Data Directory";
```

#### Paso 2: Cargar el archivo Microsoft Project
`Project` representa un archivo Microsoft Project en memoria, permitiendo acceso de lectura y escritura a su contenido.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Paso 3: Definir el atributo personalizado
`ExtendedAttributeDefinition` define el esquema de un nuevo campo personalizado que puede adjuntarse a recursos o tareas.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Paso 4: Establecer valor numérico en Java
`ExtendedAttributeResource` contiene el valor de un atributo personalizado para una instancia de recurso específica.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Paso 5: Añadir recurso y adjuntar el atributo personalizado
`Resource` modela un recurso del proyecto, como una persona, equipo o material.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Paso 6: Guardar proyecto como XML
`SaveFileFormat` enumera los formatos de salida compatibles para guardar un proyecto, incluido XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Paso 7: Mostrar resultado
`System.out.println` imprime una línea de texto en la salida estándar de la consola.

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y consejos
- **Conflictos de ID de atributo:** Siempre llame a `project.getExtendedAttributes().getById(id)` antes de crear una nueva definición para evitar identificadores duplicados.  
- **Manejo de precisión:** Prefiera `BigDecimal` sobre `float`/`double` para valores numéricos exactos; esto evita errores de redondeo en los informes.  
- **Fiabilidad de la ruta del archivo:** Use `Paths.get(...).toAbsolutePath()` o configure el directorio de trabajo de su IDE para eliminar `FileNotFoundException`.  

## Preguntas frecuentes

**P: ¿Puedo crear atributos personalizados para tareas así como para recursos?**  
R: Sí – use `ExtendedAttributeTask` en lugar de `ExtendedAttributeResource` al definir el esquema del atributo.

**P: ¿Es posible agregar varios atributos personalizados a la vez?**  
R: Absolutamente. Cree objetos `ExtendedAttributeDefinition` separados para cada atributo y asígnelos a los recursos o tareas deseados.

**P: ¿En qué formatos puedo guardar el proyecto?**  
R: Aspose.Tasks admite XML, MPP, PDF, HTML y más de 30 formatos adicionales. En este ejemplo utilizamos `SaveFileFormat.Xml`.

**P: ¿Necesito una licencia para compilaciones de desarrollo?**  
R: Una licencia de evaluación temporal es suficiente para pruebas. Para cualquier implementación en producción, se requiere una licencia comercial completa.

**P: ¿Cómo leo posteriormente los valores del atributo personalizado?**  
R: Llame a `resource.getExtendedAttributes()` y recorra la colección; obtenga el valor almacenado con `getNumericValue()` o `getTextValue()`.

---

**Última actualización:** 2026-06-10  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear recursos – Gestión de recursos con Aspose.Tasks para Java](/tasks/java/resource-management/)
- [Crear campo personalizado Aspose - Manejar atributos extendidos](/tasks/java/project-management/extended-attributes/)
- [Cómo crear proyecto – Establecer nuevos atributos de tarea con Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}