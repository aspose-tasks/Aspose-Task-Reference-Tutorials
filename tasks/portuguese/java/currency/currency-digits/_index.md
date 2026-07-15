---
date: 2026-02-10
description: Aprenda como obter valores de moeda, ler arquivos do MS Project e converter
  arquivos de projeto Java usando Aspose.Tasks. Guia passo a passo para extrair dígitos
  de moeda.
linktitle: How to Get Currency from MS Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como obter a moeda do MS Project usando Aspose.Tasks
url: /pt/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Obter a Moeda do MS Project usando Aspose.Tasks

## Introdução
Se você está se perguntando **como obter a moeda** de um arquivo Microsoft Project, chegou ao lugar certo. Neste tutorial abrangente, você descobrirá **como trabalhar com valores de ms project currency** usando a biblioteca Aspose.Tasks para Java. Seja você quem está construindo uma ferramenta de relatórios, um utilitário de migração ou simplesmente precisa ler as configurações de moeda de um **arquivo de projeto java**, este guia o conduzirá por cada passo — desde o carregamento de um arquivo *.mpp* até a extração dos dígitos da moeda. Ao final, você estará confortável manipulando dados de ms project currency em suas próprias aplicações.

## Respostas Rápidas
- **Qual biblioteca lê arquivos MS Project?** Aspose.Tasks for Java.  
- **Quantas linhas de código são necessárias para obter os dígitos da moeda?** Apenas três linhas concisas após o projeto ser carregado.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior (qualquer JDK que execute Aspose.Tasks).  
- **Posso recuperar outras propriedades do Project?** Sim – Aspose.Tasks expõe um conjunto completo de campos do Project (por exemplo, data de início, taxas de custo, etc.).

## O que é ms project currency?
`ms project currency` refere‑se à precisão numérica (número de casas decimais) que o Microsoft Project usa ao exibir valores monetários. Ela é armazenada no arquivo Project como a propriedade **CURRENCY_DIGITS** e determina se os valores aparecem como números inteiros, com uma casa decimal, duas casas decimais, etc.

## Por que usar Aspose.Tasks para manipular ms project currency?
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

## Etapa 1: Definir o Diretório de Dados
Especifique a pasta que contém seu **arquivo de projeto java** (`*.mpp`).  
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

## Etapa 3: Recuperar os Dígitos da Moeda  
Com o projeto carregado, extrair os dígitos da **moeda do ms project** é uma única linha:  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
A chamada retorna um `Integer` representando o número de casas decimais (por exemplo, `2` para centavos). O valor é impresso no console, mas você também pode armazená‑lo em uma variável para processamento adicional.

## Problemas Comuns & Dicas
- **Arquivo não encontrado** – verifique novamente o caminho `dataDir` e assegure‑se de que o nome do arquivo está correto, incluindo a extensão `.mpp`.  
- **Versão de arquivo não suportada** – Aspose.Tasks suporta formatos Project 2000‑2024; arquivos mais antigos ou corrompidos podem precisar de conversão.  
- **Licença não definida** – durante o desenvolvimento uma avaliação funciona, mas para produção você deve aplicar uma licença válida para evitar marcas d'água de avaliação.

## Perguntas Frequentes

**Q: O Aspose.Tasks pode lidar com outros atributos do Project além dos dígitos da moeda?**  
A: Sim, Aspose.Tasks oferece uma ampla gama de funcionalidades para manipular vários aspectos de arquivos Project, como tarefas, recursos e campos personalizados.

**Q: O Aspose.Tasks é adequado para aplicações de nível empresarial?**  
A: Absolutamente, Aspose.Tasks foi projetado para atender às exigências de projetos corporativos, oferecendo alto desempenho e escalabilidade.

**Q: O Aspose.Tasks suporta desenvolvimento multiplataforma?**  
A: Sim, você pode usar Aspose.Tasks for Java em qualquer plataforma que suporte o Java Runtime Environment (Windows, Linux, macOS).

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Sim, você pode baixar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Onde posso obter suporte para Aspose.Tasks?**  
A: Você pode encontrar suporte no [fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Conclusão
Agora você sabe **como obter a moeda** de um arquivo MS Project usando Aspose.Tasks para Java. O processo é simples: carregue o projeto, chame `project.get(Prj.CURRENCY_DIGITS)` e use o resultado em sua aplicação. Sinta‑se à vontade para explorar outras propriedades do projeto com o mesmo padrão e integrar essa lógica em soluções maiores de relatórios ou migração.

---

**Última atualização:** 2026-02-10  
**Testado com:** Aspose.Tasks for Java (última versão no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}