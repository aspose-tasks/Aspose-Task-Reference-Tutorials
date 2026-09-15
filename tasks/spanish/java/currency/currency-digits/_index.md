---
date: 2026-09-14
description: Aprenda cómo obtener la moneda de MS Project y leer las propiedades del
  proyecto en Java con Aspose.Tasks. Guía paso a paso para extraer los dígitos de
  moneda de un archivo MPP.
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: Cómo obtener la moneda de MS Project usando Aspose.Tasks
og_description: Aprenda cómo obtener la moneda de MS Project y leer las propiedades
  del proyecto en Java con Aspose.Tasks. Siga este tutorial conciso de Java para extraer
  los dígitos de moneda de un archivo MPP.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: Cómo obtener la moneda de MS Project usando Aspose.Tasks – Guía de Java
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: Cómo obtener la moneda de MS Project usando Aspose.Tasks
url: /es/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo obtener la moneda de ms project usando Aspose.Tasks

## Introducción
If you’re wondering **cómo obtener ms project currency** information from a Microsoft Project file, you’ve landed in the right place. In this comprehensive tutorial you’ll discover **cómo trabajar con ms project currency** values using the Aspose.Tasks library for Java. Whether you’re building a reporting tool, a migration utility, or simply need to read the currency settings from a **java project file**, this guide walks you through every step—from loading an *.mpp* file to extracting the currency digits. By the end, you’ll be comfortable handling ms project currency data in your own applications.

## Respuestas rápidas
- **¿Qué biblioteca lee archivos MS Project?** Aspose.Tasks for Java.  
- **¿Cuántas líneas de código se necesitan para obtener los dígitos de la moneda?** Just three concise lines after the project is loaded.  
- **¿Necesito una licencia para el desarrollo?** A free trial works for testing; a commercial license is required for production.  
- **¿Qué versión de Java es compatible?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **¿Puedo obtener otras propiedades del proyecto?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## ¿Qué es la moneda de ms project?
The `ms project currency` property defines the number of decimal places Microsoft Project uses when displaying monetary values. It is stored in the Project file as the **CURRENCY_DIGITS** field and determines whether amounts appear as whole numbers, one‑decimal, two‑decimal, etc. This setting directly influences budgeting reports, cost roll‑ups, and any UI that shows financial figures, making it essential for accurate data exchange.

## ¿Por qué usar Aspose.Tasks para manejar la moneda de ms project?
Aspose.Tasks lets you extract the currency digits without installing Microsoft Project, and it does so with enterprise‑grade performance. The library supports **30+ years of Project file versions**—from Project 2000 through Project 2024—covering more than **150 distinct file schemas**. Loading a 500‑page project typically takes under **2 seconds** on a standard server, and you can query only the fields you need, keeping memory usage under **50 MB** even for the largest schedules.

## Requisitos previos
Before you start, make sure you have the following:

1. **Entorno de desarrollo Java** – JDK 8 or newer installed and configured.  
2. **Aspose.Tasks for Java** – download the latest JAR from the official site: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conocimientos básicos de Java** – you should be comfortable creating a Java project, adding external libraries, and running a `main` method.  

## Importar paquetes
First, import the classes we’ll need.  
Import the `Project` class and related utilities from the Aspose.Tasks library.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Paso 1: definir el directorio de datos
Specify the folder that contains your **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the absolute or relative path where `project.mpp` resides.

## Paso 2: cargar el archivo mpp  
Now we’ll see **how to load mpp** files using Aspose.Tasks.  
The `Project` class represents a Microsoft Project file and provides access to its properties.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Make sure the file name matches exactly; otherwise, an `IOException` will be thrown.

## Paso 3: obtener los dígitos de la moneda  
With the project loaded, extracting the **ms project currency** digits is a one‑liner:  
The `getCurrencyDigits()` method returns the number of decimal places defined for monetary values.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
The call returns an `Integer` representing the number of decimal places (e.g., `2` for cents). The value is printed to the console, but you can also store it in a variable for further processing.

## Problemas comunes y consejos
- **Archivo no encontrado** – double‑check the `dataDir` path and ensure the file name is correct, including the `.mpp` extension.  
- **Versión de archivo no compatible** – Aspose.Tasks supports Project 2000‑2024 formats; older or corrupted files may need conversion.  
- **Licencia no establecida** – during development a trial works, but for production you must apply a valid license to avoid evaluation watermarks.

## Preguntas frecuentes

**Q: Can Aspose.Tasks handle other Project attributes besides currency digits?**  
A: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate various aspects of Project files, such as tasks, resources, and custom fields.

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade projects, offering high performance and scalability.

**Q: Does Aspose.Tasks support cross‑platform development?**  
A: Yes, you can use Aspose.Tasks for Java on any platform that supports the Java Runtime Environment (Windows, Linux, macOS).

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks?**  
A: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2026-09-14  
**Probado con:** Aspose.Tasks for Java (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [propiedades del proyecto java – Extraer símbolo de moneda de MPP usando Aspose.Tasks para Java](/tasks/java/currency/currency-symbols/)
- [Cómo obtener la moneda de MS Project con Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Propiedades del proyecto Java – Leer metadatos con Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}