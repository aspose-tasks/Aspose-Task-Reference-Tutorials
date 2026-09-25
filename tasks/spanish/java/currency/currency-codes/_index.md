---
date: 2026-09-25
description: 'Aprenda cómo recuperar códigos de moneda de archivos MS Project usando
  Aspose.Tasks para Java: la forma rápida de obtener el código de moneda que los desarrolladores
  Java necesitan.'
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Gestionar códigos de moneda en Aspose.Tasks
og_description: Recuperar código de moneda java de archivos MS Project usando Aspose.Tasks.
  Esta guía le muestra cómo leer el proyecto, extraer el identificador ISO de la moneda
  y aplicarlo en aplicaciones Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Recuperar código de moneda java de MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Recuperar código de moneda java de MS Project con Aspose.Tasks
url: /es/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar el código de moneda java de MS Project con Aspose.Tasks

## Introducción
En este tutorial aprenderás **cómo recuperar el código de moneda java** de un archivo MS Project usando la API Aspose.Tasks para Java. Ya sea que necesites generar informes financieros multimoneda, consolidar proyectos en diferentes regiones, o simplemente mostrar el símbolo monetario correcto en un sistema posterior, los pasos a continuación te llevarán desde la configuración del entorno hasta la llamada de una sola línea que devuelve el identificador ISO de la moneda. Al final de la guía estarás cómodo cargando cualquier formato de archivo Project compatible y extrayendo el código de moneda de tres letras como `USD`, `EUR` o `GBP`.

## Respuestas rápidas
- **¿Qué hace la API?** Lee archivos MS Project y expone propiedades como el código de moneda.  
- **¿Qué lenguaje se usa?** Java, a través de la biblioteca Aspose.Tasks para Java.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo recuperar el código en una sola línea?** Sí—`prj.get(Prj.CURRENCY_CODE)` devuelve la cadena del código de moneda instantáneamente.  
- **¿Es compatible con todas las versiones de Project?** Aspose.Tasks soporta más de 20 formatos de entrada, incluidos los archivos MPP heredados, XML y XER.

## ¿Qué es leer un archivo MS Project?
Leer un archivo MS Project significa abrir programáticamente un *.mpp* (o cualquier otro formato compatible como XML o XER) y acceder a sus estructuras de datos internas. Estas estructuras incluyen tareas, recursos, calendarios, tablas de costos y configuraciones financieras. Al analizar el archivo puedes extraer información sin lanzar Microsoft Project, habilitando flujos de trabajo automatizados de informes, migración e integración.

## ¿Por qué usar Aspose.Tasks para leer archivos msproject?
Aspose.Tasks ofrece una solución puramente Java que elimina la necesidad de interop COM o una instalación local de Microsoft Project. Soporta más de 20 formatos de archivo, puede manejar proyectos con miles de tareas usando menos de 100 MB de memoria, y proporciona un modelo de objetos rico. El acceso directo a constantes como `Prj.CURRENCY_CODE` te permite recuperar la información de moneda al instante y de forma fiable.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de contar con lo siguiente:

### Kit de desarrollo Java (JDK) instalado
Se requiere un JDK reciente (11 o superior). Descárgalo desde el sitio oficial de Oracle: [aquí](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Biblioteca Aspose.Tasks para Java
Obtén los binarios más recientes de Aspose.Tasks para Java y añádelos al classpath de tu proyecto. La documentación completa y los enlaces de descarga están disponibles [aquí](https://reference.aspose.com/tasks/java/).

## Importar paquetes
La clase `Project` y las constantes `Prj` se encuentran en el espacio de nombres `com.aspose.tasks`. Importálas al inicio de tu archivo fuente Java:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guía paso a paso

### Paso 1: configurar el directorio de datos
Define la carpeta que contiene tu archivo *.mpp*. Ajusta la ruta para que coincida con tu entorno y el tiempo de ejecución pueda localizar el archivo del proyecto.

```java
String dataDir = "Your Data Directory";
```

### Paso 2: cargar el archivo del proyecto
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo MS Project en memoria. Crear una instancia lee el archivo y construye un modelo en memoria que puedes consultar.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Paso 3: recuperar el código de moneda
La constante `Prj.CURRENCY_CODE` identifica la propiedad que almacena el identificador ISO de la moneda. Llamar a `prj.get(Prj.CURRENCY_CODE)` devuelve el código de tres letras en una sola operación.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
La salida será el código ISO de moneda de tres letras (p. ej., `USD`, `EUR`, `GBP`) que el proyecto tiene configurado.

### Paso 4: cómo recuperar el código de moneda en Java (contexto adicional)
Carga tu proyecto, llama a `prj.get(Prj.CURRENCY_CODE)` y guarda el resultado en un `String`. Luego puedes pasar este valor a cualquier servicio financiero, motor de informes o componente de UI que requiera un identificador de moneda.

### Paso 5: (opcional) usar el código de moneda
Los escenarios típicos posteriores incluyen:

- **Generación de informes** – antepone el código a las columnas de costos (`USD 1,200`).  
- **Integración de API** – envía el código ISO a pasarelas de pago que exigen un parámetro de moneda.  
- **Consolidación de datos** – agrupa varios proyectos por moneda para análisis a nivel de cartera.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Salida nula** | El archivo del proyecto no define una moneda (el valor predeterminado está vacío). | Establece la moneda en Microsoft Project o asígnala mediante `prj.set(Prj.CURRENCY_CODE, "USD");` antes de leer. |
| **Archivo no encontrado** | Ruta `dataDir` incorrecta. | Verifica la ruta y asegura que el nombre del archivo coincida exactamente, incluida la sensibilidad a mayúsculas. |
| **Versión de archivo no compatible** | Archivo *.mpp* muy antiguo o corrupto. | Actualiza a la última versión de Aspose.Tasks o convierte el archivo a un formato más reciente en Microsoft Project primero. |

## Preguntas frecuentes

**Q:** ¿Puede Aspose.Tasks manejar estructuras de proyecto complejas?  
**A:** Sí, la API lee jerarquías de tareas multinivel, grupos de recursos, campos personalizados y calendarios sin limitaciones.

**Q:** ¿Es Aspose.Tasks compatible con diferentes versiones de archivos MS Project?  
**A:** Absolutamente. Soporta MPP, XML, XER y otros formatos desde Project 98 hasta las últimas versiones de Office.

**Q:** ¿Aspose.Tasks proporciona documentación y soporte?  
**A:** Referencia completa de la API, ejemplos de código y soporte técnico dedicado están disponibles en el sitio web de Aspose.

**Q:** ¿Puedo probar Aspose.Tasks antes de comprar?  
**A:** Se ofrece una prueba gratuita para que puedas evaluar todas las funciones, incluida la extracción del código de moneda.

**Q:** ¿Dónde puedo obtener una licencia temporal para evaluación?  
**A:** Las licencias temporales están disponibles en el [sitio web](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-09-25  
**Probado con:** Aspose.Tasks for Java (última versión)  
**Autor:** Aspose

## Tutoriales relacionados

- [Propiedades del proyecto Java – Leer metadatos con Aspose.Tasks](/tasks/java/project-properties/)
- [Cómo leer información del proyecto de Microsoft Project con Aspose.Tasks para Java](/tasks/java/project-properties/read-project-info/)
- [Recuperar códigos de esquema de MS Project en Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}