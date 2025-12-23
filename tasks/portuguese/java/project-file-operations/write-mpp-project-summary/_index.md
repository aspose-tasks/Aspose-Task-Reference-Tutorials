---
date: 2025-12-23
description: Aprenda a criar resumo MPP e atualizar o autor do projeto usando Aspose.Tasks
  para Java. Defina e recupere informações do projeto com facilidade.
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como criar resumo MPP e atualizar o autor do projeto com Aspose.Tasks
url: /pt/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Escreva o Resumo do Projeto MPP no Aspose.Tasks

## Introdução
Neste tutorial, você **criará resumo MPP** para um arquivo Microsoft Project e aprenderá como **atualizar o autor do projeto** usando a biblioteca Aspose.Tasks para Java. Seja construindo uma ferramenta de gerenciamento de projetos ou automatizando relatórios, controlar programaticamente as propriedades de resumo economiza tempo e garante consistência em seus projetos.

## Respostas Rápidas
- **O que significa “create MPP summary”?** Significa definir as propriedades de alto nível do projeto (autor, revisão, palavras‑chave, etc.) que aparecem na caixa de diálogo Informações de Resumo do Projeto do Microsoft Project.  
- **Qual biblioteca lida com isso?** Aspose.Tasks for Java fornece uma API fluente para ler e gravar essas propriedades.  
- **Preciso de uma licença?** Um teste gratuito está disponível, mas uma licença comercial é necessária para uso em produção.  
- **Posso também mudar o autor após o arquivo ser salvo?** Sim – você pode **atualizar o autor do projeto** chamando `project.set(Prj.AUTHOR, "New Author")` e então salvar o arquivo novamente.  
- **Quais formatos de arquivo são suportados?** Tanto MPP quanto XML (SaveFileFormat.Xml) são totalmente suportados.

## O que é create MPP summary?
Criar um resumo MPP envolve preencher os metadados do projeto — autor, número da revisão, palavras‑chave, comentários, data de criação e data de impressão. Esses metadados são armazenados no registro de Informações de Resumo do Projeto e são exibidos na seção **File → Info** do Microsoft Project.

## Por que atualizar o autor do projeto?
Manter as informações do **autor do projeto** precisas é essencial para trilhas de auditoria, colaboração e relatórios. Quando vários membros da equipe contribuem, pode ser necessário **atualizar o autor do projeto** para refletir as alterações mais recentes ou atribuir o trabalho corretamente.

## Pré‑requisitos
1. Java Development Kit (JDK) instalado na sua máquina.  
2. Aspose.Tasks for Java – faça o download a partir de [here](https://releases.aspose.com/tasks/java/).  
3. Uma IDE como IntelliJ IDEA, Eclipse ou NetBeans.

## Importar Pacotes
Primeiro, importe os pacotes necessários em sua classe Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## Etapa 1: Configurar o Projeto e Definir as Informações de Resumo
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
No código acima, nós **criamos campos de resumo MPP** como autor, revisão e palavras‑chave. Você também pode **atualizar o autor do projeto** posteriormente chamando `project.set(Prj.AUTHOR, "New Name")`.

## Etapa 2: Salvar as Informações de Resumo do Projeto
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
Salvar o projeto persiste todos os dados de resumo que você acabou de definir.

## Etapa 3: Ler as Informações de Resumo do Projeto
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
Este trecho demonstra como **ler novamente** as informações de resumo, confirmando que a operação **create MPP summary** foi bem‑sucedida.

## Problemas Comuns e Soluções
- **Valores nulos após a leitura:** Certifique‑se de que o projeto foi salvo com sucesso antes de recarregar. Verifique caminhos de arquivos e permissões.  
- **Diferenças de formatação de data:** `project.get(Prj.CREATION_DATE)` retorna um `java.util.Date`. Use `SimpleDateFormat` se precisar de um formato de exibição personalizado.  
- **Licença não definida:** Sem uma licença válida, Aspose.Tasks roda em modo de avaliação e pode inserir uma marca d'água. Registre sua licença logo no início do código.

## Perguntas Frequentes
**Q: Posso usar Aspose.Tasks for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Tasks for Java pode ser integrado perfeitamente com outras bibliotecas Java para aprimorar suas capacidades de gerenciamento de projetos.

**Q: Existe uma versão de teste disponível para Aspose.Tasks for Java?**  
A: Sim, você pode baixar uma versão de teste gratuita a partir de [here](https://releases.aspose.com/).

**Q: Com que frequência o Aspose.Tasks for Java é atualizado?**  
A: Aspose.Tasks for Java é atualizado regularmente para garantir compatibilidade com as versões mais recentes do Java e dos arquivos Microsoft Project.

**Q: Posso personalizar ainda mais as informações de resumo do projeto?**  
A: Absolutamente, Aspose.Tasks for Java oferece opções extensas para personalizar as informações de resumo do projeto de acordo com seus requisitos específicos.

**Q: Onde posso obter suporte para Aspose.Tasks for Java?**  
A: Você pode obter suporte no fórum da comunidade Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

## Conclusão
Neste tutorial, mostramos como **criar dados de resumo MPP**, **atualizar o autor do projeto**, e verificar essas alterações usando Aspose.Tasks for Java. Ao automatizar essas etapas, você obtém controle total sobre os metadados do projeto, tornando suas aplicações mais robustas e seus relatórios de projeto mais precisos.

---

**Última atualização:** 2025-12-23  
**Testado com:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}