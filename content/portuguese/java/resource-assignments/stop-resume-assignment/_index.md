---
title: Parar e retomar atribuições de recursos em Aspose.Tasks
linktitle: Parar e retomar atribuições de recursos em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como gerenciar atribuições de recursos de forma eficaz em Aspose.Tasks for Java com este tutorial passo a passo.
type: docs
weight: 23
url: /pt/java/resource-assignments/stop-resume-assignment/
---
## Introdução
Neste tutorial, aprenderemos como interromper e retomar atribuições de recursos usando Aspose.Tasks for Java. Aspose.Tasks é uma API Java poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project sem precisar do Microsoft Project instalado em seus sistemas. Dividiremos o processo em etapas gerenciáveis para facilitar o acompanhamento.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Java Development Kit (JDK) instalado em seu sistema.
-  Biblioteca Aspose.Tasks para Java baixada. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
- Compreensão básica de programação Java.
## Importar pacotes
Primeiro, vamos importar os pacotes necessários para o nosso projeto Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Etapa 1: carregar o arquivo do projeto
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Data Directory";
// Carregue o arquivo do projeto
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 Nesta etapa, carregamos o arquivo do projeto em um`Project` objeto usando o caminho do arquivo.
## Etapa 2: iterar por meio de atribuições de recursos
```java
// Definir data mínima
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterar através de atribuições de recursos
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Aqui, definimos uma data mínima e começamos a iterar cada atribuição de recurso no projeto.
## Etapa 3: verificar as datas de parada e retomada
```java
    // Verifique a data de parada
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Verifique a data do currículo
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Nesta etapa verificamos se as datas de parada e retomada de cada atribuição de recurso são anteriores à data mínima. Se forem, imprimimos “NA”, caso contrário, imprimimos as respectivas datas.
## Conclusão
Neste tutorial, aprendemos como interromper e retomar atribuições de recursos em Aspose.Tasks for Java. Seguindo as etapas fornecidas, você pode implementar facilmente essa funcionalidade em seus projetos Java.

## Perguntas frequentes
### Posso usar o Aspose.Tasks sem o Microsoft Project instalado?
Sim, Aspose.Tasks permite que você trabalhe com arquivos do Microsoft Project sem precisar do Microsoft Project instalado em seu sistema.
### Onde posso encontrar mais documentação?
 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/tasks/java/).
### Existe um teste gratuito disponível?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).
### Como posso obter suporte se encontrar algum problema?
Você pode obter apoio da comunidade[aqui](https://forum.aspose.com/c/tasks/15).
### Posso comprar uma licença temporária?
 Sim, você pode comprar uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).