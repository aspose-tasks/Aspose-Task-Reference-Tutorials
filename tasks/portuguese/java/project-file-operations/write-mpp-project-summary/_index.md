---
date: 2026-03-29
description: Aprenda como definir palavras‑chave e definir a data de criação em um
  projeto MPP usando Aspose.Tasks para Java. Guia passo a passo com exemplos de código.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como definir palavras‑chave no resumo de projeto MPP com Aspose.Tasks
url: /pt/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Definir Palavras‑chave no Resumo do Projeto MPP com Aspose.Tasks

## Introdução
Neste tutorial você descobrirá **como definir palavras‑chave** e outras informações de resumo para um arquivo de projeto MPP usando Aspose.Tasks for Java. Seja para incorporar detalhes do autor, números de revisão ou uma data de criação personalizada, este guia orienta passo a passo, com código pronto‑para‑executar. Ao final, você será capaz de definir palavras‑chave, definir a data de criação java e recuperar os dados do arquivo.

## Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.Tasks for Java  
- **Objetivo principal?** Definir palavras‑chave, informações do autor e data de criação em um arquivo MPP  
- **Quantos passos de código?** Três blocos de código simples (inicializar, salvar, ler)  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção  
- **Versão Java suportada?** Java 8 ou superior  

## O que é “como definir palavras‑chave” em um arquivo MPP?
Palavras‑chave são campos de metadados armazenados dentro de um arquivo Microsoft Project (MPP). Elas ajudam a categorizar projetos, permitem buscas rápidas e fornecem informações contextuais para ferramentas subsequentes. Aspose.Tasks expõe a propriedade `Prj.KEYWORDS`, tornando simples escrever ou atualizar esse valor programaticamente.

## Por que usar Aspose.Tasks for Java para definir palavras‑chave e data de criação?
* **Compatibilidade total com .MPP** – funciona com todos os formatos Project 2007‑2023.  
* **Nenhuma instalação de COM ou Office necessária** – Java puro, perfeito para ambientes de servidor.  
* **API rica** – além de palavras‑chave, você pode definir autor, revisão, comentários e datas em uma única chamada.  
* **Desempenho otimizado** – leitura/escrita rápida mesmo para arquivos de projeto grandes.

## Pré‑requisitos
1. **Java Development Kit (JDK)** – JDK 8 ou mais recente instalado.  
2. **Aspose.Tasks for Java** – faça o download do JAR mais recente a partir de [aqui](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans ou qualquer editor que preferir.

## Importar Pacotes
Primeiro, importe as classes necessárias. Essas importações dão acesso ao objeto `Project`, à enumeração `Prj` para campos de resumo e ao enum `SaveFileFormat` para salvar.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Etapa 1: Configurar o Projeto e Definir Informações de Resumo
Crie uma instância `Project`, então use o método `set` para gravar os metadados desejados. Observe como definimos **as palavras‑chave** e **a data de criação java** usando um objeto `Calendar`.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## Etapa 2: Salvar Informações de Resumo do Projeto
Depois de preencher os campos, persista as alterações. Aqui salvamos o projeto como XML para fácil inspeção, mas você também pode salvar novamente como MPP.

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## Etapa 3: Ler Informações de Resumo do Projeto
Para verificar se os metadados foram gravados corretamente, recarregue o arquivo e leia cada propriedade. Esta etapa demonstra que **como definir palavras‑chave** realmente funciona de ponta a ponta.

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **NullPointerException em `project.get(Prj.CREATION_DATE)`** | O calendário nunca foi definido antes de salvar. | Certifique‑se de chamar `project.set(Prj.CREATION_DATE, cal.getTime())` antes de `save()`. |
| **Palavras‑chave não aparecem na interface do Microsoft Project** | O arquivo foi salvo como XML e aberto diretamente no Project. | Salve novamente como MPP (`SaveFileFormat.MPP`) ou abra o XML via *Import* no Project. |
| **Valores de data deslocados pelo fuso horário** | O `Date` do Java inclui informação de fuso horário. | Use `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))` se precisar de datas em UTC. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Tasks for Java pode ser integrado perfeitamente com outras bibliotecas Java para aprimorar suas capacidades de gerenciamento de projetos.

**Q: Existe uma versão de avaliação disponível para Aspose.Tasks for Java?**  
A: Sim, você pode baixar uma versão de avaliação gratuita a partir de [aqui](https://releases.aspose.com/).

**Q: Com que frequência o Aspose.Tasks for Java é atualizado?**  
A: Aspose.Tasks for Java é atualizado regularmente para garantir compatibilidade com as versões mais recentes do Java e dos arquivos Microsoft Project.

**Q: Posso personalizar ainda mais as informações de resumo do projeto?**  
A: Absolutamente, Aspose.Tasks for Java fornece opções extensas para personalizar as informações de resumo do projeto de acordo com seus requisitos específicos.

**Q: Onde posso obter suporte para Aspose.Tasks for Java?**  
A: Você pode obter suporte no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

---

**Última atualização:** 2026-03-29  
**Testado com:** Aspose.Tasks for Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}