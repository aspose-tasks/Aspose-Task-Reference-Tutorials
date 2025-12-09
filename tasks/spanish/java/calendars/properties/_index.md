---
date: 2025-12-04
description: Aprenda a configurar el calendario del proyecto y gestionar las propiedades
  del calendario de MS Project en Java usando Aspose.Tasks. Guía paso a paso para
  mostrar las horas laborables del calendario y personalizar los horarios.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo establecer el calendario del proyecto con Aspose.Tasks para Java
url: /es/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el calendario del proyecto con Aspose.Tasks para Java

## Introducción
En este tutorial descubrirás **cómo establecer el calendario del proyecto** de forma programática usando la biblioteca Aspose.Tasks para Java. Controlar las propiedades del calendario te permite **mostrar las horas de trabajo del calendario**, definir días laborables personalizados y alinear el cronograma de tu proyecto con restricciones del mundo real. Recorreremos cada paso—desde la configuración del entorno hasta la iteración sobre los calendarios y la lectura de sus propiedades—para que puedas gestionar con confianza los calendarios de MS Project en tus aplicaciones.

## Respuestas rápidas
- **¿Qué significa “establecer el calendario del proyecto”?** Significa crear o actualizar los tiempos de trabajo de un calendario, el calendario base y los tipos de día dentro de un archivo MS Project.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java (cualquier versión reciente).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo mostrar las horas de trabajo del calendario?** Sí—leyendo cada `WeekDay` puedes mostrar las horas para cada tipo de día.  
- **¿Es compatible con Maven/Gradle?** Absolutamente—añade el JAR de Aspose.Tasks como dependencia.

## ¿Qué es un calendario de proyecto?
Un calendario de proyecto define los días y horas laborables para tareas, recursos y la línea de tiempo general del proyecto. En MS Project, los calendarios pueden heredar de un calendario base, y cada tipo de día (p. ej., **Standard**, **Non‑working**) puede tener su propio horario de trabajo. Gestionar estos ajustes de forma programática permite ajustes dinámicos del cronograma sin edición manual.

## ¿Por qué gestionar el calendario de MS Project programáticamente?
- **Automatización:** Ajustar calendarios en muchos proyectos con un solo script.  
- **Consistencia:** Aplicar políticas de tiempo de trabajo a nivel de organización.  
- **Integración:** Sincronizar calendarios con sistemas externos (RRHH, ERP).  
- **Visibilidad:** Mostrar rápidamente **las horas de trabajo del calendario** para informes o depuración.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- **Java Development Kit (JDK) 8+** instalado y `JAVA_HOME` configurado.  
- **Aspose.Tasks for Java** biblioteca descargada desde la [página de descarga](https://releases.aspose.com/tasks/java/). Añade el JAR al classpath de tu proyecto o a las dependencias de Maven/Gradle.  

## Importar paquetes
Primero, importa las clases centrales de Aspose.Tasks que utilizaremos a lo largo del tutorial:

```java
import com.aspose.tasks.*;
```

## Paso 1: Configurar el directorio de datos
Define la carpeta que contiene tus archivos de proyecto. Reemplaza el marcador de posición con la ruta real en tu máquina.

```java
String dataDir = "Your Data Directory";
```

## Paso 2: Definir unidades de tiempo
Los tiempos de trabajo se expresan en milisegundos. Definir constantes reutilizables hace que el código sea más fácil de leer.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Paso 3: Cargar datos del proyecto
Crea una instancia de `Project` cargando un archivo XML de MS Project existente (`.xml` o `.mpp`). Esto nos da acceso a todos los calendarios almacenados en el archivo.

```java
Project project = new Project(dataDir + "project.xml");
```

## Paso 4: Recorrer los calendarios y mostrar las horas de trabajo
Ahora iteramos sobre cada calendario, imprimimos su identificador único, nombre, calendario base y las horas de trabajo para cada tipo de día. Esto demuestra **cómo establecer el calendario del proyecto** y también **cómo mostrar las horas de trabajo del calendario**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Qué hace este código
- **Filtra calendarios sin nombre** (algunos calendarios internos pueden tener un nombre `null`).  
- **Imprime UID y nombre** – útil para identificar el calendario más tarde.  
- **Muestra el calendario base** – ya sea “Self” (el calendario es su propio base) o el nombre del calendario heredado.  
- **Recorre cada `WeekDay`** para calcular y mostrar el total de horas de trabajo (`workingTime` está en milisegundos, por lo que lo dividimos por `OneHour`).  

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` on `cal.getBaseCalendar()` | El calendario es él mismo un calendario base (`isBaseCalendar()` devuelve `true`). | Utiliza la verificación ternaria como se muestra (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | El archivo del proyecto usa una unidad de tiempo diferente (ticks). | Verifica el formato del archivo; Aspose.Tasks normaliza a milisegundos, pero asegúrate de estar cargando el tipo de archivo correcto. |
| Unable to locate `project.xml` | Ruta `dataDir` incorrecta. | Usa una ruta absoluta o `Paths.get(dataDir, "project.xml").toString()`. |

## Preguntas frecuentes

**P: ¿Puedo modificar las propiedades del calendario programáticamente usando Aspose.Tasks?**  
R: Sí, la API proporciona acceso completo de lectura/escritura a los calendarios, permitiéndote añadir, editar o eliminar tiempos de trabajo, excepciones y relaciones de calendario base.

**P: ¿Existen limitaciones para la personalización del calendario con Aspose.Tasks?**  
R: La biblioteca replica las capacidades de Microsoft Project, por lo que puedes personalizar prácticamente todos los aspectos del calendario. Sólo versiones muy antiguas de archivos Project pueden presentar pequeñas incompatibilidades.

**P: ¿Puedo integrar la gestión de calendarios en proyectos Java existentes?**  
R: Absolutamente. Simplemente añade el JAR de Aspose.Tasks a tu ruta de compilación y usa los mismos patrones de código mostrados aquí.

**P: ¿Aspose.Tasks admite otras funcionalidades de gestión de proyectos además de la gestión de calendarios?**  
R: Sí, cubre tareas, recursos, asignaciones, esquemas, líneas base y más, convirtiéndose en una solución integral para la automatización de proyectos basada en Java.

**P: ¿Hay soporte técnico disponible para desarrolladores que usan Aspose.Tasks?**  
R: Sí, Aspose ofrece foros dedicados, soporte por correo electrónico y documentación extensa para todos los usuarios con licencia.

## Conclusión
Al seguir esta guía ahora sabes **cómo establecer el calendario del proyecto**, leer y **mostrar las horas de trabajo del calendario**, e integrar estas capacidades en cualquier aplicación Java usando Aspose.Tasks. Esto te permite automatizar ajustes de cronograma, aplicar políticas de trabajo consistentes y crear soluciones de gestión de proyectos más robustas.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}