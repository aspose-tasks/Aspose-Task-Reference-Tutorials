---
date: 2025-12-04
description: Aprenda cómo leer las propiedades de moneda en Java a partir de archivos
  de MS Project usando Aspose.Tasks para Java. Siga esta guía paso a paso para extraer
  el código de moneda, el símbolo, los dígitos y la posición de forma programática.
language: es
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Leer propiedades de moneda Java con proyectos Aspose.Tasks
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer propiedades de moneda Java con Aspose.Tasks Projects

## Introducción
En este tutorial **leerás propiedades de moneda Java** de archivos Microsoft Project usando la API Aspose.Tasks para Java. Aspose.Tasks te permite trabajar con archivos .mpp sin necesidad de tener Microsoft Project instalado, lo que lo hace ideal para informes automatizados, migración de datos o integración en aplicaciones empresariales basadas en Java. Al final de esta guía, podrás extraer el código de moneda, el símbolo, el número de dígitos decimales y la posición del símbolo directamente de un archivo de proyecto.

## Respuestas rápidas
- **¿Qué significa “read currency properties java”?** Se refiere a obtener los metadatos relacionados con la moneda (código, símbolo, dígitos, posición) de un archivo MS Project usando código Java.  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita de Aspose.Tasks disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versión de JDK se necesita?** Java 8 o superior.  
- **¿Puedo modificar la configuración de moneda después de leerla?** Sí, Aspose.Tasks permite operaciones de lectura y escritura sobre las propiedades de moneda.  
- **¿Es compatible con todas las versiones .mpp?** La API soporta archivos creados con Microsoft Project 2003‑2021.

## ¿Qué es read currency properties java?
Leer propiedades de moneda en Java significa acceder a la configuración a nivel de proyecto que define cómo se muestran los valores monetarios en un archivo Microsoft Project. Estas configuraciones incluyen el código ISO de la moneda (p. ej., **USD**), el símbolo (**$**), el número de dígitos decimales y si el símbolo aparece antes o después del importe.

## ¿Por qué leer propiedades de moneda java con Aspose.Tasks?
- **No se necesita instalación de Microsoft Project** – la API funciona en cualquier plataforma que soporte Java.  
- **Extracción rápida y en proceso** – ideal para el procesamiento por lotes de gran número de archivos de proyecto.  
- **Control total** – puedes combinar los valores obtenidos con informes personalizados o integrarlos en sistemas ERP.  
- **Compatibilidad entre versiones** – funciona con archivos .mpp de Project 2003 hasta la última versión 2021.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – Java 8 o superior instalado y configurado en tu `PATH`.  
2. **Aspose.Tasks for Java JAR** – descarga la última biblioteca desde [here](https://releases.aspose.com/tasks/java/) y añádela al classpath de tu proyecto.  

## Importar paquetes
Comienza importando el espacio de nombres de Aspose.Tasks necesario para la manipulación de proyectos:

```java
import com.aspose.tasks.*;
```

## Paso 1: Configurar el directorio del proyecto
Define la carpeta que contiene el archivo `.mpp` que deseas analizar. Mantener la ruta en una variable hace que el código sea reutilizable:

```java
String dataDir = "Your Data Directory";
```

*Reemplaza `"Your Data Directory"` con la ruta absoluta o relativa a la carpeta donde reside `project.mpp`.*

## Paso 2: Crear una instancia del lector de proyecto
Carga el archivo Microsoft Project en un objeto `Project`. Este objeto te brinda acceso a todas las propiedades del proyecto, incluidas las de moneda:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Si tu archivo tiene otro nombre, cambia `"project.mpp"` en consecuencia.*

## Paso 3: Mostrar las propiedades de moneda
Ahora recupera cada atributo de moneda usando la enumeración `Prj` y muestra los resultados en la consola. La API devuelve objetos que puedes convertir a cadenas para su visualización:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Lo que verás:**  
- **Currency Code** – código ISO‑4217 como `USD`, `EUR`, `JPY`.  
- **Currency Digits** – normalmente `2` para la mayoría de las monedas, `0` para el yen japonés.  
- **Currency Symbol** – el carácter que se muestra en los informes (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` para **antes** del importe, `1` para **después**.

## Paso 4: Finalizar el proceso
Indica que la extracción finalizó con éxito. Este mensaje simple es útil cuando el código se ejecuta como parte de un trabajo por lotes más grande:

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | La ruta `dataDir` es incorrecta o el nombre del archivo está mal escrito. | Verifica la cadena del directorio y asegura que el archivo `.mpp` exista en la ubicación especificada. |
| **NullPointerException on `project.get(...)`** | El archivo de proyecto no contiene información de moneda (poco probable) o la clave de la propiedad es incorrecta. | Usa `project.contains(Prj.CURRENCY_CODE)` para comprobar la existencia antes de leer. |
| **LicenseException** | Ejecutar sin una licencia válida de Aspose.Tasks en un entorno de producción. | Aplica un archivo de licencia usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");` antes de crear el objeto `Project`. |

## Preguntas frecuentes

**Q: ¿Aspose.Tasks es compatible con todas las versiones de Microsoft Project?**  
A: Aspose.Tasks soporta archivos .mpp generados por Microsoft Project 2003‑2021, cubriendo tanto formatos antiguos como los más recientes.

**Q: ¿Puedo modificar las propiedades de moneda usando Aspose.Tasks?**  
A: Sí, puedes leer y escribir la configuración de moneda. Usa `project.set(Prj.CURRENCY_CODE, "EUR");` y luego guarda el proyecto.

**Q: ¿Aspose.Tasks es adecuado para uso comercial?**  
A: Absolutamente. Es una biblioteca comercial; puedes adquirir una licencia [here](https://purchase.aspose.com/buy).

**Q: ¿Aspose.Tasks ofrece una prueba gratuita?**  
A: Sí, hay una prueba totalmente funcional disponible [here](https://releases.aspose.com/).

**Q: ¿Dónde puedo obtener ayuda o soporte para Aspose.Tasks?**  
A: El foro oficial de Aspose.Tasks es el mejor lugar para asistencia – visítalo [here](https://forum.aspose.com/c/tasks/15).

## Conclusión
Ahora sabes cómo **leer propiedades de moneda java** de un archivo MS Project usando Aspose.Tasks para Java. Esta capacidad te permite incorporar metadatos de moneda en informes personalizados, análisis financieros o pipelines de integración sin depender de Microsoft Project. Siéntete libre de experimentar modificando las propiedades o combinando estos datos con otros atributos del proyecto para crear soluciones más ricas.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}