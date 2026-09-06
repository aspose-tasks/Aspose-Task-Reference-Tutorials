---
date: 2026-08-24
description: Aprenda cómo agregar un recurso a MS Project, establecer la tarifa estándar
  y otras propiedades del recurso en MS Project usando Aspose.Tasks para Java, y gestionar
  los recursos de manera eficiente.
keywords:
- add resource ms project
- set resource rate
- manage ms project resources
- create ms project file
lastmod: 2026-08-24
linktitle: Establecer propiedades del recurso en Aspose.Tasks
og_description: Agregue un recurso a MS Project y establezca la tarifa estándar usando
  Aspose.Tasks para Java. Aprenda los requisitos previos, el código paso a paso y
  la solución de problemas en esta guía concisa.
og_image_alt: Screenshot of Aspose.Tasks Java code setting resource rates
og_title: Agregar recurso a MS Project y establecer tarifa con Aspose.Tasks (Java)
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  headline: How to add resource ms project with Aspose.Tasks
  type: TechArticle
- description: Learn how to add resource ms project, set standard rate and other resource
    properties in MS Project using Aspose.Tasks for Java, and manage resources efficiently.
  name: How to add resource ms project with Aspose.Tasks
  steps:
  - name: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
    text: Install JDK 8 or newer. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
  - name: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
    text: Choose an IDE such as IntelliJ IDEA, Eclipse, or NetBeans and configure
      it for Java development.
  - name: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
    text: Download the latest Aspose.Tasks for Java package from the [download page](https://releases.aspose.com/tasks/java/).
  - name: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
    text: Add the JAR files to your project’s classpath or declare the Maven/Gradle
      dependency as shown in the product documentation.
  type: HowTo
- questions:
  - answer: Yes, it supports all major Project formats, including large files with
      thousands of tasks and resources, preserving every field without data loss.
    question: Can Aspose.Tasks for Java handle complex MS Project files?
  - answer: Yes, you can access a free trial of Aspose.Tasks for Java from the [Aspose.Tasks
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: You can seek assistance on the [support forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks for Java?
  - answer: A temporary license is available from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Purchase a full license from the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase a licensed version?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose tasks
- java project automation
- ms project resources
- resource rate
title: Cómo agregar un recurso a MS Project con Aspose.Tasks
url: /es/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar recurso ms project y establecer tarifa en Aspose.Tasks

## Introducción
Si está desarrollando aplicaciones Java que necesitan leer o escribir archivos Microsoft Project, **agregar un recurso ms project** y configurar su tarifa estándar es una tarea rutinaria pero esencial. En esta guía verá cómo crear un objeto `Project`, agregar un recurso y establecer tanto tarifas estándar como de horas extra usando Aspose.Tasks para Java. Al final podrá automatizar cálculos de costos y mantener sus cronogramas de proyecto actualizados sin requerir que Microsoft Project esté instalado.

## Respuestas rápidas
- **¿Qué clase representa un archivo Project?** `Project`
- **¿Qué llamada agrega un nuevo recurso?** `project.getResources().add()`
- **¿Cómo se establece la tarifa estándar?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **¿Se requiere una licencia para uso en producción?** Sí, debe cargar una licencia válida de Aspose.Tasks.
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores (se recomienda Java 17+).

## Qué es “establecer tarifa estándar”
La operación *establecer tarifa estándar* asigna un costo horario predeterminado a un recurso. Esta tarifa es utilizada por los gerentes de proyecto para calcular los gastos de mano de obra, generar informes de costos y pronosticar presupuestos, asegurando que los cálculos de costos reflejen el precio esperado del trabajo realizado por cada recurso a lo largo del ciclo de vida del proyecto.

## Por qué establecer tarifas con Aspose.Tasks?
Aspose.Tasks puede procesar **más de 50 formatos de entrada y salida**, incluidos archivos MPP, MPX, XML y Primavera, y maneja proyectos de cientos de páginas sin cargar todo el archivo en memoria. Esto permite procesamiento por lotes de alto rendimiento en servidores Windows, Linux o macOS, reduciendo el esfuerzo manual hasta en un 90 % en escenarios típicos de automatización.

## Requisitos previos
Antes de comenzar, asegúrese de que los siguientes elementos estén listos:

### Configuración del entorno de desarrollo Java
1. Instale JDK 8 o una versión más reciente. Puede descargarlo desde el [sitio web de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Elija un IDE como IntelliJ IDEA, Eclipse o NetBeans y configúrelo para el desarrollo Java.

### Instalación de Aspose.Tasks para Java
1. Descargue el paquete más reciente de Aspose.Tasks para Java desde la [página de descarga](https://releases.aspose.com/tasks/java/).  
2. Añada los archivos JAR al classpath de su proyecto o declare la dependencia Maven/Gradle como se muestra en la documentación del producto.

## Importar paquetes
Importe las clases principales de Aspose.Tasks que necesitará. Este paso le brinda acceso a los tipos `Project`, `Resource` y `Rsc` que se usan más adelante.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Paso 1: crear un objeto proyecto
La clase `Project` es el objeto de nivel superior que representa un archivo MS Project completo en memoria. Instanciarla crea un proyecto vacío que puede poblar con tareas, recursos y otros datos.

```java
Project project = new Project();
```

## Paso 2: agregar un recurso (add resource ms project)
La clase `Resource` modela un único recurso del proyecto, como una persona, equipo o material. Agregar un recurso mediante `project.getResources().add()` devuelve una instancia `Resource` no nula lista para la configuración de propiedades.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Paso 3: establecer propiedades del recurso (how to set rates)
El enum `Rsc` contiene constantes para los campos del recurso, como `STANDARD_RATE` y `OVERTIME_RATE`.  
Establece las tarifas estándar y de horas extra llamando a `set` en el objeto `Resource` con los valores apropiados del enum `Rsc`. Las tarifas se almacenan como `BigDecimal` para preservar la precisión monetaria.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| `NullPointerException` al llamar a `set` | El recurso no se agregó correctamente. | Asegúrese de que `project.getResources().add()` devuelva un `Resource` no nulo. |
| Las tarifas aparecen como 0 en el archivo guardado | Se usó `int` en lugar de `BigDecimal`. | Siempre use `BigDecimal.valueOf()` para valores monetarios. |
| Licencia no encontrada | El archivo de licencia no se cargó antes de crear `Project`. | Cargue la licencia (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) al iniciar el programa. |

## Conclusión
Ahora sabe cómo **agregar recurso ms project**, crear un objeto `Project` y **establecer tarifas estándar y de horas extra** usando Aspose.Tasks para Java. Esta capacidad le permite automatizar cálculos de costos, generar informes personalizados y gestionar completamente los recursos de MS Project desde cualquier aplicación Java.

## Preguntas frecuentes
**Q: ¿Puede Aspose.Tasks para Java manejar archivos MS Project complejos?**  
A: Sí, admite todos los formatos principales de Project, incluidos archivos grandes con miles de tareas y recursos, preservando cada campo sin pérdida de datos.

**Q: ¿Hay una versión de prueba gratuita disponible?**  
A: Sí, puede acceder a una prueba gratuita de Aspose.Tasks para Java desde la [página de prueba gratuita de Aspose.Tasks](https://releases.aspose.com/).

**Q: ¿Dónde puedo obtener soporte para Aspose.Tasks para Java?**  
A: Puede buscar asistencia en el [foro de soporte](https://forum.aspose.com/c/tasks/15).

**Q: ¿Cómo obtengo una licencia temporal para evaluación?**  
A: Una licencia temporal está disponible en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo comprar una versión con licencia?**  
A: Compre una licencia completa en la [página de compra](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-08-24  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo crear recursos – Gestión de recursos con Aspose.Tasks para Java](/tasks/java/resource-management/)
- [Agregar recurso al proyecto con Aspose.Tasks para Java](/tasks/java/resource-management/create-resources/)
- [Cómo agregar recurso al proyecto y manejar propiedades de retraso de nivelación en Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}