---
date: 2026-09-09
description: Aprenda cómo cambiar currency symbol en proyectos Java de Aspose.Tasks,
  establecer currency codes, ajustar symbols y aplicar custom formats para archivos
  de Microsoft Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Establecer Currency Properties en proyectos de Aspose.Tasks
og_description: Cómo cambiar currency symbol en Aspose.Tasks usando Java. Descubra
  instrucciones paso a paso, requisitos previos y consejos para personalizar project
  cost formatting.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Cómo cambiar currency symbol en Aspose.Tasks – Guía de Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Cómo cambiar currency symbol en proyectos de Aspose.Tasks – Guía de Java
url: /es/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo cambiar el símbolo de moneda en Aspose.Tasks – Guía Java

## Introducción
En este tutorial aprenderás **cómo cambiar el símbolo de moneda** para un archivo Microsoft Project usando la API Java de Aspose.Tasks. Ya sea que estés preparando informes para un cliente en el extranjero, consolidando presupuestos en múltiples regiones, o simplemente necesites que coincidan con los estándares contables de tu empresa, ajustar el símbolo de moneda garantiza que cada campo relacionado con costos muestre el signo monetario correcto. La guía recorre cada paso, desde la configuración del entorno de desarrollo hasta la persistencia de los cambios en un archivo de proyecto nuevo o existente.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java.  
- **¿Puedo cambiar el símbolo de moneda?** Sí – establezca `Prj.CURRENCY_SYMBOL` y elija `CurrencySymbolPositionType`.  
- **¿Qué formatos de archivo son compatibles?** XML, MPP y muchos otros a través de `SaveFileFormat`.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.  
- **¿Cuánto tiempo lleva la implementación?** Alrededor de 5‑10 minutos para una configuración básica.  

## Cómo cambiar el símbolo de moneda en Aspose.Tasks usando Java
Carga el proyecto objetivo (o crea uno nuevo), establece las propiedades de moneda deseadas y guarda el archivo. La operación completa consta de tres llamadas a la API: crear o cargar un objeto `Project`, asignar el código de moneda, el símbolo y la posición, y luego invocar `project.save`. Este enfoque funciona tanto para proyectos nuevos como para archivos existentes sin requerir que Microsoft Project esté instalado.

