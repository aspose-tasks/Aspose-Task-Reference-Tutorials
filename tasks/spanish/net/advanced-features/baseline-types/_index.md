---
date: 2026-04-30
description: Aprende cómo establecer la línea base y manipular las líneas base del
  proyecto de manera eficiente usando Aspose.Tasks para .NET.
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Diferentes tipos de líneas base en Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo establecer la línea base en Aspose.Tasks – Diferentes tipos de línea base
url: /es/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tipos diferentes de líneas base en Aspose.Tasks

## Introducción

En la gestión de proyectos, **cómo establecer la línea base** correctamente puede marcar la diferencia entre un proyecto que se mantiene en camino y uno que se sale de control. Aspose.Tasks para .NET le brinda una API completa para crear, actualizar y comparar líneas base, permitiéndole **seguimiento del progreso del proyecto** contra el plan original. En este tutorial aprenderá cómo establecer una línea base, trabajar con varios tipos de líneas base y usar los datos para analizar la **línea base vs cronograma real** de su proyecto.

## Respuestas rápidas
- **¿Qué es una línea base?** Una captura instantánea del cronograma, costo y datos de trabajo tomada en un punto específico de un proyecto.  
- **¿Cuántas líneas base puede almacenar Aspose.Tasks?** Hasta 11 líneas base distintas por proyecto.  
- **¿Por qué establecer una línea base?** Para comparar el rendimiento real con el plan original e identificar variaciones.  
- **¿Necesito una licencia para probar esto?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.  
- **¿Qué versiones de .NET son compatibles?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## ¿Qué es “cómo establecer la línea base” en Aspose.Tasks?
Establecer una línea base significa llamar al método `SetBaseline` en un objeto `Project`. La API le permite elegir entre varios valores de `BaselineType` (Baseline, Baseline1 … Baseline10) para que pueda conservar capturas históricas a medida que el proyecto evoluciona.

## ¿Por qué gestionar líneas base del proyecto?
- **Medir la variación:** Ver rápidamente si las tareas están adelantadas o retrasadas respecto al cronograma.  
- **Control de costos:** Comparar el costo de la línea base con el gasto real.  
- **Informes a interesados:** Exportar datos de la línea base a PDF, XLSX u otros formatos para una comunicación clara.  
- **Planificación de escenarios:** Almacenar múltiples líneas base para evaluar cronogramas “what‑if”.

## Requisitos previos

### 1. Familiaridad con C# y .NET Framework
Se requiere una comprensión básica de clases, métodos y conceptos orientados a objetos en C#.

### 2. Instalación de Aspose.Tasks para .NET
Asegúrese de que la biblioteca esté añadida a su proyecto. Puede descargarla desde el [sitio web de Aspose.Tasks](https://releases.aspose.com/tasks/net/) o instalarla mediante NuGet.

### 3. Entorno de Desarrollo Integrado (IDE)
Visual Studio (o cualquier IDE compatible) se recomienda para escribir, compilar y depurar código C#.

## Importar espacios de nombres

Antes de comenzar a trabajar con Aspose.Tasks en nuestro proyecto C#, necesitamos importar los espacios de nombres necesarios para acceder a las clases y métodos requeridos. Siga estos pasos:

```csharp

```

Ahora que hemos configurado los requisitos previos e importado los espacios de nombres necesarios, vamos a sumergirnos en la configuración de diferentes tipos de líneas base usando Aspose.Tasks para .NET. Desglosaremos cada ejemplo en varios pasos para mayor claridad y facilidad de comprensión.

## Cómo establecer una línea base en Aspose.Tasks

### Paso 1: Cargar el archivo del proyecto
Primero, necesitamos cargar el archivo del proyecto en el que pretendemos establecer la línea base. Este paso implica inicializar un objeto `Project` y cargar el archivo del proyecto. Así es como puede hacerlo:

```csharp
var project = new Project("Project2.mpp");
```

### Paso 2: Establecer la línea base
Una vez que el proyecto está cargado, podemos proceder a establecer la línea base. Las líneas base proporcionan una captura del cronograma inicial del proyecto, que sirve como punto de referencia para la comparación a medida que el proyecto avanza. Use el método `SetBaseline` para establecer la línea base. Por ejemplo, para establecer la línea base para todo el proyecto, use la enumeración `BaselineType.Baseline`:

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### Paso 3: Trabajar con líneas base del proyecto
Después de establecer la línea base, puede trabajar con varios campos de líneas base del proyecto para analizar y rastrear el progreso del proyecto con precisión. Este paso implica acceder a datos de la línea base como fechas de inicio, fechas de finalización, duraciones y costos. Aquí es donde puede aprovechar el amplio conjunto de funciones que ofrece Aspose.Tasks para manipular los datos de la línea base según sus requisitos.

## Problemas comunes y soluciones
- **Línea base no aplicada:** Asegúrese de que el archivo del proyecto se guarde después de llamar a `SetBaseline`. Use `project.Save("output.mpp");` si necesita conservar los cambios.  
- **Conflicto de múltiples líneas base:** Al establecer más de una línea base, especifique el `BaselineType` correcto (p.ej., `Baseline1`, `Baseline2`).  
- **Desajuste de versión:** Verifique que la versión del DLL de Aspose.Tasks coincida con el runtime .NET objetivo.

## Preguntas frecuentes

**Q: ¿Puedo establecer múltiples líneas base para un solo proyecto usando Aspose.Tasks para .NET?**  
A: Sí, Aspose.Tasks permite establecer hasta 11 líneas base para un proyecto, proporcionando capacidades de seguimiento exhaustivas.

**Q: ¿Es Aspose.Tasks compatible con diferentes formatos de archivo de proyecto?**  
A: ¡Absolutamente! Aspose.Tasks soporta varios formatos de archivo de proyecto como MPP, XML y MPX, garantizando compatibilidad en diferentes plataformas.

**Q: ¿Cómo puedo visualizar los datos de la línea base en mi proyecto?**  
A: Puede utilizar Aspose.Tasks para exportar los datos del proyecto a formatos de archivo populares como PDF o XLSX, lo que permite una visualización y compartición fácil de la información de la línea base.

**Q: ¿Aspose.Tasks ofrece soporte para integrarse con herramientas de gestión de proyectos?**  
A: Aspose.Tasks proporciona documentación extensa y foros de soporte para ayudar a los desarrolladores a integrar sin problemas sus funciones con herramientas y plataformas populares de gestión de proyectos.

**Q: ¿Puedo probar Aspose.Tasks antes de comprar?**  
A: Sí, puede explorar Aspose.Tasks mediante una prueba gratuita disponible en el sitio web, lo que le permite experimentar sus capacidades de primera mano.

---

**Última actualización:** 2026-04-30  
**Probado con:** Aspose.Tasks for .NET (última versión estable)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}