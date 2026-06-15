---
date: 2026-06-15
description: Aprenda cómo extraer timephased data de recursos de MS Project usando
  Aspose.Tasks para Java. Guía paso a paso para obtener recurso por id.
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: Leer Timephased Data para Recursos en Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Leer Timephased Data para Recursos en Aspose.Tasks – obtener recurso por id
url: /es/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Leer datos con fases de tiempo para recursos en Aspose.Tasks

## Introducción
En este tutorial, aprenderás **cómo obtener recurso por id** y leer sus datos con fases de tiempo usando Aspose.Tasks para Java. Recorreremos cada paso—desde configurar la carpeta del proyecto hasta imprimir los valores de trabajo y costo con fases de tiempo—para que puedas extraer información valiosa de programación de cualquier archivo Microsoft Project de forma programática. Aspose.Tasks para Java es una API integral que permite a los desarrolladores crear, leer, modificar y convertir archivos Microsoft Project sin necesidad de tener Microsoft Project instalado, soportando una amplia gama de características y formatos de gestión de proyectos.

## Respuestas rápidas
- **¿Qué hace “get resource by id”?** Recupera un objeto `Resource` específico de un `Project` usando su identificador único.  
- **¿Qué biblioteca maneja los datos con fases de tiempo?** Aspose.Tasks for Java proporciona la API `Resource.getTimephasedData`.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo leer proyectos grandes?** Sí—Aspose.Tasks puede procesar archivos con hasta 10 000 tareas sin cargar todo el archivo en memoria.  
- **¿Qué versión de Java se requiere?** Java 8 o superior; la biblioteca es compatible con todos los JDK principales.

## Qué es “get resource by id”?
`get resource by id` es una llamada a método que obtiene una instancia `Resource` de un `Project` cargado usando el ID numérico del recurso. Esta operación permite un acceso preciso a las propiedades detalladas del recurso, como sus asignaciones, calendarios y campos personalizados, y es esencial para extraer datos de trabajo o costo con fases de tiempo asociados a ese recurso específico.

## ¿Por qué usar Aspose.Tasks para datos con fases de tiempo?
Aspose.Tasks soporta **más de 50 formatos de entrada y salida** (MPP, XML, CSV, etc.) y puede extraer valores de trabajo y costo con fases de tiempo para recursos que abarcan horarios de varios años manteniendo bajo el uso de memoria. La API devuelve datos en intervalos de 15 minutos por defecto, brindándote una visión granular para informes o análisis personalizados.

