---
title: Atributos de tarefa estendidos em Aspose.Tasks
linktitle: Atributos de tarefa estendidos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Explore atributos de tarefa estendidos em Aspose.Tasks for Java. Guia passo a passo, perguntas frequentes e suporte. Otimize seu gerenciamento de projetos hoje!
weight: 16
url: /pt/java/task-properties/extended-task-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Atributos de tarefa estendidos em Aspose.Tasks

## Introdução
Bem-vindo ao nosso guia completo sobre como aproveitar atributos de tarefa estendidos em Aspose.Tasks for Java. Aspose.Tasks é uma biblioteca Java poderosa que permite trabalhar perfeitamente com documentos do Microsoft Project. Neste tutorial, nos aprofundaremos nos atributos de tarefa estendidos e demonstraremos como você pode utilizá-los para aprimorar seus recursos de gerenciamento de projetos.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico de programação Java.
- Instalado o Java Development Kit (JDK) em sua máquina.
- Um ambiente de desenvolvimento integrado (IDE), como IntelliJ ou Eclipse.
## Importar pacotes
Comece importando os pacotes necessários para iniciar seu projeto Aspose.Tasks:
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
Agora, vamos dividir o exemplo em várias etapas para guiá-lo durante o processo:
## Etapa 1: Acessando Tarefas e Atributos Estendidos
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## Etapa 2: recuperando o ID do campo e o GUID do valor
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## Etapa 3: Lidando com Diferentes Tipos de Atributos
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
Repita essas etapas para cada tarefa do seu projeto para explorar e manipular atributos de tarefa estendidos.
## Conclusão
Concluindo, compreender e utilizar atributos de tarefas estendidos em Aspose.Tasks for Java pode aprimorar significativamente seus recursos de gerenciamento de projetos. Este guia fornece uma base sólida para você começar esta jornada.
## perguntas frequentes
### Posso modificar atributos de tarefas estendidas programaticamente?
Sim, você pode modificar atributos de tarefa estendidos usando Aspose.Tasks for Java. Consulte a documentação para obter instruções detalhadas.
### Existe uma versão de teste disponível?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte para Aspose.Tasks for Java?
 Para suporte, visite o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Como posso obter uma licença temporária?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar a versão completa do Aspose.Tasks for Java?
 Você pode comprar a versão completa[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
