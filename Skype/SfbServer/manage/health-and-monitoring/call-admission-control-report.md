---
title: Report di controllo ammissione chiamata in Skype for Business Server
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
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: "Riepilogo: informazioni sui report di controllo dell'ammissione alle chiamate usati in Skype for Business Server."
ms.openlocfilehash: 5a8df542e666975e207bd5a105cb4c1d7261b51f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818167"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Report di controllo ammissione chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni sui report di controllo dell'ammissione alle chiamate usati in Skype for Business Server.
  
Il report controllo ammissione chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza che sono state svolte in restrizioni impostate in posizione tramite il controllo di ammissione delle chiamate. Il controllo di ammissione delle chiamate consente agli amministratori di consentire o meno le sessioni di comunicazione basate sui vincoli di larghezza di banda. Ad esempio, gli amministratori possono creare criteri che impongono un limite alla quantità di larghezza di banda disponibile per le chiamate vocali e video. Se è stato raggiunto il limite di larghezza di banda, non è possibile inserire nuove chiamate vocali o videochiamate finché una delle chiamate correnti non è terminata e ha liberato le risorse di rete necessarie.
  
## <a name="accessing-the-call-admission-control-report"></a>Accesso al report di controllo ammissione chiamata

Il report controllo ammissione chiamata si accede dalla Home page dei report di monitoraggio. Nel report controllo ammissione chiamata è possibile eseguire il drill-down per uno dei report seguenti:
  
- Report Dettagli conferenza-per accedere a questo report, fare clic sulla metrica dettagli di una sessione di conferenza. 
    
- Report Dettagli sessione peer-to-peer-per accedere a questo report, fare clic sulla metrica Dettagli per una sessione peer-to-peer.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Uso ottimale del report di controllo dell'ammissione alle chiamate

Per ottenere un elenco delle chiamate non riuscite a causa della larghezza di banda insufficiente, selezionare chiamate rifiutate a causa del controllo di ammissione di chiamata nell'elenco a discesa categoria chiamata. La maggior parte delle chiamate restituite avrà probabilmente un ID di diagnostica pari a 5:
  
Larghezza di banda insufficiente per stabilire una sessione. Provare a eseguire la reinstradazione PSTN.
  
Ciò indica che le limitazioni del controllo di ammissione alle chiamate impedivano che la chiamata venisse eseguita nella rete VoIP.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report controllo ammissione chiamata consente di filtrare le chiamate dall'utente che ha avviato la chiamata o dall'utente che è stato chiamato. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report controllo ammissione chiamata.
  
**Filtri dei report di controllo ammissione chiamata**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Tipo di attività** <br/> | Tipo di attività. Selezionare una delle attività seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Categoria chiamata** <br/> | Indica il motivo per cui è stato usato CAC per la chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Chiamata rifiutata a causa del controllo di ammissione di chiamata <br/>  Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

La tabella seguente elenca le informazioni fornite nel report di controllo dell'ammissione delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.
  
**Metriche per le sessioni peer-to-peer**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettaglio** <br/> |No  <br/> |Quando si fa clic su questo elemento, il report Mostra un report Dettagli sessione peer-to-peer per la sessione specificata.  <br/> |
|**Dall'utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**All'utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente invitato a partecipare alla sessione.  <br/> |
|**Modalità** <br/> |Sì  <br/> |Modalità di comunicazione (ad esempio audio e video) usate durante la sessione.  <br/> |
|**Invitare il tempo** <br/> |Sì  <br/> |Data e ora in cui l'invito alla sessione iniziale è stato inviato all'utente da.  <br/> |
|**Tempo di risposta** <br/> |Sì  <br/> |Data e ora in cui è stata ricevuta l'accettazione dell'invito.  <br/> |
|**Ora di fine** <br/> |Sì  <br/> |Data e ora di fine della sessione.  <br/> |
|**ID diagnostica** <br/> |Sì  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione alle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.
  
**Metriche per le sessioni di conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**URI conferenza** <br/> |Sì  <br/> |Identificatore univoco per la conferenza. Quando si fa clic su questo elemento, il report Mostra i singoli partecipanti alla conferenza.  <br/> |
|**Organizzatore** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/> |
|**Pool** <br/> |Sì  <br/> |Server perimetrale usato nella conferenza.  <br/> |
|**Ora di inizio** <br/> |Sì  <br/> |Data e ora in cui è stata avviata la conferenza.  <br/> |
|**Ora di fine** <br/> |Sì  <br/> |Data e ora di fine della conferenza.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Metriche per singoli partecipanti alla conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione delle chiamate per singoli partecipanti alla conferenza.
  
**Metriche per singoli partecipanti alla conferenza**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ruolo** <br/> |No  <br/> |Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.  <br/> |
|**Partecipante** <br/> |No  <br/> |Indirizzo SIP del partecipante alla conferenza.  <br/> |
|**Connettività** <br/> |No  <br/> |Connettività di rete (in genere da interno o da esterno) per il partecipante.  <br/> |
|**Modalità** <br/> |No  <br/> |Tipo di conferenza (ad esempio, A/V Conferencing).  <br/> |
|**Tempo di partecipazione** <br/> |No  <br/> |Data e ora in cui il partecipante ha partecipato alla conferenza.  <br/> |
|**Ora di uscita** <br/> |No  <br/> |Data e ora in cui il partecipante ha lasciato la conferenza.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |
   

