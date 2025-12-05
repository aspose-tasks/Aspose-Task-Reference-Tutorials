---
date: 2025-12-05
description: Aprenda a manejar los dígitos de moneda en MS Project de manera eficiente
  usando Aspose.Tasks para Java. Guía paso a paso que cubre el manejo de archivos
  de proyecto Java y cómo cargar archivos MPP.
language: es
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Manejar los dígitos de moneda de MS Project con Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manejar los dígitos de moneda de MS Project con Aspose.Tasks

## Introducción
En este tutorial exhaustivo descubrirás **cómo trabajar con los valores de moneda de MS Project** usando la biblioteca Aspose.Tasks para Java. Ya sea que estés construyendo una herramienta de informes, una utilidad de migración, o simplemente necesites leer la configuración de moneda de un **archivo de proyecto Java**, esta guía te acompañará paso a paso—desde cargar un archivo *.mpp* hasta extraer los dígitos de moneda. Al final, te sentirás cómodo manejando datos de moneda de MS Project en tus propias aplicaciones.

## Respuestas rápidas
- **¿Qué biblioteca lee archivos de MS Project?** Aspose.Tasks para Java.  
- **¿Cuántas líneas de código se necesitan para obtener los dígitos de moneda?** Solo tres líneas concisas después de cargar el proyecto.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior (cualquier JDK que ejecute Aspose.Tasks).  
- **¿Puedo obtener otras propiedades del proyecto?** Sí – Aspose.Tasks expone un conjunto completo de campos del proyecto (p. ej., fecha de inicio, tarifas de costos, etc.).

## ¿Qué es la moneda de MS Project?
`ms project currency` se refiere a la precisión numérica (número de decimales) que Microsoft Project usa al mostrar valores monetarios. Se almacena en el archivo del proyecto como la propiedad **CURRENCY_DIGITS** y determina si los importes aparecen como números enteros, con un decimal, dos decimales, etc.

## ¿Por qué usar Aspose.Tasks para manejar la moneda de MS Project?
- **No se requiere instalación de Microsoft Project** – trabaja directamente con archivos *.mpp* en cualquier plataforma que soporte Java.  
- **Seguridad de tipos fuerte** – la API devuelve valores tipados, reduciendo errores de análisis.  
- **Optimizada para rendimiento** – carga proyectos grandes rápidamente y extrae solo los campos que necesitas.  
- **Multiplataforma** – se ejecuta en Windows, Linux o macOS sin modificaciones.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

1. **Entorno de desarrollo Java** – JDK 8 o superior instalado y configurado.  
2. **Aspose.Tasks para Java** – descarga el JAR más reciente desde el sitio oficial: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
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
Especifica la carpeta que contiene tu **archivo de proyecto Java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Reemplaza `"Your Data Directory"` con la ruta absoluta o relativa donde reside `project.mpp`.

## Paso 2: Cargar el archivo MPP  
Ahora veremos **cómo cargar archivos mpp** usando Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Asegúrate de que el nombre del archivo coincida exactamente; de lo contrario, se lanzará una `IOException`.

## Paso 3: Recuperar los dígitos de moneda  
Con el proyecto cargado, extraer los **dígitos de moneda de MS Project** es una sola línea:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
La llamada devuelve un `Integer` que representa el número de decimales (p. ej., `2` para centavos). El valor se imprime en la consola, pero también puedes almacenarlo en una variable para procesamiento posterior.

## Problemas comunes y consejos
- **Archivo no encontrado** – verifica la ruta `dataDir` y asegura que el nombre del archivo sea correcto, incluida la extensión `.mpp`.  
- **Versión de archivo no compatible** – Aspose.Tasks soporta formatos Project 2000‑2024; los archivos más antiguos o corruptos pueden necesitar conversión.  
- **Licencia no establecida** – durante el desarrollo una prueba funciona, pero en producción debes aplicar una licencia válida para evitar marcas de evaluación.

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks manejar otros atributos del proyecto además de los dígitos de moneda?**  
R: Sí, Aspose.Tasks ofrece una amplia gama de funcionalidades para manipular varios aspectos de los archivos de proyecto, como tareas, recursos y campos personalizados.

**P: ¿Es Aspose.Tasks adecuado para aplicaciones a nivel empresarial?**  
R: Absolutamente, Aspose.Tasks está diseñado para satisfacer las exigencias de proyectos de nivel empresarial, ofreciendo alto rendimiento y escalabilidad.

**P: ¿Aspose.Tasks admite desarrollo multiplataforma?**  
R: Sí, puedes usar Aspose.Tasks para Java en cualquier plataforma que soporte el Java Runtime Environment (Windows, Linux, macOS).

**P: ¿Puedo probar Aspose.Tasks antes de comprar?**  
R: Sí, puedes descargar una versión de prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo obtener soporte para Aspose.Tasks?**  
R: Puedes encontrar soporte en el [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2025-12-05  
**Probado con:** Aspose.Tasks para Java 24.11 (última disponible al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}