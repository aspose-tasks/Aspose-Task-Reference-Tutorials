---
date: 2025-12-15
description: Aprenda a ler dados do MS Project Online usando Aspose.Tasks Java. Este
  guia mostra como recuperar a lista de projetos, listar projetos do SharePoint e
  obter a contagem de recursos.
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 'Aspose.Tasks Java - Leitura sem esforço de dados do MS Project Online'
url: /pt/java/project-data-reading/read-project-online/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java: Leitura sem esforço de dados do MS Project Online

## Introdução
No âmbito da gestão de projetos, manipular os dados do Microsoft Project Online de forma eficiente é crucial para operações simplificadas. **aspose tasks java** oferece uma API robusta e fácil de usar que permite ler dados do Project Online sem precisar lidar com chamadas HTTP de baixo nível. Neste tutorial, vamos percorrer como recuperar uma lista de projetos, listar projetos do SharePoint e obter a contagem de recursos de cada projeto — tudo com apenas algumas linhas de código Java.

## Respostas Rápidas
- **O que o aspose tasks java faz?** Ele lê e manipula arquivos do Microsoft Project e dados do Project Online programaticamente.  
- **Preciso de licença para experimentar?** Um teste gratuito está disponível; uma licença é necessária para uso em produção.  
- **Quais credenciais são necessárias?** Domínio do SharePoint, nome de usuário e senha (ou token Azure AD).  
- **Posso listar projetos do SharePoint?** Sim – use `ProjectServerManager.getProjectList()` para recuperá‑los.  
- **Como obtenho a contagem de recursos?** Carregue cada objeto `Project` e chame `project.getResources().size()`.

## O que é aspose tasks java?
**aspose tasks java** é uma biblioteca voltada para desenvolvedores que abstrai as complexidades dos formatos de arquivo do Microsoft Project e das APIs REST do Project Server. Ela permite ler, criar e modificar dados de projetos diretamente a partir de aplicações Java, facilitando a integração com sistemas corporativos existentes.

## Por que usar aspose tasks java para ler MS Project Online?
- **Sem manipulação manual de HTTP** – a biblioteca cuida da autenticação e das chamadas REST.  
- **Segurança de tipos forte** – trabalhe com `Project`, `ProjectInfo` e outros POJOs em vez de JSON bruto.  
- **Multiplataforma** – funciona em qualquer ambiente compatível com JVM.  
- **Conjunto de recursos rico** – além da leitura, você também pode atualizar tarefas, recursos e cronogramas.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – JDK 8 ou superior instalado.  
2. **Aspose.Tasks for Java library** – faça o download em [here](https://releases.aspose.com/tasks/java/).  
3. **Conta Microsoft Project Online** – com permissões para ler projetos.  
4. **Endereço do domínio SharePoint** – onde sua instância do Project Online está hospedada.  
5. **Nome de usuário e senha** – ou credenciais Azure AD adequadas para autenticação.

## Importar Pacotes
Primeiro, importe as classes essenciais do Aspose.Tasks que usaremos ao longo do tutorial:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## Etapa 1: Definir domínio SharePoint, nome de usuário e senha
Defina os detalhes de conexão para o seu ambiente Project Online. Substitua os valores de espaço reservado pelas suas próprias credenciais.

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## Etapa 2: Autenticar com credenciais do Project Server
Crie um objeto `ProjectServerCredentials` e inicialize um `ProjectServerManager`. Esse gerenciador cuidará de todas as chamadas subsequentes ao Project Online.

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## Etapa 3: Recuperar lista de projetos e exibir informações
Use o gerenciador para **recuperar a lista de projetos** (listar projetos do SharePoint) e imprimir detalhes básicos como nome, data de criação e data da última gravação.

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## Etapa 4: Carregar projetos individuais e exibir contagem de recursos
Para cada projeto retornado na etapa anterior, carregue o objeto `Project` completo e exiba a **contagem de recursos**.

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## Problemas Comuns e Soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| **Falha na autenticação** | Domínio, nome de usuário ou senha incorretos. | Verifique as credenciais e assegure que a conta possui permissões de leitura no Project Online. |
| **SSLHandshakeException** | Tempo de execução Java não possui a versão TLS necessária. | Atualize o JDK para a versão mais recente ou habilite TLS 1.2+. |
| **`reader.getProjectList()` retorna vazio** | A conta não tem acesso a nenhum projeto. | Verifique as permissões no Project Online ou use uma conta de administrador. |
| **Projetos grandes causam OutOfMemoryError** | Carregar muitos projetos simultaneamente consome memória. | Carregue os projetos um de cada vez e libere referências após o uso. |

## Perguntas Frequentes
### Q: Posso usar aspose tasks java para modificar dados do MS Project Online?
A: Sim, o Aspose.Tasks oferece amplas capacidades tanto para leitura **quanto** para modificação de dados do Project Online programaticamente.

### Q: O Aspose.Tasks suporta outros formatos de arquivos de gerenciamento de projetos?
A: Absolutamente. Ele suporta MPP, XML, Primavera e muitos outros, garantindo compatibilidade em diversos ecossistemas de projetos.

### Q: Existe uma versão de teste gratuita do Aspose.Tasks para Java?
A: Sim, você pode obter um teste gratuito em [here](https://releases.aspose.com/) para explorar os recursos e funcionalidades do Aspose.Tasks.

### Q: Onde encontro documentação completa do Aspose.Tasks para Java?
A: Consulte a documentação detalhada [here](https://reference.aspose.com/tasks/java/) para orientações abrangentes sobre como utilizar o Aspose.Tasks em seus projetos Java.

### Q: Quais opções de suporte estão disponíveis para o Aspose.Tasks para Java?
A: Se encontrar problemas ou tiver dúvidas, pode buscar assistência no fórum da comunidade Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2025-12-15  
**Testado com:** Aspose.Tasks for Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}