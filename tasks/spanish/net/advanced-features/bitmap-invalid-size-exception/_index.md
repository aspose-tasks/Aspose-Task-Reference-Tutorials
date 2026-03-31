---
date: 2026-03-21
description: Aprenda cómo exportar una imagen y manejar BitmapInvalidSizeException
  al guardar un proyecto como imagen en Aspose.Tasks para .NET. Incluye pasos para
  guardar el proyecto como imagen y exportar el proyecto a PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Cómo exportar una imagen y manejar la excepción de tamaño inválido
url: /es/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo exportar una imagen – Manejo de la excepción de tamaño inválido para Bitmap en Aspose.Tasks

En este tutorial aprenderá **cómo exportar una imagen** desde un archivo Microsoft Project usando Aspose.Tasks para .NET y, lo que es más importante, cómo capturar la `BitmapInvalidSizeException` que puede ocurrir durante el proceso. Exportar un proyecto como una imagen es un requisito común para paneles de informes, documentación o simplemente compartir una captura visual de un cronograma. Al final de esta guía podrá **guardar el proyecto como imagen** de forma fiable e incluso **exportar el proyecto a formato PNG** sin bloqueos inesperados.

## Respuestas rápidas
- **¿Qué excepción puede ocurrir al exportar una imagen?** `BitmapInvalidSizeException`  
- **¿Qué formato se usa en el ejemplo?** PNG (`SaveFileFormat.Png`)  
- **¿Necesito una licencia especial?** Se requiere una licencia válida de Aspose.Tasks para uso en producción.  
- **¿Puedo cambiar la escala de tiempo?** Sí – puede establecer la unidad de escala de tiempo (minutos, horas, días, etc.).  
- **¿El código es compatible con .NET Core?** Absolutamente – la misma API funciona en .NET Framework y .NET Core.

## Qué es la BitmapInvalidSizeException?
`BitmapInvalidSizeException` se lanza cuando las dimensiones del bitmap calculadas para la imagen están fuera del rango admitido (por ejemplo, el ancho o la altura son cero o exceden los límites internos). Esto suele ocurrir cuando la escala de tiempo o la configuración de vista generan una imagen que es demasiado grande o demasiado pequeña.

## ¿Por qué exportar un proyecto como una imagen?
- **Informes visuales** – incruste un diagrama de Gantt en PDFs, documentos Word o páginas web.  
- **Compartir multiplataforma** – los archivos PNG pueden verse en cualquier dispositivo sin necesidad de Microsoft Project.  
- **Rendimiento** – las imágenes son ligeras en comparación con los archivos de proyecto completos para vistas previas rápidas.

## Requisitos previos
1. Conocimientos básicos de C# y desarrollo .NET.  
2. Aspose.Tasks para .NET instalado (paquete NuGet `Aspose.Tasks`).  
3. Un archivo de muestra de Microsoft Project (p. ej., `Blank2010.mpp`).  

## Importar espacios de nombres
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guía paso a paso

### Paso 1: Inicializar el proyecto y elegir una vista
Primero, cree una instancia de `Project` y seleccione la vista que desea renderizar (aquí usamos la primera vista de diagrama de Gantt).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Paso 2: Configurar las opciones de guardado de imagen (Exportar proyecto a PNG)
Establezca el formato de imagen deseado y indique a Aspose.Tasks que use la escala de tiempo definida en la vista.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Paso 3: Ajustar la unidad de escala de tiempo (Controlar el tamaño de la imagen)
Cambiar la escala de tiempo influye en las dimensiones del bitmap. En este ejemplo usamos **minutos** para mantener el tamaño de la imagen manejable.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Paso 4: Intentar guardar el proyecto como una imagen
Esta línea realiza la operación real de **guardar el proyecto como imagen**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Paso 5: Capturar y manejar la BitmapInvalidSizeException
Envuelva la llamada de guardado en un bloque `try / catch` para que su aplicación pueda reaccionar de forma elegante si el tamaño del bitmap es inválido.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| La excepción sigue lanzándose después de ajustar la escala de tiempo | La escala de tiempo sigue produciendo un bitmap demasiado grande | Reduzca `view.MiddleTimescaleTier.Count` o cambie a una `TimescaleUnit` más gruesa (p. ej., Horas). |
| El archivo de salida está vacío | Ruta de archivo incorrecta o faltan permisos de escritura | Verifique que `DataDir` apunte a una carpeta con permisos de escritura y que el nombre de archivo termine con `.png` si cambia el formato. |
| La calidad de la imagen es pobre | El DPI predeterminado puede ser bajo | Establezca `options.DpiX` y `options.DpiY` a valores más altos (p. ej., 300). |

## Preguntas frecuentes

**Q: ¿Qué causa la BitmapInvalidSizeException en Aspose.Tasks?**  
A: Ocurre cuando las dimensiones calculadas del bitmap son inválidas—típicamente porque la escala de tiempo crea una imagen que es demasiado grande o tiene ancho/alto cero.

**Q: ¿Puedo personalizar la escala de tiempo al exportar una imagen?**  
A: Sí. Puede modificar `view.MiddleTimescaleTier.Unit` y `Count` según sus necesidades, como se muestra en el tutorial.

**Q: ¿Aspose.Tasks admite otros formatos de imagen además de PNG?**  
A: Absolutamente. `SaveFileFormat` también incluye JPEG, BMP, GIF y TIFF. Simplemente cambie el valor del enum en `ImageSaveOptions`.

**Q: ¿Se requiere una licencia para exportar imágenes en un entorno de producción?**  
A: Sí. Aunque la biblioteca funciona en modo de evaluación, una licencia comercial elimina las limitaciones de evaluación y brinda soporte completo.

**Q: ¿Cómo puedo mejorar la calidad del PNG exportado?**  
A: Aumente la configuración de DPI (`options.DpiX` y `options.DpiY`) o ajuste la escala de tiempo de la vista para producir un bitmap más grande.

## Conclusión
Al seguir los pasos anteriores ahora sabe **cómo exportar una imagen** desde un archivo Project, cómo **guardar el proyecto como imagen**, y cómo manejar de forma elegante la `BitmapInvalidSizeException`. Estas técnicas hacen que sus canalizaciones de informes sean más robustas y garantizan que las exportaciones visuales funcionen de manera fiable en diferentes tamaños de proyecto y escalas de tiempo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-21  
**Probado con:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose