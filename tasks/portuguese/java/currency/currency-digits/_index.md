---
date: 2025-12-05
description: Aprenda a lidar com dígitos de moeda no MS Project de forma eficiente
  usando Aspose.Tasks para Java. Guia passo a passo que cobre o tratamento de arquivos
  de projeto Java e como carregar arquivos MPP.
language: pt
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Manipular dígitos de moeda do MS Project com Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipular dígitos de moeda do MS Project com Aspose.Tasks

## Introdução
Neste tutorial abrangente você descobrirá **como trabalhar com valores de moeda do MS Project** usando a biblioteca Aspose.Tasks para Java. Seja construindo uma ferramenta de relatórios, um utilitário de migração ou simplesmente precisando ler as configurações de moeda de um **arquivo de projeto Java**, este guia o conduz passo a passo — desde o carregamento de um arquivo *.mpp* até a extração dos dígitos de moeda. Ao final, você estará confortável em manipular dados de moeda do MS Project em suas próprias aplicações.

## Respostas Rápidas
- **Qual biblioteca lê arquivos MS Project?** Aspose.Tasks for Java.  
- **Quantas linhas de código são necessárias para obter os dígitos de moeda?** Apenas três linhas concisas após o projeto ser carregado.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior (qualquer JDK que execute Aspose.Tasks).  
- **Posso recuperar outras propriedades do Project?** Sim – Aspose.Tasks expõe um conjunto completo de campos do Project (por exemplo, data de início, taxas de custo, etc.).

## O que é moeda do MS Project?
`ms project currency` refere‑se à precisão numérica (número de casas decimais) que o Microsoft Project usa ao exibir valores monetários. Ela é armazenada no arquivo do Project como a propriedade **CURRENCY_DIGITS** e determina se os valores aparecem como números inteiros, com uma casa decimal, duas casas decimais, etc.

## Por que usar Aspose.Tasks para manipular moeda do MS Project?
- **Nenhuma instalação do Microsoft Project necessária** – trabalhe diretamente com arquivos *.mpp* em qualquer plataforma que suporte Java.  
- **Segurança de tipos forte** – a API devolve valores tipados, reduzindo erros de análise.  
- **Desempenho otimizado** – carregue projetos grandes rapidamente e extraia apenas os campos que você precisa.  
- **Multiplataforma** – execute em Windows, Linux ou macOS sem modificações.

## Pré‑requisitos
Antes de começar, certifique‑se de que você possui o seguinte:

1. **Ambiente de Desenvolvimento Java** – JDK 8 ou mais recente instalado e configurado.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente no site oficial: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Conhecimento básico de Java** – você deve estar confortável criando um projeto Java, adicionando bibliotecas externas e executando um método `main`.  

## Importar Pacotes
Primeiro, importe as classes que precisaremos.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: Definir Diretório de Dados
Especifique a pasta que contém seu **arquivo de projeto Java** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Substitua `"Your Data Directory"` pelo caminho absoluto ou relativo onde `project.mpp` está localizado.

## Etapa 2: Carregar o Arquivo MPP  
Agora veremos **como carregar arquivos mpp** usando Aspose.Tasks.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Certifique‑se de que o nome do arquivo corresponde exatamente; caso contrário, será lançada uma `IOException`.

## Etapa 3: Recuperar Dígitos de Moeda  
Com o projeto carregado, extrair os dígitos de **moeda do MS Project** é uma única linha:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
A chamada devolve um `Integer` representando o número de casas decimais (por exemplo, `2` para centavos). O valor é impresso no console, mas você também pode armazená‑lo em uma variável para processamento posterior.

## Problemas Comuns e Dicas
- **Arquivo não encontrado** – verifique novamente o caminho `dataDir` e assegure‑se de que o nome do arquivo está correto, incluindo a extensão `.mpp`.  
- **Versão de arquivo não suportada** – Aspose.Tasks suporta formatos Project 2000‑2024; arquivos mais antigos ou corrompidos podem precisar de conversão.  
- **Licença não definida** – durante o desenvolvimento uma avaliação funciona, mas para produção você deve aplicar uma licença válida para evitar marcas d’água de avaliação.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com outros atributos do Project além dos dígitos de moeda?**  
A: Sim, o Aspose.Tasks oferece uma ampla gama de funcionalidades para manipular vários aspectos dos arquivos Project, como tarefas, recursos e campos personalizados.

**Q: O Aspose.Tasks é adequado para aplicações de nível empresarial?**  
A: Absolutamente, o Aspose.Tasks foi projetado para atender às demandas de projetos de nível empresarial, oferecendo alto desempenho e escalabilidade.

**Q: O Aspose.Tasks suporta desenvolvimento multiplataforma?**  
A: Sim, você pode usar o Aspose.Tasks for Java em qualquer plataforma que suporte o Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Sim, você pode baixar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso obter suporte para o Aspose.Tasks?**  
A: Você pode encontrar suporte no [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2025-12-05  
**Testado com:** Aspose.Tasks for Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}