## Por qué usar Aspose.Tasks para cambiar la moneda
Aspose.Tasks ofrece **cobertura completa de la API para más de 30 propiedades relacionadas con la moneda**, lo que permite definir el código, el símbolo, los dígitos decimales y la posición en un solo lugar. La biblioteca procesa archivos Project de cientos de páginas en menos de un segundo en hardware de servidor típico, y funciona en Windows, Linux y macOS sin dependencias adicionales.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK) 8 o superior** – la API requiere al menos JDK 8.  
2. **Aspose.Tasks for Java** – descarga el último JAR desde la [página de descarga de Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA o cualquier editor que soporte Java.  
4. **Una carpeta con permisos de escritura** – donde se guardará el archivo de proyecto generado.  

## Importar paquetes
Las siguientes clases te dan acceso a las propiedades del proyecto, manejo de archivos y configuraciones de moneda.  

`Project` – representa un archivo Microsoft Project en memoria.  
`Prj` – contiene constantes para todas las propiedades a nivel de proyecto, incluidos los campos de moneda.  
`CurrencySymbolPositionType` – enumera las posibles posiciones del símbolo de moneda (antes o después del importe).  

Estas importaciones son necesarias antes de que cualquier código pueda manipular un proyecto.

## Guía paso a paso

### Paso 1: Definir el directorio de datos
Elige una carpeta que contenga tus archivos fuente y donde se escribirá la salida. Asegúrate de que el directorio exista y de que tu proceso Java tenga permiso de escritura.

### Paso 2: Crear una nueva instancia de proyecto
La clase `Project` es el objeto de nivel superior de Aspose.Tasks que representa un archivo Project único en memoria. Instanciarla crea un proyecto en blanco listo para configurarse.

### Paso 3: Establecer propiedades de moneda
Aquí configuras el código de moneda, el número de dígitos decimales, el propio símbolo y la posición del símbolo.  

- **Currency code** – un código ISO 4217 de tres letras como `AUD` o `USD`.  
- **Decimal digits** – típicamente 2 para la mayoría de las monedas.  
- **Currency symbol** – el carácter o cadena que se muestra con los importes, p. ej., `$` o `€`.  
- **Symbol position** – `CurrencySymbolPositionType.Before` coloca el símbolo antes del número; `After` lo coloca después.

Estas configuraciones afectan a todos los campos relacionados con costos (tarifas de recursos, presupuestos de tareas, etc.) en el proyecto.

> **Consejo profesional:** Si necesitas cambiar la moneda de un archivo existente, cárgalo con `new Project("file.mpp")` antes de aplicar las configuraciones anteriores.

### Paso 4: Guardar el proyecto actualizado
Escribe el proyecto de nuevo en disco usando el formato deseado. El formato XML es legible por humanos, mientras que `SaveFileFormat.MPP` preserva la compatibilidad total con Microsoft Project.

### Paso 5: Confirmar el éxito
Imprime un mensaje corto o una entrada de registro para saber que la operación se completó sin errores. Esto es especialmente útil en pipelines automatizados.

## Problemas comunes y soluciones
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` en `project.save`** | `dataDir` no es una ruta válida o no tiene permiso de escritura. | Asegúrese de que el directorio exista y de que su proceso Java tenga acceso de escritura. |
| **El símbolo de moneda no se muestra** | La posición del símbolo está configurada incorrectamente para su configuración regional. | Use `CurrencySymbolPositionType.Before` si el símbolo debe preceder al importe. |
| **El archivo del proyecto no se abre en MS Project** | Guardando en un formato antiguo con configuraciones incompatibles. | Guarde usando `SaveFileFormat.MPP` para compatibilidad total con versiones recientes de MS Project. |

## Preguntas frecuentes

**Q: ¿Puedo establecer múltiples monedas en un solo proyecto usando Aspose.Tasks?**  
A: Sí, puedes asignar diferentes configuraciones de moneda a recursos o tareas individuales modificando sus respectivos campos de costo después de que se haya definido la moneda a nivel de proyecto.

**Q: ¿Aspose.Tasks es compatible con diferentes versiones de archivos de Microsoft Project?**  
A: Absolutamente. La biblioteca admite archivos MPP desde Project 2000 hasta las versiones más recientes, así como XML y otros formatos de intercambio.

**Q: ¿Aspose.Tasks ofrece soporte para formatos de moneda personalizados?**  
A: Sí, puedes definir símbolos personalizados, dígitos decimales y posicionamiento para cumplir con cualquier requisito regional, y estas configuraciones se guardan en el archivo.

**Q: ¿Puedo integrar Aspose.Tasks con otros frameworks de Java?**  
A: Por supuesto. La API es Java puro, por lo que funciona sin problemas con Spring, Hibernate, Maven, Gradle y otros ecosistemas.

**Q: ¿Dónde puedo encontrar ayuda adicional o ejemplos?**  
A: Visita el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener asistencia de la comunidad, o consulta la documentación oficial para referencias detalladas de la API.

## Conclusión
Ahora sabes **cómo cambiar el símbolo de moneda** en proyectos Aspose.Tasks usando Java, cómo establecer el código de moneda, ajustar los dígitos decimales y aplicar un símbolo personalizado. Estas capacidades te permiten generar informes de costos específicos por localidad, alinear los presupuestos del proyecto con los estándares contables regionales y mantener tus archivos Microsoft Project consistentes en equipos globales.

---

**Última actualización:** 2026-09-09  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Tutoriales relacionados

- [propiedades del proyecto java – Extraer símbolo de moneda de MPP usando Aspose.Tasks para Java](/tasks/java/currency/currency-symbols/)
- [Leer propiedades de moneda Java con proyectos Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Gestionar códigos de moneda Java con Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}