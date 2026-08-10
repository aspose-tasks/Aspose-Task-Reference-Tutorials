---
date: 2026-03-27
description: Aprende cómo usar Aspose y Aspose.Tasks para extraer los detalles del
  calendario del proyecto de archivos de Microsoft Project usando Java. Guía paso
  a paso con ejemplos de código.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo usar Aspose.Tasks para recuperar la información del calendario de MS Project
url: /es/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo usar Aspose.Tasks para obtener información del calendario de MS Project

## Introducción
En este tutorial, **descubrirás cómo usar Aspose.Tasks** para recuperar programáticamente la información del calendario de archivos Microsoft Project. Acceder a datos del calendario como días laborables, horas y excepciones es esencial cuando necesitas **extraer el calendario del proyecto** para informes, integración o lógica de programación personalizada. Repasemos el proceso paso a paso, y verás exactamente **cómo usar Aspose** para extraer estos datos de un archivo *.mpp*.

## Respuestas rápidas
- **¿Qué biblioteca usa este tutorial?** Aspose.Tasks for Java.  
- **¿Qué palabra clave principal se cubre?** *how to use aspose*.  
- **¿Qué puedes extraer?** Calendarios de proyecto, incluidos los días y horas laborables.  
- **¿Necesito una licencia?** Hay una prueba gratuita disponible; se requiere una licencia para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.

## ¿Qué es Aspose.Tasks y por qué usarlo?
Aspose.Tasks es una potente API de Java que permite a los desarrolladores leer, escribir y manipular archivos Microsoft Project sin necesidad de tener Microsoft Project. Al usar Aspose.Tasks puedes **how to extract calendar** información, automatizar cálculos de programación e integrar datos del proyecto con otros sistemas empresariales, todo desde código Java puro.

## ¿Por qué extraer información del calendario del proyecto?
Los calendarios del proyecto determinan las fechas de las tareas, la asignación de recursos y los cálculos de la línea de tiempo general. Al extraer estos datos puedes:
- Generar informes personalizados que reflejen los horarios laborales reales.  
- Sincronizar las líneas de tiempo de Microsoft Project con sistemas externos (ERP, BI, etc.).  
- Realizar análisis de escenarios modificando la configuración del calendario programáticamente.  
- **Extraer datos del calendario de MS Project** para la migración a otras herramientas de planificación.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de programación en Java.  
- Java Development Kit (JDK) instalado en tu sistema.  
- Biblioteca Aspose.Tasks for Java. Puedes descargarla desde [aquí](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importa las clases necesarias de Aspose.Tasks en tu proyecto Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Paso 1: Establecer el directorio de datos
Define la carpeta que contiene tu archivo *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Reemplaza `"Your Data Directory"` con la ruta absoluta a la carpeta donde se encuentra **project.mpp**.

## Paso 2: Definir unidades de tiempo
Crea constantes que ayuden a convertir la representación interna del tiempo a horas legibles por humanos.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Estos valores se expresan en microsegundos, que es como Aspose.Tasks almacena el tiempo internamente.

## Paso 3: Crear una instancia de Project
Carga el archivo Microsoft Project en un objeto `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

El constructor `Project` analiza el archivo *.mpp* y hace que todos los datos del proyecto, incluidos los calendarios, sean accesibles a través de la API.

## Paso 4: Recuperar información de los calendarios
Obtén la colección de calendarios definidos en el proyecto.

```java
CalendarCollection alCals = project.getCalendars();
```

Un proyecto puede contener varios calendarios (estándar, de recursos y personalizados). Esta colección te brinda acceso a cada uno.

## Paso 5: Iterar a través de los calendarios
Recorre cada calendario, muestra su UID, nombre y los días laborables con sus horas correspondientes.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

El bucle interno verifica cada objeto `WeekDay`. Si el día está marcado como laborable, imprime el tipo de día (Monday, Tuesday, …) junto con las horas laborables calculadas.

## Paso 6: Mostrar mensaje de finalización
Indica que el proceso de extracción ha finalizado.

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **No se devolvieron calendarios** | El archivo del proyecto puede no contener calendarios personalizados. | Verifica que el *.mpp* realmente define calendarios o ábrelo en Microsoft Project para confirmarlo. |
| **Horas laborables incorrectas** | Las constantes de conversión de tiempo están incorrectas para una versión diferente de Project. | Ajusta `OneSec`, `OneMin`, `OneHour` si trabajas con una versión más reciente de Aspose.Tasks que cambia la unidad de tiempo interna. |
| **`NullPointerException` on `cal.getName()`** | Algunos objetos de calendario podrían ser nulos. | Agrega una verificación de nulo antes de acceder a las propiedades (ya demostrado). |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks con otros lenguajes de programación?**  
A: Sí, Aspose.Tasks soporta múltiples plataformas y lenguajes de programación, incluidos .NET, C++, Python y Java.

**Q: ¿Hay una versión de prueba gratuita disponible para Aspose.Tasks?**  
A: Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener soporte para Aspose.Tasks?**  
A: Puedes obtener soporte del foro de la comunidad de Aspose.Tasks [aquí](https://forum.aspose.com/c/tasks/15).

**Q: ¿Puedo comprar una licencia temporal para Aspose.Tasks?**  
A: Sí, las licencias temporales están disponibles para su compra [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo encontrar documentación detallada de Aspose.Tasks?**  
A: Puedes consultar la documentación [aquí](https://reference.aspose.com/tasks/java/).

## Conclusión
Al seguir estos pasos, **ahora sabes cómo usar Aspose.Tasks para extraer información del calendario del proyecto** de un archivo MS Project usando Java. Puedes integrar esta lógica en aplicaciones más grandes, automatizar informes o sincronizar horarios con otros sistemas empresariales. Recuerda, dominar **how to use aspose** abre la puerta a muchos escenarios avanzados de automatización de gestión de proyectos.

---

**Última actualización:** 2026-03-27  
**Probado con:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}