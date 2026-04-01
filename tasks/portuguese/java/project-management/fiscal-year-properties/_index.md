---
date: 2026-04-01
description: Aprenda como salvar XML, definir o ano fiscal e converter MPP para XML
  usando Aspose.Tasks para Java. Guia passo a passo com exemplos de código.
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: Como salvar XML e gerenciar o ano fiscal no Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como salvar XML e gerenciar o ano fiscal no Aspose.Tasks
url: /pt/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como salvar XML e gerenciar ano fiscal no Aspose.Tasks

## Introdução
Se você precisa **how to save xml** arquivos gerados a partir de dados do Microsoft Project, Aspose.Tasks for Java oferece uma maneira limpa e livre de licença para fazer isso. Neste tutorial, percorreremos o carregamento de um arquivo MPP, a exibição das informações do ano fiscal, a definição das propriedades do ano fiscal e, finalmente, a **how to save xml** de saída. Você também verá como **how to set fiscal** detalhes e **how to convert mpp** arquivos sem nunca abrir o Microsoft Project.

## Respostas rápidas
- **What does “manage fiscal year” mean in Aspose.Tasks?** O que significa “manage fiscal year” no Aspose.Tasks? Permite definir o mês de início do ano fiscal e habilitar a numeração do ano fiscal para um projeto.  
- **How to set fiscal year start month?** Como definir o mês de início do ano fiscal? Use a propriedade `Prj.FY_START_DATE` com um valor enum `Month` (por exemplo, `Month.JULY`).  
- **Can I load an MPP file?** Posso carregar um arquivo MPP? Sim, basta criar uma instância `Project` com o caminho para o arquivo *.mpp*.  
- **How to convert MPP to XML?** Como converter MPP para XML? Chame `project.save(..., SaveFileFormat.Xml)` após definir as propriedades desejadas.  
- **Do I need a license?** Preciso de licença? Um teste gratuito está disponível; uma licença comercial é necessária para uso em produção.  

## O que é “manage fiscal year” em arquivos de projeto?
Gerenciar o ano fiscal significa configurar o calendário que seu projeto segue para relatórios financeiros. Isso inclui definir o mês de início do ano fiscal e, opcionalmente, habilitar a numeração do ano fiscal, o que afeta como as datas são calculadas e exibidas nos relatórios.

## Por que usar Aspose.Tasks para manipulação de ano fiscal?
- **No Microsoft Project required** – Sem necessidade do Microsoft Project – trabalhe com arquivos de projeto diretamente em Java.  
- **Full control** – Controle total – defina o início do ano fiscal, habilite a numeração e converta formatos programaticamente.  
- **Robust API** – API robusta – manipulação confiável de arquivos MPP grandes e exportação XML sem problemas.  

## Pré-requisitos
Antes de começar, certifique‑se de que você tem o seguinte:
1. Java Development Kit (JDK) instalado no seu sistema.  
2. Aspose.Tasks for Java JAR – faça o download a partir de [here](https://releases.aspose.com/tasks/java/) e adicione ao classpath do seu projeto.

## Importar Pacotes
Para começar, importe as classes necessárias no seu arquivo fonte Java:
```java
import com.aspose.tasks.*;
```

## Como carregar um arquivo MPP e exibir informações do ano fiscal
A seguir, dividimos o processo em etapas claras e numeradas.

### Etapa 1: Carregar arquivo de projeto
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
Aqui nós **load an MPP file** (`project.mpp`) a partir do diretório especificado. Esta é a primeira etapa em qualquer manipulação relacionada ao ano fiscal.

### Etapa 2: Exibir propriedades do ano fiscal
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
As propriedades `Prj.FY_START_DATE` e `Prj.FISCAL_YEAR_START` permitem que você **display fiscal year** detalhes, respondendo à pergunta “qual é a configuração fiscal atual?”.

### Etapa 3: Definir início do ano fiscal e habilitar numeração
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Nesta etapa nós **how to set fiscal** configurações:
- `Month.JULY` define o mês de início do ano fiscal.  
- `NullableBool(true)` ativa a numeração do ano fiscal.  
- Finalmente, o projeto é **converted MPP to XML** usando `SaveFileFormat.Xml`.

### Etapa 4: Confirmar a operação
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
Uma mensagem simples no console confirma que o ano fiscal foi configurado e o arquivo salvo.

## Por que isso importa
Salvar o projeto como XML fornece uma representação portátil baseada em texto que pode ser facilmente analisada, versionada ou integrada a outros sistemas. Quando as configurações do ano fiscal estão corretas, relatórios financeiros e painéis subsequentes alinhar‑se‑ão com os períodos contábeis da sua organização.

## Casos de uso comuns
- **Financial reporting** – Relatórios financeiros – Alinhe cronogramas de projetos com um calendário fiscal antes de exportar para ferramentas de BI.  
- **Data migration** – Migração de dados – Converta arquivos *.mpp* legados para XML para importação em plataformas de gerenciamento de projetos baseadas na nuvem.  
- **Automated audits** – Auditorias automatizadas – Verifique programaticamente se cada projeto usa o mês de início fiscal correto.

## Dicas de solução de problemas e armadilhas comuns
| Problema | Solução |
|----------|---------|
| **Valor de mês incorreto** | Certifique‑se de usar o enum `Month` (por exemplo, `Month.JANUARY`). |
| **Arquivo não encontrado** | Verifique se `dataDir` aponta para a pasta correta e se o nome do arquivo corresponde. |
| **Falha ao salvar** | Verifique as permissões de gravação no diretório de destino e se o `SaveFileFormat` é suportado. |
| **Ano fiscal não refletido no XML** | Após salvar, abra o XML e confirme que os nós `<FiscalYearStart>` e `<FiscalYearNumbering>` contêm os valores esperados. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks for Java para manipular outras propriedades do projeto?**  
A: Sim, Aspose.Tasks fornece funcionalidade abrangente para gerenciar várias propriedades do projeto além das configurações de ano fiscal.

**Q: O Aspose.Tasks for Java é compatível com diferentes formatos de arquivo de projeto?**  
A: Sim, ele suporta uma ampla gama de formatos, incluindo MPP, XML e outros.

**Q: Como posso obter suporte se encontrar algum problema ao usar Aspose.Tasks for Java?**  
A: Você pode buscar assistência na comunidade Aspose.Tasks no [forum](https://forum.aspose.com/c/tasks/15) ou contatar diretamente a equipe de suporte.

**Q: O Aspose.Tasks oferece uma versão de teste gratuita?**  
A: Sim, você pode acessar a versão de teste gratuito do Aspose.Tasks a partir de [here](https://releases.aspose.com/).

**Q: Onde posso comprar uma licença para Aspose.Tasks for Java?**  
A: Você pode comprar uma licença para Aspose.Tasks for Java a partir de [here](https://purchase.aspose.com/buy).

## Conclusão
Gerenciar propriedades do ano fiscal no Aspose.Tasks for Java é simples. Seguindo as etapas acima, você pode **how to save xml**, **load mpp file**, **display fiscal year**, **set fiscal year** e **convert mpp to xml** com confiança. Use essas técnicas para manter seus cronogramas de projeto alinhados ao calendário financeiro da sua organização e para criar representações XML portáteis para processamento posterior.

---

**Last Updated:** 2026-04-01  
**Testado com:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}