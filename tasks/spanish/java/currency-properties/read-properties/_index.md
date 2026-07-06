---
date: 2026-02-07
description: Aprende cómo leer las propiedades de moneda en Java y extraer el símbolo
  de moneda en Java de los archivos de MS Project usando Aspose.Tasks para Java. Sigue
  esta guía paso a paso para extraer el código de moneda, el símbolo, los dígitos
  y la posición de forma programática.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Leer propiedades de moneda en Java con proyectos Aspose.Tasks
url: /es/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer propiedades de moneda Java con proyectos Aspose.Tasks

## Introducción
En este tutorial **leerás propiedades de moneda java** de archivos Microsoft Project usando la API Aspose.Tasks for Java. Aspose.Tasks te permite trabajar con archivos .mpp sin necesidad de tener Microsoft Project instalado, lo que lo hace ideal para informes automatizados, migración de datos o integración en aplicaciones empresariales basadas en Java. Al final de esta guía, podrás extraer el código de moneda, el símbolo, el número de dígitos decimales y la posición del símbolo directamente de un archivo de proyecto.

## Respuestas rápidas
- **¿Qué significa “read currency properties java”?** Se refiere a recuperar metadatos relacionados con la moneda (código, símbolo, dígitos, posición) de un archivo MS Project usando código Java.  
- **¿Necesito una licencia para probar esto?** Hay una prueba gratuita de Aspose.Tasks disponible; se requiere una licencia comercial para uso en producción.  
- **¿Qué versión de JDK se requiere?** Java 8 o superior.  
- **¿Puedo modificar la configuración de moneda después de leerla?** Sí, Aspose.Tasks permite operaciones de lectura y escritura sobre las propiedades de moneda.  
- **¿Es compatible con todas las versiones de .mpp?** La API soporta archivos creados con Microsoft Project 2003‑2021.

## ¿Qué es read currency properties java?
Leer propiedades de moneda en Java significa acceder a la configuración a nivel de proyecto que define cómo se muestran los valores monetarios en un archivo Microsoft Project. Estas configuraciones incluyen el código ISO de la moneda (p. ej., **USD**), el símbolo (**$**), el número de dígitos decimales y si el símbolo aparece antes o después del importe.

## ¿Por qué leer propiedades de moneda java con Aspose.Tasks?
- **No se necesita instalación de Microsoft Project** – la API funciona en cualquier plataforma que soporte Java.  
- **Extracción rápida y en‑proceso** – ideal para el procesamiento por lotes de gran número de archivos de proyecto.  
- **Control total** – puedes combinar los valores obtenidos con informes personalizados o integrarlos en sistemas ERP.  
- **Compatibilidad entre versiones** – funciona con archivos .mpp desde Project 2003 hasta la última versión 2021.

