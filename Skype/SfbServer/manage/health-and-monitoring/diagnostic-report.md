---
title: Rapporto di diagnostica in Skype for Business Server
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Riepilogo: informazioni sul rapporto di diagnostica in Skype for Business Server.'
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041993"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Rapporto di diagnostica in Skype for Business Server
 
**Riepilogo:** Informazioni sul rapporto di diagnostica in Skype for Business Server.
  
Nel Rapporto di diagnostica vengono fornite informazioni per la diagnostica e la risoluzione dei problemi di una sessione non riuscita. Queste informazioni includono l'ID diagnostica e l'intestazione di diagnostica segnalati quando la sessione ha avuto esito negativo. L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione di tale ID. Nel rapporto possono inoltre essere inclusi per la risoluzione dei problemi dettagli importanti, noti al componente di segnalazione errori. Ad esempio:
  
- Codice di causa fornito dal gateway PSTN che ha generato il problema. Se una chiamata in uscita ha esito negativo sulla rete PSTN, viene generato automaticamente un codice di causa ISUP (ISDN User Part). Un gateway PSTN ad esempio può inviare un codice di causa 34 per indicare l'indisponibilità di circuiti o canali per effettuare la chiamata.
    
- FQDN del peer, porta ed errori Winsock per i problemi di connettività.
    
- Nomi ricercati per i problemi di risoluzione DNS. Tale risoluzione ha luogo ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome di dispositivo specificato.
    
## <a name="accessing-the-diagnostic-report"></a>Accesso al Rapporto di diagnostica

È possibile accedere al rapporto di diagnostica facendo clic sulla metrica del rapporto di diagnostica (dettaglio) nel [rapporto Dettagli sessione peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) o nel rapporto Dettagli conferenza.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il Rapporto di diagnostica.
  
## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica per ogni sessione.
  
**Metriche del Rapporto di diagnostica**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Ora rapporto** <br/> |No  <br/> |Data e ora di registrazione del rapporto.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato per la sessione non riuscita.  <br/> |
|**Tipo di richiesta** <br/> |No  <br/> |Tipo di richiesta SIP non riuscita. Ad esempio, INVITE, BYE o SERVICE.  <br/> |
|**Source** <br/> |No  <br/> |Origine dell'errore.  <br/> |
|**URI utente di origine** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Da agente utente** <br/> |No  <br/> |Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.  <br/> |
|**Tipo di contenuto** <br/> |No  <br/> |Tipo di contenuto multimediale con errori. Un tipo di contenuto comune è ad esempio Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per gli annunci di sessione, gli inviti per le sessioni e altre forme di avvio di sessioni multimediali.  <br/> |
|**Applicazione** <br/> |No  <br/> |Applicazione coinvolta nell'errore.  <br/> |
|**URI utente di destinazione** <br/> |No  <br/> |Indirizzo SIP dell'utente che è stato invitato nella sessione.  <br/> |
|**Tempi partecipazione conferenza (ms)** <br/> |No  <br/> |Intervallo di tempo, in millisecondi, che è stato necessario all'utente per partecipare alla conferenza.  <br/> |
|**Intestazione di diagnostica** <br/> |No  <br/> |Descrizione dell'ID diagnostica.  <br/> |
   
È possibile trovare un elenco di errori diagnostici nella [pagina di intestazione MS-Diagnostics](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx).
  

