---
title: Rapporto elenco chiamate di Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: "Riepilogo: informazioni sull'applicazione Response Group in Skype for Business Server."
ms.openlocfilehash: 0761e58027260a4528f7764858ba54d00b4a9c146f32945222a4ed6763912b0e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54345693"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Rapporto elenco chiamate di Response Group in Skype for Business Server

**Riepilogo:** Informazioni sull'applicazione Response Group in Skype for Business Server.

L'applicazione Response Group consente a Skype for Business Server di rispondere e instradare le chiamate telefoniche in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate a Response Group non vengono instradate a una singola persona ma piuttosto a un team di persone definito gruppo di agenti. Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Skype for Business Server instradare automaticamente la chiamata al primo agente dell'help desk disponibile. In alternativa, Skype for Business Server può porre una serie di domande ("Premere 1 se si verificano problemi hardware. Premere 2 in caso di problemi software. Premere 3 se si verificano problemi di rete.") e quindi instradare la chiamata all'agente dell'help desk più appropriato in base alla risposta a tali domande.

Il Rapporto Elenco chiamate Response Group è una raccolta di chiamate di un determinato tipo effettuate per un determinato periodo di tempo. Il Rapporto di utilizzo di Response Group, che deve essere aperto prima di poter aprire il Rapporto Elemento chiamate Response Group, riconosce i tipi di chiamate seguenti:

- **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

- **Chiamate riuscite**. Numero totale di chiamate prese dall'applicazione Response Group.

- **Chiamate offerte**. Numero totale di chiamate trasferite a un agente Response Group.

- **Chiamate con risposta**. Numero totale di chiamate che hanno effettivamente ricevuto una risposta da un agente Response Group.

- **Percentuale di chiamate abbandonate.** Percentuale di chiamate ricevute dall'applicazione Response Group alle quali però non è stata mai fornita risposta da un agente. Questo valore viene calcolato sottraendo il valore di Chiamate con risposta dal valore di Chiamate ricevute e quindi dividendo tale valore per il numero di Chiamate ricevute. Se ad esempio si ricevono 10 chiamate, di cui 7 con risposta, sarà necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta. Tale valore verrà poi diviso per 10 e si otterrà una percentuale di chiamate interrotte pari al 30%.

- **Chiamate trasferite**. Numero totale di chiamate di Response Group trasferite a causa del timeout o dell'overflow di una coda.

## <a name="accessing-the-response-group-call-list-report"></a>Accesso al Rapporto Elenco chiamate Response Group

È possibile accedere al Rapporto elenco chiamate di Response Group solo facendo clic su una delle metriche seguenti disponibili nel [Rapporto utilizzo Response Group in Skype for Business Server](response-group-usage-report.md):

- Chiamate ricevute

- Chiamate riuscite

- Chiamate offerte

- Chiamate con risposta

- Chiamate trasferite

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Utilizzo ottimale del Rapporto Elenco chiamate Response Group

Il Rapporto Elenco chiamate Response Group consente di limitare i dati visualizzati alle chiamate che interessano un particolare flusso di lavoro di Response Group. A tale scopo, è necessario immettere l'URI del flusso di lavoro, ovvero l'indirizzo SIP del flusso di lavoro, nella casella URI flusso di lavoro. Prima di poter immettere tali informazioni, è tuttavia necessario che la casella URI flusso di lavoro sia visibile. Per visualizzare le opzioni di filtro per il Rapporto Elenco chiamate Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del rapporto.

Si noti che nell'elenco chiamate Response Group non vengono visualizzate informazioni relative al codice di risposta o all'ID diagnostica posizionando il puntatore del mouse su una di queste metriche. Se sono necessarie ulteriori informazioni, è possibile prendere nota del codice di risposta e/o dell'ID diagnostica e quindi cercare tali valori nel Rapporto errori principali [in Skype for Business Server](top-failures-report.md).

Per sapere ad esempio quale singolo flusso di lavoro ha ricevuto il maggior numero di chiamate, è possibile eseguire le operazioni seguenti:

1. Nel Rapporto di utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica Chiamate ricevute. Verrà aperto il Rapporto Elenco chiamate Response Group.

2. Esportare i dati visualizzati nel Rapporto Elenco chiamate Response Group. Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi utilizzare Excel per convertire tali dati in un file con valori delimitati da virgole.

3. Eseguire le analisi utilizzando Windows PowerShell.

Ad esempio, se i dati sono stati salvati in un file denominato C:\Data\Response_Group_Call_List_Report.csv, sarà quindi possibile utilizzare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel rapporto:

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

Verranno restituite informazioni simili alle seguenti:

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

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri applicabili al rapporto Elenco chiamate Response Group.

**Filtri rapporto Elenco chiamate Response Group**


| **Nome**               | **Descrizione**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **From** <br/>         | Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
| **To** <br/>           | Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/>        |
| **URI flusso di lavoro** <br/> | Consente di limitare i dati restituiti al flusso di lavoro di Response Group specificato. Per utilizzare questo filtro, immettere l'indirizzo SIP del flusso di lavoro, ad esempio:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Chiamate** <br/>        | È possibile selezionare uno dei tipi di chiamata seguenti: <br/>  Chiamate ricevute <br/>  Chiamate completate <br/>  Chiamate offerte <br/>  Chiamate con risposta <br/>  Chiamate trasferite <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel rapporto Elenco chiamate Response Group Call per ogni chiamata ricevuta dall'applicazione Response Group.

**Metriche del rapporto Elenco chiamate Response Group**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Chiamante** <br/> |No  <br/> |Indirizzo SIP del chiamante.  <br/> |
|**Flusso di lavoro** <br/> |No  <br/> |Indirizzo SIP del flusso di lavoro Response Group.  <br/> |
|**Ora inizio** <br/> |No  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**Ora fine** <br/> |No  <br/> |Data e ora di fine della chiamata.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato per la sessione non riuscita.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.  <br/> |


