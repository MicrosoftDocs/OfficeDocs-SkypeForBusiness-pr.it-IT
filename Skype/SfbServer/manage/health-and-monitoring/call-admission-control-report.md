---
title: Report di controllo di ammissione di chiamata in Skype for Business Server
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
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Riepilogo: informazioni sui report di controllo di ammissione di chiamata utilizzati in Skype for Business Server.'
ms.openlocfilehash: ce7f8e622ece066d58cbc2c23a6423e19b084622
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826526"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Report di controllo di ammissione di chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni sui rapporti di controllo di ammissione di chiamata usati in Skype for Business Server.
  
Il Rapporto controllo di ammissione di chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza sottoposte alle limitazioni imposte dal servizio Controllo di ammissione di chiamata. Il controllo di ammissione di chiamata consente agli amministratori di consentire (o non consentire) sessioni di comunicazione basate su vincoli di larghezza di banda. Gli amministratori possono ad esempio creare criteri che limitano la larghezza di banda disponibile per le chiamate vocali e video. Se il limite di larghezza di banda viene raggiunto, non è possibile avviare ulteriori chiamate vocali o video se prima non termina una delle chiamate in corso liberando le risorse di rete necessarie.
  
## <a name="accessing-the-call-admission-control-report"></a>Accesso al Rapporto controllo di ammissione di chiamata

È possibile accedere al Rapporto controllo di ammissione di chiamata dalla home page di Relazioni monitoraggio. Dal Rapporto controllo di ammissione di chiamata è possibile eseguire il drill-down nei report seguenti:
  
- Rapporto Dettagli conferenza-per accedere a questo rapporto, fare clic sulla metrica dettagli da una sessione di conferenza. 
    
- Rapporto Dettagli sessione peer-to-peer-per accedere a questo rapporto, fare clic sulla metrica Dettagli per una sessione peer-to-peer.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Utilizzare al meglio il Rapporto controllo di ammissione di chiamata

Per visualizzare un elenco delle chiamate non riuscite per larghezza di banda insufficiente, selezionare Chiamate rifiutate a causa del controllo di ammissione di chiamata dall'elenco a discesa Categoria chiamata. La maggior parte delle chiamate restituite avrà probabilmente l'ID diagnostica 5:
  
Larghezza di banda insufficiente per stabilire la sessione. Tentare il reindirizzamento PSTN.
  
Questo indica che le limitazioni imposte dal servizio Controllo di ammissione di chiamata hanno impedito l'esecuzione della chiamata nella rete VoIP.
  
## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto controllo di ammissione di chiamata consente di filtrare le chiamate in base all'utente che le ha avviate o all'utente chiamato. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppabili per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri applicabili al Rapporto controllo di ammissione di chiamata.
  
**Filtri del Rapporto controllo di ammissione di chiamata**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 7/17/12015 1:00 PM  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/17/12015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/13/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[Tutti]** per visualizzare dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.<br/> |
|**Tipo di attività** <br/> | Selezionare una delle attività seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Categoria chiamata** <br/> | Indica il motivo per cui è stato utilizzato il controllo di ammissione chiamata. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Chiamate rifiutate a causa del controllo di ammissione di chiamata <br/>  Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

Nella tabella seguente sono elencate le informazioni riportate nel Rapporto controllo di ammissione di chiamata per le sessioni peer-to-peer, ovvero che coinvolgono solo due partecipanti.
  
**Metriche per le sessioni peer-to-peer**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettagli** <br/> |No  <br/> |Se si fa clic su questa opzione, nel rapporto viene visualizzato un rapporto dettagliato sulla sessione peer-to-peer specificata.  <br/> |
|**Da utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**A utente** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che è stato invitato a partecipare alla sessione.  <br/> |
|**Modalità** <br/> |Sì  <br/> |Modalità di comunicazione, ad esempio audio e video, utilizzate durante la sessione.  <br/> |
|**Ora invito** <br/> |Sì  <br/> |Date e ora in cui è stato inviato l'invito iniziale alla sessione alla persona indicata in Da utente.  <br/> |
|**Ora risposta** <br/> |Sì  <br/> |Data e ora in cui è stata ricevuta l'informazione che l'invito è stato accettato.  <br/> |
|**Ora fine** <br/> |Sì  <br/> |Data e ora di fine della sessione.  <br/> |
|**ID diagnostica** <br/> |Sì  <br/> |Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori. Le intestazioni di diagnostica sono facoltative (è possibile che non siano incluse in alcune sessioni SIP) e gli ID diagnostica vengono riportati solo per le sessioni in cui si sono verificati problemi.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni riportate nel Rapporto di controllo di ammissione di chiamata per le sessioni di conferenza, ovvero che coinvolgono almeno tre partecipanti.
  
**Metriche per le sessioni di conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**URI conferenza** <br/> |Sì  <br/> |Identificatore univoco della conferenza. Se si fa clic su questa opzione, nel rapporto vengono visualizzati i singoli partecipanti alla conferenza.  <br/> |
|**Organizzatore** <br/> |Sì  <br/> |Indirizzo SIP dell'utente che ha organizzato la conferenza.  <br/> |
|**Pool** <br/> |Sì  <br/> |Server perimetrale utilizzato nella conferenza.  <br/> |
|**Ora inizio** <br/> |Sì  <br/> |Data e ora di inizio della conferenza.  <br/> |
|**Ora fine** <br/> |Sì  <br/> |Data e ora di fine della conferenza.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Metriche per i singoli partecipanti alla conferenza

Nella tabella seguente sono elencate le informazioni riportate nel Rapporto di controllo di ammissione di chiamata per i singoli partecipanti alla conferenza.
  
**Metriche per i singoli partecipanti alla conferenza**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ruolo** <br/> |No  <br/> |Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.  <br/> |
|**Partecipante** <br/> |No  <br/> |Indirizzo SIP del partecipante alla conferenza.  <br/> |
|**Connettività** <br/> |No  <br/> |Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.  <br/> |
|**Modalità** <br/> |No  <br/> |Tipo di conferenza, ad esempio audio/video.  <br/> |
|**Ora partecipazione** <br/> |No  <br/> |Data e ora in cui il partecipante si è unito alla conferenza.  <br/> |
|**Ora uscita** <br/> |No  <br/> |Data e ora in cui il partecipante è uscito dalla conferenza.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.  <br/> |
   

