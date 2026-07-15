---
date: 2026-02-10
description: 'Aprenda cómo recuperar los códigos de moneda de los archivos MS Project
  usando Aspose.Tasks para Java: la forma rápida de obtener el código de moneda que
  los desarrolladores Java necesitan.'
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo recuperar la moneda de MS Project con Aspose.Tasks
url: /es/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo obtener la moneda de MS Project con Aspise.Tasks

## Introduction
¡Bienvenido! En este tutorial descubrirá **cómo obtener códigos de moneda** de un archivo MS Project usando la API Aspose.Tasks Java. Ya sea que esté generando informes financieros multimoneda, consolidando proyectos de diferentes regiones, o simplemente necesite los símbolos monetarios correctos para el procesamiento posterior, esta guía lo lleva paso a paso—desde configurar su entorno hasta extraer el código de moneda programáticamente. Al final, se sentirá cómodo leyendo archivos MS Project y usando la llamada **get currency code java** para obtener el identificador ISO de la moneda.

## Quick Answers
- **¿Qué hace la API?** Lee archivos MS Project y expone propiedades como el código de moneda.  
- **¿Qué lenguaje se usa?** Java, a través de la biblioteca Aspose.Tasks para Java.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo obtener el código en una línea?** Sí—`prj.get(Prj.CURRENCY_CODE)` devuelve la cadena del código de moneda.  
- **¿Es compatible con todas las versiones de Project?** Aspose.Tasks admite tanto formatos antiguos (MPP) como nuevos (XML, XER).

## What is **read ms project file**?
Leer un archivo MS Project significa abrir programáticamente un documento *.mpp* (u otro soportado) y acceder a sus estructuras de datos—tareas, recursos, calendarios y configuraciones financieras—sin interacción manual con Microsoft Project.

## Why use Aspose.Tasks to **read msproject** files?
- **Soporte completo de formatos** – funciona con archivos desde Project 98 hasta las últimas versiones de Office.  
- **No se necesita COM ni instalación de Office** – Java puro, perfecto para automatización del lado del servidor.  
- **API rica** – brinda acceso directo a propiedades como `Prj.CURRENCY_CODE`, permitiéndole **how to retrieve currency** información al instante.  
- **Rendimiento** – análisis ligero, ideal para procesamiento por lotes de muchos proyectos.

## Prerequisites
Before we dive into the code, ensure you have the following:

### Java Development Kit (JDK) Installed
Asegúrese de que un JDK reciente esté disponible en su máquina. Puede descargar e instalar la última versión del JDK desde [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
Descargue y configure la biblioteca Aspose.Tasks para Java. La documentación detallada y los últimos binarios están disponibles [here](https://reference.aspose.com/tasks/java/).

## Import Packages
Para comenzar, importemos los paquetes necesarios en su proyecto Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
Defina la carpeta que contiene su archivo *.mpp*. Ajuste la ruta para que coincida con su entorno.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Cree una instancia `Project` cargando el archivo MS Project. Este es el punto donde **read msproject** datos en memoria.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
Ahora que el proyecto está cargado, puede **how to retrieve currency** información con una sola llamada. Esto demuestra el uso de **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
La salida será el código ISO de tres letras (p. ej., `USD`, `EUR`, `GBP`) que el proyecto tiene configurado.

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
Si necesita almacenar el valor para uso posterior, simplemente asígnele a una variable:

*No se requiere bloque de código adicional* – simplemente conserve la cadena devuelta por `prj.get(Prj.CURRENCY_CODE)` y pásela a cualquier servicio financiero, motor de informes o componente UI.

### Step 5: (Optional) Use the Currency Code
Podría querer aplicar el código obtenido en otro lugar—por ejemplo, formatear valores de costo en un informe personalizado o enviarlo a una API financiera. Escenarios típicos incluyen:

- **Generación de informes** – anteponga el código a las columnas de costo (`USD 1,200`).
- **Integración de API** – envíe el código ISO a pasarelas de pago que requieran un identificador de moneda.
- **Consolidación de datos** – agrupe varios proyectos por moneda para análisis de cartera.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Salida nula** | Project file does not define a currency (default is empty). | Set the currency in Microsoft Project or assign it via `prj.set(Prj.CURRENCY_CODE, "USD");` before reading. |
| **Archivo no encontrado** | Incorrect `dataDir` path. | Verify the path and ensure the file name matches exactly, including case sensitivity. |
| **Versión de archivo no compatible** | Very old or corrupted *.mpp* file. | Use the latest Aspose.Tasks version or convert the file to a newer format in Microsoft Project first. |

## Frequently Asked Questions

**P: ¿Puede Aspose.Tasks manejar estructuras de proyecto complejas?**  
R: Sí, la API puede leer y manipular jerarquías de tareas multinivel, grupos de recursos y campos personalizados sin problemas.

**P: ¿Es Aspose.Tasks compatible con diferentes versiones de archivos MS Project?**  
R: Absolutamente. Soporta MPP, XML, XER y otros formatos en muchas versiones de Microsoft Project.

**P: ¿Aspose.Tasks ofrece documentación y soporte?**  
R: Documentación completa, ejemplos de código y soporte dedicado están disponibles en el sitio web de Aspose.

**P: ¿Puedo probar Aspose.Tasks antes de comprar?**  
R: Se ofrece una prueba gratuita para que pueda evaluar todas las funciones, incluido leer códigos de moneda.

**P: ¿Dónde puedo obtener licencias temporales para Aspose.Tasks?**  
R: Las licencias temporales pueden obtenerse en el [website](https://purchase.aspose.com/temporary-license/) para evaluaciones a corto plazo.

---

**Última actualización:** 2026-02-10  
**Probado con:** Aspose.Tasks for Java (latest version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}