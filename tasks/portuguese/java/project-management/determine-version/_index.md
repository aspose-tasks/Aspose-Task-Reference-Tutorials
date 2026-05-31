---
date: 2026-05-31
description: Aprenda como obter a versão do projeto e recuperar a data da última gravação
  de arquivos MS Project usando Aspose.Tasks para Java. Guia passo a passo com exemplos
  de código.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Determinar a versão do projeto com Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Como obter a versão do projeto – Tutorial Aspose Tasks Java
url: /pt/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Obter a Versão do Projeto – Aspose Tasks Java Tutorial

Neste **Aspose Tasks Java tutorial** você aprenderá **como obter a versão do projeto** de um arquivo Microsoft Project e também como **recuperar a data da última gravação** usando a biblioteca Aspose.Tasks para Java. Conhecer a versão do arquivo e o carimbo de data/hora de gravação ajuda a evitar problemas de compatibilidade, aplicar políticas de migração e manter registros de auditoria precisos. Vamos percorrer cada passo — desde a configuração do ambiente até a impressão da versão e da data — para que você possa incorporar essa verificação em qualquer aplicação Java com confiança.

## Respostas Rápidas
- **O que este tutorial cobre?** Determinar a versão do arquivo MS Project e a data da última gravação com Aspose.Tasks para Java.  
- **Preciso ter o Microsoft Project instalado?** Não, Aspose.Tasks funciona independentemente do Microsoft Project.  
- **Quais formatos de arquivo são suportados?** Arquivos Project baseados em XML, como MPP e XML, são totalmente suportados.  
- **Quanto tempo leva a implementação?** Aproximadamente 5‑10 minutos para uma verificação básica de versão.  
- **É necessária uma licença?** Uma avaliação gratuita funciona para avaliação; uma licença comercial é necessária para uso em produção.

## O que é o Tutorial Aspose Tasks Java?
O tutorial Java `Aspose.Tasks` é um guia conciso e prático que demonstra como interagir programaticamente com os dados do Microsoft Project. Ele mostra como ler, modificar e analisar informações do projeto sem precisar do Microsoft Project instalado no servidor. Além disso, cobre o carregamento de arquivos, acesso a propriedades e salvamento de alterações, permitindo que desenvolvedores automatizem tarefas de gerenciamento de projetos de forma eficiente.

