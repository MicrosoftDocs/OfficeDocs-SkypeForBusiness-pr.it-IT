---
title: Report Dettagli sessione peer-to-peer in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Riepilogo: informazioni sul report Dettagli sessione peer-to-peer in Skype for Business Server.'
ms.openlocfilehash: 768609c68e37eebf46c350009638b960066f9456
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188735"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Report Dettagli sessione peer-to-peer in Skype for Business Server
 
**Riepilogo:** Informazioni sul report Dettagli sessione peer-to-peer in Skype for Business Server.
  
Il report Dettagli sessione peer-to-peer restituisce informazioni dettagliate su una sessione peer-to-peer. Ad esempio, se selezioni una sessione di messaggistica istantanea, il report indica il numero di messaggi inviati da ognuno dei due utenti della sessione.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Accesso al report Dettagli sessione peer-to-peer

È possibile accedere al report Dettagli sessione peer-to-peer da uno dei report seguenti (a cui è possibile accedere tutti dalla Home page dei report di monitoraggio):
  
- Rapporto inventario telefoni IP
    
- Rapporto attività utente
    
- Rapporto controllo di ammissione di chiamata
    
- Rapporto Elenco errori 
    
Dall'interno del report Dettagli sessione peer-to-peer è possibile accedere al [report di diagnostica in Skype for Business Server](diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (Dettagli). Per accedere al report errori principali, è anche possibile fare clic su una delle due metriche seguenti:
  
- Risposta
    
- ID diagnostica
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Sfruttare al meglio il report Dettagli sessione peer-to-peer

Il report Dettagli sessione peer-to-peer include un numero elevato di metriche, molte delle quali potrebbero non essere familiari con gli amministratori di sistema. Spesso, tuttavia, è possibile visualizzare una descrizione comando che offre una breve descrizione di tale metrica semplicemente tenendo il mouse sopra l'etichetta metrica.
  
Tieni presente che le metriche effettive visualizzate in un determinato report dipendono dal tipo di sessione peer-to-peer selezionata. Una sessione audio/video segnalerà un set di metriche diverso rispetto a una sessione di messaggistica istantanea.
  
È anche possibile tenere il mouse sopra il codice di risposta e le metriche degli ID diagnostici per ottenere una descrizione dei valori seguenti:
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report del dettaglio della sessione peer-to-peer.
  
## <a name="session-information-metrics"></a>Metriche delle informazioni sulla sessione

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni sessione.
  
**Metriche delle informazioni sulla sessione**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**FQDN del pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale coinvolto nella sessione.  <br/> |
|**Invitare il tempo** <br/> |Data e ora in cui l'invito alla sessione è stato inviato in origine.  <br/> |
|**Tempo di risposta** <br/> |Data e ora in cui è stata ricevuta l'accettazione dell'invito.  <br/> |
|**Dall'utente** <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Dall'agente utente** <br/> |Software usato dall'endpoint dell'utente che ha avviato la sessione.  <br/> |
|**È da utente interno** <br/> |Indica se l'utente che ha avviato la sessione è stato connesso alla rete interna.  <br/> |
|**Viene dall'utente integrato con il telefono da tavolo** <br/> |Indica se l'endpoint usato dall'utente che ha avviato la sessione è integrato con il telefono desktop.  <br/> |
|**Priorità della sessione** <br/> |Priorità assegnata alla sessione. Le priorità valide sono: sconosciuto; Non urgente; Normale Urgente e di emergenza.  <br/> |
|**Codice di risposta** <br/> |Codice di risposta SIP inviato quando la sessione non è riuscita.  <br/> |
|**Front-end** <br/> |Nome del server front-end usato nella conferenza.  <br/> |
|**Tempo di acquisizione** <br/> |Data e ora in cui sono state registrate le informazioni sulla sessione.  <br/> |
|**Ora di fine** <br/> |Data e ora di fine della sessione.  <br/> |
|**All'utente** <br/> |Indirizzo SIP dell'utente invitato alla sessione.  <br/> |
|**All'agente utente** <br/> |Software usato dall'endpoint dell'utente invitato alla sessione.  <br/> |
|**È l'utente interno** <br/> |Indica se l'utente invitato alla sessione è stato connesso alla rete interna.  <br/> |
|**È l'utente integrato con il telefono da tavolo** <br/> |Indica se l'endpoint usato dall'utente invitato alla sessione è integrato con il telefono desktop.  <br/> |
|**Viene riprovata la sessione** <br/> |Indica se la sessione è un tentativo di riprovare una sessione che non è riuscita in precedenza.  <br/> |
|**ID diagnostica** <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Posizionare il puntatore del mouse sul numero di ID per visualizzare informazioni aggiuntive su tale ID.  <br/> |
   
## <a name="metrics-for-modalities"></a>Metriche per le modalità

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni modalità di sessione.
  
**Metriche per le modalità**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Modalità** <br/> |No  <br/> |Modalità usate nella sessione. Ad esempio, messaggistica istantanea (IM) o trasferimento di file.  <br/> |
|**Da messaggi utente** <br/> |No  <br/> |Numero di messaggi inviati dall'utente che ha avviato la sessione.  <br/> |
|**Per i messaggi degli utenti** <br/> |No  <br/> |Numero di messaggi inviati dall'utente che è stato invitato a partecipare alla sessione.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Metriche per i report di diagnostica

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni report di diagnostica.
  
**Metriche per i report di diagnostica**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Dettaglio** <br/> |No  <br/> |Quando si fa clic su questo elemento, il report Mostra il rapporto di diagnostica per la sessione.  <br/> |
|**Tempo di report** <br/> |No  <br/> |Data e ora in cui il report è stato registrato.  <br/> |
|**Richiesta** <br/> |No  <br/> |Tipo di richiesta SIP. Ad esempio, invita o BYE.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.  <br/> |
|**Tipo di contenuto** <br/> |No  <br/> |Tipo di contenuto multimediale usato nella conferenza. Ad esempio, un tipo di contenuto comune è Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.  <br/> |
|**Segnalato da** <br/> |No  <br/> |Computer (ovvero client o server) che ha segnalato il problema.  <br/> |
   

