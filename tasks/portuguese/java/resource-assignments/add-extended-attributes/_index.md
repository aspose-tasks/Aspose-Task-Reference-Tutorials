---
date: 2026-01-05
description: Aprenda como definir a data de início do projeto e salvar o XML do MS
  Project usando Aspose.Tasks para Java. Guia passo a passo para desenvolvedores Java.
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Definir a data de início do projeto com Aspose.Tasks para Java
url: /pt/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Data de Início do Projeto com Aspose.Tasks para Java

## Introdução
Neste tutorial você aprenderá **como definir a data de início do projeto** em um arquivo Microsoft Project e, em seguida, **salvar o XML do MS Project** usando a biblioteca Aspose.Tasks para Java. Seja automatizando um pipeline de relatórios ou construindo uma ferramenta personalizada de gerenciamento de projetos, dominar essa tarefa economizará tempo e eliminará erros manuais.

## Respostas Rápidas
- **Qual é o método principal para definir uma data de início?** Use `project.set(Prj.START_DATE, …)`.
- **Qual formato devo usar para exportar o arquivo?** Salve como XML com `SaveFileFormat.Xml`.
- **Preciso de uma licença para esta operação?** Uma versão de avaliação funciona, mas uma licença completa remove marcas d'água.
- **Posso alterar a data de início após criar tarefas?** Sim, atualize a propriedade do projeto antes de adicionar tarefas.
- **Isso é compatível com todas as versões do MS Project?** Aspose.Tasks suporta XML, MPP e mais.

## O que é “Definir Data de Início do Projeto”?
Definir a data de início do projeto estabelece o calendário base a partir do qual todos os cálculos de agendamento de tarefas começam. É o primeiro passo para construir programaticamente um cronograma de projeto confiável.

## Por que usar Aspose.Tasks para Java?
Aspose.Tasks fornece uma API pura‑Java que funciona em qualquer plataforma sem exigir a instalação do Microsoft Project. Ela permite criar, modificar e exportar dados de projetos rapidamente, tornando‑a ideal para automação no lado do servidor.

## Pré‑requisitos
1. **Java Development Kit (JDK)** – qualquer versão recente do JDK.
2. **Aspose.Tasks para Java** – faça o download [aqui](https://releases.aspose.com/tasks/java/).
3. **IDE** – IntelliJ IDEA, Eclipse ou sua IDE Java preferida.

## Importar Pacotes
Primeiro, importe as classes necessárias:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Etapa 1: Configurar Diretório de Dados
Defina onde os arquivos gerados serão armazenados.

```java
String dataDir = "Your Data Directory";
```

### Etapa 2: Criar uma Instância de Projeto
Instancie um novo projeto vazio.

```java
Project project = new Project();
```

### Etapa 3: Definir Propriedades de Informações do Projeto
Aqui nós **definimos a data de início do projeto** e propriedades de agendamento relacionadas.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Etapa 4: Salvar XML do MS Project
Exporte o projeto configurado para um arquivo XML.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções
- **Formato de data incorreto:** Certifique‑se de usar `java.util.Calendar` e chamar `getTime()` antes de atribuir.
- **Arquivo não salvo:** Verifique se `dataDir` aponta para uma pasta existente e gravável.
- **Avisos de licença:** A versão de avaliação adiciona marcas d'água; aplique uma licença válida para removê‑las.

## Perguntas Frequentes

### Q: Posso usar Aspose.Tasks para Java para ler arquivos MS Project?  
**A:** Sim, Aspose.Tasks para Java fornece funcionalidades robustas tanto para leitura quanto para gravação de arquivos MS Project.

### Q: O Aspose.Tasks para Java é compatível com diferentes versões do MS Project?  
**A:** Absolutamente, Aspose.Tasks para Java suporta vários formatos do MS Project, garantindo ampla compatibilidade.

### Q: Existem limitações na versão de avaliação do Aspose.Tasks para Java?  
**A:** A versão de avaliação permite explorar a biblioteca, mas adiciona marcas d'água aos arquivos de saída.

### Q: Como posso obter suporte para Aspose.Tasks para Java?  
**A:** Você pode buscar assistência no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

### Q: Posso comprar uma licença temporária para Aspose.Tasks para Java?  
**A:** Sim, licenças temporárias estão disponíveis para uso de curto prazo. Obtenha uma [aqui](https://purchase.aspose.com/temporary-license/).

### Q: Salvar como XML preserva campos personalizados?  
**A:** Sim, ao salvar usando `SaveFileFormat.Xml`, todos os atributos personalizados e campos estendidos são mantidos.

### Q: Posso alterar a data de início após adicionar tarefas?  
**A:** Você pode atualizar a data de início a qualquer momento antes de salvar; basta chamar `project.set(Prj.START_DATE, …)` novamente.

---

**Última atualização:** 2026-01-05  
**Testado com:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}