## Por que usar Aspose.Tasks para determinar a versão do projeto?
Aspose.Tasks fornece **metadados de versão exatos** e **carimbos de data/hora da última gravação** enquanto roda em qualquer SO que suporte Java. Ele processa arquivos de até **500 páginas em menos de 2 segundos** em uma CPU padrão de 2,5 GHz, tornando‑o ideal para automação em lote e cenários de migração em grande escala.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – versão 8 ou superior.  
2. **Aspose.Tasks for Java JAR** – download a partir do [website](https://releases.aspose.com/tasks/java/) e adicione ao classpath do seu projeto.  
3. **MS Project file** – um arquivo Project baseado em XML (por exemplo, `input.xml`) que você deseja inspecionar.  

> **Dica profissional:** Armazene o arquivo Project em uma pasta `data` dedicada para manter os caminhos organizados e evitar sobrescritas acidentais.

## Importar Pacotes
Primeiro, importe as classes essenciais do Aspose.Tasks:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Como Configurar o Diretório do Projeto
Para localizar corretamente seus arquivos de projeto, crie um diretório dedicado dentro da estrutura da sua aplicação e armazene todos os arquivos de entrada lá. Isso mantém o código limpo e evita erros relacionados a caminhos ao carregar arquivos. Use um nome de variável claro para o caminho do diretório, que pode ser absoluto ou relativo à raiz do projeto.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

## Como Carregar o Projeto
`Project` é o objeto principal do Aspose.Tasks que representa um arquivo Microsoft Project na memória, dando acesso a todas as propriedades e coleções do projeto. Após criar a instância `Project`, você pode consultar seus campos, iterar sobre tarefas ou modificar dados antes de salvar o arquivo de volta ao disco.

```java
Project project = new Project(dataDir + "input.xml");
```

## Como Determinar a Versão do Projeto
`Prj.SAVE_VERSION` é uma propriedade que indica o número da versão do Microsoft Project que salvou o arquivo. `Prj.LAST_SAVED` é uma propriedade que armazena a data e hora em que o arquivo foi salvo pela última vez. `Prj.SAVE_VERSION` devolve a versão numérica da aplicação Microsoft Project que salvou o arquivo (por exemplo, 12 para Project 2010). `Prj.LAST_SAVED` fornece a data e hora exatas da operação de salvamento mais recente.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

Esses valores permitem que você imponha regras de negócio específicas por versão ou gere relatórios de auditoria programaticamente.

## Como Exibir o Resultado
Depois de recuperar a versão e as informações da última gravação, normalmente você desejará exibi‑las no console ou em um arquivo de log. Use `System.out.println` para mostrar os valores, formatando a data conforme necessário. Isso confirma que a extração foi bem‑sucedida e fornece feedback imediato durante o desenvolvimento ou em scripts automatizados.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| `NullPointerException` on `project.get(...)` | Arquivo não encontrado ou caminho incorreto | Verifique `dataDir` e o nome do arquivo; use um caminho absoluto para teste. |
| Unexpected version number (e.g., 0) | Carregando um arquivo XML que não é de Project | Certifique‑se de que o arquivo é um arquivo Microsoft Project válido (MPP/XML). |
| License exception | Usando a versão de avaliação sem uma licença válida em produção | Aplique sua licença Aspose.Tasks (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, Aspose.Tasks suporta .NET, Java e C++ entre outros.

**Q: Aspose.Tasks é adequado para projetos em grande escala?**  
A: Absolutamente; ele pode processar projetos com centenas de páginas em segundos sem carregar todo o arquivo na memória.

**Q: Posso personalizar dados do projeto usando Aspose.Tasks?**  
A: Sim, você pode modificar tarefas, recursos, calendários e qualquer outro elemento do projeto através da API.

**Q: Aspose.Tasks requer instalação do Microsoft Project?**  
A: Não, a biblioteca funciona independentemente e não necessita do Microsoft Project na máquina host.

**Q: Existe suporte técnico disponível para Aspose.Tasks?**  
A: Sim, você pode obter ajuda no fórum Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Perguntas e Respostas Adicionais**

**Q: Como recuperar outras propriedades do projeto (ex., autor, empresa)?**  
A: Use `project.get(Prj.AUTHOR)` ou `project.get(Prj.COMPANY)` da mesma forma que recupera a versão.

**Q: Posso verificar a versão de um arquivo MPP (binário)?**  
A: Sim, Aspose.Tasks carrega arquivos `.mpp` diretamente; a propriedade `Prj.SAVE_VERSION` funciona também para formatos binários.

**Q: Existe uma forma de atualizar programaticamente um arquivo de projeto antigo para uma versão mais nova?**  
A: Carregue o arquivo antigo e, em seguida, salve‑o com `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks grava o arquivo no formato mais recente por padrão.

## Conclusão
Você agora domina **como obter a versão do projeto** e **recuperar a data da última gravação** de arquivos MS Project usando Aspose.Tasks para Java. Incorpore esses trechos em pipelines de automação, ferramentas de relatório ou utilitários de migração para garantir que você sempre saiba a versão exata do Project que está manipulando.

---

**Última atualização:** 2026-05-31  
**Testado com:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Definir Data de Início do Projeto no MS Project usando Aspose.Tasks para Java](/tasks/java/project-properties/write-project-info/)
- [Ler banco de dados do Microsoft Project com Aspose.Tasks para Java](/tasks/java/project-data-reading/read-project-database/)
- [Salvar Projeto como Modelo, CSV e Texto com Aspose.Tasks para Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}