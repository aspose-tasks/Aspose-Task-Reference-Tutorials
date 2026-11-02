---
date: 2026-10-31
description: Aprenda como salvar projeto como PDF e ler o banco de dados do Microsoft
  Project com Aspose.Tasks for Java, além de conectar ao Project Server, converter
  o projeto para HTML e exportar o projeto para XML.
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Lendo Dados do Projeto do Banco de Dados do Microsoft Project no Aspose.Tasks
og_description: Salvar projeto como PDF e ler o banco de dados do Microsoft Project
  usando Aspose.Tasks for Java. Aprenda a conectar ao Project Server, exportar para
  HTML, XML e CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Salvar projeto como PDF e ler banco de dados do Microsoft Project com Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Salvar projeto como PDF e ler banco de dados do Microsoft Project com Aspose.Tasks
  for Java
url: /pt/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar projeto como PDF e ler o banco de dados do Microsoft Project com Aspose.Tasks para Java

## Introdução
Neste tutorial você descobrirá como **ler o banco de dados do Microsoft Project** diretamente de um Microsoft Project Server e, em seguida, **salvar o projeto como PDF** usando a API Aspose.Tasks Java. Seja para gerar relatórios imprimíveis, migrar dados legados ou incorporar informações de projeto em um portal personalizado, este guia o conduz por cada passo — desde a configuração da conexão JDBC até a exportação do projeto para PDF, XML ou HTML. Ao final, você terá uma solução pronta para produção que roda em qualquer servidor Java sem precisar instalar o Microsoft Project.

## Respostas rápidas
- **O que o Aspose.Tasks faz?** Ele fornece uma API pure‑Java para ler, gravar e manipular arquivos e bancos de dados do Microsoft Project.  
- **Preciso ter o Microsoft Project instalado?** Não, o Aspose.Tasks funciona independentemente do Microsoft Project.  
- **Qual tipo de banco de dados é suportado?** Microsoft SQL Server, o back‑end do Project Server.  
- **Posso exportar para outros formatos?** Sim—PDF, XML, HTML, CSV, PNG, JPEG e mais.  
- **Quais são os principais pré‑requisitos?** JDK 8 ou superior, biblioteca Aspose.Tasks para Java, driver JDBC do SQL Server e credenciais válidas do Project Server.

## O que significa “ler o banco de dados do Microsoft Project”?
Ler um banco de dados do Microsoft Project significa conectar ao repositório SQL Server do Project Server, extrair os dados de projeto armazenados e carregá‑los em um objeto `Project` que o Aspose.Tasks pode manipular. Essa abordagem é ideal para relatórios automatizados, migração de dados ou análises personalizadas.

## Por que usar o Aspose.Tasks para Java?
O Aspose.Tasks para Java permite trabalhar com dados do Microsoft Project sem precisar da aplicação desktop, oferecendo uma solução pure‑Java que roda em qualquer plataforma. Ele fornece um modelo de objetos abrangente para tarefas, recursos, calendários e campos personalizados, e pode lidar com grandes projetos corporativos de forma eficiente, tornando‑o ideal para cenários de relatórios automatizados, migração e integração.

- **Sem dependência do Microsoft Project** – execute em qualquer servidor ou ambiente CI.  
- **Modelo de objetos rico** – acesse tarefas, recursos, atribuições, calendários e campos personalizados programaticamente.  
- **Múltiplas opções de exportação** – o Aspose.Tasks suporta exportação para **mais de 20 formatos de arquivo**, incluindo PDF, XML, HTML, CSV, PNG e JPEG, com uma única chamada de API.  
- **Alto desempenho** – a biblioteca pode processar projetos contendo **até 10.000 tarefas** em menos de um minuto, e transmite dados para evitar carregar o arquivo inteiro na memória.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
2. Biblioteca Aspose.Tasks para Java adicionada ao classpath do seu projeto.  
3. Credenciais de acesso ao banco de dados SQL do Project Server (nome do servidor, porta, nome do banco, usuário, senha) para conectar ao Project Server.  
4. O driver JDBC da Microsoft para SQL Server (por exemplo, `sqljdbc4.jar`).  

## Importar pacotes
Primeiro, importe as classes que você precisará. A lista inclui classes principais do Aspose.Tasks e utilitários padrão do Java.

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

## Como conectar ao Project Server
Estabelecer uma conexão confiável é a base para ler os dados do projeto. Certifique‑se de que a instância do SQL Server esteja acessível a partir do seu host Java e de que o login usado tenha permissões **SELECT** no esquema do Project Server. Também verifique a latência da rede e configure quaisquer ajustes SSL necessários para garantir comunicação segura.

