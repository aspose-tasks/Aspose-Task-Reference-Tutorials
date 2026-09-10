---
date: 2026-09-09
description: Aprenda como mudar o currency symbol em projetos Aspose.Tasks Java, definir
  currency codes, ajustar symbols e aplicar custom formats para arquivos Microsoft
  Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Definir Currency Properties em projetos Aspose.Tasks
og_description: Como mudar o currency symbol em Aspose.Tasks usando Java. Descubra
  instruções passo a passo, pré-requisitos e dicas para personalizar o project cost
  formatting.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Como mudar o currency symbol em Aspose.Tasks – guia Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Como mudar o currency symbol em projetos Aspose.Tasks – guia Java
url: /pt/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como alterar o símbolo da moeda no Aspose.Tasks – Guia Java

## Introdução
Neste tutorial você aprenderá **como alterar o símbolo da moeda** para um arquivo Microsoft Project usando a API Aspose.Tasks Java. Seja preparando relatórios para um cliente no exterior, consolidando orçamentos em várias regiões, ou simplesmente precisando adequar aos padrões contábeis da sua empresa, ajustar o símbolo da moeda garante que todo campo relacionado a custos exiba o sinal monetário correto. O guia percorre cada passo, desde a configuração do ambiente de desenvolvimento até a persistência das alterações em um arquivo de projeto novo ou existente.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Tasks for Java.  
- **Posso alterar o símbolo da moeda?** Sim – defina `Prj.CURRENCY_SYMBOL` e escolha `CurrencySymbolPositionType`.  
- **Quais formatos de arquivo são suportados?** XML, MPP e muitos outros via `SaveFileFormat`.  
- **Preciso de uma licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença é necessária para produção.  
- **Quanto tempo leva a implementação?** Cerca de 5‑10 minutos para uma configuração básica.

## Como alterar o símbolo da moeda no Aspose.Tasks usando Java?
Carregue o projeto alvo (ou crie um novo), defina as propriedades de moeda desejadas e salve o arquivo. Toda a operação consiste em três chamadas de API: criar ou carregar um objeto `Project`, atribuir o código da moeda, símbolo e posição, e então invocar `project.save`. Essa abordagem funciona tanto para projetos novos quanto para arquivos existentes sem exigir a instalação do Microsoft Project.

