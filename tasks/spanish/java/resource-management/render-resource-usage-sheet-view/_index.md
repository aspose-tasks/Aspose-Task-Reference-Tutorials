---
date: 2026-01-15
description: Aprenda a guardar un proyecto como PDF y a generar las vistas de Uso
  de recursos y Hoja de MS Project usando Aspose.Tasks para Java. Siga nuestra guía
  paso a paso para exportar el proyecto a PDF sin esfuerzo.
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Guardar proyecto como PDF – Renderizar uso de recursos y vista de hoja en Aspose.Tasks
url: /es/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar proyecto como PDF – Renderizar Vista de Uso de Recursos y Hoja en Aspose.Tasks

## Introducción
En este tutorial descubrirá cómo **guardar proyecto como PDF** mientras renderiza las vistas de Uso de Recursos y Hoja de un archivo Microsoft Project. Ya sea que necesite generar un informe imprimible para las partes interesadas o convertir archivos MPP a un formato universalmente visible, Aspose.Tasks para Java hace que el proceso sea sencillo—no se requiere instalación de Microsoft Project.

## Respuestas rápidas
- **¿Qué hace “guardar proyecto como pdf”?** Convierte un archivo de Project (MPP) en un documento PDF preservando la vista seleccionada.  
- **¿Qué vista se puede exportar?** Uso de Recursos, Hoja, Gantt, Uso de Tareas y más.  
- **¿Puedo cambiar la escala de tiempo en el PDF?** Sí—las opciones incluyen Días, TercerosDeMeses y Meses.  
- **¿Necesito Microsoft Project instalado?** No, Aspose.Tasks funciona de forma independiente.  
- **¿Se requiere una licencia para producción?** Sí, se necesita una licencia comercial para uso que no sea de prueba.

## ¿Qué es “guardar proyecto como PDF”?
Guardar un proyecto como PDF crea una representación estática y de alta resolución de una vista de Project elegida. Esto es ideal para compartir con clientes, archivar o imprimir sin exponer el archivo de proyecto subyacente.

## ¿Por qué usar Aspose.Tasks para exportar proyecto a PDF?
- **Sin dependencias externas** – funciona en cualquier plataforma que soporte Java.  
- **Control granular** – puede seleccionar la vista, la escala de tiempo y el diseño.  
- **Alta fidelidad** – el PDF refleja la apariencia de la vista original de Project.  
- **Listo para automatización** – intégrelo en pipelines CI, servicios de informes o convertidores por lotes.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – se recomienda la última versión.  
2. **Aspose.Tasks para Java** – descárguelo desde la [página de descarga](https://releases.aspose.com/tasks/java/).  

## Importar paquetes
Primero, importe las clases necesarias en su proyecto Java:

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Guía paso a paso

### Paso 1: Leer el proyecto fuente
Cargue el archivo MPP que desea convertir.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Paso 2: Definir SaveOptions con la escala de tiempo requerida (Exportar proyecto a PDF)
Configure las opciones de exportación PDF y establezca la escala de tiempo deseada.  
*Aquí usamos **Días** como ejemplo.*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Paso 3: Establecer el formato de presentación a ResourceUsage
Elija la vista que desea renderizar. En este caso, la vista **Uso de Recursos**.

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Paso 4: Guardar el proyecto (Convertir MPP a PDF)
Ejecute la conversión y genere el archivo PDF.

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Paso 5: Renderizar vistas para otras configuraciones de escala de tiempo (Cambiar escala de tiempo PDF)
Repita los pasos anteriores para producir PDFs con diferentes escalas de tiempo como **TercerosDeMeses** y **Meses**.

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Problemas comunes y soluciones
- **Errores de archivo no encontrado** – Verifique que `dataDir` apunte a la carpeta correcta y que el nombre del archivo MPP coincida exactamente.  
- **Salida PDF en blanco** – Asegúrese de que `PresentationFormat` coincida con una vista que contenga datos (p. ej., ResourceUsage).  
- **Escala de tiempo incorrecta** – Verifique que `options.setTimescale()` se llame antes de cada `project.save()`.

## Preguntas frecuentes

### ¿Puede Aspose.Tasks renderizar otras vistas además de Uso de Recursos y Hoja?
Aspose.Tasks admite la renderización de varias vistas como Diagrama de Gantt, Uso de Tareas y vistas de Calendario, entre otras.

### ¿Es Aspose.Tasks compatible con diferentes versiones de archivos de Microsoft Project?
Sí, Aspose.Tasks soporta una amplia gama de formatos de archivo de Microsoft Project, incluidos MPP, MPT y formatos XML.

### ¿Puedo personalizar la apariencia de las vistas renderizadas usando Aspose.Tasks?
¡Absolutamente! Aspose.Tasks ofrece extensas opciones para personalizar la apariencia y el diseño de las vistas renderizadas según sus requisitos específicos.

### ¿Aspose.Tasks requiere que Microsoft Project esté instalado en el sistema?
No, Aspose.Tasks es una biblioteca independiente y no necesita que Microsoft Project esté instalado para su funcionamiento.

### ¿Está disponible soporte técnico para los usuarios de Aspose.Tasks?
Sí, los usuarios de Aspose.Tasks pueden acceder al soporte técnico a través del [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-15  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

---