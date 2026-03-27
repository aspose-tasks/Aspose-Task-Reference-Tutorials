---
date: 2026-03-27
description: Aprende cómo exportar MPP a SVG en Java con Aspose.Tasks. Guía paso a
  paso, ejemplos de código y consejos para guardar un proyecto como SVG rápidamente.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo exportar MPP a SVG en Java usando Aspose.Tasks
url: /es/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo exportar MPP a SVG en Java

## Exportar MPP a SVG – Introducción
En este tutorial aprenderá a **exportar MPP a SVG** usando Aspose.Tasks para Java. Convertir un archivo Microsoft Project (MPP) a una imagen Scalable Vector Graphics (SVG) le permite incrustar diagramas de alta calidad, independientes de la resolución, directamente en páginas web, informes o paneles. Repasaremos la configuración necesaria, mostraremos el código exacto que necesita y explicaremos cada paso para que pueda **guardar el proyecto como SVG** en sus propias aplicaciones con confianza.

## Respuestas rápidas
- **¿Qué significa “exportar MPP a SVG”?**  
  Convierte un archivo Microsoft Project (.mpp) en una imagen SVG que puede mostrarse en cualquier navegador sin pérdida de calidad.  
- **¿Qué biblioteca realiza la conversión?**  
  Aspose.Tasks para Java proporciona un método `save` de una sola línea para efectuar la conversión.  
- **¿Necesito una licencia?**  
  Se requiere una licencia temporal para uso comercial; hay una prueba gratuita disponible.  
- **¿Cuáles son los requisitos previos?**  
  Java JDK 8+ y el JAR de Aspose.Tasks para Java.  
- **¿Cuánto tiempo tarda la conversión?**  
  Normalmente menos de un segundo para archivos de proyecto estándar.

## ¿Qué es “exportar MPP a SVG”?
Exportar MPP a SVG significa tomar la representación visual de un cronograma de proyecto —tareas, líneas de tiempo y recursos— y escribirla como un archivo SVG. SVG es basado en XML, ligero y se escala perfectamente en pantallas de alta resolución.

## ¿Por qué exportar MPP a SVG con Aspose.Tasks?
- **No se requiere instalación de Microsoft Project** – la biblioteca funciona de forma independiente.  
- **Fidelidad total** – los diagramas, barras de Gantt y hitos conservan sus estilos.  
- **Multiplataforma** – ejecute el código en Windows, Linux o macOS.  
- **API de una sola línea** – una única llamada guarda el proyecto como SVG, integrándose naturalmente en pipelines Java existentes.

## Requisitos previos
- **Java Development Kit (JDK)** – versión 8 o posterior. Descárguelo desde el sitio web de Oracle.  
- **Aspose.Tasks para Java** – obtenga la biblioteca desde la página oficial de descargas **[aquí](https://releases.aspose.com/tasks/java/)**.  

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

> **Consejo:** Use una ruta absoluta o una ruta relativa a la carpeta de recursos de su proyecto para evitar `FileNotFoundException`.

## Paso 2: Cargar el archivo MPP
Cree una instancia `Project` cargando el archivo Microsoft Project existente.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Esta línea lee *HomeMovePlan.mpp* desde la carpeta que definió anteriormente.

## Paso 3: Guardar el proyecto como SVG
Ahora puede **exportar MPP a SVG** con un solo comando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

El método escribe `project5.svg` en el mismo directorio. El SVG resultante puede abrirse en cualquier navegador moderno o incrustarse directamente en HTML.

## Casos de uso comunes
- **Paneles de proyecto** – incruste gráficos Gantt en portales web sin que el cliente necesite instalar Microsoft Project.  
- **Informes automatizados** – genere imágenes SVG al vuelo para informes PDF o HTML.  
- **Colaboración entre equipos** – comparta un cronograma visual con partes interesadas que solo necesiten un navegador para verlo.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Archivo no encontrado** | Ruta `dataDir` incorrecta | Verifique que la cadena del directorio termine con un separador (`/` o `\\`). |
| **Salida SVG en blanco** | Proyecto cargado sin vistas | Asegúrese de que el archivo MPP contenga una vista de diagrama de Gantt antes de guardarlo. |
| **Excepción de licencia** | No se aplicó una licencia válida | Aplique una licencia temporal usando `License.setLicense("path/to/license.xml")` antes de llamar a `save`. |

## Preguntas frecuentes

**P: ¿Aspose.Tasks para Java es compatible con todas las versiones de archivos Microsoft Project?**  
R: Sí, admite formatos MPP, MPT y XML desde versiones antiguas hasta las últimas versiones de Project.

**P: ¿Puedo personalizar la apariencia del SVG generado?**  
R: Por supuesto. Use `SvgOptions` para establecer fuentes, colores y opciones de diseño antes de llamar a `save`.

**P: ¿Aspose.Tasks para Java requiere una licencia para uso comercial?**  
R: Sí, se necesita una licencia válida para producción. Puede obtener una licencia temporal **[aquí](https://purchase.aspose.com/temporary-license/)**.

**P: ¿Puedo probar Aspose.Tasks para Java antes de comprar?**  
R: Sí, hay una prueba gratuita disponible **[aquí](https://purchase.aspose.com/buy)**.

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?**  
R: Visite el foro de la comunidad **[aquí](https://forum.aspose.com/c/tasks/15)** para hacer preguntas y compartir comentarios.

## Conclusión
Ahora sabe cómo **exportar MPP a SVG** en Java y cómo **guardar el proyecto como SVG** de manera eficiente usando Aspose.Tasks. Esta capacidad le permite integrar visualizaciones de proyecto enriquecidas en portales web, paneles de informes o cualquier lugar donde se necesiten gráficos escalables. Experimente con `SvgOptions` para afinar la salida, y tendrá una herramienta poderosa en su conjunto de desarrollo.

---

**Última actualización:** 2026-03-27  
**Probado con:** Aspose.Tasks para Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}