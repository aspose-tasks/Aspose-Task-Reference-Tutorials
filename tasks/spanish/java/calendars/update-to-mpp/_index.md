---
date: 2025-12-03
description: Aprende cómo crear un calendario en MS Project, convertir el proyecto
  a MPP y guardar el proyecto MPP sin esfuerzo usando Aspose.Tasks para Java.
language: es
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Crear calendario en MS Project y guardar como MPP con Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear calendario MS Project y guardarlo como MPP con Aspose.Tasks

## Introducción

En la gestión moderna de proyectos a menudo necesitas **crear archivos de calendario MS Project** y luego compartirlos en el formato nativo MPP. Ya sea que estés consolidando cronogramas de múltiples fuentes o migrando datos heredados, poder generar un calendario programáticamente ahorra tiempo y elimina errores manuales. Este tutorial te guía a través del proceso completo de crear un calendario en MS Project, personalizarlo y, finalmente, **convertir el proyecto a MPP** usando la API Java de Aspose.Tasks.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Crear un calendario en MS Project y guardarlo como un archivo MPP con Aspose.Tasks para Java.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o superior (JDK 8+).  
- **¿Puedo personalizar el calendario?** Sí, puedes agregar horarios de trabajo, excepciones y festivos.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un calendario básico.

## ¿Qué es “crear calendario MS Project”?

Crear un calendario MS Project significa definir programáticamente los días laborables, horas y excepciones que impulsan la programación de tareas dentro de un archivo Microsoft Project. Al usar Aspose.Tasks puedes construir, modificar y persistir estos calendarios sin nunca abrir la interfaz de Microsoft Project.

## ¿Por qué usar Aspose.Tasks para esta tarea?

- **Compatibilidad total .NET/Java** – funciona en cualquier plataforma que soporte Java.  
- **No se necesita instalación de COM u Office** – ideal para automatización del lado del servidor.  
- **API completa** – soporta todas las propiedades del calendario, incluidas semanas de trabajo personalizadas y festivos.  
- **Salida directa MPP** – puedes **guardar el proyecto como MPP** sin conversiones intermedias.

## Requisitos previos

1. **Java Development Kit (JDK) 8+** – asegúrate de que `java -version` muestre 1.8 o superior.  
2. **Aspose.Tasks for Java** – descarga el JAR más reciente desde el [sitio web de Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse o cualquier editor que prefieras.  
4. **Conocimientos básicos de Java** – familiaridad con clases, métodos y E/S de archivos.

## Guía paso a paso

### Paso 1: Importar paquetes requeridos

Primero, trae las clases de Aspose.Tasks y las utilidades de Java al alcance.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Paso 2: Configurar el directorio de datos

Define dónde vivirán tus plantillas de entrada y archivos de salida. Reemplaza el marcador de posición con la ruta real en tu máquina.

```java
String dataDir = "Your Data Directory";
```

### Paso 3: Definir nombres de archivo de entrada y salida

Cargaremos un archivo MPP existente (o un proyecto en blanco) y escribiremos el resultado en un nuevo archivo.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Paso 4: Cargar el proyecto y agregar un nuevo calendario

Crea una instancia `Project` a partir del archivo fuente y agrega un calendario llamado **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Paso 5: Personalizar el calendario (opcional)

Si necesitas horarios de trabajo específicos, festivos o excepciones, llama a tu propio método auxiliar. El ejemplo usa `GetTestCalendar` como marcador de posición.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Consejo profesional:** Puedes manipular directamente `cal1.getWeekDays()` para establecer las horas de trabajo de cada día de la semana.

### Paso 6: Asignar el calendario al proyecto

Indica al proyecto que use el calendario recién creado para todos sus cálculos de programación.

```java
project.set(Prj.CALENDAR, cal1);
```

### Paso 7: Guardar el proyecto como MPP

Ahora **convierte el proyecto a MPP** guardándolo con la opción `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Paso 8: Confirmar la finalización exitosa

Un mensaje simple en la consola te indica que el proceso finalizó sin errores.

```java
System.out.println("Process completed Successfully");
```

## Casos de uso comunes

- **Generación automática de cronogramas** para proyectos recurrentes (p. ej., sprints semanales).  
- **Migrar calendarios heredados de CSV o Excel** a un archivo MS Project con todas sus funcionalidades.  
- **Informes del lado del servidor** donde un servicio web devuelve un archivo MPP bajo demanda.  

## Solución de problemas y errores comunes

| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` al ejecutar `project.save` | `dataDir` apunta a una carpeta que no existe | Asegúrate de que el directorio exista o créalo programáticamente. |
| El calendario no se aplica a las tareas | Las tareas siguen referenciando el calendario predeterminado | Después de establecer `Prj.CALENDAR`, también actualiza `Task.CALENDAR` de cada tarea si fueron sobrescritas previamente. |
| El archivo de salida tiene 0 KB | Faltan permisos de escritura | Ejecuta la JVM con los permisos de sistema de archivos adecuados o elige una ruta con permisos de escritura. |

## Preguntas frecuentes

**P: ¿Aspose.Tasks para Java es compatible con diferentes versiones de MS Project?**  
R: Sí, Aspose.Tasks para Java soporta una amplia gama de versiones de MS Project, desde Project 2007 hasta la última versión, garantizando compatibilidad sin problemas.

**P: ¿Puedo personalizar los calendarios según requisitos específicos del proyecto?**  
R: Por supuesto. Puedes definir días laborables, establecer semanas de trabajo personalizadas, agregar festivos e incluso crear varios calendarios dentro de un mismo archivo de proyecto.

**P: ¿Aspose.Tasks para Java ofrece soporte para solución de problemas y asistencia?**  
R: Sí, puedes obtener ayuda en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**P: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
R: Sí, una prueba gratuita totalmente funcional está disponible [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks para Java?**  
R: Las licencias temporales pueden solicitarse a través del sitio web de Aspose [aquí](https://purchase.aspose.com/temporary-license/).

**Última actualización:** 2025-12-03  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}