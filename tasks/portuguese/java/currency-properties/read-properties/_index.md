---
date: 2025-12-04
description: Aprenda como ler propriedades de moeda em Java a partir de arquivos MS
  Project usando Aspose.Tasks para Java. Siga este guia passo a passo para extrair
  o código da moeda, símbolo, casas decimais e posição programaticamente.
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: Ler Propriedades de Moeda Java com Projetos Aspose.Tasks
url: /pt/java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler Propriedades de Moeda Java com Aspose.Tasks Projects

## Introdução
Neste tutorial você **read currency properties Java** dos arquivos Microsoft Project usando a API Aspose.Tasks for Java. Aspose.Tasks permite trabalhar com arquivos .mpp sem precisar ter o Microsoft Project instalado, tornando‑a ideal para relatórios automatizados, migração de dados ou integração em aplicações corporativas baseadas em Java. Ao final deste guia, você será capaz de extrair o código da moeda, o símbolo, o número de casas decimais e a posição do símbolo diretamente de um arquivo de projeto.

## Respostas Rápidas
- **O que significa “read currency properties java”?** Refere‑se à recuperação de metadados relacionados à moeda (código, símbolo, dígitos, posição) de um arquivo MS Project usando código Java.  
- **Preciso de uma licença para experimentar?** Um teste gratuito do Aspose.Tasks está disponível; uma licença comercial é necessária para uso em produção.  
- **Qual versão do JDK é necessária?** Java 8 ou superior.  
- **Posso modificar as configurações de moeda após lê‑las?** Sim, o Aspose.Tasks permite operações de leitura e gravação nas propriedades de moeda.  
- **Isso é compatível com todas as versões .mpp?** A API suporta arquivos criados com Microsoft Project 2003‑2021.

## O que é read currency properties java?
Ler propriedades de moeda em Java significa acessar as configurações ao nível do projeto que definem como os valores monetários são exibidos em um arquivo Microsoft Project. Essas configurações incluem o código ISO da moeda (por exemplo, **USD**), o símbolo (**$**), o número de casas decimais e se o símbolo aparece antes ou depois do valor.

## Por que ler read currency properties java com Aspose.Tasks?
- **Nenhuma instalação do Microsoft Project necessária** – a API funciona em qualquer plataforma que suporte Java.  
- **Extração rápida e em‑processo** – ideal para processamento em lote de um grande número de arquivos de projeto.  
- **Controle total** – você pode combinar os valores obtidos com relatórios personalizados ou integrá‑los a sistemas ERP.  
- **Suporte entre versões** – funciona com arquivos .mpp do Project 2003 até a versão mais recente de 2021.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – Java 8 ou mais recente instalado e configurado no seu `PATH`.  
2. **Aspose.Tasks for Java JAR** – faça o download da biblioteca mais recente a partir de [here](https://releases.aspose.com/tasks/java/) e adicione‑a ao classpath do seu projeto.  

## Importar Pacotes
Comece importando o namespace Aspose.Tasks necessário para a manipulação de projetos:

```java
import com.aspose.tasks.*;
```

## Etapa 1: Configurar o Diretório do Seu Projeto
Defina a pasta que contém o arquivo `.mpp` que você deseja analisar. Manter o caminho em uma variável torna o código reutilizável:

```java
String dataDir = "Your Data Directory";
```

*Substitua `"Your Data Directory"` pelo caminho absoluto ou relativo da pasta onde `project.mpp` está localizado.*

## Etapa 2: Criar uma Instância do Leitor de Projeto
Carregue o arquivo Microsoft Project em um objeto `Project`. Esse objeto dá acesso a todas as propriedades do projeto, incluindo as configurações de moeda:

```java
Project project = new Project(dataDir + "project.mpp");
```

*Se o seu arquivo tiver um nome diferente, altere `"project.mpp"` conforme necessário.*

## Etapa 3: Exibir Propriedades de Moeda
Agora recupere cada atributo de moeda usando a enumeração `Prj` e imprima os resultados no console. A API retorna objetos que podem ser convertidos em strings para exibição:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**O que será exibido:**  
- **Currency Code** – código ISO‑4217 como `USD`, `EUR`, `JPY`.  
- **Currency Digits** – normalmente `2` para a maioria das moedas, `0` para o iene japonês.  
- **Currency Symbol** – o caractere exibido nos relatórios (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` para **antes** do valor, `1` para **depois**.

## Etapa 4: Conclusão do Processamento
Sinalize que a extração terminou com sucesso. Esta mensagem simples é útil quando o código é executado como parte de um job em lote maior:

```java
System.out.println("Process completed Successfully");
```

## Problemas Comuns e Soluções

| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **FileNotFoundException** | O caminho `dataDir` está incorreto ou o nome do arquivo está escrito errado. | Verifique a string do diretório e assegure que o arquivo `.mpp` exista no local especificado. |
| **NullPointerException on `project.get(...)`** | O arquivo de projeto não contém informações de moeda (improvável) ou a chave da propriedade está errada. | Use `project.contains(Prj.CURRENCY_CODE)` para verificar a existência antes de ler. |
| **LicenseException** | Execução sem uma licença válida do Aspose.Tasks em ambiente de produção. | Aplique um arquivo de licença usando `License license = new License(); license.setLicense("Aspose.Tasks.lic");` antes de criar o objeto `Project`. |

## Perguntas Frequentes

**Q: O Aspose.Tasks é compatível com todas as versões do Microsoft Project?**  
A: O Aspose.Tasks suporta arquivos .mpp gerados pelo Microsoft Project 2003‑2021, abrangendo tanto formatos antigos quanto os mais recentes.

**Q: Posso modificar as propriedades de moeda usando o Aspose.Tasks?**  
A: Sim, você pode ler e gravar as configurações de moeda. Use `project.set(Prj.CURRENCY_CODE, "EUR");` e então salve o projeto.

**Q: O Aspose.Tasks é adequado para uso comercial?**  
A: Absolutamente. É uma biblioteca comercial; você pode adquirir uma licença [here](https://purchase.aspose.com/buy).

**Q: O Aspose.Tasks oferece um teste gratuito?**  
A: Sim, um teste totalmente funcional está disponível em [here](https://releases.aspose.com/).

**Q: Onde posso buscar ajuda ou suporte para o Aspose.Tasks?**  
A: O fórum oficial do Aspose.Tasks é o melhor lugar para assistência – visite‑o [here](https://forum.aspose.com/c/tasks/15).

## Conclusão
Agora você aprendeu como **read currency properties java** de um arquivo MS Project usando o Aspose.Tasks for Java. Essa capacidade permite incorporar metadados de moeda em relatórios personalizados, análises financeiras ou pipelines de integração sem depender do próprio Microsoft Project. Sinta‑se à vontade para experimentar a modificação das propriedades ou combinar esses dados com outros atributos do projeto para criar soluções mais robustas.

---

**Last Updated:** 2025-12-04  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}