---
date: 2026-01-10
description: Aprenda como interromper a atribuição, gerenciar atribuições de recursos
  e visualizar um exemplo de atribuição de recurso no Aspose.Tasks para Java com este
  tutorial passo a passo.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como interromper a atribuição e retomar as atribuições de recursos no Aspose.Tasks
url: /pt/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como interromper a atribuição e retomar atribuições de recursos no Aspose.Tasks

## Introdução
Neste tutorial, **você descobrirá como interromper uma atribuição** e retomá‑la posteriormente usando o Aspose.Tasks para Java. Aspose.Tasks é uma poderosa API Java que permite ler formatos de arquivos de projeto Java, manipular dados do Microsoft Project e gerenciar atribuições de recursos sem precisar do Microsoft Project instalado. Vamos percorrer cada passo, explicar por que cada linha é importante e oferecer dicas práticas que você pode aplicar a projetos do mundo real.

## Respostas Rápidas
- **O que significa “interromper a atribuição”?** Marca uma atribuição de recurso como temporariamente inativa a partir de uma data de parada específica.  
- **Posso retomar a mesma atribuição mais tarde?** Sim, definindo uma data de retomada na mesma atribuição.  
- **Preciso do Microsoft Project para usar esta API?** Não, o Aspose.Tasks funciona independentemente do Microsoft Project.  
- **Qual versão do Java é necessária?** Java 8 ou superior é recomendada.  
- **Onde posso baixar a biblioteca?** Na página oficial de download do Aspose.Tasks Java.

## O que é “interromper atribuição” no contexto do Aspose.Tasks?
Interromper uma atribuição indica ao agendador que ignore o trabalho alocado a um recurso após a **data de parada** até a **data de retomada** (se houver). Isso é útil para lidar com férias, indisponibilidade de equipamentos ou qualquer período em que um recurso não deva ser considerado ativo.

## Por que usar o Aspose.Tasks para gerenciar atribuições de recursos?
- **Não é necessário o Microsoft Project** – trabalhe diretamente com arquivos .mpp.  
- **Controle total sobre datas** – você pode verificar programaticamente a data de parada, a data de retomada e ajustá‑las.  
- **Multiplataforma** – execute em qualquer SO que suporte Java.  
- **API rica** – fornece um *exemplo de atribuição de recurso* que você pode estender para relatórios personalizados.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

- Java Development Kit (JDK) instalado no seu sistema.  
- Biblioteca Aspose.Tasks para Java baixada. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).  
- Compreensão básica de programação Java.  

## Importar Pacotes
Primeiro, vamos importar os pacotes necessários para o nosso projeto Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Etapa 1: Carregar o Arquivo de Projeto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Aqui nós **lêmos o formato de arquivo de projeto Java** (`.mpp`) e criamos um objeto `Project` que nos dá acesso a todos os dados do projeto, incluindo as atribuições de recursos.

## Etapa 2: Iterar pelas Atribuições de Recursos
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Definimos uma **data mínima** para filtrar datas fictícias e então iteramos por cada atribuição. Este é o padrão típico de *exemplo de atribuição de recurso* usado quando você precisa inspecionar ou modificar atribuições.

## Etapa 3: Verificar Datas de Parada e Retomada
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

Neste bloco verificamos a **data de parada** e a **data de retomada** para cada atribuição. Se a data for anterior à nossa `minDate`, tratamos como não definida (`"NA"`); caso contrário, exibimos a data real. Essa lógica é essencial para **gerenciar atribuições de recursos** corretamente.

## Problemas Comuns e Soluções
- **Datas nulas** – `ra.get(Asn.STOP)` pode retornar `null`. Proteja‑se adicionando uma verificação de nulo antes de chamar `.before(minDate)`.  
- **Caminho de arquivo incorreto** – Certifique‑se de que `dataDir` termina com um separador de caminho (`/` ou `\\`) adequado ao seu SO.  
- **Incompatibilidade de versão** – Use a versão mais recente do Aspose.Tasks para Java para evitar valores de enum ausentes.

## Perguntas Frequentes
### Posso usar o Aspose.Tasks sem o Microsoft Project instalado?
Sim, o Aspose.Tasks permite trabalhar com arquivos do Microsoft Project sem precisar do Microsoft Project instalado no seu sistema.

### Onde posso encontrar mais documentação?
Você pode encontrar documentação detalhada [aqui](https://reference.aspose.com/tasks/java/).

### Existe uma versão de avaliação gratuita disponível?
Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter suporte se encontrar algum problema?
Você pode obter suporte da comunidade [aqui](https://forum.aspose.com/c/tasks/15).

### Posso comprar uma licença temporária?
Sim, você pode comprar uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

## Perguntas Frequentes

**Q: Como eu programaticamente defino uma data de parada para uma atribuição?**  
A: Use `ra.set(Asn.STOP, yourDateObject);` onde `yourDateObject` é um `java.util.Date`.

**Q: O que acontece se a data de retomada for anterior à data de parada?**  
A: A API não impõe ordem cronológica; porém, o agendador tratará a atribuição como ativa somente após a data mais tardia das duas, portanto você deve validar as datas manualmente.

**Q: Posso filtrar atribuições para incluir apenas aquelas que têm uma data de parada definida?**  
A: Sim, itere por `prj.getResourceAssignments()` e verifique `ra.get(Asn.STOP) != null`.

**Q: É possível remover uma data de parada uma vez definida?**  
A: Defina a data de parada como `null` usando `ra.set(Asn.STOP, null);` e então salve o projeto.

**Q: O Aspose.Tasks suporta outros campos relacionados a datas, como início, término ou início real?**  
A: Absolutamente. O enum `Asn` fornece constantes para todos os campos de atribuição, como `Asn.START`, `Asn.FINISH`, etc.

## Conclusão
Seguindo estas etapas, você agora sabe **como interromper uma atribuição**, inspecionar as datas de parada/retomada e retomar a atribuição quando necessário. Essa capacidade permite que você **gerencie atribuições de recursos** de forma mais precisa, especialmente em cenários como férias de recursos ou indisponibilidade de equipamentos. Sinta‑se à vontade para estender o exemplo para atualizar datas, gerar relatórios ou integrar com sua própria lógica de agendamento.

---

**Última atualização:** 2026-01-10  
**Testado com:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}