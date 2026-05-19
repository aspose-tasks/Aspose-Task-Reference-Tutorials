---
date: 2026-01-15
description: Aprenda cómo trabajar con el costo presupuestado de trabajo programado
  en archivos de Microsoft Project usando Aspose.Tasks para Java. Siga nuestra guía
  paso a paso.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Trabajo programado de costo presupuestado con Aspose.Tasks para Java
url: /es/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# costo presupuestado del trabajo programado con Aspose.Tasks for Java

## Introducción

Gestionar **budgeted cost work scheduled** (BCWS) es esencial para mantener un proyecto en buen camino y garantizar que el pronóstico financiero se alinee con el trabajo planificado. En Microsoft Project, BCWS representa la cantidad de dinero que debería haberse gastado para el trabajo programado hasta una fecha específica. Aspose.Tasks for Java le brinda control total programático sobre estos valores, permitiéndole leer, modificar e informar sobre los costos de recursos sin abrir manualmente el archivo .mpp. En este tutorial recorreremos un ejemplo completo que muestra cómo cargar un proyecto, iterar sobre sus recursos y mostrar el **budgeted cost work scheduled** junto con otras métricas de costo clave.

## Respuestas rápidas
- **¿Qué significa BCWS?** Budgeted Cost Work Scheduled – el costo planificado para el trabajo programado hasta la fecha.  
- **¿Qué propiedad de la API recupera BCWS?** `Rsc.BCWS` on a `Resource` object.  
- **¿Necesito una licencia para ejecutar el ejemplo?** A free evaluation license works for testing; a full license is required for production.  
- **¿Puedo modificar los valores de BCWS?** Yes, you can set `Rsc.BCWS` just like any other numeric field.  
- **¿Versiones de Project compatibles?** All Microsoft Project versions from 2000 to the latest .mpp format.

## ¿Qué es el costo presupuestado del trabajo programado?

**Budgeted Cost Work Scheduled (BCWS)** es una medida de desempeño que refleja el costo que debería haberse incurrido para el trabajo planificado hasta un punto dado en el tiempo. Es una piedra angular de Earned Value Management (EVM) y ayuda a los gerentes de proyecto a comparar el gasto planificado con el real.

## Requisitos previos

Antes de sumergirse en el código, asegúrese de tener:

1. Un sólido dominio de los fundamentos de Java.  
2. Aspose.Tasks for Java añadido a su proyecto (Maven/Gradle o JAR).  
3. Un archivo Microsoft Project (`.mpp`) que contenga recursos con datos de costo (p. ej., *ResourceCosts.mpp*).

## Importar paquetes

Primero, importe las clases de Aspose.Tasks requeridas para manejar proyectos y recursos:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Paso 1: Definir el directorio de datos

```java
String dataDir = "Your Data Directory";
```

Reemplace `"Your Data Directory"` con la ruta absoluta o relativa donde se encuentra *ResourceCosts.mpp*.

## Paso 2: Cargar el archivo MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

El constructor `Project` lee el archivo .mpp y construye una representación en memoria que puede consultar.

## Paso 3: Iterar a través de los recursos

```java
for (Resource res : prj.getResources()) {
```

Este bucle recorre cada recurso definido en el proyecto, dándole acceso a sus campos de costo.

## Paso 4: Verificar el nombre y los costos del recurso

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Dentro del bloque `if` nosotros:

* Imprima el **costo total** (`Rsc.COST`).  
* Imprima el **costo real del trabajo realizado** (`Rsc.ACWP`).  
* Imprima el **budgeted cost work scheduled** (`Rsc.BCWS`) – la métrica principal en la que nos enfocamos.  
* Imprima el **budgeted cost work performed** (`Rsc.BCWP`).

Estos cuatro valores le dan una instantánea rápida de dónde está el proyecto financieramente.

## Por qué es importante monitorear el costo presupuestado del trabajo programado

* **Early warning:** Si BCWS es significativamente mayor que el costo real, puede estar sobreasignando recursos.  
* **Earned Value Analysis:** BCWS es una entrada clave para calcular Cost Variance (CV) y Schedule Variance (SV).  
* **Forecasting:** Datos precisos de BCWS ayudan a predecir futuras necesidades de flujo de efectivo e informan los informes a los interesados.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| `null` impreso para BCWS | El recurso no tiene una tabla de tarifas de costo definida | Defina una tabla de tarifas de costo para el recurso en Microsoft Project o configúrela programáticamente mediante `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` al iterar recursos | Archivo .mpp corrupto o contiene entradas de recursos vacías | Valide el archivo .mpp en Microsoft Project y elimine los recursos vacíos |
| Valores inesperados (p.ej., BCWS negativo) | Campos personalizados que sobrescriben los campos de costo estándar | Asegúrese de estar accediendo al `Rsc.BCWS` estándar y no a un campo personalizado con el mismo nombre |

## Preguntas frecuentes

**P: ¿Puedo actualizar el valor de BCWS programáticamente?**  
R: Sí. Use `res.set(Rsc.BCWS, newValue)` y luego guarde el proyecto con `prj.save("Updated.mpp")`.

**P: ¿Aspose.Tasks admite proyectos multimoneda?**  
R: Absolutamente. Los campos de costo respetan la configuración de moneda definida en el archivo del proyecto.

**P: ¿Hay alguna forma de exportar estas métricas de costo a CSV?**  
R: Puede iterar sobre los recursos y escribir los valores en un `StringBuilder` o usar una biblioteca CSV para generar el archivo.

**P: ¿En qué se diferencia BCWS de BCWP?**  
R: BCWS es el costo planificado para el trabajo programado, mientras que BCWP (Budgeted Cost Work Performed) refleja el costo planificado para el trabajo que realmente se ha completado.

**P: ¿Necesito una licencia especial para leer datos de costo?**  
R: La licencia de evaluación brinda acceso completo de lectura/escritura; se requiere una licencia comercial para implementaciones en producción.

## Conclusión

Al aprovechar Aspose.Tasks for Java, obtiene acceso preciso y programático a **budgeted cost work scheduled** y otras métricas de costo vitales. Esto le permite crear paneles personalizados, automatizar informes de Earned Value y mantener sus proyectos financieramente en buen camino, todo sin interacción manual con Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose