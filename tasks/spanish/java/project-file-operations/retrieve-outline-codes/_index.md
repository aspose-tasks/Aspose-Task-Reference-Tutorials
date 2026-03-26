---
date: 2025-12-20
description: Aprenda a obtener los códigos de esquema de MS Project de forma programática
  usando Aspose.Tasks para Java. Mejore sus capacidades de gestión de proyectos.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Obtener códigos de esquema de MS Project en Aspose.Tasks
url: /es/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar códigos de esquema de MS Project en Aspose.Tasks

## Introducción
En este tutorial, descubrirás **cómo recuperar códigos de esquema de MS Project** usando Aspose.Tasks para Java. Los códigos de esquema en MS Project te ofrecen una forma poderosa de categorizar tareas, recursos y asignaciones, y acceder a ellos programáticamente te permite crear informes personalizados, automatización o soluciones de integración. Recorreremos un ejemplo completo, paso a paso, que puedes copiar en tu propio proyecto.

## Respuestas rápidas
- **¿Qué hace el código?** Carga un archivo Project y muestra cada definición de código de esquema, sus máscaras y sus valores.  
- **¿Qué biblioteca se requiere?** Aspose.Tasks para Java (cualquier versión reciente).  
- **¿Necesito una licencia?** Una versión de prueba funciona para desarrollo; se requiere una licencia completa para producción.  
- **¿Qué versión de Java se admite?** Java 8 o superior.  
- **¿Puedo modificar los códigos después de recuperarlos?** Sí, la misma API te permite agregar, editar o eliminar códigos de esquema.

## ¿Qué son los códigos de esquema de MS Project?
Los códigos de esquema son campos personalizados que permiten a los gerentes de proyecto agrupar y filtrar tareas más allá de la jerarquía predeterminada. Pueden ser valores numéricos simples, cadenas o incluso códigos personalizados a nivel empresarial definidos a nivel de organización. Al leer estos códigos, puedes impulsar paneles de control, exportar datos o aplicar convenciones de nomenclatura automáticamente.

## ¿Por qué recuperar los códigos de esquema de MS Project con Aspose.Tasks?
- **Automatización:** Generar informes o activar flujos de trabajo sin exportación manual.  
- **Integración:** Sincronizar códigos de esquema con ERP, PPM o herramientas de BI.  
- **Personalización:** Aplicar reglas de negocio basadas en los valores de los códigos (p. ej., asignación de costos).  
- **Multiplataforma:** Funciona en Windows, Linux y macOS, independiente de la interfaz de Microsoft Project.

## Requisitos previos
Antes de comenzar, asegúrate de tener los siguientes requisitos configurados:

### 1. Entorno de desarrollo Java
Asegúrate de tener instalado el Java Development Kit (JDK) en tu sistema. Puedes descargar e instalar el JDK desde el sitio web de Oracle.

### 2. Biblioteca Aspose.Tasks
Descarga e incluye la biblioteca Aspose.Tasks en tu proyecto Java. Puedes descargar la biblioteca desde la [Página de descarga de Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).

## Importar paquetes
Primero, importa los paquetes necesarios de Aspose.Tasks en tu código Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Ahora desglosaremos el código de ejemplo proporcionado en varios pasos:

## Paso 1: Cargar el proyecto
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
En este paso, cargamos el archivo Microsoft Project en un objeto `Project` usando el nombre de archivo proporcionado.

## Paso 2: Recuperar códigos de esquema
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Iteramos a través de cada definición de código de esquema en el proyecto.

## Paso 3: Acceder a las propiedades del código de esquema
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperamos e imprimimos varias propiedades de la definición del código de esquema, como Alias, ID de campo y Nombre de campo.

## Paso 4: Verificar código personalizado empresarial
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verificamos si el código de esquema es un código personalizado empresarial y mostramos el resultado en consecuencia.

## Paso 5: Mostrar máscaras de códigos de esquema
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteramos a través de cada máscara asociada al código de esquema y mostramos su nivel y valor de máscara.

## Paso 6: Mostrar valores de códigos de esquema
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iteramos a través de cada valor de código de esquema y mostramos su descripción, ID de valor, valor y tipo.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Sin salida** | Ruta del archivo del proyecto incorrecta | Verifica que `projectName` apunte a un archivo `.mpp` válido. |
| **Valores nulos** | Código de esquema no definido en el archivo | Asegúrate de que el archivo Project realmente contenga códigos de esquema (verifica en la UI de MS Project). |
| **LicenseException** | Uso de la versión de prueba sin activación adecuada | Aplica una licencia temporal o completa mediante `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Tasks para Java para modificar los códigos de esquema en un archivo Project?**  
A: Sí, Aspose.Tasks para Java proporciona APIs para modificar los códigos de esquema programáticamente. Puedes agregar, editar o eliminar definiciones usando el mismo objeto `Project`.

**Q: ¿Hay una versión de prueba disponible para Aspose.Tasks para Java?**  
A: Sí, puedes descargar una versión de prueba gratuita de Aspose.Tasks para Java desde el [sitio web de Aspose.Tasks](https://releases.aspose.com/).

**Q: ¿Cómo puedo obtener soporte técnico para Aspose.Tasks para Java?**  
A: Puedes obtener soporte técnico visitando el [foro de Aspose.Tasks](https://forum.aspose.com/c/tasks/15) y publicando tus consultas allí.

**Q: ¿Puedo adquirir una licencia temporal para Aspose.Tasks para Java?**  
A: Sí, puedes adquirir una licencia temporal para Aspose.Tasks para Java desde la [página de compra](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo encontrar la documentación completa para Aspose.Tasks para Java?**  
A: Puedes consultar la [documentación](https://reference.aspose.com/tasks/java/) para obtener información detallada sobre el uso de Aspose.Tasks para Java.

## Conclusión
En este tutorial, hemos aprendido cómo recuperar **códigos de esquema de MS Project** usando Aspose.Tasks para Java. Siguiendo los pasos proporcionados, puedes acceder y manipular eficazmente los códigos de esquema en tus aplicaciones Java, habilitando capacidades avanzadas de gestión de proyectos como informes personalizados, automatización e integración con otros sistemas empresariales.

---

**Última actualización:** 2025-12-20  
**Probado con:** Aspose.Tasks para Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}