---
date: 2026-02-10
description: Aprenda como recuperar códigos de moeda de arquivos MS Project usando
  Aspose.Tasks para Java – a maneira rápida de obter o código de moeda que os desenvolvedores
  Java precisam.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como recuperar a moeda do MS Project com Aspose.Tasks
url: /pt/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recuperar a Moeda do MS Project com Aspise.Tasks

## Introdução
Bem‑vindo! Neste tutorial você descobrirá **how to retrieve currency** códigos de moeda de um arquivo MS Project usando a API Java do Aspose.Tasks. Seja gerando relatórios financeiros multi‑moeda, consolidando projetos de diferentes regiões ou simplesmente precisando dos símbolos monetários corretos para processamento posterior, este guia o conduzirá por cada etapa — desde a configuração do ambiente até a extração programática do código da moeda. Ao final, você estará confortável em ler arquivos MS Project e usar a chamada **get currency code java** para obter o identificador ISO da moeda.

## Respostas Rápidas
- **O que a API faz?** Ela lê arquivos MS Project e expõe propriedades como o código da moeda.  
- **Qual linguagem é usada?** Java, via a biblioteca Aspose.Tasks for Java.  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso recuperar o código em uma linha?** Sim—`prj.get(Prj.CURRENCY_CODE)` retorna a string do código da moeda.  
- **É compatível com todas as versões do Project?** Aspose.Tasks suporta tanto formatos antigos (MPP) quanto novos (XML, XER).

## O que é **read ms project file**?
Ler um arquivo MS Project significa abrir programaticamente um documento de projeto *.mpp* (ou outro suportado) e acessar suas estruturas de dados — tarefas, recursos, calendários e configurações financeiras — sem interação manual com o Microsoft Project.

## Por que usar Aspose.Tasks para **read msproject** files?
- **Suporte total a formatos** – funciona com arquivos do Project 98 até as versões mais recentes do Office.  
- **Nenhum COM ou instalação do Office necessária** – puro Java, perfeito para automação no lado do servidor.  
- **API rica** – fornece acesso direto a propriedades como `Prj.CURRENCY_CODE`, permitindo que você **how to retrieve currency** informações instantaneamente.  
- **Desempenho** – análise leve, ideal para processamento em lote de muitos projetos.

## Pré-requisitos
Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

### Java Development Kit (JDK) Instalado
Certifique‑se de que um JDK recente está disponível na sua máquina. Você pode baixar e instalar a versão mais recente do JDK a partir de [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Biblioteca Aspose.Tasks for Java
Baixe e configure a biblioteca Aspose.Tasks for Java. Documentação detalhada e os binários mais recentes estão disponíveis [here](https://reference.aspose.com/tasks/java/).

## Importar Pacotes
Para começar, vamos importar os pacotes necessários no seu projeto Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Guia passo a passo

### Etapa 1: Configurar o Diretório de Dados
Defina a pasta que contém seu arquivo *.mpp*. Ajuste o caminho para corresponder ao seu ambiente.
```java
String dataDir = "Your Data Directory";
```

### Etapa 2: Carregar o Arquivo do Projeto
Crie uma instância `Project` carregando o arquivo MS Project. Este é o ponto onde você **read msproject** os dados na memória.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Etapa 3: Recuperar o Código da Moeda
Agora que o projeto está carregado, você pode **how to retrieve currency** informações com uma única chamada. Isso demonstra o uso de **get currency code java**.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
A saída será o código ISO de três letras da moeda (por exemplo, `USD`, `EUR`, `GBP`) que o projeto está configurado para usar.

### Etapa 4: Como Recuperar o Código da Moeda em Java (Contexto Adicional)
Se precisar armazenar o valor para uso posterior, basta atribuí‑lo a uma variável:

*Nenhum bloco de código extra é necessário* – apenas mantenha a string retornada por `prj.get(Prj.CURRENCY_CODE)` e passe‑a para qualquer serviço financeiro, motor de relatórios ou componente de UI.

### Etapa 5: (Opcional) Usar o Código da Moeda
Você pode querer aplicar o código recuperado em outro lugar — como formatar valores de custo em um relatório personalizado ou enviá‑lo para uma API financeira. Cenários típicos incluem:

- **Geração de relatórios** – prefixar o código nas colunas de custo (`USD 1,200`).  
- **Integração de API** – enviar o código ISO para gateways de pagamento que exigem um identificador de moeda.  
- **Consolidação de dados** – agrupar vários projetos por moeda para análise de portfólio.

## Problemas Comuns e Soluções
| Problema | Razão | Solução |
|----------|-------|---------|
| **Saída nula** | O arquivo do projeto não define uma moeda (padrão é vazio). | Defina a moeda no Microsoft Project ou atribua‑a via `prj.set(Prj.CURRENCY_CODE, "USD");` antes de ler. |
| **Arquivo não encontrado** | Caminho `dataDir` incorreto. | Verifique o caminho e assegure‑se de que o nome do arquivo corresponde exatamente, incluindo sensibilidade a maiúsculas/minúsculas. |
| **Versão de arquivo não suportada** | Arquivo *.mpp* muito antigo ou corrompido. | Use a versão mais recente do Aspose.Tasks ou converta o arquivo para um formato mais recente no Microsoft Project primeiro. |

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com estruturas de projeto complexas?**  
A: Sim, a API pode ler e manipular hierarquias de tarefas de múltiplos níveis, pools de recursos e campos personalizados sem problemas.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos MS Project?**  
A: Absolutamente. Ele suporta MPP, XML, XER e outros formatos em várias versões do Microsoft Project.

**Q: O Aspose.Tasks fornece documentação e suporte?**  
A: Documentação abrangente, exemplos de código e suporte dedicado estão disponíveis no site da Aspose.

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Um teste gratuito é oferecido para que você possa avaliar todos os recursos, incluindo a leitura de códigos de moeda.

**Q: Onde posso obter licenças temporárias para o Aspose.Tasks?**  
A: Licenças temporárias podem ser obtidas no [website](https://purchase.aspose.com/temporary-license/) para avaliação de curto prazo.

**Última atualização:** 2026-02-10  
**Testado com:** Aspose.Tasks for Java (versão mais recente)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}