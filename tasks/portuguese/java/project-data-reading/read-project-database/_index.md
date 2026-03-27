---
date: 2026-02-18
description: Aprenda a salvar o projeto como PDF e ler o banco de dados do Microsoft
  Project com Aspose.Tasks para Java, além de conectar ao Project Server, converter
  o projeto para HTML e exportar o projeto para XML.
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salvar projeto como PDF e ler o banco de dados do Project com Aspose.Tasks
  para Java
url: /pt/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar projeto como PDF e ler banco de dados do Microsoft Project com Aspose.Tasks para Java

## Introdução
Neste tutorial você descobrirá como **ler o banco de dados do Microsoft Project** diretamente de um Microsoft Project Server e então **salvar o projeto como PDF** usando a API Aspose.Tasks Java. Seja para gerar relatórios, migrar dados ou integrar informações de projetos em suas próprias aplicações, este guia orienta você em cada passo — desde a configuração da conexão ao banco de dados até a exportação do projeto para PDF, XML ou HTML. Ao final, você terá uma solução sólida, pronta para produção, que funciona sem a necessidade de instalar o Microsoft Project na máquina host.

## Respostas rápidas
- **O que o Aspose.Tasks faz?** Ele fornece uma API pura em Java para ler, gravar e manipular arquivos e bancos de dados do Microsoft Project.  
- **Preciso ter o Microsoft Project instalado?** Não, o Aspose.Tasks funciona independentemente do Microsoft Project.  
- **Qual tipo de banco de dados é suportado?** Microsoft SQL Server (o backend do Project Server).  
- **Posso exportar para outros formatos?** Sim, além de PDF você pode salvar como XML, HTML, CSV e mais.  
- **Quais são os principais pré‑requisitos?** JDK, biblioteca Aspose.Tasks para Java, o driver JDBC do SQL Server e credenciais para **conectar ao Project Server**.

## O que significa “ler banco de dados do Microsoft Project”?
Ler um banco de dados do Microsoft Project significa conectar ao repositório SQL Server do Project Server, extrair os dados de projeto armazenados e carregá‑los em um objeto `Project` que o Aspose.Tasks pode manipular. Essa abordagem é ideal para relatórios automatizados, migração de dados ou análises personalizadas.

## Por que usar Aspose.Tasks para Java?
- **Sem dependência do Microsoft Project** – execute em qualquer servidor ou ambiente CI.  
- **Modelo de objetos rico** – acesse tarefas, recursos, atribuições, calendários e campos personalizados programaticamente.  
- **Múltiplas opções de exportação** – PDF, XML, HTML, PNG, etc., com uma única chamada de API.  
- **Alto desempenho** – otimizado para projetos corporativos de grande porte.

## Pré‑requisitos
Antes de começar, verifique se você tem:

1. Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
2. Biblioteca Aspose.Tasks para Java adicionada ao classpath do seu projeto.  
3. Credenciais de acesso ao banco de dados SQL do Project Server (nome do servidor, porta, nome do banco, usuário, senha) **para conectar ao Project Server**.  
4. O driver Microsoft JDBC para SQL Server (por exemplo, `sqljdbc4.jar`).  

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
Estabelecer uma conexão confiável é a base para ler os dados do projeto. Certifique‑se de que a instância do SQL Server esteja acessível a partir da sua máquina Java e de que o login usado tenha permissões **SELECT** no esquema do Project Server.

## Etapa 1: Configurar a conexão ao banco de dados
Crie uma instância de `MspDbSettings` que contém a string de conexão JDBC. Substitua os valores de placeholder pelos detalhes reais do seu servidor.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Dica profissional:** Armazene a string de conexão em um arquivo de configuração seguro ou em variável de ambiente, em vez de codificar credenciais no código.

## Etapa 2: Adicionar o driver JDBC
Carregue o driver Microsoft SQL Server JDBC em tempo de execução para que a JVM possa se comunicar com o banco de dados.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Aviso:** Garanta que a versão do driver corresponda à sua versão do SQL Server. Usar um driver incompatível pode causar falhas de conexão.

## Etapa 3: Ler os dados do projeto
Instancie um objeto `Project` passando o `MspDbSettings`. O Aspose.Tasks buscará os dados do projeto no banco automaticamente.

```java
Project project = new Project(settings);
```

Neste ponto você pode explorar o objeto `project` — listar tarefas, recursos ou modificar campos conforme necessário.

## Etapa 4: Salvar o projeto como PDF
Exporte o projeto carregado para o formato de sua escolha. O exemplo abaixo salva o projeto como **PDF**, ideal para relatórios imprimíveis. Você também pode **exportar o projeto para XML** ou **converter o projeto para HTML** alterando o enum `SaveFileFormat`.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

Se preferir XML, basta substituir `SaveFileFormat.Pdf` por `SaveFileFormat.Xml`. Para saída HTML, use `SaveFileFormat.Html`.

## Problemas comuns & soluções
| Problema | Causa típica | Solução |
|----------|--------------|---------|
| **Timeout de conexão** | Endereço/porta incorretos ou firewall bloqueando | Verifique o endereço do servidor, abra a porta 1433 e teste a conectividade com um programa JDBC simples. |
| **Erro de autenticação** | Usuário/senha inválidos ou SQL Server não configurado para autenticação SQL | Use um login SQL válido ou habilite a autenticação mista no servidor. |
| **Driver não encontrado** | JAR JDBC não está no classpath | Certifique‑se de que `addJDBCDriver` aponta para o arquivo `.jar` correto e que o caminho usa barras duplas (`\\`). |
| **Projeto vazio após carregamento** | Permissões insuficientes para ler tabelas do Project Server | Conceda ao login direitos SELECT no esquema do banco de dados do Project Server. |

## Perguntas frequentes

**P: O Aspose.Tasks pode ser usado para ler dados de projeto de outros bancos além do Microsoft Project?**  
R: Sim, o Aspose.Tasks suporta leitura de dados de projeto de várias fontes, incluindo arquivos XML, Primavera e bancos de dados do Microsoft Project.

**P: O Aspose.Tasks é compatível com diferentes versões do Microsoft Project?**  
R: Sim, o Aspose.Tasks foi projetado para funcionar com múltiplas versões do Microsoft Project, garantindo integração sem interrupções.

**P: Posso manipular os dados do projeto antes de salvá‑los?**  
R: Absolutamente, o Aspose.Tasks oferece uma API completa para adicionar tarefas, atualizar recursos e definir propriedades do projeto antes da exportação.

**P: O Aspose.Tasks suporta múltiplos formatos de saída?**  
R: Sim, você pode salvar projetos como PDF, XML, HTML, CSV, PNG, JPEG e muito mais.

**P: Onde posso encontrar suporte ou assistência adicional com o Aspose.Tasks?**  
R: Para ajuda extra, visite o fórum Aspose.Tasks ou explore a documentação disponível no site [aqui](https://forum.aspose.com/c/tasks/15).

## Conclusão
Seguindo este guia passo a passo, você agora sabe como **ler o banco de dados do Microsoft Project**, **salvar o projeto como PDF** e exportar para outros formatos usando o Aspose.Tasks para Java. Essa abordagem elimina a dependência do Microsoft Project, simplifica a geração automática de relatórios e abre caminho para integrações personalizadas poderosas.

---

**Última atualização:** 2026-02-18  
**Testado com:** Aspose.Tasks para Java 24.5 (mais recente na data de publicação)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}