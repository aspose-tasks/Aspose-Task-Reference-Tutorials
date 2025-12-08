---
date: 2025-12-07
description: Aprenda cómo guardar el archivo del proyecto, escribir y leer fórmulas
  de MS Project, y agregar fórmulas de campos personalizados usando Aspose.Tasks para
  Java.
language: es
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Guardar archivo de proyecto y escribir fórmulas de MS Project con Aspose.Tasks
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar archivo de proyecto y escribir fórmulas de MS Project con Aspose.Tasks

## Introducción
En el ámbito de la gestión de proyectos, el manejo eficaz de los datos es fundamental. Aspose.Tasks para Java es una solución robusta que facilita la manipulación y extracción de datos de archivos Microsoft Project. Una característica poderosa que ofrece es la capacidad de escribir y leer fórmulas de MS Project. **También aprenderá cómo *guardar archivo de proyecto* después de aplicar esas fórmulas**, asegurando que sus cambios se conserven para análisis futuros. Este tutorial le guiará a través del proceso de aprovechar esta funcionalidad para mejorar sus tareas de gestión de proyectos.

## Respuestas rápidas
- **¿Qué hace “save project file”?** Escribe todos los cambios en memoria de vuelta a un archivo .mpp en disco.  
- **¿Puedo añadir fórmulas a campos personalizados?** Sí – puede crear un campo personalizado y asignar una fórmula como “double task cost”.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué IDE funciona mejor?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, VS Code) compilará el ejemplo.  
- **¿Es la API compatible con la última versión de MS Project?** Aspose.Tasks soporta todos los formatos .mpp recientes.

## ¿Qué es “save project file” en Aspose.Tasks?
Guardar un archivo de proyecto significa persistir el estado actual del objeto `Project` —incluyendo tareas, recursos y cualquier fórmula personalizada— en un archivo físico de Microsoft Project (`.mpp`). Esta operación es esencial después de modificar datos, como añadir un campo personalizado o cambiar costos de tareas.

## ¿Por qué añadir un campo personalizado y crear una fórmula de campo personalizado?
Añadir un campo personalizado le brinda un contenedor flexible para información adicional que no está cubierta por los campos predeterminados. Al adjuntar una fórmula —como una que **double task cost**— automatiza cálculos, reduce errores manuales y mantiene sus datos de planificación consistentes.

## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de contar con los siguientes requisitos:

1. **Java Development Kit (JDK)** – Java 8 o superior instalado en su máquina.  
2. **Aspose.Tasks for Java** – Descargue e instale desde [here](https://releases.aspose.com/tasks/java/).  
3. **Entorno de Desarrollo Integrado (IDE)** – Elija su IDE preferido para desarrollo Java (IntelliJ IDEA, Eclipse, VS Code, etc.).  

## Importación de paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java:

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Paso 1: Configurar el directorio de datos
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Defina la carpeta donde se encuentran sus archivos MS Project. Aquí es donde cargará el archivo fuente y, posteriormente, **save project file**.

## Paso 2: Cargar archivo de proyecto
```java
Project project = new Project(dataDir + "project.mpp");
```
Cargue el archivo Microsoft Project existente en un objeto `Project` para que pueda leer o modificar su contenido.

## Paso 3: Añadir campo personalizado y crear fórmula de campo personalizado
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
En este paso **add custom field** “Double Costs” y **create custom field formula** que multiplica el `[Cost]` de la tarea por 2, efectivamente **double task cost**. El método `setFormula` incrusta el cálculo directamente en el archivo de proyecto.

## Paso 4: Añadir tarea y establecer costo
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
Cree una nueva tarea y asigne un costo base de `100`. Cuando el proyecto se guarde, el campo personalizado mostrará automáticamente `200` debido a la fórmula definida anteriormente.

## Paso 5: Guardar archivo de proyecto
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
Finalmente, **save project file** con todas las modificaciones. El método `save` escribe el proyecto actualizado, incluido el nuevo campo personalizado y sus valores calculados, en `saved.mpp`.

## Problemas y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Fórmula no aplicada** | El campo personalizado no se añadió a la colección `ExtendedAttributes` del proyecto. | Asegúrese de que `project.getExtendedAttributes().add(attr);` se ejecute antes de guardar. |
| **Archivo no encontrado** | Ruta `dataDir` incorrecta. | Verifique que la cadena del directorio termine con un separador de ruta (`/` o `\\`). |
| **El costo aparece como 0** | El costo de la tarea no se estableció antes de guardar. | Llame a `task.set(Tsk.COST, ...)` antes de `project.save`. |

## Preguntas frecuentes
**P: ¿Aspose.Tasks es compatible con todas las versiones de MS Project?**  
R: Sí, Aspose.Tasks soporta una amplia gama de versiones de MS Project, desde formatos .mpp antiguos hasta las últimas versiones.

**P: ¿Puedo integrar Aspose.Tasks en mi proyecto Java existente?**  
R: Absolutamente. La API está diseñada para una integración sin problemas; solo agregue el JAR de Aspose.Tasks al classpath de su proyecto.

**P: ¿Existen limitaciones en los tipos de fórmulas que puedo crear?**  
R: La biblioteca soporta la mayor parte de la sintaxis de fórmulas nativas de MS Project, incluyendo aritmética, lógica y funciones integradas. Funciones personalizadas complejas pueden requerir soluciones alternativas.

**P: ¿Aspose.Tasks admite despliegue multiplataforma?**  
R: Sí, la biblioteca se ejecuta en cualquier plataforma que soporte Java, incluyendo Windows, Linux y macOS.

**P: ¿Cómo puedo obtener soporte técnico para Aspose.Tasks?**  
R: Visite el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para ayuda de la comunidad, o abra un ticket de soporte si posee una licencia comercial.

## Conclusión
En este tutorial cubrimos cómo **save project file**, **add custom field**, y **create a custom field formula** que **double task cost** usando Aspose.Tasks para Java. Al seguir estos pasos podrá automatizar cálculos, enriquecer los datos de su proyecto y asegurar que todos los cambios se conserven para futuros informes y análisis.

---

**Última actualización:** 2025-12-07  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}