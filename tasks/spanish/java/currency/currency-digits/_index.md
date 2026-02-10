---
date: 2026-02-10
description: Aprende cómo obtener valores de moneda, leer archivos de MS Project y
  convertir archivos de proyecto a Java usando Aspose.Tasks. Guía paso a paso para
  extraer dígitos de moneda.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo obtener la moneda de MS Project con Aspose.Tasks
url: /es/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo obtener la moneda de MS Project usando Aspose.Tasks

## Introducción
Si te preguntas **cómo obtener la moneda** de un archivo Microsoft Project, has llegado al lugar correcto. En este tutorial exhaustivo descubrirás **cómo trabajar con valores de ms project currency** usando la biblioteca Aspose.Tasks para Java. Ya sea que estés construyendo una herramienta de informes, una utilidad de migración o simplemente necesites leer la configuración de moneda de un **archivo de proyecto java**, esta guía te lleva paso a paso—from cargar un archivo *.mpp* hasta extraer los dígitos de la moneda. Al final, te sentirás cómodo manejando datos de ms project currency en tus propias aplicaciones.

## Respuestas rápidas
- **¿Qué biblioteca lee archivos MS Project?** Aspose.Tasks for Java.  
- **¿Cuántas líneas de código se necesitan para obtener los dígitos de la moneda?** Solo tres líneas concisas después de cargar el proyecto.  
- **¿Necesito una licencia para el desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior (cualquier JDK que ejecute Aspose.Tasks).  
- **¿Puedo recuperar otras propiedades del proyecto?** Sí – Aspose.Tasks expone un conjunto completo de campos del proyecto (p. ej., fecha de inicio, tarifas de costos, etc.).

## Qué es la moneda de ms project?
`ms project currency` se refiere a la precisión numérica (número de decimales) que Microsoft Project usa al mostrar valores monetarios. Se almacena en el archivo del proyecto como la propiedad **CURRENCY_DIGITS** y determina si los importes aparecen como números enteros, con un decimal, dos decimales, etc.

## ¿Por qué usar Aspose.Tasks para manejar la moneda de ms project?
- **No se requiere instalación de Microsoft Project** – trabaja directamente con archivos *.mpp* en cualquier plataforma que soporte Java.  
- **Fuerte seguridad de tipos** – la API devuelve valores fuertemente tipados, reduciendo errores de análisis.  
- **Optimizado para rendimiento** – carga proyectos grandes rápidamente y extrae solo los campos que necesitas.  
- **Multiplataforma** – se ejecuta en Windows, Linux o macOS sin modificaciones.

## Requisitos previos
Antes de comenzar, asegúrate de tener lo siguiente:

1. **Entorno de desarrollo Java** – JDK 8 o posterior instalado y configurado.  
2. **Aspose.Tasks for Java** – descarga el JAR más reciente desde el sitio oficial: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conocimientos básicos de Java** – deberías estar cómodo creando un proyecto Java, añadiendo bibliotecas externas y ejecutando un método `main`.  

## Importar paquetes
Primero, importa las clases que necesitaremos.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Paso 1: Definir el directorio de datos
Especifica la carpeta que contiene tu **archivo de proyecto java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Reemplaza `"Your Data Directory"` con la ruta absoluta o relativa donde se encuentra `project.mpp`.

## Paso 2: Cargar el archivo MPP  
Ahora veremos **cómo cargar archivos mpp** usando Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Asegúrate de que el nombre del archivo coincida exactamente; de lo contrario, se lanzará una `IOException`.

## Paso 3: Recuperar los dígitos de la moneda  
Con el proyecto cargado, extraer los dígitos de la **moneda de ms project** es una sola línea:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
La llamada devuelve un `Integer` que representa el número de decimales (p. ej., `2` para centavos). El valor se imprime en la consola, pero también puedes almacenarlo en una variable para procesamiento posterior.

## Problemas comunes y consejos
- **Archivo no encontrado** – verifica la ruta `dataDir` y asegúrate de que el nombre del archivo sea correcto, incluida la extensión `.mpp`.  
- **Versión de archivo no compatible** – Aspose.Tasks soporta formatos Project 2000‑2024; los archivos más antiguos o corruptos pueden necesitar conversión.  
- **Licencia no establecida** – durante el desarrollo una prueba funciona, pero para producción debes aplicar una licencia válida para evitar marcas de agua de evaluación.

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks manejar otros atributos del proyecto además de los dígitos de la moneda?**  
R: Sí, Aspose.Tasks ofrece una amplia gama de funcionalidades para manipular varios aspectos de los archivos del proyecto, como tareas, recursos y campos personalizados.

**P: ¿Es Aspose.Tasks adecuado para aplicaciones a nivel empresarial?**  
R: Absolutamente, Aspose.Tasks está diseñado para satisfacer las demandas de proyectos de nivel empresarial, ofreciendo alto rendimiento y escalabilidad.

**P: ¿Aspose.Tasks soporta desarrollo multiplataforma?**  
R: Sí, puedes usar Aspose.Tasks for Java en cualquier plataforma que soporte el Java Runtime Environment (Windows, Linux, macOS).

**P: ¿Puedo probar Aspose.Tasks antes de comprar?**  
R: Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks?**  
R: Puedes encontrar soporte en el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusión
Ahora sabes **cómo obtener los dígitos de la moneda** de un archivo MS Project usando Aspose.Tasks for Java. El proceso es sencillo: carga el proyecto, llama a `project.get(Prj.CURRENCY_DIGITS)` y usa el resultado en tu aplicación. Siéntete libre de explorar otras propiedades del proyecto con el mismo patrón e integrar esta lógica en soluciones de informes o migración más grandes.

---

**Última actualización:** 2026-02-10  
**Probado con:** Aspose.Tasks for Java (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}