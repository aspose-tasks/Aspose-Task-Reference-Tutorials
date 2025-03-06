---
title: Atualizar arquivo MPP em Aspose.Tasks
linktitle: Atualizar arquivo MPP em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como atualizar arquivos MPP perfeitamente usando Aspose.Tasks for Java. Siga nosso guia passo a passo para manipulação eficiente de arquivos de projeto.
weight: 19
url: /pt/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atualizar arquivo MPP em Aspose.Tasks

## Introdução
No domínio do gerenciamento de projetos, o manuseio e atualização de arquivos de projeto é uma tarefa crucial. Aspose.Tasks for Java fornece uma solução poderosa para desenvolvedores Java manipularem arquivos do Microsoft Project perfeitamente. Neste tutorial, nos aprofundaremos na atualização de arquivos MPP usando Aspose.Tasks for Java.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter o seguinte:
1. Ambiente de Desenvolvimento Java: Certifique-se de ter o Java instalado em seu sistema.
2.  Aspose.Tasks para Java: Baixe e instale Aspose.Tasks para Java do[página de download](https://releases.aspose.com/tasks/java/).
3. Conhecimento básico de Java: É necessária familiaridade com a linguagem de programação Java para acompanhar os exemplos.

## Importar pacotes
Em primeiro lugar, você precisa importar os pacotes necessários para o seu projeto Java para utilizar as funcionalidades do Aspose.Tasks de forma eficaz.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Esta linha de código importa todas as classes e métodos essenciais da biblioteca Aspose.Tasks, permitindo que você trabalhe com arquivos do Microsoft Project sem esforço.

Agora, vamos dividir o processo de atualização de um arquivo MPP usando Aspose.Tasks for Java em etapas gerenciáveis.
## Etapa 2: definir o diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho real onde seu arquivo MPP está localizado.
## Etapa 3: leia o projeto existente
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Este código lê um arquivo de projeto MPP existente chamado`SampleMSP2010.mpp` do diretório de dados especificado.
## Etapa 4: crie uma nova tarefa
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Aqui, adicionamos uma nova tarefa chamada “Task1” à tarefa raiz do projeto.
## Etapa 5: definir datas de início e término
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Essas linhas de código definem a data de início e a data de término da tarefa recém-criada.
## Etapa 6: salve o projeto
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Finalmente, esta etapa salva o projeto atualizado com a tarefa recém-adicionada em um novo arquivo MPP denominado`AfterLinking.mpp`.

## Conclusão
Neste tutorial, exploramos como atualizar arquivos MPP usando Aspose.Tasks for Java. Seguindo o guia passo a passo, você pode manipular com eficiência arquivos do Microsoft Project em seus aplicativos Java.
## Perguntas frequentes
### P: O Aspose.Tasks for Java pode lidar com estruturas de projetos complexas?
R: Sim, Aspose.Tasks for Java fornece recursos robustos para lidar com estruturas de projetos complexos com eficiência.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks for Java?
 R: Sim, você pode baixar uma versão de avaliação gratuita no site[local na rede Internet](https://releases.aspose.com/).
### P: O Aspose.Tasks for Java oferece suporte a diferentes versões de arquivos do Microsoft Project?
R: Com certeza, Aspose.Tasks for Java oferece suporte a várias versões de arquivos do Microsoft Project, incluindo formatos MPP, MPT e XML.
### P: Posso obter licenças temporárias para Aspose.Tasks for Java?
 R: Sim, licenças temporárias estão disponíveis para fins de teste. Você pode obtê-los no[página de licença temporária](https://purchase.aspose.com/temporary-license/).
### P: Onde posso procurar ajuda ou suporte em relação ao Aspose.Tasks for Java?
 R: Você pode visitar o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvida.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
