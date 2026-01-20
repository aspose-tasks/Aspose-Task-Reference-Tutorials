---
date: 2026-01-20
description: Aprenda como obter recurso por ID e extrair dados temporais de recursos
  do MS Project usando Aspose.Tasks para Java.
linktitle: Get resource by id and read timephased data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Obter recurso por ID e ler dados timephased no Aspose.Tasks
url: /pt/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obter recurso por id e ler dados faseados em Aspose.Tasks

## Introdução
Neste tutorial, vamos guiá‑lo através de **como obter recurso por id** e ler dados faseados para recursos do MS Project usando Aspose.Tasks para Java. Seja para analisar a carga de trabalho dos recursos ou a programaticamente economiza inúmeras horas manuais.

## Respostas Rápidas
- **Qual é a classe principal para carregar um projeto?** `Project` de `com.aspose.tasks`.
- **Como localizar um recurso específico?** Use `project.getResources().getByUid(resourceId)`.
- **Posso ler tanto dados de trabalho quanto de custo?** Sim – chame `resource.getTimephasedData` com o `TimephasedDataType` apropriado.
- **Preciso de uma licença para desenvolvimento?** Uma licença de avaliação gratuita funciona para testes; uma Java é suportada?** Aspose.Tasks para Java suporta JDK 8 e versões mais recentes.

## O que é **get resource by UID é atribuído pelo Microsoft Project quando o recurso é criado e permanece constante ao longo do ciclo de vida do projeto.

## Por que orçamentoquisitos
Antes de começarmos, certifique‑se de que você possui os seguintes pré‑requisitos:

1. **Java Development Kit (JDK)** – Instale o JDK 8 ou posterior. Você pode baixá‑lo no [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) e seguir as instruções de instalação.  
2. **Aspose.Tasks for Java Library** – Baixe a biblioteca Aspose.Tasks for Java na [download page](https://releases.aspose.com/tasks/java/) e siga as instruções de instalação fornecidas na documentação.  

## Importar Pacotes
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## Etapa 1: Configurar Diretório de Dados
Primeiro, defina o diretório onde seu arquivo MS Project está localizado.

```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Ler Arquivo de Modelo MS Project
Especifique o nome do seu arquivo de modelo MS Project.

```java
String fileName = "ResourceTimephasedData.mpp";
```

## Etapa 3: Carregar o Projeto (java read project resources)
Leia o arquivo de entrada usando Aspose.Tasks e carregue‑o como um objeto `Project`.

```java
Project project = new Project(dataDir + fileName);
```

## Etapa 4: **Get resource by id**
Recupere o recurso desejado do projeto pelo seu identificador exclusivo (ID). Neste exemplo, buscamos o recurso com UID = 1.

```java
Resource resource = project.getResources().getByUid(1);
```

## Etapa 5: Imprimir Dados Faseados para Trabalho do Recurso
Imprima os dados faseados para o trabalho do recurso.

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## Etapa 6: Imprimir Dados Faseados para Custo do Recurso
Imprima os dados faseados para o custo do recurso.

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Problemas Comuns e Soluções
| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **NullPointerException ao chamar `resource.getTimephasedData`** | A data de início ou término do projeto pode estar ausente. | Certifique‑se de que o arquivo do projeto contém datas de início/fim válidas ou forneça datas explícitas. |
| **UID incorreto** | Os recursos no arquivo podem ter UIDs diferentes dos esperados. | Use `project.getResources().toList()` para enumerar os UIDs disponíveis antes de buscar. |
| **Licença ausente** | Aspose.Tasks lança uma exceção se uma licença válida não for carregada em uma compilação de produção. | Carregue seu arquivo de licença via `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` |

## Perguntas Frequentes
### O Aspose.Tasks pode lidar com outros tipos de arquivos de projeto além do Microsoft Project?
Sim, o Aspose.Tasks suporta vários formatos de arquivo, incluindo MPP, XML e CSV.

### O Aspose.Tasks é compatível com diferentes ambientes de desenvolvimento Java?
Sim, o Aspose.Tasks é compatível com todos os principais IDEs e frameworks Java.

### Posso manipular dados de projeto usando Aspose.Tasks?
Absolutamente, o Aspose.Tasks fornece APIs extensas para criar, modificar e analisar dados de projeto.

### O Aspose.Tasks é adequado para projetos de nível empresarial?
Sim, o Aspose.Tasks é amplamente usado em ambientes corporativos devido à sua confiabilidade e escalabilidade.

### Onde posso encontrar suporte se encontrar problemas ao usar o Aspose.Tasks?
Você pode visitar o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para obter assistência da comunidade e da equipe de suporte.

## Perguntas Frequentes

: SimDataType` como `TimephasedDataType.ResourceWork` junto com uma coleção `TimephasedData` que você pode agregar manualmente.

**Q: Posso export usando I/O padrão Java (`FileWriter`/`BufferedWriter`).

**Q: O Aspose.Tasks suporta a leitura de arquivos de projeto criados em versões mais recentes do MS Project?**  
A: A biblioteca é atualizada regularmente para suportar os formatos MPP mais recentes; sempre use a versão mais recente do Aspose.Tasks.

**Q: Quais considerações de desempenho existem para projetos grandes?**  
A: Carregue o projeto uma única vez, reutilize a instância `Project` e evite chamadas repetidas a `getTimephasedData` para o mesmo intervalo.

---

**Last Updated:** 2026-01-20  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}