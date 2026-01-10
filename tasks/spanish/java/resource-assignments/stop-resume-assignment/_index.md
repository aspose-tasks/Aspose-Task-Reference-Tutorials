---
date: 2026-01-10
description: Aprenda cómo detener la asignación, gestionar asignaciones de recursos
  y ver un ejemplo de asignación de recursos en Aspose.Tasks para Java con este tutorial
  paso a paso.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cómo detener la asignación y reanudar asignaciones de recursos en Aspose.Tasks
url: /es/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo detener la asignación y reanudar asignaciones de recursos en Aspose.Tasks

## Introducción
En este tutorial, **descubrirás cómo detener una asignación** y luego reanudarla usando Aspose.Tasks para Java. Aspose.Tasks es una potente API de Java que permite leer formatos de archivos de proyecto Java, manipular datos de Microsoft Project y gestionar asignaciones de recursos sin necesidad de tener Microsoft Project instalado. Revisaremos cada paso, explicaremos por qué cada línea es importante y te daremos consejos prácticos que puedes aplicar a proyectos del mundo real.

## Respuestas rápidas
- **¿Qué significa “detener la asignación”?** Marca una asignación de recurso como temporalmente inactiva a partir de una fecha de detención específica.  
- **¿Puedo reanudar la misma asignación más tarde?** Sí, estableciendo una fecha de reanudación en la misma asignación.  
- **¿Necesito Microsoft Project para usar esta API?** No, Aspose.Tasks funciona de forma independiente de Microsoft Project.  
- **¿Qué versión de Java se requiere?** Se recomienda Java 8 o superior.  
- **¿Dónde puedo descargar la biblioteca?** Desde la página oficial de descarga de Aspose.Tasks Java.

## ¿Qué es “detener la asignación” en el contexto de Aspose.Tasks?
Detener una asignación indica al planificador que ignore el trabajo asignado a un recurso después de la **stop date** hasta la **resume date** (si la hay). Esto es útil para gestionar vacaciones, tiempo de inactividad de equipos o cualquier período en que un recurso no deba considerarse activo.

## ¿Por qué usar Aspose.Tasks para gestionar asignaciones de recursos?
- **No se necesita Microsoft Project** – trabaja directamente con archivos .mpp.  
- **Control total sobre las fechas** – puedes comprobar programáticamente la stop date, la resume date y ajustarlas.  
- **Multiplataforma** – se ejecuta en cualquier SO que soporte Java.  
- **API rica** – proporciona un *resource assignment example* que puedes ampliar para informes personalizados.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Java Development Kit (JDK) instalado en tu sistema.  
- Biblioteca Aspose.Tasks para Java descargada. Puedes descargarla desde [aquí](https://releases.aspose.com/tasks/java/).  
- Conocimientos básicos de programación en Java.  

## Importar paquetes
Primero, importemos los paquetes necesarios en nuestro proyecto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Paso 1: Cargar el archivo de proyecto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Aquí **leemos el archivo de proyecto Java** (`.mpp`) y creamos un objeto `Project` que nos brinda acceso a todos los datos del proyecto, incluidas las asignaciones de recursos.

## Paso 2: Recorrer las asignaciones de recursos
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Establecemos una **minimum date** para filtrar fechas de marcador de posición y luego iteramos sobre cada asignación. Este es el patrón típico del *resource assignment example* que se usa cuando necesitas inspeccionar o modificar asignaciones.

## Paso 3: Verificar fechas de detención y reanudación
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

En este bloque **verificamos la stop date** y **verificamos la resume date** para cada asignación. Si la fecha es anterior a nuestra `minDate`, la tratamos como no establecida (`"NA"`); de lo contrario, imprimimos la fecha real. Esta lógica es esencial para **manage resource assignments** correctamente.

## Problemas comunes y soluciones
- **Fechas nulas** – `ra.get(Asn.STOP)` puede devolver `null`. Protégete añadiendo una verificación de null antes de llamar a `.before(minDate)`.  
- **Ruta de archivo incorrecta** – Asegúrate de que `dataDir` termine con un separador de ruta (`/` o `\\`) apropiado para tu SO.  
- **Desajuste de versión** – Usa la última versión de Aspose.Tasks para Java para evitar valores de enum faltantes.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks sin Microsoft Project instalado?
Sí, Aspose.Tasks te permite trabajar con archivos de Microsoft Project sin necesidad de tener Microsoft Project instalado en tu sistema.

### ¿Dónde puedo encontrar más documentación?
Puedes encontrar documentación detallada [aquí](https://reference.aspose.com/tasks/java/).

### ¿Hay una versión de prueba gratuita disponible?
Sí, puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener soporte si encuentro algún problema?
Puedes obtener soporte de la comunidad [aquí](https://forum.aspose.com/c/tasks/15).

### ¿Puedo comprar una licencia temporal?
Sí, puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Preguntas y respuestas frecuentes

**P: ¿Cómo establezco programáticamente una stop date para una asignación?**  
R: Usa `ra.set(Asn.STOP, yourDateObject);` donde `yourDateObject` es un `java.util.Date`.

**P: ¿Qué ocurre si la resume date es anterior a la stop date?**  
R: La API no impone un orden cronológico; sin embargo, el planificador tratará la asignación como activa solo después de la fecha más tardía de las dos, por lo que deberás validar las fechas tú mismo.

**P: ¿Puedo filtrar asignaciones solo a aquellas que tengan una stop date establecida?**  
R: Sí, recorre `prj.getResourceAssignments()` y verifica `ra.get(Asn.STOP) != null`.

**P: ¿Es posible eliminar una stop date una vez establecida?**  
R: Establece la stop date a `null` con `ra.set(Asn.STOP, null);` y luego guarda el proyecto.

**P: ¿Aspose.Tasks admite otros campos relacionados con fechas como start, finish o actual start?**  
R: Absolutamente. El enum `Asn` proporciona constantes para todos los campos de asignación, como `Asn.START`, `Asn.FINISH`, etc.

## Conclusión
Al seguir estos pasos ahora sabes **cómo detener la asignación**, inspeccionar las fechas de detención/reanudación y reanudar la asignación cuando sea necesario. Esta capacidad te permite **manage resource assignments** con mayor precisión, especialmente en escenarios como vacaciones de recursos o tiempo de inactividad de equipos. Siéntete libre de ampliar el ejemplo para actualizar fechas, generar informes o integrarlo con tu propia lógica de planificación.

---

**Última actualización:** 2026-01-10  
**Probado con:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}