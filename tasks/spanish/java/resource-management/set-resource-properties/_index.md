---
date: 2026-01-18
description: Aprenda a establecer la tarifa estándar y otras propiedades de recursos
  en MS Project usando Aspose.Tasks para Java, incluido cómo agregar recursos en MS
  Project y gestionar los recursos de manera eficiente.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo establecer la tarifa estándar para recursos en Aspose.Tasks
url: /es/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer tarifa estándar para recursos en Aspose.Tasks

## Introducción
Si está creando aplicaciones Java que necesitan interactuar con archivos Microsoft Project, **establecer la tarifa estándar** para un recurso es una de las tareas más comunes. En este tutorial aprenderá cómo **establecer la tarifa estándar** y otras propiedades de recursos usando Aspose.Tasks para Java. Al final de la guía podrá crear un objeto de proyecto, agregar un recurso a un archivo MS Project y gestionar los recursos de MS Project con confianza.

## Respuestas rápidas
- **¿Cuál es la clase principal para trabajar con un archivo Project?** `Project`
- **¿Qué método agrega un nuevo recurso?** `project.getResources().add()`
- **¿Cómo se establece la tarifa estándar?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia válida de Aspose.Tasks.
- **¿Qué versión de Java es compatible?** Java 8+ (se recomienda el JDK más reciente).

## ¿Qué es “establecer tarifa estándar”?
La operación *establecer tarifa estándar* asigna un costo horario predeterminado a un recurso. Los gerentes de proyecto utilizan este valor para calcular costos laborales, generar informes de costos y pronosticar presupuestos.

## ¿Por qué establecer tarifas con Aspose.Tasks?
- **No se necesita instalación de Microsoft Project** – manipule archivos directamente desde Java.
- **Fidelidad total** – todos los campos de recursos, incluidos horas extra y tarifas de costo, se conservan.
- **Multiplataforma** – funciona en Windows, Linux y macOS.
- **Amigable para automatización** – ideal para procesamiento por lotes o integración con pipelines CI.

## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:

### Configuración del entorno de desarrollo Java
1. **Instalar JDK:** Asegúrese de tener el Java Development Kit (JDK) instalado en su sistema. Puede descargarlo desde el [sitio web de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. **Configuración del IDE:** Elija un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA, Eclipse o NetBeans y configúrelo en su máquina.

### Instalación de Aspose.Tasks para Java
1. **Descargar Aspose.Tasks para Java:** Visite la [página de descarga](https://releases.aspose.com/tasks/java/) y obtenga la última versión de Aspose.Tasks para Java.
2. **Integrar con el proyecto:** Incorpore la biblioteca Aspose.Tasks para Java en su proyecto Java añadiéndola como una dependencia.

## Importar paquetes
Para comenzar, necesita importar los paquetes necesarios de Aspose.Tasks para Java en su proyecto. Este paso garantiza que tenga acceso a las funcionalidades requeridas.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Paso 1: Crear un objeto Project
Crear un **objeto project** es el primer paso para cualquier manipulación de MS Project. Representa todo el archivo de proyecto en memoria.

```java
Project project = new Project();
```

## Paso 2: Agregar un recurso (add resource ms project)
Ahora **agregaremos recurso MS Project** usando la colección Resources. El nombre del recurso puede ser cualquier cosa que tenga sentido para su planificación.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Paso 3: Establecer propiedades del recurso (how to set rates)
Aquí es donde **establecemos la tarifa estándar** y también demostramos cómo establecer una tarifa de horas extra. Estas tarifas se almacenan como valores `BigDecimal` para preservar la precisión.

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
| Las tarifas aparecen como 0 en el archivo guardado | Uso de `int` en lugar de `BigDecimal`. | Siempre use `BigDecimal.valueOf()` para valores monetarios. |
| Licencia no encontrada | El archivo de licencia no se cargó antes de crear `Project`. | Cargue la licencia (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) al inicio de su programa. |

## Conclusión
Siguiendo estos pasos ha aprendido cómo **crear un objeto project**, **agregar un recurso MS Project** y **establecer la tarifa estándar** junto con otras propiedades del recurso. Esto le permite automatizar cálculos de costos, generar informes personalizados y gestionar completamente los recursos de MS Project desde Java.

## Preguntas frecuentes
### ¿Puede Aspose.Tasks para Java manejar archivos MS Project complejos?
Sí, Aspose.Tasks para Java es capaz de manejar una amplia gama de formatos de archivos MS Project, incluidos los complejos con jerarquías extensas de tareas.

### ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?
Sí, puede acceder a una prueba gratuita de Aspose.Tasks para Java desde [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte para Aspose.Tasks para Java?
Puede buscar asistencia y participar en discusiones relacionadas con Aspose.Tasks para Java en el [foro de soporte](https://forum.aspose.com/c/tasks/15).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks para Java?
Puede obtener una licencia temporal desde la [página de licencia temporal](https://purchase.aspose.com/temporary-license/) para propósitos de evaluación.

### ¿Dónde puedo comprar una versión con licencia de Aspose.Tasks para Java?
Puede comprar una versión con licencia de Aspose.Tasks para Java desde la [página de compra](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-18  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose