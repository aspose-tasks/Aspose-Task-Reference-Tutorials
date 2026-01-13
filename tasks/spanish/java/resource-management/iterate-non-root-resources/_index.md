---
date: 2026-01-13
description: Aprenda cómo iterar recursos que no son raíz en archivos de Microsoft
  Project usando Aspose.Tasks para Java.
linktitle: Iterate Non-Root Resources with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Iterar recursos no raíz con Aspose.Tasks para Java
url: /es/java/resource-management/iterate-non-root-resources/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Iterar recursos no raíz con Aspose.Tasks para Java

## Introducción
Aspose.Tasks para Java es una biblioteca potente que brinda a los desarrolladores una forma limpia y orientada a objetos de trabajar con archivos de Microsoft Project. En este tutorial aprenderás **cómo iterar recursos no raíz** para que puedas leer, modificar o analizar datos de recursos sin lidiar con el marcador de posición raíz. Ya sea que estés construyendo una herramienta de informes, un script de migración o un programador personalizado, dominar esta técnica hará que tu código sea más preciso y eficiente.

## Respuestas rápidas
- **¿Qué significa “recurso no raíz”?** Un recurso que no es el marcador de posición predeterminado “Project” (el nodo raíz).  
- **¿Por qué filtrar el recurso raíz?** La raíz no contiene datos útiles de programación y puede saturar los informes.  
- **¿Qué clase de Aspose.Tasks proporciona la colección de recursos?** `Project.getResources()`.  
- **¿Necesito una licencia para este código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo usar esto con Java 17?** Sí – Aspose.Tasks es compatible con Java 8 y versiones superiores.

## Requisitos previos
Antes de sumergirte en el código, asegúrate de tener:

1. **Java Development Kit (JDK)** – Instala el JDK más reciente desde el [sitio web de Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Biblioteca Aspose.Tasks para Java** – Obtén el JAR más reciente desde la [página de descargas](https://releases.aspose.com/tasks/java/).  

## Importar paquetes
En tu proyecto Java, importa las clases necesarias de Aspose.Tasks:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Paso 1: Configurar el directorio de datos
```java
String dataDir = "Your Data Directory";
```
Reemplaza `"Your Data Directory"` con la ruta absoluta donde se encuentran tus archivos `.mpp`.

## Paso 2: Cargar el archivo de proyecto
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
Esto crea una instancia de `Project` cargando **ResourceCosts.mpp** desde la carpeta que especificaste.

## Paso 3: Iterar sobre recursos no raíz
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
El bucle recorre cada objeto `Resource` en el proyecto. La comprobación `isRoot()` omite el recurso raíz incorporado, y la instrucción `System.out.println` imprime el nombre de cada **recurso no raíz**.

## Cómo iterar recursos no raíz
El fragmento anterior muestra el patrón central:

1. Obtén la colección completa con `prj.getResources()`.  
2. Usa `isRoot()` para filtrar el marcador de posición.  
3. Accede a cualquier campo del recurso (p. ej., `Rsc.NAME`, `Rsc.COST`) según sea necesario.

Puedes ampliar este patrón para agregar costos, exportar a CSV o aplicar reglas de negocio personalizadas.

## Problemas comunes y consejos
- **Comprobaciones de nulos** – Algunos recursos pueden tener campos opcionales; siempre protege contra `null` al llamar a `get()`.  
- **Rendimiento** – Para proyectos muy grandes, considera iterar con un bucle basado en índices para evitar crear colecciones intermedias.  
- **Licenciamiento** – Ejecutar el código sin una licencia válida añadirá una marca de agua a los archivos exportados; asegúrate de activar tu licencia al inicio de la aplicación.

## Conclusión
Al seguir estos pasos ahora sabes **cómo iterar recursos no raíz** usando Aspose.Tasks para Java. Esta técnica te ayuda a centrarte en los recursos reales del proyecto, limpiar las extracciones de datos y crear soluciones de gestión de proyectos más fiables.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Tasks para Java para crear nuevos archivos de proyecto?
Sí, Aspose.Tasks ofrece capacidades completas CRUD (Crear, Leer, Actualizar, Eliminar) para los formatos de proyecto MPP, MPT y XML.  

### ¿Aspose.Tasks admite todas las versiones de archivos de Microsoft Project?
Absolutamente. Maneja archivos de Project 2003‑2019, incluidas las últimas especificaciones de MPP.  

### ¿Aspose.Tasks es compatible con frameworks Java como Spring?
Sí, puedes inyectar la biblioteca en beans de Spring o usarla en cualquier aplicación Java estándar.  

### ¿Puedo personalizar los campos de datos del proyecto usando Aspose.Tasks?
Definitivamente. La API te permite agregar, modificar o eliminar campos personalizados en tareas, recursos y asignaciones.  

### ¿Aspose.Tasks proporciona soporte y documentación para desarrolladores?
El producto incluye documentación completa de la API, ejemplos de código y un foro de soporte dedicado para asistencia rápida.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-01-13  
**Probado con:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

---