---
date: 2025-12-20
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

# Recuperar códigos de contorno do MS Project com Aspose.Tasks

## Introdução
Neste tutorial, você descobrirá **como recuperar códigos de contorno do MS Project** usando Aspose.Tasks para Java. Os códigos de contorno no MS Project oferecem uma maneira poderosa de categorizar tarefas, recursos e atribuições, e acessá‑los programaticamente permite criar relatórios personalizados, automação ou soluções de integração. Vamos percorrer um exemplo completo, passo a passo, que você pode copiar para o seu próprio projeto.

## Respostas rápidas
- **O que o código faz?** Ele carrega um arquivo Project e imprime cada definição de código de contorno, suas máscaras e seus valores.  
- **Qual biblioteca é necessária?** Aspose.Tasks para Java (qualquer versão recente).  
- **Preciso de licença?** Uma versão de avaliação funciona para desenvolvimento; uma licença completa é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Posso modificar os códigos após recuperá‑los?** Sim – a mesma API permite adicionar, editar ou excluir códigos de contorno.

## O que são códigos de contorno do ms project?
Códigos de contorno são campos personalizados que permitem aos gerentes de projeto agrupar e filtrar tarefas além da hierarquia padrão. Eles podem ser valores numéricos simples, strings ou até códigos personalizados corporativos definidos ao nível da organização. Ao ler esses códigos, você pode alimentar painéis, exportar dados ou aplicar convenções de nomenclatura automaticamente.

## Por que recuperar códigos de contorno do ms project com Aspose.Tasks?
- **Automação:** Gere relatórios ou acione fluxos de trabalho sem exportação manual.  
- **Integração:** Sincronize códigos de contorno com ERP, PPM ou ferramentas de BI.  
- **Personalização:** Aplique regras de negócio com base nos valores dos códigos (por exemplo, alocação de custos).  
- **Multiplataforma:** Funciona no Windows, Linux e macOS, independente da interface do Microsoft Project.

## Pré‑requisitos
Antes de começar, certifique‑se de que os seguintes pré‑requisitos estejam configurados:

### 1. Ambiente de desenvolvimento Java
Garanta que o Java Development Kit (JDK) esteja instalado em seu sistema. Você pode baixar e instalar o JDK a partir do site da Oracle.

### 2. Biblioteca Aspose.Tasks
Baixe e inclua a biblioteca Aspose.Tasks em seu projeto Java. Você pode baixar a biblioteca na [Página de Download do Aspose.Tasks para Java](https://releases.aspose.com/tasks/java/).

## Importar pacotes
Primeiro, importe os pacotes necessários do Aspose.Tasks em seu código Java:
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
Recuperamos e imprimimos várias propriedades da definição do código de contorno, como Alias, ID do Campo e Nome do Campo.

## Etapa 4: Verificar código personalizado corporativo
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Verificamos se o código de contorno é um código personalizado corporativo e imprimimos o resultado adequadamente.

## Etapa 5: Exibir máscaras de código de contorno
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Iteramos por cada máscara associada ao código de contorno e imprimimos seu nível e valor da máscara.

## Etapa 6: Exibir valores de código de contorno
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Iteramos por cada valor de código de contorno e imprimimos sua descrição, ID do valor, valor e tipo.

## Problemas comuns e soluções
| Problema | Motivo | Correção |
|----------|--------|----------|
| **Nenhuma saída** | Caminho do arquivo do projeto incorreto | Verifique se `projectName` aponta para um arquivo `.mpp` válido. |
| **Valores nulos** | Código de contorno não definido no arquivo | Certifique‑se de que o arquivo Project realmente contém códigos de contorno (verifique na UI do MS Project). |
| **LicenseException** | Uso da avaliação sem ativação adequada | Aplique uma licença temporária ou completa via `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |

## Perguntas frequentes

**P: Posso usar Aspose.Tasks para Java para modificar códigos de contorno em um arquivo Project?**  
R: Sim, o Aspose.Tasks para Java fornece APIs para modificar códigos de contorno programaticamente. Você pode adicionar, editar ou excluir definições usando o mesmo objeto `Project`.

**P: Existe uma versão de avaliação disponível para Aspose.Tasks para Java?**  
R: Sim, você pode baixar uma versão de avaliação gratuita do Aspose.Tasks para Java na [página do Aspose.Tasks](https://releases.aspose.com/).

**P: Como posso obter suporte técnico para Aspose.Tasks para Java?**  
R: Você pode obter suporte técnico visitando o [fórum do Aspose.Tasks](https://forum.aspose.com/c/tasks/15) e postando suas dúvidas lá.

**P: Posso comprar uma licença temporária para Aspose.Tasks para Java?**  
R: Sim, você pode adquirir uma licença temporária para Aspose.Tasks para Java na [página de compra](https://purchase.aspose.com/temporary-license/).

**P: Onde encontro a documentação completa do Aspose.Tasks para Java?**  
R: Consulte a [documentação](https://reference.aspose.com/tasks/java/) para informações detalhadas sobre o uso do Aspose.Tasks para Java.

## Conclusão
Neste tutorial, aprendemos como recuperar **códigos de contorno do ms project** usando Aspose.Tasks para Java. Seguindo as etapas fornecidas, você pode acessar e manipular efetivamente os códigos de contorno em suas aplicações Java, habilitando recursos avançados de gerenciamento de projetos, como relatórios personalizados, automação e integração com outros sistemas corporativos.

---

**Última atualização:** 2025-12-20  
**Testado com:** Aspose.Tasks para Java 24.12 (mais recente na data da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}