---
title: Rapporto dettagli sessione peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Riepilogo: informazioni sul Rapporto dettagli sessione peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 6ca45f05c3ee8346c6c6cac5bf5a1845be2d3a20
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774806"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Rapporto dettagli sessione peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto dettagli sessione peer-to-peer in Skype for Business Server.
  
Nel rapporto Dettagli sessione peer-to-peer vengono fornite informazioni dettagliate sulle sessioni peer-to-peer. Ad esempio, se si seleziona una sessione di messaggistica istantanea, nel rapporto sarà indicato il numero di messaggi inviato da ciascuno dei due utenti della sessione.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Accedere al Rapporto Dettagli sessione peer-to-peer

È possibile accedere al rapporto Dettagli sessione peer-to-peer da uno dei seguenti rapporti (ai quali è possibile accedere dalla pagina principale dei rapporti di monitoraggio):
  
- Rapporto inventario telefoni IP
    
- Rapporto attività utente
    
- Rapporto controllo di ammissione di chiamata
    
- Rapporto Elenco errori 
    
Dal Rapporto dettagli sessione peer-to-peer è possibile accedere al Rapporto di diagnostica [in Skype for Business Server](diagnostic-report.md) facendo clic sulla metrica Rapporto di diagnostica (dettagli). Facendo clic su una delle seguenti due metriche, è inoltre possibile accedere al Rapporto errori principali:
  
- Risposta
    
- ID diagnostica
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Utilizzare al meglio il Rapporto Dettagli sessione peer-to-peer

Il Rapporto Dettagli sessione peer-to-peer include molte metriche, alcune delle quali potrebbero essere sconosciute agli amministratori di sistema. Spesso, tuttavia, è possibile visualizzare un tooltip contenente la descrizione della metrica, semplicemente passando il mouse sull'etichetta della metrica.
  
Tenere sempre presente che le metriche reali mostrate in un rapporto dipendono dal tipo di sessione peer-to-peer selezionato. Una sessione audio/video riporta un set di metriche diverso rispetto a quello di una sessione di messaggistica istantanea.
  
Passando il mouse sulle metriche Codice di risposta e ID diagnostica, è possibile ottenere una descrizione dei valori:
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il rapporto Dettagli sessione peer-to-peer.
  
## <a name="session-information-metrics"></a>Metriche di informazioni sulla sessione

Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni sessione.
  
**Metriche di informazioni sulla sessione**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**FQDN pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o server perimetrale interessato dalla sessione.  <br/> |
|**Ora invito** <br/> |Data e ora in cui è stato inviato in origine l'invito alla sessione.  <br/> |
|**Ora risposta** <br/> |Data e ora in cui è stata ricevuta l'accettazione dell'invito.  <br/> |
|**Da utente** <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Da agente utente** <br/> |Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.  <br/> |
|**Da utente interno** <br/> |Indica se l'utente che ha avviato la sessione ha effettuato l'accesso alla rete interna.  <br/> |
|**Da utente integrato con telefono da tavolo** <br/> |Indica se l'endpoint utilizzato dall'utente che ha avviato la sessione è integrato con il telefono desktop dell'utente stesso.  <br/> |
|**Priorità sessione** <br/> |Priorità assegnata alla sessione. Le priorità valide sono: Sconosciuto, Non urgente, Normale, Urgente ed Emergenza.  <br/> |
|**Codice di risposta** <br/> |Codice di risposta SIP inviato quando la sessione non è riuscita.  <br/> |
|**Front End** <br/> |Nome del server Front End Server utilizzato nella conferenza.  <br/> |
|**Ora di acquisizione** <br/> |Data e ora in cui sono state registrate le informazioni sulla sessione.  <br/> |
|**Ora fine** <br/> |Data e ora di fine della sessione.  <br/> |
|**A utente** <br/> |Indirizzo SIP dell'utente invitato alla sessione.  <br/> |
|**Ad agente utente** <br/> |Software utilizzato dall'endpoint dell'utente invitato alla sessione.  <br/> |
|**A utente interno** <br/> |Indica se l'utente invitato alla sessione ha effettuato l'accesso alla rete interna.  <br/> |
|**A utente integrato con telefono da tavolo** <br/> |Indica se l'endpoint utilizzato dall'utente invitato alla sessione è integrato con il telefono desktop dell'utente stesso.  <br/> |
|**Sessione ripetuta** <br/> |Indica se la sessione è un tentativo di ripetizione di una sessione non riuscita in precedenza.  <br/> |
|**ID diagnostica** <br/> |Identificatore univoco, sotto forma di intestazione ms-diagnostics, allegato a un messaggio SIP che include spesso informazioni utili per la risoluzione degli errori. Posizionare il puntatore del mouse sull'ID per visualizzare informazioni aggiuntive sull'ID stesso.  <br/> |
   
## <a name="metrics-for-modalities"></a>Metriche per le modalità

Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni modalità di sessione.
  
**Metriche per le modalità**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Modalità** <br/> |No  <br/> |Modalità utilizzate nella sessione, ad esempio messaggistica istantanea o trasferimento di file.  <br/> |
|**Messaggi da utente** <br/> |No  <br/> |Numero di messaggi inviati dall'utente che ha avviato la sessione.  <br/> |
|**Messaggi a utente** <br/> |No  <br/> |Numero di messaggi inviati dall'utente invitato a partecipare alla sessione.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Metriche per i rapporti di diagnostica

Nella tabella seguente sono elencate le informazioni disponibili nel rapporto Dettagli sessione peer-to-peer per ogni rapporto di diagnostica.
  
**Metriche per i rapporti di diagnostica**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettagli** <br/> |No  <br/> |Quando si fa clic su questo elemento, nel rapporto viene visualizzato il rapporto di diagnostica per la sessione.  <br/> |
|**Ora rapporto** <br/> |No  <br/> |Data e ora di registrazione del rapporto.  <br/> |
|**Richiesta** <br/> |No  <br/> |Tipo di richiesta SIP, ad esempio INVITE o BYE.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.  <br/> |
|**Tipo di contenuto** <br/> |No  <br/> |Tipo di contenuto multimediale utilizzato nella conferenza. Un tipo di contenuto comune, ad esempio, è Application/sdp. SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per annunci di sessioni, inviti a sessioni e altre forme di avvio di sessioni multimediali.  <br/> |
|**Segnalato da** <br/> |No  <br/> |Computer, ovvero client o server, che ha segnalato il problema.  <br/> |
   

