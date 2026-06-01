---
date: 2026-01-13
description: Aprenda cómo crear un atributo personalizado, cargar un archivo de Microsoft
  Project, establecer un valor numérico en Java y guardar el proyecto como XML con
  Aspose.Tasks para Java.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo crear un atributo personalizado en MS Project usando Aspose.Tasks
url: /es/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un atributo personalizado en MS Project usando Aspose.Tasks

## Introducción
En este tutorial, **descubrirás cómo crear un atributo personalizado** para recursos en un archivo de Microsoft Project usando Aspose.Tasks para Java. Recorreremos la carga de un archivo de Microsoft Project, la definición de un nuevo atributo numérico, la asignación de un valor y, finalmente, el guardado del proyecto como XML. Al final, tendrás un ejemplo práctico y claro que podrás adaptar a tus propias soluciones de gestión de proyectos.

## Respuestas rápidas
- **¿Qué significa “atributo personalizado”?**  
  Un campo definido por el usuario que almacena información adicional (p. ej., Edad, Nivel de habilidad) para un recurso o tarea.  
- **¿Qué biblioteca gestiona esto?**  
  Aspose.Tasks para Java proporciona una API fluida para crear y administrar atributos personalizados.  
- **¿Necesito una licencia?**  
  Una licencia temporal gratuita funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Puedo establecer valores numéricos?**  
  Sí – usa `setNumericValue` con un `BigDecimal` (p. ej., `30.5345`).  
- **¿Cómo se guarda el proyecto?**  
  El archivo modificado puede guardarse como XML usando `SaveFileFormat.Xml`.

## ¿Qué es un atributo personalizado?
Un **atributo personalizado** (también llamado atributo extendido) es una columna adicional que puedes añadir a recursos o tareas en Microsoft Project. Permite capturar datos que no están cubiertos por los campos incorporados, como la edad del empleado, el nivel de certificación o cualquier métrica específica del negocio.

## ¿Por qué crear un atributo personalizado en MS Project?
- **Adaptar los datos del proyecto** a las necesidades de tu organización.  
- **Habilitar informes avanzados** almacenando valores que pueden consultarse posteriormente.  
- **Mantener la consistencia** entre varios proyectos aplicando programáticamente la misma definición de atributo.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Entorno de desarrollo Java** – JDK 8 o superior instalado.  
2. **Aspose.Tasks para Java** – Descarga la última versión desde [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA o cualquier IDE compatible con Java.  

## Guía paso a paso

### Importar paquetes
Primero, importa las clases de Aspose.Tasks que necesitarás. Estas proporcionan la funcionalidad central para manejar proyectos, recursos y atributos extendidos.

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

### Paso 1: Definir el directorio de datos
Establece la carpeta donde se encuentra tu archivo de proyecto fuente y donde se escribirá la salida.

```java
String dataDir = "Your Data Directory";
```

### Paso 2: Cargar el archivo de Microsoft Project
Crea una instancia de `Project` cargando el archivo existente. Este es el paso de **cargar archivo de Microsoft Project** que te brinda acceso completo a su contenido.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Paso 3: Definir el atributo personalizado
Definiremos un nuevo atributo numérico llamado **Age**. La API verifica si la definición ya existe; de no ser así, la crea.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Paso 4: Establecer valor numérico en Java
Crea una instancia del atributo para un recurso específico y asigna un valor numérico usando `setNumericValue`. Esto demuestra **set numeric value java** en acción.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Paso 5: Añadir recurso y adjuntar el atributo personalizado
Añade un nuevo recurso llamado **R1** y adjunta el atributo personalizado creado previamente.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Paso 6: Guardar el proyecto como XML
Finalmente, persiste los cambios guardando el proyecto. Este es el paso de **save project as xml**, que produce una representación XML limpia del archivo actualizado.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Paso 7: Mostrar el resultado
Imprime una confirmación amigable para que sepas que el proceso se completó sin errores.

```java
System.out.println("Process completed Successfully");
```

Al seguir estos pasos, has **creado un atributo personalizado**, cargado un archivo de Microsoft Project, establecido un valor numérico usando Java y guardado el proyecto como XML.

## Errores comunes y consejos
- **Conflictos de ID de atributo:** Siempre verifica `getById` antes de crear una nueva definición para evitar IDs duplicados.  
- **Manejo de precisión:** `BigDecimal` conserva la precisión decimal; evita usar `float` o `double` para valores exactos.  
- **Rutas de archivo:** Usa rutas absolutas o configura el directorio de trabajo de tu IDE para prevenir `FileNotFoundException`.  

## Preguntas frecuentes

**P: ¿Puedo crear atributos personalizados para tareas además de recursos?**  
R: Sí – usa `ExtendedAttributeTask` en lugar de `ExtendedAttributeResource` al definir el atributo.

**P: ¿Es posible añadir varios atributos personalizados a la vez?**  
R: Absolutamente. Crea objetos `ExtendedAttributeDefinition` separados para cada atributo y adjúntalos a los recursos o tareas deseados.

**P: ¿En qué formatos puedo guardar el proyecto?**  
R: Aspose.Tasks admite XML, MPP y varios otros formatos como PDF y HTML. En este ejemplo usamos `SaveFileFormat.Xml`.

**P: ¿Necesito licenciar Aspose.Tasks para compilaciones de desarrollo?**  
R: Una licencia temporal es suficiente para evaluación. Para despliegues en producción, se requiere una licencia completa.

**P: ¿Cómo leo de nuevo los valores del atributo personalizado más adelante?**  
R: Usa `resource.getExtendedAttributes()` para iterar sobre los atributos adjuntos y obtener sus valores con `getNumericValue()` o `getTextValue()`.

## Conclusión
Crear un **atributo personalizado** en Microsoft Project con Aspose.Tasks para Java es sencillo una vez que comprendes el flujo de trabajo: cargar el proyecto, definir el atributo, establecer su valor, adjuntarlo a un recurso y guardar el archivo. Este enfoque te permite ampliar los modelos de datos del proyecto de forma programática, habilitando informes más ricos e integraciones más estrechas con tus procesos de negocio.

---

**Última actualización:** 2026-01-13  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}