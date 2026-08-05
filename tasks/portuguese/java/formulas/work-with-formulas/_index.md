---
date: 2026-02-13
description: Aprenda a calcular dias entre datas, criar um projeto de teste e adicionar
  um campo personalizado ao manipular arquivos do Microsoft Project usando Aspose.Tasks
  para Java.
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Calcule dias entre datas com Aspose.Tasks para Java
url: /pt/java/formulas/work-with-formulas/
weight: 11
---

.DEADLINE, Calendar, etc not translated.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calcular dias entre datas com Aspose.Tasks para Java

## Introdução
Neste tutorial você **calculará dias entre datas** criando um projeto de teste, adicionando um campo personalizado e usando fórmulas do Microsoft Project através da biblioteca Aspose.Tasks para Java. Seja para gerar cronogramas, calcular prazos ou automatizar relatórios, o Aspose.Tasks permite manipular dados do Project programaticamente sem necessidade de instalação desktop. Ao final do guia você terá um exemplo executável que define um atributo estendido, define um prazo para uma tarefa e salva o projeto como um arquivo MPP.

## Respostas rápidas
- **O que o tutorial cobre?** Criação de um projeto de teste, adição de um campo personalizado, definição de um atributo estendido e definição de prazo para uma tarefa com uma fórmula para **calcular dias entre datas**.  
- **Qual biblioteca é necessária?** Aspose.Tasks for Java (versão mais recente).  
- **Preciso de uma licença?** Um teste gratuito funciona para desenvolvimento; uma licença é necessária para produção.  
- **Qual IDE posso usar?** Qualquer IDE Java (IntelliJ IDEA, Eclipse, VS Code) que suporte JDK 8+.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para copiar o código e executá‑lo.

## O que é “calcular dias entre datas” no Aspose.Tasks?
Calcular dias entre datas significa usar uma fórmula do Project que subtrai um campo de data (por exemplo, **Finish**) de outro (por exemplo, **Deadline**) e devolve a diferença numérica em dias. Isso é útil para monitorar atrasos de cronograma, medir tempo de reserva ou gerar relatórios personalizados.

## Por que usar Aspose.Tasks para calcular dias entre datas?
- **Cobertura total da API** – acesso a todas as propriedades de Project, Task e Resource.  
- **Nenhuma instalação do Office necessária** – funciona em servidores, pipelines CI e contêineres Docker.  
- **Multiplataforma** – executa em Windows, Linux e macOS com o mesmo código Java.  
- **Engine de fórmulas robusta** – permite definir cálculos como `[Deadline] - [Finish]` diretamente dentro do arquivo de projeto.

## Como definir prazo para uma tarefa
Definir um prazo é o primeiro passo antes de calcular o intervalo. O prazo é armazenado no campo `Tsk.DEADLINE` de uma tarefa e pode ser atribuído usando uma instância `java.util.Calendar`.

## Como definir atributo estendido
Um atributo estendido é o campo personalizado que armazenará o resultado da sua fórmula. Você o define uma única vez, atribui um alias para legibilidade e, em seguida, anexa uma fórmula que realiza a subtração de datas.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

- **Java Development Kit (JDK) 8+** – faça o download no site da Oracle ou adote o OpenJDK.  
- **Aspose.Tasks for Java** – obtenha o JAR mais recente na [página de download do Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) e adicione‑o ao classpath do seu projeto ou às dependências Maven/Gradle.

## Importar Pacotes
Primeiro, importe as classes que precisaremos:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Guia passo a passo

### Etapa 1: Criar um Projeto de Teste com um Campo Personalizado
Começamos **criando um projeto de teste** e adicionando um campo personalizado que mais tarde armazenará o resultado da nossa fórmula.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Dica profissional:* `CreateTestProjectWithCustomField()` é um método auxiliar que cria um cronograma mínimo e registra um atributo estendido pronto para a atribuição da fórmula.

### Etapa 2: Definir um Atributo Estendido (Adicionar Campo Personalizado)
Em seguida, **definimos um atributo estendido** – essencialmente o campo personalizado – e lhe damos um alias amigável. É aqui que adicionamos a lógica do campo personalizado.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** torna o campo legível no Project.  
- **Formula** calcula o número de dias entre a data *Finish* de uma tarefa e sua *Deadline* – o núcleo de *calcular dias entre datas*.

### Etapa 3: Definir Prazo para uma Tarefa (Adicionar Tarefa de Prazo e Definir Prazo da Tarefa)
Agora **adicionamos dados de tarefa de prazo** definindo a propriedade *Deadline* em uma tarefa específica.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- A instância `Calendar` define o momento exato do prazo.  
- `set(Tsk.DEADLINE, …)` **define o prazo da tarefa** para a tarefa escolhida.

### Etapa 4: Salvar o Projeto (Manipular Arquivo Microsoft Project)
Por fim, **manipulamos o Microsoft Project** persistindo as alterações em um arquivo MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Você pode abrir `SaveFile.mpp` no Microsoft Project para ver o campo personalizado, o resultado da fórmula e o prazo refletidos no cronograma.

## Problemas comuns e soluções
| Problema | Solução |
|----------|----------|
| **Formula not evaluating** | Certifique‑se de que a string `Formula` do atributo usa nomes de campo corretos (por exemplo, `[Deadline]`, `[Finish]`). |
| **Task not found** | Verifique se o ID da tarefa (`1` no exemplo) existe; use `project.getRootTask().getChildren().size()` para depurar. |
| **License exception** | Aplique uma licença válida do Aspose.Tasks antes de chamar qualquer método da API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, o Aspose.Tasks fornece APIs para .NET, Java e outras plataformas, permitindo que você **manipule arquivos Microsoft Project** na linguagem de sua escolha.

**Q: Existe um teste gratuito disponível para o Aspose.Tasks?**  
A: Absolutamente. Baixe um teste totalmente funcional na [página de download do Aspose.Tasks](https://releases.aspose.com/).

**Q: Onde posso encontrar documentação detalhada para o Aspose.Tasks?**  
A: A documentação oficial está hospedada em [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).

**Q: Como posso obter suporte para o Aspose.Tasks?**  
A: Visite o [forum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para fazer perguntas e compartilhar experiências com a comunidade.

**Q: Preciso de uma licença temporária para avaliação?**  
A: Uma licença temporária está disponível para testes de curto prazo; você pode solicitar uma [aqui](https://purchase.aspose.com/temporary-license/).

---

**Última atualização:** 2026-02-13  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}