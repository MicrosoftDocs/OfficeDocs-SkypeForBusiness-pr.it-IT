---
title: Report elenco errori in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Riepilogo: informazioni sul report elenco errori in Skype for Business Server.'
ms.openlocfilehash: d0ba76974d99b123c99e3df40a6850736423ab73
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992823"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Report elenco errori in Skype for Business Server 
 
**Riepilogo:** Informazioni sul report elenco errori in Skype for Business Server.
  
Il report elenco errori contiene informazioni sui singoli partecipanti che hanno partecipato a una sessione peer-to-peer o conferenza non riuscita. Queste informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID di diagnostica associati all'errore.
  
## <a name="accessing-the-failure-list-report"></a>Accesso al report elenco errori

Per accedere al report elenco errori, fare clic su una delle metriche seguenti nel [report distribuzione errori in Skype for Business Server](failure-distribution-report.md):
  
- Principali motivi diagnostici (sessioni)
    
- Modalità top (sessioni)
    
- Pool principali (sessioni)
    
- Origini principali (sessioni)
    
- Componenti principali (sessioni)
    
- Inizio da utenti (sessioni)
    
- Inizio per gli utenti (sessioni)
    
- Inizio da agenti utente (sessioni)
    
Nel report elenco errori è possibile accedere al [report Dettagli sessione peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) facendo clic sulla metrica di dettaglio della sessione per una sessione peer-to-peer. È anche possibile accedere al report Dettagli conferenza facendo clic sulla metrica conferenza per una conferenza.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Sfruttare al meglio il report elenco errori

Nel report elenco errori è possibile visualizzare una descrizione per ogni codice di risposta o ogni ID di diagnostica semplicemente tenendo premuto il mouse su tale valore. Ad esempio, se si tiene premuto il mouse sull'ID di diagnostica 7025, in una descrizione comandi verranno visualizzati i seguenti elementi:
  
Errore del server interno che crea elementi multimediali per l'utente.
  
È importante notare che il report elenco errori non offre un modo semplice per recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita, né offre un modo per determinare gli utenti più spesso coinvolti in un errore sessione. Per prima cosa, il report elenco errori non ha funzionalità di filtro. Tuttavia, se si esportano i dati e quindi lo si converte in un file con valori delimitati da virgole, è possibile usare Windows PowerShell per trovare le risposte a domande come quelle. Supponiamo ad esempio di salvare i dati in un. File CSV denominato C:\Data\ Failure_List. csv. In base ai dati salvati nel file, questo comando elenca tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Questo comando restituirà un elenco simile al seguente:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Questi due comandi segnalano il numero totale di sessioni non riuscite in cui ogni utente è coinvolto:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Che restituirà dati simili a questi:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report elenco errori.
  
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report elenco errori per ogni chiamata non riuscita.
  
**Metriche rapporto Elenco errori**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tempo segnalato** <br/> |No  <br/> |Data e ora in cui il report è stato registrato.  <br/> |
|**Richiesta** <br/> |No  <br/> |Tipo di richiesta SIP non riuscito. Ad esempio, invita o BYE.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato quando la conferenza non è riuscita.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.  <br/> |
|**Tempo di costo di partecipazione (MS)** <br/> |No  <br/> |Intervallo di tempo (in millisecondi) necessario affinché l'utente partecipi alla conferenza.  <br/> |
|**Dall'utente** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la chiamata.  <br/> |
|**Dall'agente utente** <br/> |No  <br/> |Software usato dall'endpoint dell'utente che ha avviato la chiamata.  <br/> |
|**All'utente** <br/> |No  <br/> |Indirizzo SIP dell'utente che veniva chiamato.  <br/> |
   

