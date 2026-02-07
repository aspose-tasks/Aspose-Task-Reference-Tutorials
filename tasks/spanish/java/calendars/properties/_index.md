---
date: 2026-02-07
description: Aprenda cómo configurar el calendario del proyecto en Java y gestionar
  las propiedades del calendario de MS Project usando Aspose.Tasks. Guía paso a paso
  para mostrar las horas laborables del calendario y personalizar los horarios.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo establecer el calendario del proyecto en Java con Aspose.Tasks
url: /es/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el calendario del proyecto Java con Aspose.Tasks

## Introducción
En este tutorial descubrirás **how to set project calendar java** de forma programática usando la biblioteca Aspose.Tasks para Java. Controlar las propiedades del calendario te permite **display calendar working hours**, definir días laborables personalizados y alinear el cronograma de tu proyecto con restricciones del mundo real. Recorreremos cada paso—desde la configuración del entorno hasta la iteración sobre los calendarios y la lectura de sus propiedades—para que puedas **manage ms project calendar** con confianza en tus aplicaciones.

## Respuestas rápidas
- **What does “set project calendar” mean?** Significa crear o actualizar los horarios de trabajo, el calendario base y los tipos de día dentro de un archivo MS Project.  
- **Which library is required?** Aspose.Tasks for Java (cualquier versión reciente).  
- **Do I need a license?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **Can I display calendar working hours?** Sí—leyendo cada `WeekDay` puedes mostrar las horas para cada tipo de día.  
- **Is this compatible with Maven/Gradle?** Absolutamente—añade el JAR de Aspose.Tasks como dependencia.

## Cómo establecer el calendario del proyecto Java
Esta sección aborda directamente la palabra clave principal. Cubriremos los pasos exactos que necesitas para **set project calendar java**, modificar los días laborables del calendario y **calculate working hours java‑style**.

## ¿Qué es un calendario de proyecto?
Un calendario de proyecto define los días y horas laborables para tareas, recursos y la línea de tiempo general del proyecto. En MS Project, los calendarios pueden heredar de un calendario base, y cada tipo de día (p. ej., **Standard**, **Non‑working**) puede tener su propio horario de trabajo. Gestionar estos ajustes programáticamente permite ajustes dinámicos del cronograma sin edición manual.

## ¿Por qué gestionar el calendario de MS Project programáticamente?
- **Automatización:** Ajusta calendarios en muchos proyectos con un solo script.  
- **Consistencia:** Aplica políticas de tiempo de trabajo a nivel organizacional.  
- **Integración:** Sincroniza calendarios con sistemas externos (RRHH, ERP).  
- **Visibilidad:** Muestra rápidamente **display calendar working hours** para informes o depuración.  
- **Flexibilidad:** Puedes **modify calendar working days** o añadir excepciones al vuelo.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- **Java Development Kit (JDK) 8+** instalado y `JAVA_HOME` configurado.  
- **Aspose.Tasks for Java** biblioteca descargada desde la [download page](https://releases.aspose.com/tasks/java/). Añade el JAR al classpath de tu proyecto o a las dependencias de Maven/Gradle.  

## Importar paquetes
Primero, importa las clases principales de Aspose.Tasks que utilizaremos a lo largo del tutorial:

```java
import com.aspose.tasks.*;
```

## Paso 1: Configurar el directorio de datos
Define la carpeta que contiene tus archivos de proyecto. Reemplaza el marcador de posición con la ruta real en tu máquina.

```java
String dataDir = "Your Data Directory";
```

## Paso 2: Definir unidades de tiempo
Los horarios de trabajo se expresan en milisegundos. Definir constantes reutilizables facilita la lectura del código y te ayuda a **calculate working hours java** con precisión.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Paso 3: Cargar datos del proyecto
Crea una instancia de `Project` cargando un archivo XML de MS Project existente (`.xml` o `.mpp`). Esto nos brinda acceso a todos los calendarios almacenados en el archivo.

```java
Project project = new Project(dataDir + "project.xml");
```

## Recorrer calendarios Java
Ahora iteramos sobre cada calendario, imprimimos su identificador único, nombre, calendario base y las horas de trabajo para cada tipo de día. Esto demuestra **how to set project calendar java** y también cómo **display calendar working hours**.

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
- **Filters unnamed calendars** (some internal calendars may have a `null` name). → **Filtra calendarios sin nombre** (algunos calendarios internos pueden tener un nombre `null`).  
- **Prints UID and name** – useful for identifying the calendar later. → **Imprime UID y nombre**, útil para identificar el calendario más adelante.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar. → **Muestra el calendario base**, ya sea “Self” (el calendario es su propio base) o el nombre del calendario heredado.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`). → **Recorre cada `WeekDay`** para calcular y mostrar el total de horas laborables (`workingTime` está en milisegundos, por lo que lo dividimos por `OneHour`).  

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` on `cal.getBaseCalendar()` | El calendario es un calendario base (`isBaseCalendar()` devuelve `true`). | Usa la verificación ternaria como se muestra (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | El archivo del proyecto usa una unidad de tiempo diferente (ticks). | Verifica el formato del archivo; Aspose.Tasks normaliza a milisegundos, pero asegúrate de cargar el tipo de archivo correcto. |
| Unable to locate `project.xml` | Ruta `dataDir` incorrecta. | Usa una ruta absoluta o `Paths.get(dataDir, "project.xml").toString()`. |

## Preguntas frecuentes

**Q: ¿Puedo modificar las propiedades del calendario programáticamente usando Aspose.Tasks?**  
A: Sí, la API brinda acceso completo de lectura/escritura a los calendarios, permitiéndote añadir, editar o eliminar horarios de trabajo, excepciones y relaciones de calendario base.

**Q: ¿Existen limitaciones en la personalización del calendario con Aspose.Tasks?**  
A: La biblioteca refleja las capacidades de Microsoft Project, por lo que puedes personalizar prácticamente todos los aspectos del calendario. Sólo versiones muy antiguas de archivos Project pueden presentar pequeñas incompatibilidades.

**Q: ¿Puedo integrar la gestión de calendarios en proyectos Java existentes?**  
A: Absolutamente. Simplemente agrega el JAR de Aspose.Tasks a tu ruta de compilación y utiliza los mismos patrones de código mostrados aquí.

**Q: ¿Aspose.Tasks admite otras funcionalidades de gestión de proyectos además de la gestión de calendarios?**  
A: Sí, cubre tareas, recursos, asignaciones, esquemas, líneas base y más, convirtiéndose en una solución integral para la automatización de proyectos basada en Java.

**Q: ¿Hay soporte técnico disponible para desarrolladores que usan Aspose.Tasks?**  
A: Sí, Aspose ofrece foros dedicados, soporte por correo electrónico y documentación extensa para todos los usuarios con licencia.

---

**Última actualización:** 2026-02-07  
**Probado con:** Aspose.Tasks for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}