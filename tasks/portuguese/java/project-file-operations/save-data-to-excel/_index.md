---
date: 2025-12-21
description: Aprenda como exportar MPP para Excel e converter arquivo de projeto para
  Excel usando Aspose.Tasks para Java. Passos simples para desenvolvedores Java.
linktitle: Save Data to Excel in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como Exportar MPP para Excel com Aspose.Tasks para Java
url: /pt/java/project-file-operations/save-data-to-excel/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Exportar MPP para Excel com Aspose.Tasks para Java

## Introdução
Aspose.Tasks for Java é uma biblioteca poderosa que permite **exportar MPP para Excel** de forma rápida e confiável. Neste tutorial, vamos guiá‑lo passo a passo nas etapas necessárias para converter um arquivo Microsoft Project (.mpp) em uma pasta de trabalho Excel (.xlsx). Ao final, você entenderá como **converter arquivo de projeto para Excel**, por que essa conversão é útil e como integrar o processo em qualquer aplicação Java.

## Respostas Rápidas
- **O que a API faz?** Ela lê arquivos Project e os salva diretamente como pastas de trabalho XLSX.  
- **Qual formato é produzido?** Um arquivo Excel usando a opção `SaveFileFormat.Xlsx`.  
- **Preciso de licença?** Uma versão de avaliação funciona para testes; uma licença comercial é necessária para produção.  
- **Quais são os pré‑requisitos?** JDK instalado e a biblioteca Aspose.Tasks for Java adicionada ao seu projeto.  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos para uma exportação básica.

## O que é “como exportar MPP para Excel”?
Exportar MPP para Excel significa pegar o cronograma, recursos e dados de tarefas armazenados em um arquivo Microsoft Project e gravá‑los em uma planilha Excel estruturada. Isso facilita o compartilhamento dos dados do projeto com partes interessadas que podem não ter o Project instalado.

## Por que converter arquivo MPP para XLSX?
- **Acessibilidade ampliada:** Excel é onipresente em ambientes empresariais.  
- **Relatórios simplificados:** Use tabelas dinâmicas, gráficos e fórmulas do Excel para analisar métricas do projeto.  
- **Amigável à automação:** Arquivos Excel podem ser processados por outros sistemas ou scripts sem necessidade do Project.  

## Pré‑requisitos
Antes de começar, certifique‑se de que você possui o seguinte:

1. **Java Development Kit (JDK)** – instalado e adicionado ao PATH do seu sistema.  
2. **Aspose.Tasks for Java library** – faça o download pelo [download link](https://releases.aspose.com/tasks/java/) e adicione o JAR ao classpath do seu projeto.

## Importar Pacotes
Primeiro, importe as classes que você precisará. Mantenha este bloco exatamente como mostrado – ele é necessário para que a API funcione.

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Guia Passo a Passo

### Passo 1: Definir o Caminho do Diretório de Dados
Defina a pasta onde seu arquivo `.mpp` está localizado. Substitua o placeholder pelo caminho real.

```java
String dataDir = "Your Data Directory";
```

### Passo 2: Carregar o Arquivo de Projeto
Crie uma instância `Project` carregando o arquivo `.mpp` que deseja converter. Isso lê todas as tarefas, recursos e informações de agendamento.

```java
Project project = new Project(dataDir + "project5.mpp");
```

### Passo 3: Salvar o Projeto como XLSX
Por fim, exporte o projeto carregado para uma pasta de trabalho Excel. O sinalizador `SaveFileFormat.Xlsx` indica ao Aspose.Tasks que deve gerar um arquivo `.xlsx` moderno, efetivamente **convertendo arquivo MPP para XLSX**.

```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```

## Casos de Uso Comuns
- **Relatórios executivos:** Forneça instantâneos de alto nível do projeto em Excel para a alta administração.  
- **Análise de dados:** Alimente dados de tarefas e recursos no Power Query do Excel para obter insights mais profundos.  
- **Integração:** Envie o arquivo Excel exportado para sistemas downstream que aceitam apenas entradas CSV/Excel.

## Conclusão
Neste guia demonstramos **como exportar MPP para Excel** usando Aspose.Tasks for Java. Seguindo as três etapas simples — definir o diretório de dados, carregar o arquivo de Projeto e salvá‑lo como XLSX — você pode facilmente **exportar dados do projeto para Excel** e capacitar sua equipe com relatórios flexíveis e compartilháveis.

## Perguntas Frequentes
### Posso usar Aspose.Tasks para Java para manipular dados de projeto programaticamente?
Sim, Aspose.Tasks for Java oferece recursos extensivos para manipular dados de projeto, incluindo leitura, gravação e modificação de arquivos de projeto.

### Existe uma versão de avaliação gratuita disponível para Aspose.Tasks para Java?
Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks for Java [aqui](https://releases.aspose.com/).

### Onde posso encontrar a documentação do Aspose.Tasks para Java?
Você pode encontrar a documentação do Aspose.Tasks for Java [aqui](https://reference.aspose.com/tasks/java/).

### Como obter suporte para quaisquer problemas ou dúvidas relacionadas ao Aspose.Tasks para Java?
Você pode obter suporte visitando o fórum do Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

### Posso comprar uma licença temporária para Aspose.Tasks para Java?
Sim, você pode comprar uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose