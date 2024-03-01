---
title: Recuperar informações do calendário do MS Project em Aspose.Tasks
linktitle: Recuperar informações do calendário em Aspose.Tasks
second_title: API Java Aspose.Tasks
description: Aprenda como recuperar informações do calendário do MS Project usando Aspose.Tasks para Java. Guia passo a passo para acessar os detalhes do calendário de forma programática.
type: docs
weight: 14
url: /pt/java/project-file-operations/retrieve-calendar-info/
---
## Introdução
Neste tutorial, exploraremos como recuperar informações de calendário de arquivos do Microsoft Project usando a biblioteca Aspose.Tasks para Java. Aspose.Tasks fornece recursos poderosos para manipular dados do projeto, incluindo acesso a detalhes do calendário, como dias e horas úteis.
## Pré-requisitos
Antes de começarmos, certifique-se de ter o seguinte:
- Conhecimento básico de programação Java.
- Java Development Kit (JDK) instalado em seu sistema.
-  Aspose.Tasks para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/java/).
## Importar pacotes
Primeiro, você precisa importar os pacotes necessários em seu código Java para usar as funcionalidades do Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Agora vamos dividir o exemplo fornecido em várias etapas para uma melhor compreensão.
## Etapa 1: definir diretório de dados
```java
String dataDir = "Your Data Directory";
```
 Substituir`"Your Data Directory"` com o caminho para o diretório de arquivos do seu projeto.
## Passo 2: Definir Unidades de Tempo
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Essas constantes representam unidades de tempo em microssegundos.
## Etapa 3: Criar Instância do Projeto
```java
Project project = new Project(dataDir + "project.mpp");
```
 Esta linha cria uma instância do`Project` class, inicializando-a com o caminho para o arquivo do projeto (`project.mpp`).
## Etapa 4: recuperar informações dos calendários
```java
CalendarCollection alCals = project.getCalendars();
```
Aqui recuperamos uma coleção de calendários presentes no arquivo do projeto.
## Etapa 5: iterar pelos calendários
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informações do calendário
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterar durante a semana
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Tempo em milissegundos
            double time = ts / (OneHour); // Converter para horas
            if (wd.getDayWorking()) {
                // Exibir dias e horários úteis
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Este loop percorre cada calendário e imprime seu UID, nome e dias úteis com os respectivos horários de trabalho.
## Etapa 6: exibir mensagem de conclusão
```java
System.out.println("Process completed Successfully");
```
Por fim, é exibida uma mensagem indicando a conclusão do processo.
## Conclusão
Neste tutorial, aprendemos como recuperar informações de calendário de arquivos do MS Project usando Aspose.Tasks para Java. Seguindo essas etapas, você pode acessar e manipular com eficiência os dados do projeto em seus aplicativos Java.

## Perguntas frequentes
### P: Posso usar Aspose.Tasks com outras linguagens de programação?
R: Sim, Aspose.Tasks suporta múltiplas plataformas e linguagens de programação, incluindo .NET, C++, Python e Java.
### P: Existe uma avaliação gratuita disponível para Aspose.Tasks?
 R: Sim, você pode baixar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).
### P: Como posso obter suporte para Aspose.Tasks?
R: Você pode obter suporte no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).
### P: Posso comprar uma licença temporária para Aspose.Tasks?
 R: Sim, licenças temporárias estão disponíveis para compra[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso encontrar documentação detalhada para Aspose.Tasks?
 R: Você pode consultar a documentação[aqui](https://reference.aspose.com/tasks/java/).