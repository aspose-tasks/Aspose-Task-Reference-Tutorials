---
date: 2026-02-26
description: Aprenda como salvar o projeto como PDF e gerar uma planilha de tarefas
  usando Aspose.Tasks para Java. Exporte MPP para PDF rapidamente com este guia passo
  a passo.
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Salvar Projeto como PDF – Renderizar Folha de Tarefas com Aspose.Tasks para
  Java
url: /pt/java/task-properties/render-task-sheet/
weight: 27
---

 Java 24.11" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Then backtop button shortcode.

Make sure to keep all shortcodes exactly.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar Projeto como PDF – Renderizar Folha de Tarefas no Aspose.Tasks

## Introdução
Neste guia abrangente, você descobrirá como **salvar projeto como PDF** e gerar uma folha de tarefas com Aspose.Tasks para Java. Seja para exportar um arquivo MPP para PDF para revisões de partes interessadas ou simplesmente renderizar uma folha de tarefas limpa para relatórios, este tutorial o conduzirá por cada passo, explicará por que cada configuração é importante e mostrará o código exato que você precisa executar.

## Respostas Rápidas
- **O que faz “save project as pdf”?** Converte um arquivo Microsoft Project (MPP) em um documento PDF, opcionalmente formatando-o como uma folha de tarefas.  
- **Qual formato é usado para um PDF de folha de tarefas?** A opção `PresentationFormat.TaskSheet` em `PdfSaveOptions`.  
- **Preciso de uma licença para executar o código?** Uma licença temporária ou completa é necessária para produção; uma avaliação gratuita funciona para testes.  
- **Quais são os pré-requisitos principais?** Java JDK, biblioteca Aspose.Tasks para Java e um arquivo de projeto válido (ex.: *.mpp).  
- **Posso personalizar o layout do PDF?** Sim, Aspose.Tasks oferece várias propriedades `PdfSaveOptions` para estilo e configuração de página.

## O que é “save project as pdf”?
Salvar um projeto como PDF transforma os dados internos do projeto em um documento portátil e somente leitura. Isso é ideal para compartilhar cronogramas, folhas de tarefas ou relatórios de status com partes interessadas que não possuem o Microsoft Project instalado.

## Por que renderizar uma folha de tarefas?
Uma folha de tarefas apresenta cada tarefa em uma visualização tabular, mostrando IDs, nomes, datas de início/término e outros campos. Renderizá‑la para PDF garante formatação consistente em todas as plataformas e facilita a impressão ou incorporação em outros documentos.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão mais recente instalada e `java`/`javac` disponíveis no seu PATH.  
2. **Aspose.Tasks for Java** – baixe a biblioteca no site oficial [here](https://releases.aspose.com/tasks/java/).  
3. Um **arquivo de projeto** válido (`*.mpp`) que você deseja converter, por exemplo, `NewProductDev.mpp`.  

## Importar Pacotes
Primeiro, importe as classes necessárias do Aspose.Tasks. Essas importações dão acesso às opções de salvamento em PDF, formatos de apresentação e ao objeto central `Project`.

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## Guia Passo a Passo

### Etapa 1: Defina o Diretório do Documento
Defina a pasta onde o arquivo MPP de origem está localizado e onde o PDF gerado será gravado. Usar um caminho absoluto ou relativo funciona; apenas certifique‑se de que a pasta exista.

```java
String dataDir = "Your Document Directory";
```

### Etapa 2: Carregar o Arquivo de Projeto
Crie uma instância `Project` carregando o arquivo MPP existente. Esse objeto representa toda a estrutura do projeto na memória.

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### Etapa 3: Configurar Opções de Salvamento – Exportar MPP para PDF
Instancie `PdfSaveOptions` e informe ao Aspose.Tasks que você deseja que o PDF seja renderizado como uma **folha de tarefas**. Esta é a etapa chave para o caso de uso *export project pdf*.

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### Etapa 4: Salvar o Projeto como Folha de Tarefas – Salvar Projeto como PDF
Chame o método `save` no objeto `Project`, passando o nome do arquivo de destino e as opções configuradas. Esta ação **converte o arquivo MPP em um PDF** formatado como uma folha de tarefas.

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### Etapa 5: Revisar o Resultado
Navegue até o diretório que você especificou (`dataDir`). Você deverá ver `taskSheet.pdf` contendo uma lista bem formatada de todas as tarefas. Abra‑o com qualquer visualizador de PDF para verificar se a conversão foi bem‑sucedida.

## Problemas Comuns e Soluções
- **FileNotFoundException** – Certifique‑se de que `dataDir` termina com um separador de caminho (`/` ou `\\`) e que o nome do arquivo MPP está correto.  
- **LicenseException** – Se você encontrar erros de licença, aplique uma licença temporária ou comprada antes de chamar qualquer API do Aspose.Tasks.  
- **Blank PDF** – Verifique se o projeto realmente contém tarefas; um projeto vazio produzirá um PDF vazio.

## Perguntas Frequentes

**Q: O Aspose.Tasks é compatível com todas as versões do Java?**  
A: Sim, o Aspose.Tasks funciona com uma ampla gama de versões do Java. Consulte a [documentation](https://reference.aspose.com/tasks/java/) para detalhes.

**Q: Posso experimentar o Aspose.Tasks antes de comprar?**  
A: Claro! Explore a versão de avaliação gratuita [here](https://releases.aspose.com/).

**Q: Onde posso encontrar suporte para o Aspose.Tasks?**  
A: Junte‑se à comunidade Aspose.Tasks no [forum](https://forum.aspose.com/c/tasks/15) para suporte e discussões.

**Q: Como obtenho uma licença temporária para o Aspose.Tasks?**  
A: Obtenha sua licença temporária [here](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso comprar o Aspose.Tasks para Java?**  
A: Compre o Aspose.Tasks para Java [here](https://purchase.aspose.com/buy).

## Conclusão
Seguindo estas etapas, você aprendeu como **salvar projeto como PDF**, especificamente renderizando uma folha de tarefas, usando Aspose.Tasks para Java. Essa capacidade permite *exportar MPP para PDF* rapidamente, compartilhar instantâneos de projeto legíveis e integrar dados do projeto em fluxos de trabalho de relatórios mais amplos.

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}