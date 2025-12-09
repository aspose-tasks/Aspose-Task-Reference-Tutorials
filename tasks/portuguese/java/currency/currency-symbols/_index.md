---
date: 2025-12-05
description: Aprenda como extrair o símbolo de moeda mpp e alterar o símbolo de moeda
  java com Aspose.Tasks para Java. Recupere o símbolo de moeda java rapidamente para
  gerenciamento de projetos.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Extrair símbolo de moeda mpp usando Aspose.Tasks para Java
url: /pt/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrair símbolo de moeda mpp usando Aspose.Tasks para Java

## Introdução
Neste tutorial você **extrairá o símbolo de moeda mpp** de um arquivo Microsoft Project e descobrirá como **alterar o símbolo de moeda java** ou **recuperar o símbolo de moeda java** usando a biblioteca Aspose.Tasks. Seja construindo uma ferramenta de relatórios, integrando dados do Project a um sistema financeiro ou simplesmente precisando exibir o símbolo de moeda correto na sua UI, dominar esta tarefa pequena porém essencial tornará suas aplicações Java mais robustas e amigáveis.

## Respostas rápidas
- **O que significa “extract currency symbol mpp”?** Significa ler o símbolo de moeda armazenado em um arquivo MPP (Microsoft Project).  
- **Qual biblioteca trata disso?** Aspose.Tasks para Java fornece uma API simples para a tarefa.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Quanto tempo leva?** Com o código abaixo, você obtém o símbolo em menos de um minuto.  
- **Posso também mudar o símbolo?** Sim – você pode definir um novo valor usando a mesma propriedade `Prj.CURRENCY_SYMBOL`.

## O que é “extract currency symbol mpp”?
O Microsoft Project armazena o símbolo de moeda (por exemplo, $, €, £) no cabeçalho do arquivo de projeto. A operação **extract currency symbol mpp** lê esse valor para que você possa exibi‑lo ou manipulá‑lo programaticamente.

## Por que mudar o símbolo de moeda java?
Projetos frequentemente abrangem várias regiões. Poder **change currency symbol java** em tempo de execução permite adaptar relatórios, faturas ou painéis ao mercado local sem recriar todo o arquivo de projeto.

## Pré‑requisitos
Antes de prosseguir, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks para Java** – baixe o JAR mais recente na [página de download do Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Um arquivo **project.mpp** válido colocado em uma pasta que você possa referenciar a partir do seu código.

## Importar pacotes
Primeiro, importe as classes que usaremos para trabalhar com arquivos Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Etapa 1: Definir o diretório de dados
Informe à aplicação onde seu arquivo *.mpp* está localizado.

```java
String dataDir = "Your Data Directory";
```

> **Dica:** Use `System.getProperty("user.dir")` para construir um caminho absoluto que funcione em qualquer máquina.

## Etapa 2: Carregar o arquivo MS Project
Crie um objeto `Project` que representa o arquivo MPP na memória.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Etapa 3: Recuperar (e opcionalmente mudar) o símbolo de moeda
Agora nós **retrieve currency symbol java** lendo a propriedade `Prj.CURRENCY_SYMBOL`. Você também pode **change currency symbol java** atribuindo uma nova string à mesma propriedade.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

A chamada `System.out.println` imprime o símbolo (por exemplo, `$`) no console, confirmando que a extração foi bem‑sucedida.

## Problemas comuns e como corrigi‑los
| Sintoma | Causa provável | Solução |
|---------|----------------|----------|
| `NullPointerException` em `project.get(...)` | Caminho do arquivo errado ou arquivo não encontrado | Verifique `dataDir` e o nome do arquivo; use `new File(dataDir).exists()` para depurar |
| Símbolo inesperado (ex.: `?`) | Projeto criado com localidade não padrão | Garanta que o arquivo MPP de origem realmente define um símbolo de moeda; você pode definir um programaticamente como mostrado acima |
| Erro de licença | Uso da avaliação sem um arquivo de licença válido | Carregue sua licença com `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` antes de criar o objeto `Project` |

## Perguntas frequentes

**P: Posso manipular outros atributos do projeto além dos símbolos de moeda usando Aspose.Tasks?**  
R: Sim, Aspose.Tasks permite editar tarefas, recursos, atribuições, calendários e muitas outras propriedades do projeto.

**P: O Aspose.Tasks é compatível com diferentes versões de arquivos MS Project?**  
R: Absolutamente. Ele suporta formatos MPP, MPT e XML do Project 98 até as versões mais recentes.

**P: O Aspose.Tasks oferece documentação e suporte para desenvolvedores?**  
R: Documentação completa da API, exemplos de código e um fórum de suporte dedicado estão disponíveis no site do Aspose.Tasks.

**P: Posso experimentar o Aspose.Tasks antes de comprá‑lo?**  
R: Sim – um trial totalmente funcional pode ser baixado no [site da Aspose](https://purchase.aspose.com/buy).

**P: Como posso obter uma licença temporária para o Aspose.Tasks?**  
R: Licenças temporárias são fornecidas na [página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

---

**Última atualização:** 2025-12-05  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}