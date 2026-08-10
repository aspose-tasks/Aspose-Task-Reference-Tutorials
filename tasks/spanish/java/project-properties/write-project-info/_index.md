---
date: 2026-05-15
description: Aprenda cómo establecer la fecha de inicio del proyecto, escribir la
  información del proyecto y guardar el proyecto como XML usando Aspose.Tasks para
  Java.
keywords:
- set project start date
- save project as xml
- Aspose.Tasks Java
linktitle: Escribir información del proyecto en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  headline: Set Project Start Date in MS Project using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to set project start date, write project information, and
    save project as XML using Aspose.Tasks for Java.
  name: Set Project Start Date in MS Project using Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
    text: '**Java Development Kit (JDK)** – any recent version (8+ recommended).'
  - name: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from [here](https://releases.aspose.com/tasks/java/).'
  - name: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
    text: '**An IDE** – IntelliJ IDEA, Eclipse, or your favorite Java editor.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java provides robust functionalities for both reading
      and writing MS Project files.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, Aspose.Tasks for Java supports various MS Project versions,
      ensuring seamless handling of MPP, XML, and Primavera formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial version allows full feature exploration but inserts a watermark
      on generated files and limits the number of project entities you can create.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Establecer la fecha de inicio del proyecto en MS Project usando Aspose.Tasks
  para Java
url: /es/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer la fecha de inicio del proyecto en MS Project usando Aspose.Tasks para Java

## Introducción
En este tutorial, descubrirás cómo **establecer la fecha de inicio del proyecto** y escribir información adicional de MS Project con Aspose.Tasks para Java. Ya sea que estés automatizando cronogramas de proyectos, generando informes o integrando datos de Project en un sistema más amplio, controlar la fecha de inicio programáticamente te brinda un control preciso sobre tus líneas de tiempo. Recorreremos cada paso—desde la configuración del entorno hasta guardar el proyecto actualizado como un archivo XML—para que puedas aplicar estas técnicas de inmediato.

## Respuestas rápidas
- **¿Cuál es la clase principal para manipular un proyecto?** `Project` de la biblioteca Aspose.Tasks.  
  La clase `Project` representa un archivo MS Project en memoria.  
- **¿Cómo establezco la fecha de inicio del proyecto?** Usa `project.set(Prj.START_DATE, <date>)`.  
  `Prj.START_DATE` es la clave de propiedad utilizada para establecer la fecha de inicio del proyecto.  
- **¿Puedo también establecer la fecha de estado?** Sí, con `project.set(Prj.STATUS_DATE, <date>)`.  
  `Prj.STATUS_DATE` especifica la fecha que refleja el estado actual del proyecto.  
- **¿Qué formato debo usar para exportar el proyecto?** Guardar como XML con `SaveFileFormat.Xml`.  
  `SaveFileFormat.Xml` indica que el proyecto se guardará en formato XML.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Tasks para obtener la funcionalidad completa.  
- **¿Qué entornos admite Aspose.Tasks?** Windows, Linux y macOS con Java 8+.

## ¿Qué es establecer la fecha de inicio del proyecto?
Establecer la fecha de inicio del proyecto determina el día del calendario en que comienza el cronograma, estableciendo la línea base para todos los cálculos de tareas, dependencias y análisis de ruta crítica. Al definir esta fecha programáticamente garantizas que cada archivo de proyecto generado comience desde el mismo punto, eliminando errores de entrada manual y asegurando resultados reproducibles en distintas compilaciones.

## ¿Por qué usar Aspose.Tasks para Java para escribir información del proyecto?
Aspose.Tasks para Java ofrece **más de 150 propiedades de proyecto configurables** y soporta **más de 30 formatos de archivo**, permitiéndote leer, modificar y escribir datos de MS Project sin necesidad de tener Microsoft Project instalado. La biblioteca se ejecuta en Windows, Linux y macOS, procesa archivos de cientos de páginas en modo de bajo consumo de memoria y puede integrarse en pipelines CI/CD, servicios de procesamiento por lotes o back‑ends basados en la nube. Estas capacidades cuantificadas la convierten en la opción más fiable para la automatización a escala empresarial.

## Prerrequisitos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – cualquier versión reciente (se recomienda 8+).  
2. **Biblioteca Aspose.Tasks para Java** – descárgala [aquí](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse o tu editor Java favorito.  

## Importar paquetes
Primero, importa los paquetes necesarios en tu proyecto Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Paso 1: Configurar el directorio de datos
Define el directorio donde se almacenarán los datos de tu proyecto.
```java
String dataDir = "Your Data Directory";
```

## Paso 2: Crear instancia del proyecto
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un único archivo MS Project en memoria. Inicializarla crea un cronograma vacío que puedes comenzar a poblar de inmediato.
```java
Project project = new Project();
```

## Paso 3: Establecer propiedades de información del proyecto
Aquí establecemos la **fecha de inicio del proyecto**, la bandera de iniciar el cronograma desde la fecha de inicio y la fecha de estado—cubriendo las palabras clave principales y secundarias *escribir información del proyecto* y *cómo establecer el estado*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Paso 4: Guardar el proyecto como XML
Finalmente, persiste el archivo de proyecto actualizado. Guardar como XML garantiza la máxima compatibilidad con herramientas posteriores y mantiene el tamaño del archivo reducido.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Fecha de inicio incorrecta** | El mes del calendario es base cero en Java. | Usa `Calendar.JULY` (o suma 1 al índice del mes) como se muestra. |
| **Archivo no guardado** | `dataDir` no existe o carece de permisos de escritura. | Crea el directorio previamente o elige una ruta con permisos de escritura. |
| **Advertencia de licencia** | Ejecutar sin licencia agrega una marca de agua. | Aplica una licencia válida de Aspose.Tasks antes de crear el objeto `Project`. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Tasks para Java para leer archivos MS Project?**  
R: Sí, Aspose.Tasks para Java proporciona funcionalidades robustas tanto para leer como para escribir archivos MS Project.

**P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de MS Project?**  
R: Absolutamente, Aspose.Tasks para Java soporta varias versiones de MS Project, asegurando un manejo sin problemas de formatos MPP, XML y Primavera.

**P: ¿Hay limitaciones en la versión de prueba de Aspose.Tasks para Java?**  
R: La versión de prueba permite explorar todas las funciones, pero inserta una marca de agua en los archivos generados y limita la cantidad de entidades del proyecto que puedes crear.

**P: ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?**  
R: Puedes buscar asistencia en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**P: ¿Puedo comprar una licencia temporal para Aspose.Tasks para Java?**  
R: Sí, las licencias temporales están disponibles para uso a corto plazo. Puedes obtener una [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora sabes cómo **establecer la fecha de inicio del proyecto**, escribir información esencial del proyecto y **guardar el proyecto como XML** usando Aspose.Tasks para Java. Estos bloques de construcción te permiten automatizar flujos de trabajo de gestión de proyectos, generar cronogramas consistentes e integrar datos de MS Project en tus aplicaciones Java. A continuación, explora cómo añadir tareas, recursos y campos personalizados para enriquecer aún más tus cronogramas automatizados.

---

**Última actualización:** 2026-05-15  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo establecer el calendario del proyecto con Aspose.Tasks para Java](/tasks/java/calendars/properties/)
- [Cómo leer información del proyecto de Microsoft Project con Aspose.Tasks para Java](/tasks/java/project-properties/read-project-info/)
- [Cargar archivo MPP en Java - Administrar propiedades del proyecto con Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}