## Requisitos previos
1. **Java Development Kit (JDK)** – Java 8 o más reciente instalado y configurado en tu `PATH`.  
2. **Aspose.Tasks for Java JAR** – descarga la última biblioteca desde [aquí](https://releases.aspose.com/tasks/java/) y añádela al classpath de tu proyecto.  

## Importar paquetes
Begin by importing the Aspose.Tasks namespace required for project manipulation:

```java
import com.aspose.tasks.*;
```

## Paso 1: Configura tu directorio de proyecto
Define the folder that contains the `.mpp` file you want to analyze. Keeping the path in a variable makes the code reusable:

```java
String dataDir = "Your Data Directory";
```

*Reemplaza `"Your Data Directory"` con la ruta absoluta o relativa a la carpeta donde se encuentra `project.mpp`.*

## Paso 2: Crear una instancia de lector de proyecto
Load the Microsoft Project file into a `Project` object. This object gives you access to all project properties, including currency settings:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Si tu archivo tiene un nombre diferente, cambia `"project.mpp"` en consecuencia.*

## Paso 3: Mostrar propiedades de moneda
Now retrieve each currency attribute using the `Prj` enumeration and print the results to the console. The API returns objects that you can convert to strings for display:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**Lo que verás:**  
- **Currency Code** – código ISO‑4217 como `USD`, `EUR`, `JPY`.  
- **Currency Digits** – usualmente `2` para la mayoría de las monedas, `0` para el yen japonés.  
- **Currency Symbol** – el carácter que se muestra en los informes (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` para **antes** del importe, `1` para **después**.

## ¿Cómo extraer el símbolo de moneda java?
Si tu único interés es el propio símbolo, puedes centrarte en la propiedad `Prj.CURRENCY_SYMBOL`. La misma llamada `project.get(...)` devuelve el símbolo, que puedes almacenar, registrar o pasar a otro servicio para su procesamiento posterior. Esto es especialmente útil cuando necesitas **extraer símbolo de moneda java** para paneles financieros o componentes de UI localizados.

## Paso 4: Finalizar proceso
Signal that the extraction finished successfully. This simple message is helpful when the code runs as part of a larger batch job:

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **FileNotFoundException** | La ruta `dataDir` es incorrecta o el nombre del archivo está mal escrito. | Verifica la cadena del directorio y asegura que el archivo `.mpp` exista en la ubicación especificada. |
| **NullPointerException on `project.get(...)`** | El archivo de proyecto no contiene información de moneda (poco probable) o la clave de la propiedad es incorrecta. | Utiliza `project.contains(Prj.CURRENCY_CODE)` para comprobar la existencia antes de leer. |
| **LicenseException** | Ejecutar sin una licencia válida de Aspose.Tasks en un entorno de producción. | Aplica un archivo de licencia usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");` antes de crear el objeto `Project`. |

## Preguntas frecuentes
**Q: ¿Es Aspose.Tasks compatible con todas las versiones de Microsoft Project?**  
**A:** Aspose.Tasks soporta archivos .mpp generados por Microsoft Project 2003‑2021, cubriendo tanto los formatos antiguos como los más recientes.

**Q: ¿Puedo modificar las propiedades de moneda usando Aspose.Tasks?**  
**A:** Sí, puedes leer y escribir la configuración de moneda. Usa `project.set(Prj.CURRENCY_CODE, "EUR");` y luego guarda el proyecto.

**Q: ¿Es Aspose.Tasks adecuado para uso comercial?**  
**A:** Absolutamente. Es una biblioteca comercial; puedes comprar una licencia [aquí](https://purchase.aspose.com/buy).

**Q: ¿Aspose.Tasks ofrece una prueba gratuita?**  
**A:** Sí, hay una prueba totalmente funcional disponible [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo buscar ayuda o soporte para Aspose.Tasks?**  
**A:** El foro oficial de Aspose.Tasks es el mejor lugar para obtener asistencia – visítalo [aquí](https://forum.aspose.com/c/tasks/15).

## Preguntas frecuentes adicionales (optimizado por IA)

**Q: ¿Cómo extraigo programáticamente solo el símbolo de moneda en Java?**  
**A:** Llama a `project.get(Prj.CURRENCY_SYMBOL)` y convierte el resultado a `String`. Esto devuelve el símbolo exacto usado en el archivo de proyecto.

**Q: ¿Puedo leer propiedades de moneda de un archivo .mpp protegido con contraseña?**  
**A:** Sí. Carga el archivo con la sobrecarga adecuada del constructor `Project` que acepta una contraseña, y luego lee las propiedades como se muestra.

**Q: ¿Qué rendimiento puedo esperar al procesar muchos archivos de proyecto?**  
**A:** Aspose.Tasks funciona en‑proceso y típicamente lee un archivo .mpp estándar en unos pocos milisegundos. Para operaciones masivas, considera reutilizar la misma instancia `Project` cuando sea posible.

## Conclusión
Ahora has aprendido cómo **leer propiedades de moneda java** y **extraer símbolo de moneda java** de un archivo MS Project usando Aspose.Tasks para Java. Esta capacidad te permite incorporar metadatos de moneda en informes personalizados, análisis financieros o pipelines de integración sin depender de Microsoft Project. Siéntete libre de experimentar modificando las propiedades o combinando estos datos con otros atributos del proyecto para crear soluciones más completas.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}