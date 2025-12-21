---
date: 2025-12-21
description: Aprenda como salvar o projeto como modelo, exportar MPP para CSV e converter
  MPP para texto usando Aspose.Tasks para Java.
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Salvar projeto como modelo, CSV e texto com Aspose.Tasks para Java
url: /pt/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salvar Projeto como Modelo, CSV e Texto com Aspise.Tasks

## Introdução
Neste tutorial, você descobrirá **como salvar projeto como modelo** e também como exportar seus arquivos Microsoft Project (MPP) para formatos CSV e texto simples usando a biblioteca Aspose.Tasks para Java. Seja para criar um modelo de projeto reutilizável, gerar relatórios CSV para análise ou produzir extratos de texto simples para integração, estas etapas o guiarão pelo processo de forma rápida e eficiente.

## Respostas Rápidas
- **Posso exportar MPP para CSV?** Sim – use `project.save(..., SaveFileFormat.CSV)`.  
- **Como exportar texto?** Salve com `SaveFileFormat.TEXT`.  
- **O que faz “save project as template”?** Ele cria um arquivo `.mpt` que remove os valores reais e de linha de base, pronto para reutilização.  
- **Preciso de licença?** Uma versão de avaliação está disponível; uma licença comercial é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8+ é suportado.

## O que é “save project as template”?
Salvar um projeto como modelo (`.mpt`) captura a estrutura, a hierarquia de tarefas e as atribuições de recursos, ao mesmo tempo que remove as datas reais de início/fim e os dados de linha de base. Isso torna o modelo ideal para reutilizar um layout de projeto padrão em vários novos projetos.

## Por que usar Aspose.Tasks para Java?
Aspose.Tasks permite manipular arquivos Microsoft Project sem instalar o próprio Microsoft Project. Ele suporta **como exportar MPP**, **como exportar texto** e **converter MPP para CSV**, tudo a partir de código Java puro, o que é perfeito para automação no lado do servidor, pipelines de CI ou utilitários de desktop.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem:

1. Java Development Kit (JDK) 8 ou superior instalado.  
2. Biblioteca Aspose.Tasks para Java adicionada ao seu projeto. Baixe-a de [here](https://releases.aspose.com/tasks/java/).  
3. Familiaridade básica com a sintaxe Java e configuração de projetos Maven/Gradle.

## Importar Pacotes
Primeiro, importe as classes necessárias no seu arquivo fonte Java:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Salvar Projeto como CSV (Exportar MPP para CSV)
Exportar um arquivo MPP para CSV é útil para análise de dados no Excel ou em ferramentas de BI.

### Passo 1: Carregar o Projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Passo 2: Salvar como CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Salvar Projeto como Texto (Como Exportar Texto)
Se precisar de uma representação em texto simples de tarefas, recursos ou atribuições, salve o projeto como um arquivo de texto.

### Passo 1: Carregar o Projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Passo 2: Salvar como Texto
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Salvar Projeto como Modelo (Criar Modelo de Projeto Java)
Criar um modelo reutilizável remove datas reais e linhas de base, deixando um esqueleto limpo para novos projetos.

### Passo 1: Carregar o Projeto
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Passo 2: Definir Opções do Modelo
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Passo 3: Salvar como Modelo
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Problemas Comuns e Dicas
- **File Not Found:** Certifique‑se de que o caminho para `YourProject.mpp` está correto ou use um caminho absoluto.  
- **License Exceptions:** Sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar marcas d'água. Aplique sua licença cedo no código (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Large Projects:** Para arquivos MPP muito grandes, considere aumentar o tamanho do heap da JVM (`-Xmx2g`) para evitar `OutOfMemoryError`.

## Conclusão
Cobrimos **como salvar projeto como modelo**, bem como como **exportar MPP para CSV** e **converter MPP para texto** usando Aspose.Tasks para Java. Essas funcionalidades permitem automatizar o gerenciamento de dados de projetos, gerar modelos reutilizáveis e integrar informações de projetos em outros sistemas — tudo sem precisar do Microsoft Project instalado.

## Perguntas Frequentes
### Q: O Aspose.Tasks para Java pode lidar com arquivos de projeto complexos?
A: Absolutamente! Aspose.Tasks para Java pode lidar com projetos de diferentes complexidades com facilidade, oferecendo suporte abrangente aos formatos de arquivo Microsoft Project.  
### Q: Existe uma versão de avaliação disponível para Aspose.Tasks para Java?
A: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks para Java em [here](https://releases.aspose.com/).  
### Q: Onde posso encontrar suporte para Aspose.Tasks para Java?
A: Você pode visitar o [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) para qualquer assistência ou dúvidas sobre Aspose.Tasks para Java.  
### Q: Posso comprar uma licença temporária para Aspose.Tasks para Java?
A: Sim, você pode comprar uma licença temporária em [here](https://purchase.aspose.com/temporary-license/), permitindo avaliar todo o potencial da biblioteca.  
### Q: O Aspose.Tasks para Java é compatível com diferentes sistemas operacionais?
A: Sim, Aspose.Tasks para Java é compatível com vários sistemas operacionais, incluindo Windows, macOS e Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose  

---