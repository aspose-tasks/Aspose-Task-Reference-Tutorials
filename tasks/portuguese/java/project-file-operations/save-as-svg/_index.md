---
date: 2025-12-21
description: Aprenda como criar SVG a partir de arquivos MPP em Java e salvar o projeto
  como SVG usando a biblioteca Aspose.Tasks. Guia passo a passo com exemplos de código.
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como criar SVG a partir de MPP em Java usando Aspose.Tasks
url: /pt/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar SVG a partir de MPP em Java

## Introdução
Neste tutorial você aprenderá como **criar SVG a partir de MPP** usando Aspose.Tasks for Java. Converter um arquivo Microsoft Project (MPP) para gráficos vetoriais escaláveis (SVG) permite incorporar diagramas de alta qualidade e independentes de resolução diretamente em páginas da web, relatórios ou painéis. Vamos percorrer a configuração necessária, mostrar o código exato que você precisa e explicar cada passo para que você possa **salvar o projeto como SVG** em suas próprias aplicações.

## Respostas Rápidas
- **O que significa “criar SVG a partir de MPP”?**  
  Converte um arquivo Microsoft Project (.mpp) em uma imagem SVG que pode ser exibida em qualquer navegador sem perda de qualidade.  
- **Qual biblioteca realiza a conversão?**  
  Aspose.Tasks for Java fornece um método `save` de uma única linha para executar a conversão.  
- **Preciso de licença?**  
  Uma licença temporária é necessária para uso comercial; um teste gratuito está disponível.  
- **Quais são os pré-requisitos?**  
  Java JDK 8+ e o JAR do Aspose.Tasks for Java.  
- **Quanto tempo leva a conversão?**  
  Normalmente menos de um segundo para arquivos de projeto padrão.

## O que é “criar SVG a partir de MPP”?
Criar um SVG a partir de um arquivo MPP significa exportar a representação visual de um cronograma de projeto — tarefas, linhas do tempo e recursos — para o formato Scalable Vector Graphics. SVG é baseado em XML, leve e escala perfeitamente em telas de alta resolução.

## Por que usar Aspose.Tasks para salvar o projeto como SVG?
- **Nenhuma instalação do Microsoft Project necessária** – a biblioteca funciona de forma independente.  
- **Fidelidade total** – gráficos, barras de Gantt e marcos mantêm seus estilos.  
- **Multiplataforma** – execute o código no Windows, Linux ou macOS.  
- **Integração fácil** – chamada de API de uma linha se encaixa naturalmente em pipelines Java existentes.

## Pré-requisitos
- **Java Development Kit (JDK)** – versão 8 ou posterior. Baixe no site da Oracle.  
- **Aspose.Tasks for Java** – obtenha a biblioteca na página oficial de download **[aqui](https://releases.aspose.com/tasks/java/)**.  

## Importar Pacotes
Primeiro, importe as classes que você precisará. O bloco de importação permanece inalterado.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Etapa 1: Definir o Diretório de Dados
Especifique onde o seu arquivo MPP de origem está localizado e onde o SVG será gravado.

```java
String dataDir = "Your Data Directory";
```

> **Dica profissional:** Use um caminho absoluto ou um caminho relativo à pasta de recursos do seu projeto para evitar `FileNotFoundException`.

## Etapa 2: Carregar o Arquivo MPP
Crie uma instância `Project` carregando o arquivo Microsoft Project existente.

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

Esta linha lê *HomeMovePlan.mpp* da pasta que você definiu anteriormente.

## Etapa 3: Salvar o Projeto como SVG
Agora você pode **salvar o projeto como SVG** com um único comando.

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

O método grava `project5.svg` no mesmo diretório. O SVG resultante pode ser aberto em qualquer navegador moderno ou incorporado diretamente em HTML.

## Problemas Comuns e Soluções
| Problema | Motivo | Solução |
|----------|--------|---------|
| **Arquivo não encontrado** | Caminho `dataDir` incorreto | Verifique se a string do diretório termina com um separador (`/` ou `\\`). |
| **Saída SVG em branco** | Projeto carregado sem visualizações | Certifique-se de que o arquivo MPP contém uma visualização de diagrama de Gantt antes de salvar. |
| **Exceção de licença** | Nenhuma licença válida aplicada | Aplique uma licença temporária usando `License.setLicense("path/to/license.xml")` antes de chamar `save`. |

## Perguntas Frequentes

**Q: O Aspose.Tasks for Java é compatível com todas as versões de arquivos Microsoft Project?**  
A: Sim, ele suporta os formatos MPP, MPT e XML, desde versões mais antigas até as últimas versões do Project.

**Q: Posso personalizar a aparência da saída SVG?**  
A: Absolutamente. Use `SvgOptions` para definir fontes, cores e opções de layout antes de chamar `save`.

**Q: O Aspose.Tasks for Java requer licença para uso comercial?**  
A: Sim, uma licença válida é necessária para produção. Você pode obter uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Posso experimentar o Aspose.Tasks for Java antes de comprar?**  
A: Sim, um teste gratuito está disponível **[aqui](https://purchase.aspose.com/buy)**.

**Q: Onde posso obter suporte para o Aspose.Tasks for Java?**  
A: Visite o fórum da comunidade **[aqui](https://forum.aspose.com/c/tasks/15)** para fazer perguntas e compartilhar feedback.

## Conclusão
Agora você sabe como **criar SVG a partir de MPP** em Java e eficientemente **salvar o projeto como SVG** usando Aspose.Tasks. Essa capacidade permite integrar visualizações de projeto ricas em portais web, painéis de relatórios ou qualquer lugar onde gráficos escaláveis são necessários. Experimente `SvgOptions` para ajustar finamente a saída, e você terá uma ferramenta poderosa em seu conjunto de desenvolvimento.

---

**Última atualização:** 2025-12-21  
**Testado com:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}