---
date: 2026-02-05
description: Aprenda cómo agregar festivos a un calendario, asignar el calendario
  a un proyecto y guardar el archivo de MS Project como MPP usando Aspose.Tasks para
  Java.
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Agregar días festivos al calendario y guardar como MPP con Aspose.Tasks
url: /es/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar días festivos al calendario y guardar como MPP con Aspose.Tasks

## Introducción

En la gestión moderna de proyectos a menudo necesitas **add holidays to calendar** archivos, crear un **MS Project calendar**, y luego compartir el cronograma en el formato nativo MPP. Ya sea que estés consolidando líneas de tiempo de múltiples fuentes o migrando datos heredados, generar un calendario programáticamente elimina errores manuales y acelera la entrega. Este tutorial te guía a través del proceso completo de crear un calendario en MS Project, personalizarlo con festivos, **assign calendar to project**, y finalmente **convert project to MPP** usando la API Java de Aspose.Tasks.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Agregar festivos a un calendario, asignarlo a un proyecto y guardar el resultado como archivo MPP con Aspose.Tasks para Java.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o superior (JDK 8+).  
- **¿Puedo personalizar el calendario?** Sí – puedes agregar horarios de trabajo, excepciones y festivos.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un calendario básico.  

## ¿Qué es “create calendar MS Project”?

Crear un calendario MS Project significa definir programáticamente los días laborables, horas y excepciones que impulsan la programación de tareas dentro de un archivo Microsoft Project. Al usar Aspose.Tasks puedes **java create project calendar**, modificarlo y persistir los cambios sin abrir nunca la interfaz de Microsoft Project.

## ¿Por qué usar Aspose.Tasks para esta tarea?

- **Compatibilidad total .NET/Java** – funciona en cualquier plataforma que soporte Java.  
- **Sin necesidad de COM o instalación de Office** – ideal para automatización del lado del servidor y **automate schedule generation**.  
- **API rica** – soporta cada propiedad del calendario, incluyendo semanas de trabajo personalizadas y festivos.  
- **Salida directa a MPP** – puedes **save project as MPP** sin conversiones intermedias.

## Requisitos previos

1. **Java Development Kit (JDK) 8+** – asegúrate de que `java -version` muestre 1.8 o superior.  
2. **Aspose.Tasks for Java** – descarga el JAR más reciente desde el [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, o cualquier editor que prefieras.  
4. **Conocimientos básicos de Java** – familiaridad con clases, métodos y E/S de archivos.

## Cómo agregar días festivos al calendario

A continuación, recorremos cada paso, desde la configuración del entorno hasta la persistencia del archivo MPP final. Los bloques de código permanecen sin cambios respecto al tutorial original; las explicaciones circundantes se han ampliado para mayor claridad.

### Paso 1: Importar paquetes requeridos

Primero, trae las clases de Aspose.Tasks y las utilidades de Java al alcance.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Paso 2: Configurar el directorio de datos

Define dónde vivirán tu plantilla de entrada y los archivos de salida. Reemplaza el marcador de posición con la ruta real en tu máquina.

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

> **Pro tip:** Puedes manipular directamente `cal1.getWeekDays()` para establecer horas laborables para cada día de la semana, o usar `cal1.getExceptions()` para **add holidays to calendar**.

### Paso 6: Asignar el calendario al proyecto

Indica al proyecto que use el calendario recién creado para todos sus cálculos de programación.

```java
project.set(Prj.CALENDAR, cal1);
```

### Paso 7: Guardar el proyecto como MPP

Ahora **convert project to MPP** guardándolo con la opción `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Paso 8: Confirmar la finalización exitosa

Un simple mensaje en la consola te informa que el proceso terminó sin errores.

```java
System.out.println("Process completed Successfully");
```

## Casos de uso comunes

- **Generación automatizada de cronogramas** para proyectos recurrentes (p. ej., sprints semanales).  
- **Migración de calendarios heredados en CSV o Excel** a un archivo MS Project con todas sus funciones.  
- **Informes del lado del servidor** donde un servicio web devuelve un archivo MPP bajo demanda.  

## Solución de problemas y errores comunes

| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` al guardar el proyecto | `dataDir` apunta a una carpeta que no existe | Asegúrate de que el directorio exista o créalo programáticamente. |
| El calendario no se aplica a las tareas | Las tareas siguen referenciando el calendario predeterminado | Después de establecer `Prj.CALENDAR`, también actualiza `Task.CALENDAR` de cada tarea si se había sobrescrito previamente. |
| El archivo de salida tiene 0 KB | Falta de permisos de escritura | Ejecuta la JVM con los derechos de sistema de archivos adecuados o elige una ruta que sea escribible. |

## Preguntas frecuentes

**Q: ¿Es Aspose.Tasks para Java compatible con diferentes versiones de MS Project?**  
A: Sí, Aspose.Tasks para Java soporta una amplia gama de versiones de MS Project, desde Project 2007 hasta la última versión, garantizando una compatibilidad sin problemas.

**Q: ¿Puedo personalizar los calendarios según requisitos específicos del proyecto?**  
A: Absolutamente. Puedes definir días laborables, establecer semanas de trabajo personalizadas, agregar festivos e incluso crear múltiples calendarios dentro de un solo archivo de proyecto.

**Q: ¿Aspose.Tasks para Java ofrece soporte para solución de problemas y asistencia?**  
A: Sí, puedes obtener ayuda en el foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**Q: ¿Hay una prueba gratuita disponible para Aspose.Tasks para Java?**  
A: Sí, una prueba gratuita totalmente funcional está disponible [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Tasks para Java?**  
A: Las licencias temporales pueden solicitarse a través del sitio web de Aspose [aquí](https://purchase.aspose.com/temporary-license/).

**Última actualización:** 2026-02-05  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}