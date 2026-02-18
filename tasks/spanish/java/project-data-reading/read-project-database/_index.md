---
date: 2026-02-18
description: Aprenda cómo guardar el proyecto como PDF y leer la base de datos de
  Microsoft Project con Aspose.Tasks para Java, además de conectar al Project Server,
  convertir el proyecto a HTML y exportar el proyecto a XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Guardar proyecto como PDF y leer la base de datos del proyecto con Aspose.Tasks
  para Java
url: /es/java/project-data-reading/read-project-database/
weight: 12
---

 "Tested With", "Author". Keep as is? Should translate to Spanish: "Última actualización", "Probado con", "Autor". But maybe keep as is? The instruction: translate all text content naturally to Spanish. So yes translate those.

Make sure to keep markdown formatting.

Let's produce.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar proyecto como PDF y leer la base de datos de Microsoft Project con Aspose.Tasks para Java

## Introducción
En este tutorial descubrirás cómo **leer la base de datos de Microsoft Project** directamente desde un Microsoft Project Server y luego **guardar el proyecto como PDF** usando la API Aspose.Tasks para Java. Ya sea que necesites generar informes, migrar datos o integrar la información del proyecto en tus propias aplicaciones, esta guía te acompañará paso a paso—desde la configuración de la conexión a la base de datos hasta la exportación del proyecto a PDF, XML o HTML. Al final, tendrás una solución sólida y lista para producción que funciona sin instalar Microsoft Project en la máquina host.

## Respuestas rápidas
- **¿Qué hace Aspose.Tasks?** Proporciona una API pura de Java para leer, escribir y manipular archivos y bases de datos de Microsoft Project.  
- **¿Necesito tener Microsoft Project instalado?** No, Aspose.Tasks funciona de forma independiente de Microsoft Project.  
- **¿Qué tipo de base de datos es compatible?** Microsoft SQL Server (el backend de Project Server).  
- **¿Puedo exportar a otros formatos?** Sí, además de PDF puedes guardar en XML, HTML, CSV y más.  
- **¿Cuáles son los requisitos principales?** JDK, la biblioteca Aspose.Tasks para Java, el controlador JDBC de SQL Server y credenciales para **conectarse a Project Server**.

## ¿Qué significa “leer la base de datos de Microsoft Project”?
Leer una base de datos de Microsoft Project implica conectarse al repositorio SQL Server de Project Server, extraer los datos del proyecto almacenados y cargarlos en un objeto `Project` que Aspose.Tasks puede manipular. Este enfoque es ideal para informes automatizados, migración de datos o análisis personalizados.

## ¿Por qué usar Aspose.Tasks para Java?
- **Sin dependencia de Microsoft Project** – se ejecuta en cualquier servidor o entorno CI.  
- **Modelo de objetos rico** – acceso programático a tareas, recursos, asignaciones, calendarios y campos personalizados.  
- **Múltiples opciones de exportación** – PDF, XML, HTML, PNG, etc., con una sola llamada a la API.  
- **Alto rendimiento** – optimizado para proyectos empresariales de gran tamaño.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. Un entorno de desarrollo Java funcional (JDK 8 o superior).  
2. La biblioteca Aspose.Tasks para Java añadida al classpath de tu proyecto.  
3. Credenciales de acceso a la base de datos SQL del Project Server (nombre del servidor, puerto, nombre de la base de datos, usuario, contraseña) **para conectarse a Project Server**.  
4. El controlador JDBC de Microsoft para SQL Server (por ejemplo, `sqljdbc4.jar`).  

## Importar paquetes
Primero, importa las clases que necesitarás. La lista incluye clases centrales de Aspose.Tasks y utilidades estándar de Java.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## Cómo conectarse a Project Server
Establecer una conexión fiable es la base para leer los datos del proyecto. Asegúrate de que la instancia de SQL Server sea accesible desde tu host Java y de que el usuario que uses tenga permisos **SELECT** sobre el esquema de Project Server.

