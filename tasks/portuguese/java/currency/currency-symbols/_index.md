---
date: 2026-02-10
description: Aprenda como extrair e atualizar propriedades de projetos Java, como
  o símbolo da moeda, usando o Aspose.Tasks para Java. Altere a moeda do projeto e
  recupere o símbolo da moeda facilmente.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: propriedades do projeto java – Extrair símbolo de moeda de MPP usando Aspose.Tasks
  para Java
url: /pt/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair símbolo de moeda mpp usando Aspose.Tasks para Java

## Introdução
Neste tutorial você aprenderá a trabalhar com **java project properties** — especificamente como extrair o símbolo de moeda de um arquivo Microsoft Project (MPP) e como **change currency symbol java** ou **retrieve currency symbol java** usando a biblioteca Aspose.Tasks. Seja construindo uma ferramenta de relatórios, integrando dados do Project a um sistema financeiro, ou simplesmente precisando exibir o símbolo de moeda correto na sua UI, dominar esta tarefa pequena mas essencial tornará suas aplicações Java mais robustas e amigáveis ao usuário.

## Respostas Rápidas
- **O que significa “extract currency symbol mpp”?** Significa ler o símbolo de moeda armazenado em um arquivo MPP (Microsoft Project).  
- **Qual biblioteca lida com isso?** Aspose.Tasks for Java fornece uma API simples para a tarefa.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva?** Com o código abaixo, você pode obter o símbolo em menos de um minuto.  
- **Posso também alterar o símbolo?** Sim – você pode definir um novo valor usando a mesma propriedade `Prj.CURRENCY_SYMBOL`.

## O que é “extract currency symbol mpp”?
O Microsoft Project armazena o símbolo de moeda (por exemplo, $, €, £) no cabeçalho do arquivo de projeto. A operação **extract currency symbol mpp** lê esse valor para que você possa exibi-lo ou manipulá-lo programaticamente.

## Por que atualizar o símbolo de moeda nas propriedades do projeto java?
Os projetos frequentemente abrangem várias regiões. Poder **change project currency** ou **update currency symbol** em tempo de execução permite adaptar relatórios, faturas ou painéis ao mercado local sem recriar todo o arquivo de projeto. Essa flexibilidade é uma parte central de gerenciar java project properties de forma eficaz.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks for Java** – baixe o JAR mais recente da [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Um arquivo **project.mpp** válido colocado em uma pasta que você possa referenciar no seu código.

## Importar Pacotes
Primeiro, importe as classes que precisaremos para trabalhar com arquivos Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Etapa 1: Definir o Diretório de Dados
Informe à aplicação onde seu arquivo *.mpp* está localizado.

```java
String dataDir = "Your Data Directory";
```

> **Dica profissional:** Use `System.getProperty("user.dir")` para construir um caminho absoluto que funcione em qualquer máquina.

## Etapa 2: Carregar o Arquivo MS Project
Crie um objeto `Project` que representa o arquivo MPP na memória.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 3: Recuperar (e opcionalmente alterar) o Símbolo de Moeda
Agora nós **retrieve currency symbol java** lendo a propriedade `Prj.CURRENCY_SYMBOL`. Você também pode **change currency symbol java** (ou **change project currency**) atribuindo uma nova string à mesma propriedade.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

A chamada `System.out.println` imprime o símbolo (por exemplo, `$`) no console, confirmando que a extração foi bem‑sucedida.

## Problemas Comuns & Como Corrigi‑los
| Sintoma | Causa Provável | Solução |
|---------|----------------|----------|
| `NullPointerException` on `project.get(...)` | Caminho de arquivo errado ou arquivo não encontrado | Verifique `dataDir` e o nome do arquivo; use `new File(dataDir).exists()` para depurar |
| Símbolo inesperado (por exemplo, `?`) | Projeto criado com uma localidade não‑padrão | Certifique-se de que o arquivo MPP de origem realmente define um símbolo de moeda; você pode definir um programaticamente como mostrado acima |
| Erro de licença | Usando a avaliação sem um arquivo de licença válido | Carregue sua licença com `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de criar o objeto `Project` |

## Perguntas Frequentes

**Q: Posso manipular outros atributos do projeto além de símbolos de moeda usando Aspose.Tasks?**  
A: Sim, Aspose.Tasks permite editar tarefas, recursos, atribuições, calendários e muitas outras propriedades do projeto.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos MS Project?**  
A: Absolutamente. Ele suporta formatos MPP, MPT e XML do Project 98 até as versões mais recentes.

**Q: O Aspose.Tasks oferece documentação e suporte para desenvolvedores?**  
A: Documentação completa da API, exemplos de código e um fórum de suporte dedicado estão disponíveis no site do Aspose.Tasks.

**Q: Posso experimentar o Aspose.Tasks antes de comprá‑lo?**  
A: Sim – uma avaliação totalmente funcional pode ser baixada do [Aspose website](https://purchase.aspose.com/buy).

**Q: Como posso obter uma licença temporária para o Aspose.Tasks?**  
A: Licenças temporárias são fornecidas na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

---

**Última atualização:** 2026-02-10  
**Testado com:** Aspose.Tasks for Java 24.12 (mais recente na época da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}