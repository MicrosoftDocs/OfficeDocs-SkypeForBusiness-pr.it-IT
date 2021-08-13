---
title: Rapporto elenco errori in Skype for Business Server
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
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Riepilogo: informazioni sul Rapporto elenco errori in Skype for Business Server.'
ms.openlocfilehash: b132982af91f81af1ac1d151853a3f7fdc597ff31476e6a5484fc04b9d9efa4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301352"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Rapporto elenco errori in Skype for Business Server 
 
**Riepilogo:** Informazioni sul Rapporto elenco errori in Skype for Business Server.
  
Nel Rapporto Elenco errori vengono fornite informazioni sui singoli partecipanti che hanno preso parte a una sessione di conferenza o peer-to-peer in cui si sono verificati problemi. Tali informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID diagnostica associati all'errore.
  
## <a name="accessing-the-failure-list-report"></a>Accesso al Rapporto Elenco errori

Per accedere al Rapporto elenco errori, fare clic su una delle metriche seguenti nel Rapporto distribuzione errori [in Skype for Business Server](failure-distribution-report.md):
  
- Motivi diagnostica principali (sessioni)
    
- Modalità principali (sessioni)
    
- Pool principali (sessioni)
    
- Origini principali (sessioni)
    
- Componenti principali (sessioni)
    
- Utenti di origine principali (sessioni)
    
- Utenti di destinazione principali (sessioni)
    
- Agenti utenti di origine principali (sessioni)
    
Dal Rapporto elenco errori è possibile accedere al Rapporto dettagli sessione [peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) facendo clic sulla metrica Dettagli sessione per una sessione peer-to-peer. È inoltre possibile accedere al Rapporto Dettagli conferenza facendo clic sulla metrica Conferenza per una conferenza.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Utilizzo ottimale del Rapporto Elenco errori

Nel Rapporto Elenco errori è possibile visualizzare una descrizione di ogni codice di risposta o di ogni ID diagnostica semplicemente posizionando il puntatore del mouse sul valore desiderato. Se ad esempio si posiziona il puntatore del mouse su Diagnostic ID 7025, in una descrizione comando verrà visualizzato quanto segue:
  
Internal server error creating media for user.
  
È importante notare che il Rapporto Elenco errori non consente di recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione con problemi, né consente di determinare quali utenti hanno partecipato più spesso a una sessione con problemi. Tale rapporto innanzitutto non dispone di funzionalità di filtro. Se però i dati vengono esportati e convertiti in un file con valori delimitati da virgole, è possibile utilizzare Windows PowerShell per trovare le risposte a domande come queste. Si supponga ad esempio di salvare i dati in un file CSV denominato C:\Data\Failure_List.csv. In base ai dati salvati in tale file, questo comando elencherà tutti gli utenti che hanno partecipato ad almeno una sessione con problemi: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Tale comando restituirà un elenco simile al seguente:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Questi due comandi restituiscono il numero totale di sessioni con problemi a cui ha partecipato ogni utente:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Verranno restituiti dati simili ai seguenti:
  
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

Nessuno. Non è possibile filtrare il Rapporto elenco errori.
  
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto elenco errori per ogni chiamata non riuscita.
  
**Metriche del Rapporto elenco errori**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ora rapporto** <br/> |No  <br/> |Data e ora di registrazione del rapporto.  <br/> |
|**Richiesta** <br/> |No  <br/> |Tipo di richiesta SIP non riuscita. Ad esempio, INVITE o BYE.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato per la conferenza non riuscita.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.  <br/> |
|**Tempo costo partecipazione (ms)** <br/> |No  <br/> |Intervallo di tempo, in millisecondi, necessario all'utente per partecipare alla conferenza.  <br/> |
|**Da utente** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la chiamata.  <br/> |
|**Da agente utente** <br/> |No  <br/> |Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.  <br/> |
|**A utente** <br/> |No  <br/> |Indirizzo SIP dell'utente chiamato.  <br/> |
   