## Paso 1: Configurar la conexión a la base de datos
Crea una instancia de `MspDbSettings` que contenga la cadena de conexión JDBC. Sustituye los valores de marcador de posición por los detalles reales de tu servidor.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Consejo profesional:** Guarda la cadena de conexión en un archivo de configuración seguro o en una variable de entorno en lugar de codificar las credenciales directamente.

## Paso 2: Añadir el controlador JDBC
Carga el controlador JDBC de Microsoft SQL Server en tiempo de ejecución para que la JVM pueda comunicarse con la base de datos.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Advertencia:** Asegúrate de que la versión del controlador coincida con la versión de tu SQL Server. Usar un controlador incompatible puede provocar fallos de conexión.

## Paso 3: Leer los datos del proyecto
Instancia un objeto `Project` pasando el `MspDbSettings`. Aspose.Tasks recuperará automáticamente los datos del proyecto desde la base de datos.

```java
Project project = new Project(settings);
```

En este punto puedes explorar el objeto `project`: listar tareas, recursos o modificar campos según sea necesario.

## Paso 4: Guardar el proyecto como PDF
Exporta el proyecto cargado al formato que prefieras. El ejemplo a continuación guarda el proyecto como **PDF**, ideal para informes imprimibles. También puedes **exportar el proyecto a XML** o **convertirlo a HTML** cambiando el enumerado `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Si prefieres XML, simplemente reemplaza `SaveFileFormat.Pdf` por `SaveFileFormat.Xml`. Para salida HTML, usa `SaveFileFormat.Html`.

## Problemas comunes y soluciones
| Problema | Causa típica | Solución |
|----------|--------------|----------|
| **Tiempo de espera de conexión** | Dirección/puerto incorrectos o firewall bloqueando | Verifica la dirección del servidor, abre el puerto 1433 y prueba la conectividad con un programa JDBC simple. |
| **Error de autenticación** | Usuario/contraseña inválidos o SQL Server no configurado para autenticación SQL | Usa un inicio de sesión SQL válido o habilita la autenticación mixta en el servidor. |
| **Controlador no encontrado** | JAR JDBC no está en el classpath | Asegúrate de que `addJDBCDriver` apunte al archivo `.jar` correcto y que la ruta use doble barra invertida (`\\`). |
| **Proyecto vacío después de cargar** | Permisos insuficientes para leer las tablas de Project Server | Concede al usuario derechos SELECT sobre el esquema de la base de datos de Project Server. |

## Preguntas frecuentes

**P: ¿Puede Aspose.Tasks usarse para leer datos de proyecto desde otras bases de datos además de Microsoft Project?**  
R: Sí, Aspose.Tasks admite la lectura de datos de proyecto desde diversas fuentes, incluidos archivos XML, Primavera y bases de datos de Microsoft Project.

**P: ¿Es Aspose.Tasks compatible con diferentes versiones de Microsoft Project?**  
R: Sí, Aspose.Tasks está diseñado para trabajar con múltiples versiones de Microsoft Project, garantizando una integración sin problemas.

**P: ¿Puedo manipular los datos del proyecto antes de guardarlos?**  
R: Por supuesto, Aspose.Tasks ofrece una API completa para añadir tareas, actualizar recursos y establecer propiedades del proyecto antes de la exportación.

**P: ¿Aspose.Tasks admite varios formatos de salida?**  
R: Sí, puedes guardar proyectos como PDF, XML, HTML, CSV, PNG, JPEG y más.

**P: ¿Dónde puedo encontrar más soporte o asistencia con Aspose.Tasks?**  
R: Para obtener ayuda adicional, visita el foro de Aspose.Tasks o explora la documentación disponible en el sitio web [here](https://forum.aspose.com/c/tasks/15).

## Conclusión
Siguiendo esta guía paso a paso, ahora sabes cómo **leer la base de datos de Microsoft Project**, **guardar el proyecto como PDF** y exportarlo a otros formatos usando Aspose.Tasks para Java. Este enfoque elimina la dependencia de Microsoft Project, simplifica la generación automática de informes y abre la puerta a integraciones personalizadas muy potentes.

---

**Última actualización:** 2026-02-18  
**Probado con:** Aspose.Tasks para Java 24.5 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}