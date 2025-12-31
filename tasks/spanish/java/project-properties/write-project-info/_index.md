---
date: 2025-12-31
description: Aprenda a establecer la fecha de inicio del proyecto, escribir la información
  del proyecto y guardar el proyecto como XML usando Aspose.Tasks para Java.
linktitle: Write Project Info in Aspose.Tasks
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
En este tutorial, descubrirá cómo **establecer la fecha de inicio del proyecto** y escribir información adicional de MS Project con Aspose.Tasks para Java. Ya sea que esté automatizando cronogramas de proyectos, generando informes o integrando datos de Project en un sistema más amplio, controlar la fecha de inicio de forma programática le brinda un comando preciso sobre sus líneas de tiempo. Recorreremos cada paso—desde la configuración del entorno hasta guardar el proyecto actualizado como un archivo XML—para que pueda comenzar a aplicar estas técnicas de inmediato.

## Respuestas rápidas
- **¿Cuál es la clase principal para manipular un proyecto?** `Project` de la biblioteca Aspose.Tasks.  
- **¿Cómo establezco la fecha de inicio del proyecto?** Use `project.set(Prj.START_DATE, <date>)`.  
- **¿Puedo también establecer la fecha de estado?** Sí, con `project.set(Prj.STATUS_DATE, <date>)`.  
- **¿Qué formato debo usar para exportar el proyecto?** Guárdelo como XML con `SaveFileFormat.Xml`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Tasks para obtener la funcionalidad completa.

## ¿Qué es **establecer la fecha de inicio del proyecto**?
Establecer la fecha de inicio del proyecto define el día del calendario a partir del cual comienzan todas las tareas programadas. Es el punto de anclaje para cálculos como duraciones de tareas, dependencias y rutas críticas. Al establecer esta fecha de forma programática, garantiza consistencia entre varios archivos de proyecto y elimina errores de entrada manual.

## ¿Por qué usar Aspose.Tasks para Java para escribir información del proyecto?
- **Cobertura completa de la API:** Lea, modifique y escriba cada propiedad de Project sin necesidad de tener Microsoft Project instalado.  
- **Multiplataforma:** Funciona en Windows, Linux y macOS.  
- **Listo para automatización:** Ideal para procesamiento por lotes, pipelines de CI o servicios back‑end que generan cronogramas de proyecto al vuelo.  

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – cualquier versión reciente (se recomienda 8+).  
2. **Biblioteca Aspose.Tasks para Java** – descárguela desde [aquí](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – IntelliJ IDEA, Eclipse o su editor Java favorito.  

## Importar paquetes
Primero, importe los paquetes necesarios en su proyecto Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Paso 1: Configurar el directorio de datos
Defina el directorio donde se almacenarán los datos de su proyecto.
```java
String dataDir = "Your Data Directory";
```

## Paso 2: Crear una instancia de Project
Inicialice una nueva instancia de proyecto.
```java
Project project = new Project();
```

## Paso 3: Establecer propiedades de información del proyecto
Aquí establecemos la **fecha de inicio del proyecto**, programar desde el inicio y la fecha de estado—cubriendo las palabras clave principales *escribir información del proyecto* y *cómo establecer la fecha de estado*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Paso 4: Guardar el proyecto como XML
Finalmente, persista el archivo de proyecto actualizado. Esto demuestra la palabra clave secundaria **guardar proyecto como xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Fecha de inicio incorrecta** | El mes del calendario es base cero en Java. | Use `Calendar.JULY` (o sume 1 al índice del mes) como se muestra. |
| **Archivo no guardado** | `dataDir` no existe o carece de permiso de escritura. | Cree el directorio previamente o elija una ruta con permisos de escritura. |
| **Advertencia de licencia** | Ejecutar sin licencia agrega una marca de agua. | Aplique una licencia válida de Aspose.Tasks antes de crear el objeto `Project`. |

## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Tasks para Java para leer archivos de MS Project?
R: Sí, Aspose.Tasks para Java ofrece funcionalidades robustas tanto para leer como para escribir archivos de MS Project.  
### P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de MS Project?
R: Absolutamente, Aspose.Tasks para Java soporta varias versiones de MS Project, garantizando compatibilidad con distintos formatos de archivo.  
### P: ¿Existen limitaciones en la versión de prueba de Aspose.Tasks para Java?
R: La versión de prueba le permite explorar las capacidades de la biblioteca, pero tiene ciertas limitaciones como marcas de agua en los archivos de salida.  
### P: ¿Cómo puedo obtener soporte para Aspose.Tasks para Java?
R: Puede buscar asistencia en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).  
### P: ¿Puedo comprar una licencia temporal para Aspose.Tasks para Java?
R: Sí, las licencias temporales están disponibles para usos a corto plazo. Puede obtener una [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora ha aprendido cómo **establecer la fecha de inicio del proyecto**, escribir información esencial del proyecto y **guardar el proyecto como XML** usando Aspose.Tasks para Java. Estos bloques de construcción le permiten automatizar flujos de trabajo de gestión de proyectos, generar cronogramas consistentes e integrar datos de MS Project en sus aplicaciones Java.

---

**Última actualización:** 2025-12-31  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}