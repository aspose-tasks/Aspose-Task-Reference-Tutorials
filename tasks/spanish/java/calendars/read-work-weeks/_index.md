---
date: 2026-02-05
description: Aprenda cómo leer semanas laborables en Java desde un calendario de Microsoft
  Project usando Aspose.Tasks. Siga la guía paso a paso con ejemplos de código completos.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo leer Workweeks Java del calendario de MS Project con Aspose.Tasks
url: /es/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo leer semanas laborables Java desde el calendario de MS Project con Aspose.Tasks

## Introducción
En este tutorial **aprenderás cómo leer semanas laborables Java** desde un calendario de Microsoft Project usando la biblioteca Aspose.Tasks. Ya sea que estés construyendo una herramienta de informes, sincronizando horarios o automatizando la extracción de datos de proyectos, poder acceder programáticamente a las definiciones de semanas laborables ahorra incontables horas manuales. Recorreremos la configuración requerida, te mostraremos el código exacto para obtener los detalles de las semanas laborables y explicaremos cada paso para que puedas adaptar la solución a tus propios proyectos.

## Respuestas rápidas
- **¿Qué significa “read workweeks java”?** Se refiere a extraer las definiciones de semanas laborables de un archivo Project usando código Java.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (prueba gratuita disponible).  
- **¿Necesito una licencia para desarrollo?** Una prueba funciona para pruebas; se necesita una licencia comercial para producción.  
- **¿Qué formatos de archivo son compatibles?** Se manejan tanto *.mpp* como archivos Project XML.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos una vez que la biblioteca está configurada.

## Cómo leer semanas laborables Java desde un calendario de Microsoft Project
Leer semanas laborables en Java significa usar la API de Aspose.Tasks para acceder a la `WorkWeekCollection` de un objeto calendario dentro de un archivo Microsoft Project. Cada `WorkWeek` contiene las fechas de inicio/fin y las definiciones diarias de tiempo de trabajo que determinan cómo se programan los recursos.

## ¿Por qué leer semanas laborables Java desde un calendario de Microsoft Project?
- **Automatización:** Elimina la copia‑pega manual de datos de programación.  
- **Integración:** Alimenta la información de semanas laborables a ERP, recursos humanos o sistemas de informes personalizados.  
- **Consistencia:** Garantiza que todas las herramientas posteriores respeten las mismas reglas de calendario definidas en el archivo Project.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener:

1. **Java Development Kit (JDK)** – versión 8 o posterior instalada.  
2. **Aspose.Tasks para Java** – descarga el JAR más reciente desde el sitio oficial: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Un **archivo de proyecto de ejemplo** (`ReadWorkWeeksInformation.mpp`) colocado en una carpeta conocida.

## Importar paquetes
Primero, importa las clases que necesitaremos para interactuar con calendarios y semanas laborables:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Paso 1: Configurar tu directorio de datos
Define la carpeta que contiene el archivo `.mpp`. Reemplaza el marcador de posición con la ruta real en tu máquina:

```java
String dataDir = "Your Data Directory";
```

## Paso 2: Crear una instancia de Project y acceder al calendario
Instancia un objeto `Project`, elige el calendario que deseas (por UID) y obtén su `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Consejo profesional:** Si no estás seguro del UID del calendario, puedes iterar a través de `project.getCalendars()` e imprimir el nombre y UID de cada calendario.

## Paso 3: Recorrer las semanas laborables
Recorre cada `WorkWeek` para mostrar su nombre, fechas de inicio/fin y los horarios de trabajo diarios:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Lo que verás:** La consola imprime la etiqueta de cada semana laborable (p. ej., “Standard”), su rango de fechas efectivo y puedes profundizar en las horas exactas de trabajo para cada día.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| `NullPointerException` al acceder a `calendar` | UID incorrecto o el calendario no existe | Verifica el UID con `project.getCalendars().size()` y lista los calendarios disponibles primero. |
| No hay salida para semanas laborables | El calendario seleccionado no tiene semanas laborables personalizadas (usa la predeterminada) | Usa el calendario predeterminado (`project.getDefaultCalendar()`) o crea una semana laborable programáticamente. |
| El formato de fecha se ve extraño | `System.out.println` usa el formato predeterminado de `java.util.Date` | Aplica un `SimpleDateFormat` para formatear las fechas según necesites. |

## Preguntas frecuentes

**P: ¿Puedo modificar la información de las semanas laborables usando Aspose.Tasks para Java?**  
R: Sí. La API proporciona métodos como `addWorkWeek()`, `removeWorkWeek()` y establecedores de propiedades para cambiar nombres, fechas y horarios de trabajo.

**P: ¿Aspose.Tasks es compatible con diferentes versiones de archivos Microsoft Project?**  
R: Absolutamente. Soporta archivos MPP desde Project 98 hasta las versiones más recientes, así como archivos Project XML.

**P: ¿Puedo integrar Aspose.Tasks con otros frameworks Java?**  
R: Sí. La biblioteca es puro Java, por lo que puedes usarla junto a Spring, Jakarta EE o cualquier otro framework.

**P: ¿Existe una versión de prueba disponible para Aspose.Tasks?**  
R: Sí, puedes descargar una prueba gratuita de 30 días desde el sitio oficial: [Aspose.Tasks trial](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar soporte para Aspose.Tasks?**  
R: El foro de la comunidad de Aspose es el mejor lugar: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusión
Ahora dominas **cómo leer semanas laborables Java** usando Aspose.Tasks. Siguiendo los pasos anteriores puedes extraer programáticamente las definiciones de semanas laborables de cualquier calendario de MS Project, integrar esos datos en tus aplicaciones y automatizar flujos de trabajo relacionados con la programación. Siéntete libre de experimentar creando o actualizando semanas laborables; Aspose.Tasks lo hace sencillo.

---

**Última actualización:** 2026-02-05  
**Probado con:** Aspose.Tasks para Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}