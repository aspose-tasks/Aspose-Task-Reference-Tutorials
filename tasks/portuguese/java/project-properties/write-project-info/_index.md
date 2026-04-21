---
date: 2025-12-31
description: Aprenda como definir a data de início do projeto, escrever informações
  do projeto e salvar o projeto como XML usando Aspose.Tasks para Java.
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Definir a data de início do projeto no MS Project usando Aspose.Tasks para
  Java
url: /pt/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir a Data de Início do Projeto no MS Project usando Aspose.Tasks para Java

## Introdução
Neste tutorial, você descobrirá como **definir a data de início do projeto** e gravar informações adicionais do MS Project com Aspose.Tasks para Java. Seja automatizando cronogramas de projetos, gerando relatórios ou integrando dados do Project a um sistema maior, controlar a data de início programaticamente oferece comando preciso sobre seus prazos. Percorreremos cada passo — desde a configuração do ambiente até a gravação do projeto atualizado como um arquivo XML — para que você possa aplicar essas técnicas imediatamente.

## Respostas Rápidas
- **Qual é a classe principal para manipular um projeto?** `Project` da biblioteca Aspose.Tasks.  
- **Como eu defino a data de início do projeto?** Use `project.set(Prj.START_DATE, <date>)`.  
- **Posso também definir a data de status?** Sim, com `project.set(Prj.STATUS_DATE, <date>)`.  
- **Qual formato devo usar para exportar o projeto?** Salve como XML com `SaveFileFormat.Xml`.  
- **Preciso de uma licença para uso em produção?** Uma licença válida do Aspose.Tasks é necessária para funcionalidade completa.

## O que é **definir a data de início do projeto**?
Definir a data de início do projeto determina o dia do calendário a partir do qual todas as tarefas programadas começam. É o ponto de ancoragem para cálculos como durações de tarefas, dependências e caminhos críticos. Ao definir essa data programaticamente, você garante consistência entre múltiplos arquivos de projeto e elimina erros de entrada manual.

## Por que usar Aspose.Tasks para Java para escrever informações do projeto?
- **Cobertura total da API:** Leia, modifique e grave todas as propriedades do Project sem precisar do Microsoft Project instalado.  
- **Multiplataforma:** Funciona no Windows, Linux e macOS.  
- **Pronto para automação:** Ideal para processamento em lote, pipelines de CI ou serviços back‑end que geram cronogramas de projetos sob demanda.  

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – qualquer versão recente (8+ recomendada).  
2. **Aspose.Tasks para Java** – faça o download [aqui](https://releases.aspose.com/tasks/java/).  
3. **Uma IDE** – IntelliJ IDEA, Eclipse ou seu editor Java favorito.  

## Importar Pacotes
Primeiro, importe os pacotes necessários em seu projeto Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Etapa 1: Configurar o Diretório de Dados
Defina o diretório onde seus dados de projeto serão armazenados.
```java
String dataDir = "Your Data Directory";
```

## Etapa 2: Criar Instância do Projeto
Inicialize uma nova instância de projeto.
```java
Project project = new Project();
```

## Etapa 3: Definir Propriedades de Informação do Projeto
Aqui definimos a **data de início do projeto**, agenda a partir do início e data de status — cobrindo as palavras‑chave principais *escrever informações do projeto* e *como definir status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## Etapa 4: Salvar Projeto como XML
Por fim, persista o arquivo de projeto atualizado. Isto demonstra a palavra‑chave secundária **salvar projeto como xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **Data de início incorreta** | O mês do calendário é baseado em zero em Java. | Use `Calendar.JULY` (ou adicione 1 ao índice do mês) conforme mostrado. |
| **Arquivo não salvo** | `dataDir` não existe ou não tem permissão de gravação. | Crie o diretório antecipadamente ou escolha um caminho gravável. |
| **Aviso de licença** | Executar sem licença adiciona uma marca d'água. | Aplique uma licença válida do Aspose.Tasks antes de criar o objeto `Project`. |

## Perguntas Frequentes
### P: Posso usar Aspose.Tasks para Java para ler arquivos MS Project?
R: Sim, Aspose.Tasks para Java fornece funcionalidades robustas tanto para leitura quanto para gravação de arquivos MS Project.  
### P: O Aspose.Tasks para Java é compatível com diferentes versões do MS Project?
R: Absolutamente, Aspose.Tasks para Java suporta várias versões do MS Project, garantindo compatibilidade entre diferentes formatos de arquivo.  
### P: Existem limitações na versão de avaliação do Aspose.Tasks para Java?
R: Embora a versão de avaliação permita explorar as capacidades da biblioteca, ela possui algumas limitações, como marcas d'água nos arquivos de saída.  
### P: Como posso obter suporte para Aspose.Tasks para Java?
R: Você pode buscar assistência no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).  
### P: Posso comprar uma licença temporária para Aspose.Tasks para Java?
R: Sim, licenças temporárias estão disponíveis para uso de curto prazo. Você pode obter uma [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você aprendeu como **definir a data de início do projeto**, gravar informações essenciais do projeto e **salvar o projeto como XML** usando Aspose.Tasks para Java. Esses blocos de construção permitem automatizar fluxos de trabalho de gerenciamento de projetos, gerar cronogramas consistentes e integrar dados do MS Project em suas aplicações Java.

---

**Última atualização:** 2025-12-31  
**Testado com:** Aspose.Tasks para Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}