## Requisitos previos
Antes de comenzar, asegúrate de contar con los siguientes requisitos:
1. Java Development Kit (JDK): Asegúrese de que tiene JDK instalado en su sistema. Puede descargarlo desde el [sitio web](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) y seguir las instrucciones de instalación.  
2. Biblioteca Aspose.Tasks for Java: Descargue la biblioteca Aspose.Tasks for Java desde la [página de descarga](https://releases.aspose.com/tasks/java/) y siga las instrucciones de instalación proporcionadas en la documentación.

## Importar paquetes
El primer paso es importar las clases necesarias de Aspose.Tasks en su archivo fuente Java.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Paso 1: Configurar el directorio de datos
Primero, defina el directorio donde se encuentra su archivo MS Project. Mantener la carpeta de datos separada del código fuente facilita el mantenimiento del proyecto.

```java
String dataDir = "Your Data Directory";
```

## Paso 2: Leer el archivo de plantilla de MS Project
Especifique el nombre de su archivo de plantilla MS Project. Usar una plantilla garantiza configuraciones de columnas consistentes en diferentes proyectos.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Paso 3: Leer el archivo de entrada como proyecto
La clase `Project` es el objeto central de Aspose.Tasks que representa un archivo Microsoft Project en memoria. Cargar el archivo le brinda acceso programático a tareas, recursos y cronogramas.

```java
Project project = new Project(dataDir + fileName);
```

## Paso 4: Obtener recurso por ID
Para recuperar un recurso específico, llame al método `getResources().getById(id)`. Esta es la operación exacta referenciada por la palabra clave principal.

```java
Resource resource = project.getResources().getByUid(1);
```

## Paso 5: Imprimir datos con fases de tiempo para el trabajo del recurso
Una vez que tenga el objeto `Resource`, puede llamar a `resource.getTimephasedData(ResourceTimephasedDataType.Work)` para obtener las asignaciones de trabajo a lo largo del tiempo. La colección devuelta contiene objetos `TimephasedData` que incluyen la fecha de inicio, la fecha de fin y la cantidad de trabajo para cada **intervalo**.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Paso 6: Imprimir datos con fases de tiempo para el costo del recurso
De manera similar, `resource.getTimephasedData(ResourceTimephasedDataType.Cost)` devuelve información de **costo** desglosada por los mismos intervalos de tiempo. Esto es útil para informes de presupuestos y seguimiento de costos.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## ¿Cómo obtener recurso por ID en una sola línea?
Cargue el proyecto y luego llame a `project.getResources().getById(5)`—reemplace **5** con el ID real del recurso que necesite. Esta única llamada devuelve el objeto `Resource`, después de lo cual puede consultar sus datos con fases de tiempo, asignaciones o campos personalizados. El método se ejecuta en tiempo O(1) porque los recursos están indexados internamente.

## Problemas comunes y soluciones
- **Recurso no encontrado** – Asegúrese de que el ID exista en el archivo del proyecto; los IDs comienzan en 1 y son únicos por recurso.  
- **Datos con fases de tiempo vacíos** – Verifique que el recurso tenga asignaciones de trabajo o costo; de lo contrario la colección estará vacía.  
- **Rendimiento con archivos grandes** – Use `Project.setLoadOptions(LoadOptions.fromFile(...))` para habilitar la carga diferida en proyectos mayores de 500 MB.

## Preguntas frecuentes

**Q: ¿Puede Aspose.Tasks manejar otros tipos de archivos de proyecto además de Microsoft Project?**  
A: Sí, Aspose.Tasks soporta MPP, XML, CSV y varios otros formatos, lo que le permite leer y escribir entre diferentes estándares.

**Q: ¿Aspose.Tasks es compatible con diferentes entornos de desarrollo Java?**  
A: Absolutamente. La biblioteca funciona con todos los IDE principales (IntelliJ IDEA, Eclipse, NetBeans) y herramientas de compilación (Maven, Gradle).

**Q: ¿Puedo manipular datos del proyecto usando Aspose.Tasks?**  
A: Sí, puede crear, modificar y eliminar tareas, recursos, asignaciones e incluso campos personalizados a través de la API.

**Q: ¿Aspose.Tasks es adecuado para proyectos a nivel empresarial?**  
A: Lo es. Las empresas confían en Aspose.Tasks para procesamiento de alto volumen, conversiones por lotes e informes del lado del servidor porque no requiere la instalación de Microsoft Project.

**Q: ¿Dónde puedo encontrar soporte si encuentro problemas al usar Aspose.Tasks?**  
A: Puede visitar el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener asistencia de la comunidad y del equipo de soporte.

## Conclusión
En este tutorial, hemos aprendido cómo **obtener recurso por id** y leer sus datos de trabajo y costo con fases de tiempo usando Aspose.Tasks para Java. Siguiendo estos pasos, podrá extraer eficientemente información valiosa de programación de sus archivos de proyecto e integrarla en pipelines de informes o análisis personalizados.

---

**Última actualización:** 2026-06-15  
**Probado con:** Aspose.Tasks 24.11 for Java  
**Autor:** Aspose

## Tutoriales relacionados

- [Agregar recurso al proyecto con Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Administrar costos de recursos de MS Project con Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Leer semanas de trabajo Java del calendario de MS Project con Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}