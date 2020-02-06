---
title: Report elenco chiamate di Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: "Riepilogo: informazioni sull'applicazione Response Group in Skype for Business Server."
ms.openlocfilehash: 0d3d0001c5537135c2a81ea39706b0def6718fe0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818107"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Report elenco chiamate di Response Group in Skype for Business Server

**Riepilogo:** Informazioni sull'applicazione Response Group in Skype for Business Server.

L'applicazione Response Group offre un modo per Skype for Business Server di rispondere e instradare le telefonate in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate di Response Group non vengono instradate a una singola persona, ma vengono invece indirizzate a un team di persone denominato gruppo di agenti. Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Skype for Business Server può automaticamente instradare la chiamata al primo agente del supporto tecnico disponibile. In alternativa, Skype for Business Server può porre una serie di domande ("premere 1 se si verificano problemi hardware. Premere 2 Se si verificano problemi di software. Premere 3 Se si verificano problemi di rete. ") quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.

Il report elenco delle chiamate di Response Group rappresenta una raccolta di chiamate effettuate per un determinato periodo di tempo e per un determinato tipo di chiamata. Il report sull'utilizzo dei gruppi di risposte (che deve essere aperto per primo prima di poter aprire il report di elenco delle chiamate di Response Group) riconosce i tipi di chiamata seguenti:

- **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

- **Chiamate di successo**. Numero totale di chiamate rilevate dall'applicazione Response Group.

- **Chiamate offerte**. Numero totale di chiamate trasferite a un agente di Response Group.

- **Chiamate con risposta**. Numero totale di chiamate effettivamente risolte da un agente di Response Group.

- **Percentuale di chiamate abbandonate.** Percentuale di chiamate ricevute dall'applicazione Response Group, ma non è stata mai risolta da un agente. Questo valore viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute. Ad esempio, se sono state ricevute 10 chiamate e 7 sono state risolte, è necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta. Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.

- **Chiamate trasferite**. Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.

## <a name="accessing-the-response-group-call-list-report"></a>Accesso al report elenco chiamate di Response Group

È possibile accedere al report di elenco delle chiamate di Response Group solo facendo clic su una delle metriche seguenti disponibili nel [report sull'utilizzo dei gruppi di risposte in Skype for Business Server](response-group-usage-report.md):

- Chiamate ricevute

- Chiamate di successo

- Chiamate offerte

- Chiamate con risposta

- Chiamate trasferite

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Sfruttare al meglio il report elenco chiamate di Response Group

Il report elenco delle chiamate di Response Group consente di limitare i dati visualizzati alle chiamate che coinvolgono un determinato flusso di lavoro di Response Group. A questo scopo, devi immettere l'URI del flusso di lavoro (l'indirizzo SIP del flusso di lavoro) nella casella URI flusso di lavoro. Prima di poterlo fare, tuttavia, devi essere effettivamente in grado di vedere la casella URI flusso di lavoro. Per visualizzare le opzioni di filtro per il report elenco chiamate di Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del report.

Tieni presente che l'elenco delle chiamate di gruppo di risposta non Visualizza le informazioni sul codice di risposta o sull'ID di diagnostica se tieni premuto il mouse su una di queste metriche. Per altre informazioni, è possibile notare il codice di risposta e/o l'ID di diagnostica e quindi cercare tali valori nel [report errori principali in Skype for Business Server](top-failures-report.md).

una domanda simile alla seguente: "quale singolo flusso di lavoro ha ricevuto la maggior parte delle chiamate?", è possibile eseguire le operazioni seguenti:

1. Nel report sull'utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica chiamate ricevute. Che aprirà il report elenco delle chiamate di Response Group.

2. Esportare i dati visualizzati nel report elenco chiamate di Response Group. Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi usare Excel per convertire i dati in un file con valori separati da virgole.

3. Eseguire le analisi con Windows PowerShell.

Ad esempio, se i dati sono stati salvati in un file denominato C:\Data\ Response_Group_Call_List_Report. csv, è possibile usare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel report:

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

In questo modo le informazioni sono simili alle seguenti:

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report elenco chiamate di Response Group.

**Filtri dei report elenco chiamate di Response Group**


| **Nome**               | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Da** <br/>         | Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
| **A** <br/>           | Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/>        |
| **URI del flusso di lavoro** <br/> | Consente di limitare i dati restituiti al flusso di lavoro del gruppo di risposte specificato. Per usare questo filtro, immettere l'indirizzo SIP del flusso di lavoro. Ad esempio:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Chiamate** <br/>        | Puoi selezionare uno dei tipi di chiamata seguenti: <br/>  Chiamate ricevute <br/>  Chiamate di successo <br/>  Chiamate offerte <br/>  Chiamate con risposta <br/>  Chiamate trasferite <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di elenco delle chiamate di Response Group per ogni chiamata ricevuta dall'applicazione Response Group.

**Metriche del report elenco chiamate di Response Group**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Chiamante** <br/> |No  <br/> |Indirizzo SIP del chiamante.  <br/> |
|**Flusso** <br/> |No  <br/> |Indirizzo SIP del flusso di lavoro Response Group.  <br/> |
|**Ora di inizio** <br/> |No  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**Ora di fine** <br/> |No  <br/> |Data e ora di fine della chiamata.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato quando la sessione non è riuscita.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.  <br/> |


