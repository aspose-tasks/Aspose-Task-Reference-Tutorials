---
date: 2025-12-20
description: Aprenda a usar o Aspose.Tasks para extrair detalhes do calendário do
  projeto de arquivos do Microsoft Project usando Java. Guia passo a passo com exemplos
  de código.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Como usar Aspose.Tasks para recuperar informações do calendário do MS Project
url: /pt/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Usar Aspose.Tasks para Recuperar Informações do Calendário do MS Project

## Introdução
Neste tutorial, **você descobrirá como usar Aspose.Tasks** para recuperar programaticamente informações de calendário de arquivos Microsoft Project. Acessar dados de calendário, como dias úteis, horas e exceções, é essencial quando você precisa **extrair o calendário do projeto** para relatórios, integração ou lógica de agendamento personalizada. Vamos percorrer o processo passo a passo.

## Respostas Rápidas
- **Qual biblioteca este tutorial usa?** Aspose.Tasks for Java.  
- **Qual palavra‑chave principal é abordada?** *how to use aspose.tasks*.  
- **O que você pode extrair?** Calendários de projetos, incluindo dias úteis e horas.  
- **Preciso de licença?** Uma versão de avaliação gratuita está disponível; uma licença é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.

## Por que extrair informações do calendário do projeto?
Os calendários de projetos determinam datas de tarefas, alocações de recursos e cálculos de cronograma geral. Ao extrair esses dados, você pode:
- Gerar relatórios personalizados que reflitam os horários de trabalho reais.  
- Sincronizar cronogramas do Microsoft Project com sistemas externos (ERP, BI, etc.).  
- Realizar análises de “e se” modificando as configurações do calendário programaticamente.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- Java Development Kit (JDK) instalado em seu sistema.  
- Biblioteca Aspose.Tasks for Java. Você pode baixá‑la [aqui](https://releases.aspose.com/tasks/java/).

## Importar Pacotes
Primeiro, importe as classes necessárias do Aspose.Tasks para seu projeto Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Etapa 1: Definir Diretório de Dados
Defina a pasta que contém seu arquivo *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Substitua `"Your Data Directory"` pelo caminho absoluto da pasta onde **project.mpp** está localizado.

## Etapa 2: Definir Unidades de Tempo
Crie constantes que ajudam a converter a representação interna de tempo em horas legíveis.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Esses valores são expressos em microssegundos, que é como o Aspose.Tasks armazena o tempo internamente.

## Etapa 3: Criar Instância do Projeto
Carregue o arquivo Microsoft Project em um objeto `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

O construtor `Project` analisa o arquivo *.mpp* e torna todos os dados do projeto, incluindo calendários, acessíveis através da API.

## Etapa 4: Recuperar Informações dos Calendários
Obtenha a coleção de calendários definidos no projeto.

```java
CalendarCollection alCals = project.getCalendars();
```

Um projeto pode conter vários calendários (padrão, de recurso e personalizados). Essa coleção permite acesso a cada um deles.

## Etapa 5: Percorrer os Calendários
Itere por cada calendário, exibindo seu UID, nome e os dias úteis com as horas correspondentes.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

O loop interno verifica cada objeto `WeekDay`. Se o dia estiver marcado como útil, ele imprime o tipo de dia (Monday, Tuesday, …) junto com as horas de trabalho calculadas.

## Etapa 6: Exibir Mensagem de Conclusão
Indique que o processo de extração foi concluído.

```java
System.out.println("Process completed Successfully");
```

## Conclusão
Seguindo estas etapas, **agora você sabe como usar Aspose.Tasks para extrair informações do calendário do projeto** de um arquivo MS Project usando Java. Você pode integrar essa lógica em aplicações maiores, automatizar relatórios ou sincronizar cronogramas com outros sistemas corporativos.

## Perguntas Frequentes

**Q: Posso usar Aspose.Tasks com outras linguagens de programação?**  
A: Sim, o Aspose.Tasks suporta várias plataformas e linguagens, incluindo .NET, C++, Python e Java.

**Q: Existe uma versão de avaliação gratuita do Aspose.Tasks?**  
A: Sim, você pode baixar uma versão de avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Como posso obter suporte para Aspose.Tasks?**  
A: Você pode obter suporte no fórum da comunidade Aspose.Tasks [aqui](https://forum.aspose.com/c/tasks/15).

**Q: Posso comprar uma licença temporária para Aspose.Tasks?**  
A: Sim, licenças temporárias estão disponíveis para compra [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Onde encontro documentação detalhada do Aspose.Tasks?**  
A: Você pode consultar a documentação [aqui](https://reference.aspose.com/tasks/java/).

---

**Última atualização:** 2025-12-20  
**Testado com:** Aspose.Tasks for Java 24.12 (mais recente na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}