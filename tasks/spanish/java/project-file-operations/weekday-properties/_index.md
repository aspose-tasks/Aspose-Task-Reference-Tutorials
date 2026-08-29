---
date: 2026-03-29
description: Aprende cómo cambiar los días por mes y gestionar otras propiedades de
  los días de la semana en Aspose.Tasks para Java. Personaliza las fechas de inicio
  de la semana, modifica el calendario del proyecto y guarda el proyecto como XML.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cambiar los días por mes con las propiedades de día de la semana de Aspose.Tasks
url: /es/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar días por mes con las propiedades de día de la semana de Aspose.Tasks

## Introducción
Aspose.Tasks for Java le permite **cambiar días por mes** y afinar otras configuraciones de días de la semana sin necesidad de tener Microsoft Project instalado. Ya sea que esté alineando el calendario del proyecto a un mes fiscal no estándar o simplemente necesite ajustar el día de inicio de la semana, este tutorial lo guía a través de los escenarios más comunes: obtener el día de inicio de la semana actual, personalizar la fecha de inicio de la semana, modificar el calendario del proyecto y guardar el proyecto como XML.

## Respuestas rápidas
- **¿Puedo cambiar el número de días por mes?** Sí, use `Prj.DAYS_PER_MONTH` en el objeto `Project`.  
- **¿Cómo personalizo la fecha de inicio de la semana?** Establezca `Prj.WEEK_START_DAY` a un valor `DayType` (p. ej., `DayType.Monday`).  
- **¿Qué formato puedo usar para exportar el proyecto?** El ejemplo guarda el archivo como XML con `SaveFileFormat.Xml`.  
- **¿Se requiere una licencia para uso en producción?** Se necesita una licencia válida de Aspose.Tasks para implementaciones que no sean de evaluación.  
- **¿Qué IDEs son compatibles?** Cualquier IDE de Java como IntelliJ IDEA, Eclipse o NetBeans funciona.

## Qué es “cambiar días por mes” en Aspose.Tasks?
Cambiar días por mes significa actualizar la propiedad `Prj.DAYS_PER_MONTH` de una instancia `Project`. Esta propiedad indica al motor cuántos días laborables debe considerar en cada mes, lo que afecta directamente la programación de tareas y los cálculos de costos.

## Por qué modificar las propiedades del calendario del proyecto?
Personalizar el calendario del proyecto —como establecer un día de inicio de semana diferente o modificar los minutos por día— le ayuda a:
- Alinear los horarios con las semanas laborales regionales.  
- Modelar patrones de trabajo no estándar (p. ej., semanas de 4 días).  
- Garantizar informes precisos para contratos que utilizan calendarios personalizados.

## Requisitos previos
- **Java Development Kit (JDK)** – Instale el último JDK de Oracle.  
- **Aspose.Tasks for Java library** – Descárguela del sitio oficial [here](https://releases.aspose.com/tasks/java/).  
- **IDE de su elección** – IntelliJ IDEA, Eclipse o NetBeans.

## Importar paquetes
Primero, importe las clases esenciales de Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Paso 1: Cargar archivo de proyecto
Esto carga un archivo existente de Microsoft Project (`project.mpp`) desde la carpeta que especifique.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Paso 2: Mostrar propiedades de día de la semana
Aquí recuperamos e imprimimos la configuración actual de los días de la semana, incluyendo el **día de inicio de la semana** y los **días por mes**.

```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```

## Paso 3: Configurar propiedades de día de la semana
En este paso **cambiamos los días por mes** a 24, establecemos que la semana comience el lunes y ajustamos los minutos por día/semana. Esto demuestra cómo **modificar el calendario del proyecto** de forma programática.

```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```

## Paso 4: Guardar proyecto
El proyecto modificado se guarda usando el formato **guardar proyecto como XML**, lo cual es útil para la integración con otras herramientas o para almacenamiento bajo control de versiones.

```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```

## Paso 5: Mostrar resultado
Una confirmación simple de que las operaciones finalizaron sin errores.

```java
System.out.println("Process completed Successfully");
```

## Cómo personalizar la fecha de inicio de la semana
Si su organización sigue un calendario que comienza el domingo, reemplace `DayType.Monday` por `DayType.Sunday`. Se utiliza la misma propiedad (`Prj.WEEK_START_DAY`), lo que hace que el cambio sea sencillo.

## Cómo obtener el día de inicio de la semana
Puede llamar a `project.get(Prj.WEEK_START_DAY)` en cualquier momento para **obtener la información del día de inicio de la semana**, como se muestra en el Paso 2.

## Cómo modificar el calendario del proyecto
Más allá del día de inicio de la semana, también puede ajustar `Prj.MINUTES_PER_DAY` y `Prj.MINUTES_PER_WEEK` para reflejar horas de trabajo personalizadas o patrones de turnos.

## Problemas comunes y soluciones
- **Valor de tipo de día incorrecto** – Asegúrese de usar el enumerado `DayType` (p. ej., `DayType.Monday`).  
- **Errores de ruta de archivo** – Verifique que `dataDir` termine con el separador de archivos apropiado (`/` o `\`).  
- **Licencia no establecida** – Si ve advertencias de licencia, registre su licencia de Aspose.Tasks antes de crear el objeto `Project`.

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks for Java manejar estructuras de proyecto complejas?**  
A: Sí, Aspose.Tasks for Java ofrece soporte integral para manejar estructuras de proyecto complejas con facilidad.

**Q: ¿Es Aspose.Tasks for Java compatible con diferentes versiones de archivos de Microsoft Project?**  
A: Absolutamente, Aspose.Tasks for Java soporta varias versiones de archivos de Microsoft Project, garantizando compatibilidad en distintas plataformas.

**Q: ¿Puedo integrar Aspose.Tasks for Java en mis aplicaciones Java existentes?**  
A: Sí, Aspose.Tasks for Java ofrece capacidades de integración sin problemas, permitiéndole mejorar sus aplicaciones Java con potentes funciones de gestión de proyectos.

**Q: ¿Aspose.Tasks for Java proporciona documentación y soporte?**  
A: Sí, puede acceder a una documentación extensa y soporte comunitario para Aspose.Tasks for Java en su [website](https://releases.aspose.com/).

**Q: ¿Hay una versión de prueba gratuita disponible para Aspose.Tasks for Java?**  
A: Sí, puede descargar una versión de prueba gratuita de Aspose.Tasks for Java desde su [website](https://reference.aspose.com/tasks/java/) para explorar sus funciones antes de realizar una compra.

---

**Última actualización:** 2026-03-29  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}