## Por que usar o Aspose.Tasks para alterar a moeda?
Aspose.Tasks fornece **cobertura total da API para mais de 30 propriedades relacionadas à moeda**, permitindo definir código, símbolo, dígitos decimais e posicionamento em um único lugar. A biblioteca processa arquivos Project de centenas de páginas em menos de um segundo em hardware de servidor típico, e funciona em Windows, Linux e macOS sem dependências adicionais.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK) 8 ou superior** – a API requer pelo menos JDK 8.  
2. **Aspose.Tasks for Java** – baixe o JAR mais recente da [página de download do Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **Um IDE** – Eclipse, IntelliJ IDEA ou qualquer editor que suporte Java.  
4. **Uma pasta gravável** – onde o arquivo de projeto gerado será salvo.

## Importar pacotes
As classes a seguir dão acesso às propriedades do projeto, manipulação de arquivos e configurações de moeda.  

`Project` – representa um arquivo Microsoft Project na memória.  
`Prj` – contém constantes para todas as propriedades de nível de projeto, incluindo campos de moeda.  
`CurrencySymbolPositionType` – enumera as possíveis posições para o símbolo da moeda (antes ou depois do valor).  

Essas importações são necessárias antes que qualquer código possa manipular um projeto.

## Guia passo a passo

### Etapa 1: Definir o diretório de dados
Escolha uma pasta que contenha seus arquivos fonte e onde a saída será gravada. Certifique‑se de que o diretório exista e que seu processo Java tenha permissão de escrita.

### Etapa 2: Criar uma nova instância de projeto
A classe `Project` é o objeto de nível superior do Aspose.Tasks que representa um único arquivo Project na memória. Instanciá‑la cria um projeto em branco pronto para configuração.

### Etapa 3: Definir propriedades da moeda
Aqui você configura o código da moeda, número de dígitos decimais, o próprio símbolo e a posição do símbolo.  

- **Código da moeda** – um código ISO 4217 de três letras, como `AUD` ou `USD`.  
- **Dígitos decimais** – tipicamente 2 para a maioria das moedas.  
- **Símbolo da moeda** – o caractere ou string exibido com os valores, por exemplo, `$` ou `€`.  
- **Posição do símbolo** – `CurrencySymbolPositionType.Before` coloca o símbolo antes do número; `After` o coloca depois.  

Essas configurações afetam todo campo relacionado a custos (taxas de recursos, orçamentos de tarefas, etc.) no projeto.

> **Pro tip:** Se precisar alterar a moeda de um arquivo existente, carregue‑o com `new Project("file.mpp")` antes de aplicar as configurações acima.

### Etapa 4: Salvar o projeto atualizado
Grave o projeto de volta ao disco usando o formato desejado. O formato XML é legível por humanos, enquanto `SaveFileFormat.MPP` preserva total compatibilidade com o Microsoft Project.

### Etapa 5: Confirmar sucesso
Imprima uma mensagem curta ou registre uma entrada de log para saber que a operação foi concluída sem erros. Isso é especialmente útil em pipelines automatizados.

## Problemas comuns e soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **`NullPointerException` on `project.save`** | `dataDir` não é um caminho válido ou não tem permissão de escrita. | Certifique‑se de que o diretório exista e que seu processo Java tenha acesso de gravação. |
| **Currency symbol not showing** | A posição do símbolo está configurada incorretamente para sua localidade. | Use `CurrencySymbolPositionType.Before` se o símbolo deve preceder o valor. |
| **Project file does not open in MS Project** | Salvando em um formato antigo com configurações incompatíveis. | Salve usando `SaveFileFormat.MPP` para total compatibilidade com versões recentes do MS Project. |

## Perguntas frequentes

**Q: Posso definir múltiplas moedas em um único projeto usando Aspose.Tasks?**  
A: Sim, você pode atribuir diferentes configurações de moeda a recursos ou tarefas individuais modificando seus respectivos campos de custo após definir a moeda a nível de projeto.

**Q: O Aspose.Tasks é compatível com diferentes versões de arquivos Microsoft Project?**  
A: Absolutamente. A biblioteca suporta arquivos MPP do Project 2000 até as versões mais recentes, bem como XML e outros formatos de intercâmbio.

**Q: O Aspose.Tasks oferece suporte a formatos de moeda personalizados?**  
A: Sim, você pode definir símbolos personalizados, dígitos decimais e posicionamento para atender a qualquer exigência regional, e essas configurações são persistidas no arquivo salvo.

**Q: Posso integrar o Aspose.Tasks com outros frameworks Java?**  
A: Certamente. A API é pura Java, funcionando perfeitamente com Spring, Hibernate, Maven, Gradle e outros ecossistemas.

**Q: Onde posso encontrar ajuda ou exemplos adicionais?**  
A: Visite o [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para assistência da comunidade, ou consulte a documentação oficial para referências detalhadas da API.

## Conclusão
Agora você sabe **como alterar o símbolo da moeda** em projetos Aspose.Tasks usando Java, como definir o código da moeda, ajustar dígitos decimais e aplicar um símbolo personalizado. Esses recursos permitem gerar relatórios de custos específicos por localidade, alinhar orçamentos de projetos aos padrões contábeis regionais e manter seus arquivos Microsoft Project consistentes em equipes globais.

---

**Última atualização:** 2026-09-09  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Tutoriais relacionados

- [java project properties – Extract currency symbol from MPP using Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Read Currency Properties Java with Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Manage Currency Codes Java with Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}