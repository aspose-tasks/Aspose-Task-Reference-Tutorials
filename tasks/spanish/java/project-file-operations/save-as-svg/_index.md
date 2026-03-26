---
date: 2025-12-21
description: Aprenda cómo crear SVG a partir de archivos MPP en Java y guardar el
  proyecto como SVG usando la biblioteca Aspose.Tasks. Guía paso a paso con ejemplos
  de código.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo crear SVG a partir de MPP en Java usando Aspose.Tasks
url: /es/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear SVG a partir de MPP en Java

## Introducción
En este tutorial aprenderá cómo **crear SVG a partir de MPP** usando Aspose.Tasks for Java. Convertir un archivo Microsoft Project (MPP) a gráficos vectoriales escalables (SVG) le permite incrustar diagramas de alta calidad y resolución independiente directamente en páginas web, informes o paneles. Le guiaremos a través de la configuración requerida, mostraremos el código exacto que necesita y explicaremos cada paso para que pueda **guardar el proyecto como SVG** en sus propias aplicaciones.

## Respuestas rápidas
- **¿Qué significa “create SVG from MPP”?**  
  Convierte un archivo Microsoft Project (.mpp) en una imagen SVG que puede mostrarse en cualquier navegador sin pérdida de calidad.  
- **¿Qué biblioteca maneja la conversión?**  
  Aspose.Tasks for Java proporciona un método `save` de una sola línea para realizar la conversión.  
- **¿Necesito una licencia?**  
  Se requiere una licencia temporal para uso comercial; hay una prueba gratuita disponible.  
- **¿Cuáles son los requisitos previos?**  
  Java JDK 8+ y el JAR de Aspose.Tasks for Java.  
- **¿Cuánto tiempo tarda la conversión?**  
  Normalmente menos de un segundo para archivos de proyecto estándar.

## ¿Qué es “create SVG from MPP”?
Crear un SVG a partir de un archivo MPP significa exportar la representación visual de un cronograma de proyecto —tareas, líneas de tiempo y recursos— al formato Scalable Vector Graphics. SVG es basado en XML, liviano y se escala perfectamente en pantallas de alta resolución.

## ¿Por qué usar Aspose.Tasks para guardar el proyecto como SVG?
- **No se requiere instalación de Microsoft Project** – la biblioteca funciona de forma independiente.  
- **Fidelidad total** – los gráficos, barras de Gantt y hitos conservan sus estilos.  
- **Multiplataforma** – ejecute el código en Windows, Linux o macOS.  
- **Integración sencilla** – una llamada API de una línea encaja de forma natural en pipelines Java existentes.

## Requisitos previos
- **Java Development Kit (JDK)** – versión 8 o posterior. Descárguelo desde el sitio web de Oracle.  
- **Aspose.Tasks for Java** – obtenga la biblioteca desde la página oficial de descargas **[here](https://releases.aspose.com/tasks/java/)**.  

## Importar paquetes
Primero, importe las clases que necesitará. El bloque de importación permanece sin cambios.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Paso 1: Definir el directorio de datos
Especifique dónde se encuentra su archivo MPP de origen y dónde se escribirá el SVG.

```java
String dataDir = "Your Data Directory";
```

> **Consejo profesional:** Use una ruta absoluta o una ruta relativa a la carpeta de recursos de su proyecto para evitar `FileNotFoundException`.

## Paso 2: Cargar el archivo MPP
Cree una instancia `Project` cargando el archivo Microsoft Project existente.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Esta línea lee *HomeMovePlan.mpp* desde la carpeta que definió anteriormente.

## Paso 3: Guardar el proyecto como SVG
Ahora puede **guardar el proyecto como SVG** con un solo comando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

El método escribe `project5.svg` en el mismo directorio. El SVG resultante puede abrirse en cualquier navegador moderno o incrustarse directamente en HTML.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **File not found** | Ruta `dataDir` incorrecta | Verifique que la cadena del directorio termine con un separador (`/` o `\\`). |
| **Blank SVG output** | Proyecto cargado sin vistas | Asegúrese de que el archivo MPP contenga una vista de diagrama de Gantt antes de guardar. |
| **License exception** | No se aplicó una licencia válida | Aplique una licencia temporal usando `License.setLicense("path/to/license.xml")` antes de llamar a `save`. |

## Preguntas frecuentes

**Q: ¿Es Aspose.Tasks for Java compatible con todas las versiones de archivos Microsoft Project?**  
A: Sí, admite formatos MPP, MPT y XML desde versiones antiguas hasta las últimas versiones de Project.

**Q: ¿Puedo personalizar la apariencia del SVG generado?**  
A: Por supuesto. Use `SvgOptions` para establecer fuentes, colores y opciones de diseño antes de llamar a `save`.

**Q: ¿Aspose.Tasks for Java requiere una licencia para uso comercial?**  
A: Sí, se necesita una licencia válida para producción. Puede obtener una licencia temporal **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: ¿Puedo probar Aspose.Tasks for Java antes de comprar?**  
A: Sí, hay una prueba gratuita disponible **[here](https://purchase.aspose.com/buy)**.

**Q: ¿Dónde puedo obtener soporte para Aspose.Tasks for Java?**  
A: Visite el foro de la comunidad **[here](https://forum.aspose.com/c/tasks/15)** para hacer preguntas y compartir comentarios.

## Conclusión
Ahora sabe cómo **crear SVG a partir de MPP** en Java y **guardar el proyecto como SVG** de manera eficiente usando Aspose.Tasks. Esta capacidad le permite integrar visualizaciones de proyecto enriquecidas en portales web, paneles de informes o cualquier lugar donde se necesiten gráficos escalables. Experimente con `SvgOptions` para afinar la salida, y tendrá una herramienta poderosa en su conjunto de desarrollo.

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}