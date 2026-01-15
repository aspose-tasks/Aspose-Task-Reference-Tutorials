---
date: 2026-01-15
description: Aprenda como adicionar recurso ao projeto, atualizar os dados do recurso
  e salvar o projeto como MPP usando Aspose.Tasks para Java.
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Adicionar Recurso ao Projeto Usando Aspose.Tasks para Java
url: /pt/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Recurso ao Projeto Usando Aspose.Tasks para Java

## Introdução
Neste tutorial prático, você descobrirá **como adicionar recurso ao projeto** programaticamente com a API Aspose.Tasks Java. Vamos percorrer o carregamento de um arquivo XML do MS Project existente, inserir um novo recurso, atualizar suas propriedades e, finalmente, **salvar o projeto como MPP**. Ao final, você terá um padrão claro e repetível que pode ser inserido em qualquer ferramenta de relatório ou automação baseada em Java.

## Respostas Rápidas
- **O que significa “add resource to project”?** Cria uma nova entrada de recurso (pessoas, equipamentos, material) dentro de um arquivo Microsoft Project.  
- **Qual biblioteca lida com isso?** Aspose.Tasks for Java – não é necessário ter o Microsoft Project instalado.  
- **Preciso de uma licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso converter XML para MPP?** Sim – carregue o arquivo XML e **salve o projeto como MPP** usando `project.save(...)`.  
- **Qual versão do Java é necessária?** Java 6 ou posterior (Java 8+ recomendado).

## O que é “add resource to project”?
Adicionar um recurso a um projeto significa inserir uma nova linha na tabela de Recursos de um arquivo MS Project. Essa linha armazena detalhes como nome, taxas de custo, grupo e campos personalizados que as tarefas podem referenciar posteriormente.

## Por que usar Aspose.Tasks para Java?
- **Sem dependência do Microsoft Project** – funciona em qualquer SO ou servidor CI.  
- **Fidelidade total** – mantém todos os recursos nativos do Project ao converter entre formatos.  
- **API rica** – permite ler, gravar e manipular tarefas, recursos, calendários e muito mais.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. Java Development Kit (JDK) 8 ou mais recente instalado.  
2. Biblioteca Aspose.Tasks for Java – faça o download a partir de [here](https://releases.aspose.com/tasks/java/).  
3. Familiaridade básica com a sintaxe Java e configuração de projetos Maven/Gradle.

## Importar Pacotes
Adicione as classes necessárias do Aspose.Tasks ao seu arquivo fonte Java:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Etapa 1: Configurar seu Diretório de Dados
Defina onde os arquivos XML de origem e os arquivos MPP resultantes ficarão:

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Especificar Arquivos de Entrada e Saída
Aponte para o arquivo XML que você deseja converter (**convert XML to MPP**) e o arquivo MPP de destino que conterá o novo recurso:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Etapa 3: Carregar o Projeto
Crie um objeto `Project` a partir da fonte XML:

```java
Project project = new Project(file);
```

## Etapa 4: Adicionar um Recurso e Definir Atributos
É aqui que **add resource to project** e configuramos suas taxas e grupo:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*Dica profissional:* Você pode repetir a chamada `add` dentro de um loop para **update multiple resources** em uma única execução.

## Etapa 5: Salvar o Projeto
Finalmente, **save project as MPP** para persistir as alterações:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusão
Você acabou de aprender **como adicionar recurso ao projeto**, atualizar suas propriedades e **salvar o projeto como MPP** usando Aspose.Tasks para Java. Essa abordagem é ideal para pipelines de relatórios automatizados, importações em massa de recursos ou qualquer cenário em que seja necessário manipular arquivos MS Project sem a aplicação desktop.

## Perguntas Frequentes

**Q1: Posso atualizar vários recursos no mesmo projeto usando Aspose.Tasks para Java?**  
A: Sim, itere sobre `project.getResources()` ou chame `add` repetidamente, definindo os campos de cada recurso conforme necessário.

**Q2: O Aspose.Tasks suporta outros formatos de arquivo além do MS Project?**  
A: Absolutamente – XML, MPP, MPX, Primavera e muito mais são todos suportados.

**Q3: O Aspose.Tasks é compatível com diferentes versões do Java?**  
A: A biblioteca funciona com Java 6 e posterior; Java 8+ é fortemente recomendado para melhor desempenho.

**Q4: Posso realizar outras operações em arquivos MS Project com Aspose.Tasks?**  
A: Sim, você pode ler/gravar tarefas, calendários, atribuições, campos personalizados e até gerar relatórios.

**Q5: Onde posso encontrar ajuda ou suporte adicional para Aspose.Tasks?**  
A: Visite o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para assistência da comunidade e suporte oficial.

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}