## Etapa 1: configurar a conexão ao banco de dados
A classe `MspDbSettings` encapsula os detalhes da conexão JDBC necessários para acessar um banco de dados do Microsoft Project Server. Crie uma instância de `MspDbSettings` que contenha a string de conexão JDBC. Substitua os valores de placeholder pelos detalhes reais do seu servidor.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Dica:** Armazene a string de conexão em um arquivo de configuração seguro ou variável de ambiente em vez de codificar as credenciais.

## Etapa 2: adicionar driver JDBC
Carregue o driver JDBC do Microsoft SQL Server em tempo de execução para que a JVM possa se comunicar com o banco de dados.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Aviso:** Certifique‑se de que a versão do driver corresponde à sua versão do SQL Server. Usar um driver incompatível pode causar falhas de conexão.

## Etapa 3: ler dados do projeto
A classe `Project` representa um arquivo Microsoft Project carregado na memória, expondo tarefas, recursos e atribuições. Instancie um objeto `Project` passando o `MspDbSettings`. O Aspose.Tasks buscará os dados do projeto no banco de dados automaticamente.

```java
Project project = new Project(settings);
```

Neste ponto você pode explorar o objeto `project`—listar tarefas, recursos ou modificar campos conforme necessário.

## Etapa 4: salvar o projeto como PDF
A enumeração `SaveFileFormat` define o formato de saída para o método `Project.save`, como PDF, XML ou HTML. Exporte o projeto carregado para o formato de sua escolha. O exemplo abaixo salva o projeto como **PDF**, ideal para relatórios imprimíveis. Você também pode **exportar o projeto para XML** ou **converter o projeto para HTML** alterando o enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Se preferir XML, basta substituir `SaveFileFormat.Pdf` por `SaveFileFormat.Xml`. Para saída HTML, use `SaveFileFormat.Html`.

## Problemas comuns e soluções
| Problema | Causa típica | Correção |
|----------|--------------|----------|
| **Tempo limite de conexão** | Servidor/porta incorretos ou firewall bloqueando | Verifique o endereço do servidor, abra a porta 1433 e teste a conectividade com um programa simples de teste JDBC. |
| **Erro de autenticação** | Nome de usuário/senha inválidos ou SQL Server não configurado para autenticação SQL | Use um login SQL válido ou habilite a autenticação de modo misto no servidor. |
| **Driver não encontrado** | JAR JDBC não está no classpath | Certifique‑se de que `addJDBCDriver` aponta para o arquivo `.jar` correto e que o caminho usa barras invertidas duplas (`\\`). |
| **Projeto vazio após carregamento** | Permissões insuficientes para ler as tabelas do Project Server | Conceda ao login direitos SELECT no esquema do banco de dados do Project Server. |

## Perguntas frequentes

**Q: O Aspose.Tasks pode ser usado para ler dados de projeto de outros bancos de dados além do Microsoft Project?**  
A: Sim, o Aspose.Tasks suporta leitura de dados de projeto a partir de arquivos XML, bancos de dados Primavera e outros formatos padrão de projeto.

**Q: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?**  
A: Sim, a biblioteca funciona com o Microsoft Project 2007 até as versões mais recentes de 2024, garantindo integração perfeita entre versões.

**Q: Posso manipular os dados do projeto antes de salvá‑los?**  
A: Absolutamente, você pode adicionar, atualizar ou excluir tarefas, recursos e campos personalizados usando a API rica antes da exportação.

**Q: O Aspose.Tasks suporta múltiplos formatos de saída?**  
A: Sim, você pode salvar projetos como PDF, XML, HTML, CSV, PNG, JPEG e mais—mais de 20 formatos no total.

**Q: Onde posso encontrar suporte ou assistência adicional com o Aspose.Tasks?**  
A: Para ajuda adicional, visite o fórum Aspose.Tasks ou explore a documentação disponível no site [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusão
Seguindo este guia passo a passo, você agora sabe como **ler o banco de dados do Microsoft Project**, **salvar o projeto como PDF** e exportar para outros formatos usando o Aspose.Tasks para Java. Essa abordagem elimina a dependência do Microsoft Project, simplifica relatórios automatizados e abre caminho para integrações personalizadas poderosas.

---

**Última atualização:** 2026-10-31  
**Testado com:** Aspose.Tasks for Java 24.5 (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais relacionados

- [Como salvar projeto como PDF com Aspose.Tasks – Guia de exportação](/tasks/java/project-file-operations/save-as-pdf/)
- [Salvar projeto como PDF – Renderizar planilha de tarefas com Aspose.Tasks para Java](/tasks/java/task-properties/render-task-sheet/)
- [Exportar projeto para PDF e reduzir o espaço entre a lista de tarefas e o rodapé no Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}