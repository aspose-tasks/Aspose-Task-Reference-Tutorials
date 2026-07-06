---
date: 2026-02-07
description: Aprenda cómo establecer el código de moneda en Java en proyectos Aspose.Tasks,
  cambiar el símbolo de moneda y aplicar un formato de moneda personalizado para archivos
  de Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: código de moneda Java – Cómo establecerlo en proyectos Aspose.Tasks
url: /es/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo establecer el código de moneda en Aspose.Tasks – Guía Java

## Introducción
En este tutorial aprenderá **cómo establecer el código de moneda java** para un archivo Microsoft Project usando la API Java de Aspose.Tasks. Ya sea que necesite *cambiar la moneda* para equipos internacionales, ajustar el *símbolo de la moneda*, o aplicar un **formato de moneda personalizado**, los pasos a continuación lo guiarán a través del proceso con explicaciones claras y código listo‑para‑ejecutar.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Tasks for Java.  
- **¿Puedo cambiar el símbolo de la moneda?** Sí – use `CurrencySymbolPositionType` y `Prj.CURRENCY_SYMBOL`.  
- **¿Qué formatos de archivo son compatibles?** XML, MPP y muchos otros a través de `SaveFileFormat`.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 5‑10 minutos para una configuración básica.

## Cómo establecer el código de moneda Java en Aspose.Tasks
La moneda de un proyecto define cómo se muestran los valores de costo—código (p. ej., `AUD`), número de dígitos decimales, símbolo (`$`) y la posición del símbolo. Configurar estas propiedades garantiza que cada campo relacionado con costos (tarifas de recursos, presupuestos de tareas, etc.) refleje el formato monetario correcto para su audiencia.

## ¿Por qué usar Aspose.Tasks para cambiar la moneda?
- **No se necesita instalación de Microsoft Project** – manipule archivos en cualquier servidor.  
- **Cobertura completa de la API** – todos los campos relacionados con la moneda están expuestos a través de constantes `Prj`.  
- **Multiplataforma** – funciona en Windows, Linux y macOS con cualquier IDE compatible con Java.  
- **Alto rendimiento** – procesa archivos de proyecto grandes de forma rápida y fiable.  
- **Soporta formato de moneda personalizado** – puede definir símbolos, dígitos decimales y posición para coincidir con los estándares regionales.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – versión 8 o superior.  
2. **Aspose.Tasks for Java** – descargue el último JAR desde la [página de descarga de Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Un IDE** – Eclipse, IntelliJ IDEA, o cualquier editor que prefiera.  
4. **Una carpeta escribible** – donde se guardará el archivo de proyecto generado.

## Importar paquetes
Primero, importe las clases que proporcionan acceso a las propiedades del proyecto y al manejo de archivos.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Guía paso a paso

### Paso 1: Definir el directorio de datos
Especifique la carpeta que contiene sus archivos fuente y donde se escribirá la salida.

```java
String dataDir = "Your Data Directory";
```

### Paso 2: Crear una nueva instancia de Project
Instancie un nuevo objeto `Project`. Este objeto representa un archivo Microsoft Project en memoria.

```java
Project project = new Project();
```

### Paso 3: Establecer las propiedades de la moneda
Aquí es donde **establecemos el código de moneda** detalles como código, dígitos, símbolo y posición del símbolo.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Consejo profesional:** Si necesita **cambiar la moneda del proyecto** para un archivo existente, simplemente cárguelo con `new Project("file.mpp")` antes de aplicar la configuración anterior.

### Paso 4: Guardar el proyecto actualizado
Escriba el proyecto de vuelta al disco en el formato deseado. En este ejemplo usamos el formato XML, pero también puede elegir `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Paso 5: Confirmar el éxito
Imprima un mensaje amigable para saber que la operación se completó sin errores.

```java
System.out.println("Process completed Successfully");
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **`NullPointerException` on `project.save`** | `dataDir` no es una ruta válida o carece de permiso de escritura. | Asegúrese de que el directorio exista y su proceso Java tenga acceso de escritura. |
| El símbolo de moneda no se muestra | La posición del símbolo está configurada incorrectamente para su configuración regional. | Use `CurrencySymbolPositionType.Before` si el símbolo debe preceder al monto. |
| El archivo de proyecto no se abre en MS Project | Guardando en un formato antiguo con configuraciones incompatibles. | Guarde usando `SaveFileFormat.MPP` para plena compatibilidad con versiones recientes de MS Project. |

## Preguntas frecuentes

**Q: ¿Puedo establecer múltiples monedas en un solo proyecto usando Aspose.Tasks?**  
A: Sí, Aspose.Tasks le permite manejar múltiples monedas dentro de un solo archivo de proyecto configurando las propiedades de moneda por recurso o por tarea.

**Q: ¿Aspose.Tasks es compatible con diferentes versiones de archivos Microsoft Project?**  
A: Absolutamente. La biblioteca soporta archivos MPP desde Project 2000 hasta las versiones más recientes, así como XML y otros formatos.

**Q: ¿Aspose.Tasks ofrece soporte para formatos de moneda personalizados?**  
A: Sí, puede definir símbolos personalizados, dígitos decimales y posicionamiento para cumplir cualquier requisito regional.

**Q: ¿Puedo integrar Aspose.Tasks con otras bibliotecas o frameworks Java?**  
A: Por supuesto. La API es pura Java, por lo que funciona sin problemas con Spring, Hibernate, Maven, Gradle y otros ecosistemas.

**Q: ¿Dónde puedo encontrar soporte o asistencia adicional para Aspose.Tasks?**  
A: Visite el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para obtener ayuda de la comunidad, o consulte la documentación oficial para referencias detalladas de la API.

## Conclusión
Ahora sabe **cómo establecer el código de moneda java**, cómo **cambiar los valores de moneda** y cómo **cambiar el símbolo de la moneda** usando Aspose.Tasks para Java. Estas capacidades le permiten adaptar los datos de costos para equipos globales, generar informes específicos por localidad y mantener sus archivos de proyecto consistentes a través de fronteras.

---

**Última actualización:** 2026-02-07  
**Probado con:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}