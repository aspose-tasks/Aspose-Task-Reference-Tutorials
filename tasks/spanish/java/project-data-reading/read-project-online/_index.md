---
date: 2025-12-15
description: Aprenda a leer datos de MS Project Online usando Aspose Tasks para Java.
  Esta guía muestra cómo obtener la lista de proyectos, listar proyectos de SharePoint
  y obtener el recuento de recursos.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'aspose tasks java: Lectura sin esfuerzo de datos de MS Project Online'
url: /es/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Lectura sin esfuerzo de datos de MS Project Online

## Introducción
En el ámbito de la gestión de proyectos, manejar los datos de Microsoft Project Online de manera eficiente es crucial para operaciones fluidas. **aspose tasks java** ofrece una API robusta y fácil de usar que permite leer datos de Project Online sin lidiar con llamadas HTTP de bajo nivel. En este tutorial recorreremos cómo obtener una lista de proyectos, enumerar proyectos de SharePoint y obtener el recuento de recursos de cada proyecto, todo con solo unas pocas líneas de código Java.

## Respuestas rápidas
- **¿Qué hace aspose tasks java?** Lee y manipula archivos de Microsoft Project y datos de Project Online de forma programática.  
- **¿Necesito una licencia para probarlo?** Hay una prueba gratuita disponible; se requiere una licencia para uso en producción.  
- **¿Qué credenciales se requieren?** Dominio de SharePoint, nombre de usuario y contraseña (o token de Azure AD).  
- **¿Puedo enumerar proyectos de SharePoint?** Sí – usa `ProjectServerManager.getProjectList()` para recuperarlos.  
- **¿Cómo obtengo el recuento de recursos?** Carga cada objeto `Project` y llama a `project.getResources().size()`.

## ¿Qué es aspose tasks java?
**aspose tasks java** es una biblioteca orientada a desarrolladores que abstrae las complejidades de los formatos de archivo de Microsoft Project y de las API REST de Project Server. Permite leer, crear y modificar datos de proyectos directamente desde aplicaciones Java, facilitando la integración con sistemas empresariales existentes.

## ¿Por qué usar aspose tasks java para leer MS Project Online?
- **Sin manejo manual de HTTP** – la biblioteca se encarga de la autenticación y de las llamadas REST.  
- **Seguridad de tipos fuerte** – trabaja con `Project`, `ProjectInfo` y otros POJOs en lugar de JSON crudo.  
- **Multiplataforma** – se ejecuta en cualquier entorno compatible con JVM.  
- **Conjunto de funciones rico** – además de leer, también puedes actualizar tareas, recursos y cronogramas.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – JDK 8 o superior instalado.  
2. **Biblioteca Aspose.Tasks for Java** – descárgala desde [here](https://releases.aspose.com/tasks/java/).  
3. **Cuenta de Microsoft Project Online** – con permisos para leer proyectos.  
4. **Dirección del dominio de SharePoint** – donde reside tu instancia de Project Online.  
5. **Nombre de usuario y contraseña** – o credenciales adecuadas de Azure AD para la autenticación.

## Importar paquetes
Primero, importa las clases esenciales de Aspose.Tasks que utilizaremos a lo largo del tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Paso 1: Establecer dominio de SharePoint, nombre de usuario y contraseña
Define los detalles de conexión para tu entorno de Project Online. Sustituye los valores de marcador de posición por tus propias credenciales.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Paso 2: Autenticar con credenciales del servidor de proyectos
Crea un objeto `ProjectServerCredentials` e inicializa un `ProjectServerManager`. Este gestor manejará todas las llamadas posteriores a Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Paso 3: Recuperar lista de proyectos y mostrar información
Utiliza el gestor para **recuperar la lista de proyectos** (enumerar proyectos de SharePoint) y muestra detalles básicos como nombre, fecha de creación y fecha de última guardado.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Paso 4: Cargar proyectos individuales y mostrar recuento de recursos
Para cada proyecto devuelto en el paso anterior, carga el objeto `Project` completo y muestra el **recuento de recursos**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Error de autenticación** | Dominio, nombre de usuario o contraseña incorrectos. | Verifica las credenciales y asegura que la cuenta tenga permisos de lectura en Project Online. |
| **SSLHandshakeException** | El tiempo de ejecución de Java no dispone de la versión TLS requerida. | Actualiza el JDK a la última versión o habilita TLS 1.2+. |
| **`reader.getProjectList()` devuelve vacío** | La cuenta no tiene acceso a ningún proyecto. | Revisa los permisos en Project Online o utiliza una cuenta de administrador. |
| **Proyectos grandes provocan OutOfMemoryError** | Cargar muchos proyectos a la vez consume memoria. | Carga los proyectos uno por uno y libera referencias después de usarlos. |

## Preguntas frecuentes
### Q: ¿Puedo usar aspose tasks java para modificar datos de MS Project Online?
A: Sí, Aspose.Tasks ofrece amplias capacidades tanto para leer **como** modificar datos de Project Online de forma programática.

### Q: ¿Aspose.Tasks admite otros formatos de archivo de gestión de proyectos?
A: Absolutamente. Soporta MPP, XML, Primavera y muchos más, garantizando compatibilidad en diversos ecosistemas de proyectos.

### Q: ¿Existe una prueba gratuita disponible para Aspose.Tasks for Java?
A: Sí, puedes obtener una prueba gratuita desde [here](https://releases.aspose.com/) para explorar las características y funcionalidades de Aspose.Tasks.

### Q: ¿Dónde puedo encontrar documentación completa para Aspose.Tasks for Java?
A: Puedes consultar la documentación detallada [here](https://reference.aspose.com/tasks/java/) para obtener una guía completa sobre el uso de Aspose.Tasks en tus proyectos Java.

### Q: ¿Qué opciones de soporte están disponibles para Aspose.Tasks for Java?
A: Si encuentras algún problema o tienes consultas, puedes buscar asistencia en el foro de la comunidad de Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Última actualización:** 2025-12-15  
**Probado con:** Aspose.Tasks for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}