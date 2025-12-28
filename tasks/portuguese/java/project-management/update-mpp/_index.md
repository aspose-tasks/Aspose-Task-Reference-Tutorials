---
date: 2025-12-28
description: Aprenda a adicionar tarefas e atualizar arquivos MPP usando Aspose.Tasks
  para Java, uma biblioteca de gerenciamento de projetos em Java. Siga nosso guia
  passo a passo para criar tarefas em MPP e salvar o projeto como MPP.
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como adicionar tarefa e atualizar arquivo MPP no Aspose.Tasks
url: /pt/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Tarefa e Atualizar Arquivo MPP no Aspose.Tasks

## Introdução
Neste tutorial, mostraremos **como adicionar tarefa** e atualizar um arquivo MPP usando Aspose.Tasks for Java, uma **biblioteca de gerenciamento de projetos java** líder. Seja construindo um agendador personalizado ou precisando modificar planos de projeto existentes programaticamente, este guia o conduzirá por cada etapa — desde o carregamento do arquivo até a gravação das alterações como um novo documento MPP.

## Respostas Rápidas
- **O que significa “how to add task” neste contexto?** Refere‑se a criar programaticamente uma nova tarefa dentro de um arquivo Microsoft Project (MPP) existente.  
- **Qual biblioteca lida com a operação?** Aspose.Tasks for Java, uma robusta biblioteca de gerenciamento de projetos java.  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Posso salvar o resultado como MPP?** Sim — use `project.save(..., SaveFileFormat.Mpp)` para **save project as mpp**.  
- **Qual versão do Java é necessária?** Java 8 ou superior.

## O que é “how to add task” em um arquivo MPP?
Adicionar uma tarefa significa inserir um novo item de trabalho na hierarquia do projeto, definir suas datas de início/fim e persistir a alteração de volta ao arquivo MPP. Aspose.Tasks abstrai os detalhes de baixo nível do formato de arquivo, permitindo que você se concentre na lógica de negócios.

## Por que usar Aspose.Tasks for Java?
- **Compatibilidade total** com arquivos Microsoft Project 2007‑2021.  
- **Nenhuma instalação de COM ou Office** necessária — API Java pura.  
- **Conjunto rico de recursos**: vinculação de tarefas, alocação de recursos, campos personalizados e mais.  
- **Alto desempenho** para arquivos de projeto grandes, tornando‑a ideal para automação do lado do servidor.

## Prerequisites
1. **Ambiente de Desenvolvimento Java** – JDK 8+ instalado e configurado.  
2. **Aspose.Tasks for Java** – Baixe da [download page](https://releases.aspose.com/tasks/java/).  
3. **Conhecimento básico de Java** – Familiaridade com classes, objetos e manipulação de datas.  

## Importar Pacotes
Primeiro, importe as classes necessárias. Isso lhe dá acesso à manipulação de projetos, propriedades de tarefas e manipulação de datas.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Etapa 1: Definir Diretório de Dados
```java
String dataDir = "Your Data Directory";
```
Substitua `"Your Data Directory"` pelo caminho absoluto onde seu arquivo MPP de origem está localizado.

## Etapa 2: Ler Projeto Existente
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
O construtor `Project` carrega **SampleMSP2010.mpp**, fornecendo um modelo de objeto manipulável.

## Etapa 3: Criar uma Nova Tarefa (how to add task)
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Esta linha **creates task in mpp** ao adicionar um filho chamado *Task1* à tarefa raiz.

## Etapa 4: Definir Datas de Início e Término
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Aqui definimos o cronograma para a tarefa recém‑adicionada. Ajuste as datas para corresponder à linha do tempo do seu projeto.

## Etapa 5: Salvar o Projeto (save project as mpp)
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
O projeto atualizado, agora contendo a nova tarefa, é persistido como **AfterLinking.mpp**.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| **Arquivo não encontrado** | Verifique se `dataDir` termina com um separador de caminho (`/` ou `\\`) e se o nome do arquivo está correto. |
| **Datas incorretas** | Lembre‑se de que os meses do `Calendar` são baseados em zero; `Calendar.JULY` corresponde a julho. |
| **Exceção de licença** | Instale uma licença válida do Aspose.Tasks antes de chamar qualquer API para evitar marcas d'água de avaliação. |

## Perguntas Frequentes
### Q: O Aspose.Tasks for Java pode lidar com estruturas de projeto complexas?
A: Sim, o Aspose.Tasks for Java fornece recursos robustos para lidar com estruturas de projeto complexas de forma eficiente.  
### Q: Existe uma versão de teste gratuita disponível para Aspose.Tasks for Java?
A: Sim, você pode baixar uma versão de teste gratuita do [website](https://releases.aspose.com/).  
### Q: O Aspose.Tasks for Java suporta diferentes versões de arquivos Microsoft Project?
A: Absolutamente, o Aspose.Tasks for Java suporta várias versões de arquivos Microsoft Project, incluindo formatos MPP, MPT e XML.  
### Q: Posso obter licenças temporárias para Aspose.Tasks for Java?
A: Sim, licenças temporárias estão disponíveis para fins de teste. Você pode obtê‑las na [temporary license page](https://purchase.aspose.com/temporary-license/).  
### Q: Onde posso buscar ajuda ou suporte sobre Aspose.Tasks for Java?
A: Você pode visitar o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvidas.

## Perguntas Frequentes
**Q: Como adiciono várias tarefas de uma vez?**  
A: Percorra uma coleção de nomes de tarefas e repita o bloco “create task” dentro do loop.

**Q: Posso definir campos personalizados para a nova tarefa?**  
A: Sim — use `task.set(Tsk.CUSTOM_FIELD_x, value)` onde *x* é o índice do campo.

**Q: É possível copiar uma tarefa existente como modelo?**  
A: Clone a tarefa fonte (`Task cloned = sourceTask.clone();`) e então adicione‑a ao pai desejado.

**Q: E se eu precisar atualizar uma tarefa existente em vez de adicionar uma nova?**  
A: Recupere a tarefa por ID (`Task existing = project.getRootTask().getChildren().getById(id);`) e modifique suas propriedades.

**Q: O Aspose.Tasks suporta salvar em outros formatos como PDF ou PNG?**  
A: Sim — use `project.save("output.pdf", SaveFileFormat.Pdf);` ou `SaveFileFormat.Png` para representações visuais.

---

**Última atualização:** 2025-12-28  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}