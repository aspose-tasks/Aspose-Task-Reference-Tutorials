---
title: Lendo dados do projeto do banco de dados MS Project em Aspose.Tasks
linktitle: Lendo dados do projeto do banco de dados do Microsoft Project em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como ler dados do projeto do banco de dados do Microsoft Project usando Aspose.Tasks for Java. Guia passo a passo com exemplos de código.
weight: 12
url: /pt/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lendo dados do projeto do banco de dados MS Project em Aspose.Tasks

## Introdução
Neste tutorial, exploraremos como ler dados do projeto de um banco de dados do Microsoft Project usando Aspose.Tasks for Java. Aspose.Tasks é uma API Java poderosa que permite aos desenvolvedores manipular documentos do Microsoft Project sem a necessidade de instalação do Microsoft Project. Seguindo as etapas descritas neste guia, você aprenderá como extrair com eficiência os dados do projeto de um banco de dados e salvá-los no formato desejado.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
1. Conhecimento básico de programação Java.
2. Java Development Kit (JDK) instalado em seu sistema.
3. Biblioteca Aspose.Tasks para Java baixada e configurada em seu projeto.

## Importar pacotes
Para começar, importe os pacotes necessários:
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
## Etapa 1: configurar a conexão com o banco de dados
Primeiramente, você precisa configurar a conexão com o banco de dados do Microsoft Project. Isso inclui a especificação do URL do banco de dados, nome do servidor, número da porta, nome do banco de dados, nome de usuário e senha.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Etapa 2: adicionar driver JDBC
Em seguida, você precisa adicionar o driver JDBC ao seu projeto. Este driver facilita a comunicação entre aplicativos Java e o banco de dados Microsoft SQL Server.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Etapa 3: ler os dados do projeto
 Agora, crie um`Project` objeto e carregar dados do projeto do banco de dados usando as configurações definidas anteriormente.
```java
Project project = new Project(settings);
```
## Etapa 4: salvar os dados do projeto
Por fim, salve os dados do projeto no formato desejado. Neste exemplo, salvamos como um arquivo XML.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Parabéns! Você leu com êxito os dados do projeto de um banco de dados do Microsoft Project usando Aspose.Tasks for Java.

## Conclusão
Neste tutorial, cobrimos o processo de leitura de dados de projeto de um banco de dados Microsoft Project usando Aspose.Tasks for Java. Seguindo as etapas descritas, você pode extrair facilmente as informações do projeto e manipulá-las de acordo com suas necessidades. Aspose.Tasks simplifica o manuseio de documentos do Microsoft Project, permitindo extração e manipulação eficiente de dados.
## Perguntas frequentes
### P: O Aspose.Tasks pode ser usado para ler dados de projetos de outros bancos de dados além do Microsoft Project?
R: Sim, Aspose.Tasks oferece suporte à leitura de dados de projetos de várias fontes, incluindo arquivos XML, Primavera e bancos de dados do Microsoft Project.
### P: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?
R: Sim, o Aspose.Tasks foi projetado para funcionar com diferentes versões do Microsoft Project, garantindo compatibilidade e integração perfeita.
### P: Posso manipular os dados do projeto antes de salvá-lo?
R: Com certeza, Aspose.Tasks oferece uma ampla gama de recursos para manipular dados do projeto, como adicionar tarefas, atualizar recursos e definir propriedades do projeto.
### P: O Aspose.Tasks oferece suporte a vários formatos de saída?
R: Sim, Aspose.Tasks oferece suporte a vários formatos de saída, incluindo XML, PDF, HTML e formatos de imagem como PNG e JPEG.
### P: Onde posso encontrar mais suporte ou assistência com Aspose.Tasks?
 R: Para suporte ou assistência adicional, você pode visitar o fórum Aspose.Tasks ou explorar a documentação disponível no site[aqui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
