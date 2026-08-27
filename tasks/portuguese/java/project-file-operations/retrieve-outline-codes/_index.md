---
date: 2026-03-27
description: Aprenda a recuperar os códigos de contorno do MS Project programaticamente
  usando Aspose.Tasks para Java. Aprimore suas habilidades de gerenciamento de projetos.
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Recuperar códigos de estrutura do MS Project no Aspose.Tasks
url: /pt/java/project-file-operations/retrieve-outline-codes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Recuperar códigos de contorno do MS Project no Aspose.Tasks

## Introdução
Neste tutorial, você descobrirá **como recuperar códigos de contorno do MS Project** usando Aspose.Tasks para Java. Os códigos de contorno no MS Project oferecem uma maneira poderosa de categorizar tarefas, recursos e atribuições, e acessá‑los programaticamente permite criar relatórios personalizados, automação ou soluções de integração. Vamos percorrer um exemplo completo, passo a passo, que você pode copiar para o seu próprio projeto.

## Respostas rápidas
- **O que o código faz?** Carrega um arquivo Project e imprime cada definição de código de contorno, suas máscaras e seus valores.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (qualquer versão recente).  
- **Preciso de licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Posso modificar os códigos após recuperá‑los?** Sim – a mesma API permite adicionar, editar ou excluir códigos de contorno.

## O que são códigos de contorno do ms project?
Os códigos de contorno são campos personalizados que permitem aos gerentes de projeto agrupar e filtrar tarefas além da hierarquia padrão. Eles podem ser valores numéricos simples, strings ou até códigos personalizados corporativos definidos ao nível da organização. Ao ler esses códigos, você pode alimentar dashboards, exportar dados ou aplicar convenções de nomenclatura automaticamente.

## Por que recuperar códigos de contorno do ms project com Aspose.Tasks?
- **Automação:** Gere relatórios ou acione fluxos de trabalho sem exportação manual.  
- **Integração:** Sincronize códigos de contorno com ERP, PPM ou ferramentas de BI.  
- **Personalização:** Aplique regras de negócio baseadas nos valores dos códigos (por exemplo, alocação de custos).  
- **Multiplataforma:** Funciona em Windows, Linux e macOS, independente da interface do Microsoft Project.

## Como ler arquivos MPP para códigos de contorno?
Ler um arquivo MPP (Microsoft Project) é o primeiro passo para extrair códigos de contorno. Aspose.Tasks abstrai o formato do arquivo, de modo que você não precisa analisar a estrutura binária manualmente. A classe `Project` cuida do trabalho pesado, permitindo que você se concentre nos dados que realmente precisa.

## Campos personalizados no MS Project
Códigos de contorno são um tipo de **campos personalizados** no MS Project. Enquanto os campos padrão cobrem datas, durações e recursos, os campos personalizados permitem armazenar informações específicas da organização. Acessá‑los através do Aspose.Tasks oferece a mesma flexibilidade programaticamente.

## Pré‑requisitos
Antes de começar, certifique‑se de que os seguintes pré‑requisitos estejam configurados:

### 1. Ambiente de desenvolvimento Java
Garanta que o Java Development Kit (JDK) esteja instalado no seu sistema. Você pode baixar e instalar o JDK a partir do site da Oracle.

### 2. Biblioteca Aspose.Tasks
Baixe e inclua a biblioteca Aspose.Tasks no seu projeto Java. Você pode obter a biblioteca na [Página de Download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, importe os pacotes necessários do Aspose.Tasks no seu código Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```

Agora vamos dividir o código de exemplo fornecido em várias etapas:

## Etapa 1: Carregar o Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
Nesta etapa, carregamos o arquivo Microsoft Project em um objeto `Project` usando o nome de arquivo fornecido.

## Etapa 2: Recuperar códigos de contorno
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Iteramos por cada definição de código de contorno no projeto.

## Etapa 3: Acessar propriedades do código de contorno
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Recuperamos e imprimimos várias propriedades da definição do código de contorno, como Alias, Field ID e Field Name.

## Etapa 4: Verificar código personalizado corporativo
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verificamos se o código de contorno é um código personalizado corporativo e imprimimos o resultado correspondente.

## Etapa 5: Exibir máscaras do código de contorno
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteramos por cada máscara associada ao código de contorno e imprimimos seu nível e valor da máscara.

## Etapa 6: Exibir valores do código de contorno
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iteramos por cada valor do código de contorno e imprimimos sua descrição, ID do valor, valor e tipo.

## Problemas comuns e soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **Nenhuma saída** | Caminho do arquivo de projeto incorreto | Verifique se `projectName` aponta para um arquivo `.mpp` válido. |
| **Valores nulos** | Código de contorno não definido no arquivo | Certifique‑se de que o arquivo Project realmente contenha códigos de contorno (verifique na interface do MS Project). |
| **LicenseException** | Uso da avaliação sem ativação adequada | Aplique uma licença temporária ou completa via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Perguntas frequentes

**Q: Posso usar Aspose.Tasks para Java para modificar códigos de contorno em um arquivo Project?**  
A: Sim, Aspose.Tasks para Java fornece APIs para modificar códigos de contorno programaticamente. Você pode adicionar, editar ou excluir definições usando o mesmo objeto `Project`.

**Q: Existe uma versão de avaliação disponível para Aspose.Tasks para Java?**  
A: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks para Java na [página do Aspose.Tasks](https://releases.aspose.com/).

**Q: Como posso obter suporte técnico para Aspose.Tasks para Java?**  
A: Você pode obter suporte técnico visitando o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) e postando suas dúvidas lá.

**Q: Posso comprar uma licença temporária para Aspose.Tasks para Java?**  
A: Sim, você pode adquirir uma licença temporária para Aspose.Tasks para Java na [página de compra](https://purchase.aspose.com/temporary-license/).

**Q: Onde encontro a documentação completa do Aspose.Tasks para Java?**  
A: Você pode consultar a [documentação](https://reference.aspose.com/tasks/java/) para obter informações detalhadas sobre o uso do Aspose.Tasks para Java.

## Conclusão
Neste tutorial, aprendemos como recuperar **códigos de contorno do ms project** usando Aspose.Tasks para Java. Seguindo as etapas fornecidas, você pode acessar e manipular efetivamente os códigos de contorno em suas aplicações Java, habilitando capacidades avançadas de gerenciamento de projetos, como relatórios personalizados, automação e integração com outros sistemas corporativos.

---

**Última atualização:** 2026-03-27  
**Testado com:** Aspose.Tasks para Java (última versão)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}