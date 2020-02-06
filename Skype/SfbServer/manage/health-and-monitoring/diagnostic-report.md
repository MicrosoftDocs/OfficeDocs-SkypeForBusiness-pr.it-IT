---
title: Report di diagnostica in Skype for Business Server
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
description: 'Riepilogo: informazioni sul report di diagnostica in Skype for Business Server.'
ms.openlocfilehash: e8f89f1f5a013b40f7f5f105f49611542667a477
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817986"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Report di diagnostica in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di diagnostica in Skype for Business Server.
  
Il report di diagnostica fornisce informazioni di diagnostica e risoluzione dei problemi per una sessione non riuscita. Queste informazioni includono sia l'ID di diagnostica che l'intestazione di diagnostica segnalate quando la sessione non è riuscita. L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione associata per l'ID di diagnostica. Il report può anche contenere dettagli utili per la risoluzione dei problemi noti dal componente di creazione di report. Ad esempio:
  
- Il codice di causa fornito dal gateway PSTN che ha generato l'errore. Quando una chiamata in uscita ha esito negativo nella rete PSTN, viene generato automaticamente un codice di causa ISDN User Part (ISUP). Ad esempio, un gateway PSTN può inviare il codice di causa 34 per indicare che non è disponibile alcun circuito o canale per completare la chiamata.
    
- Errori di FQDN, porta e Winsock peer per i problemi di connettività.
    
- Nomi cercati per gli errori di risoluzione DNS. La risoluzione DNS viene applicata ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome del dispositivo specificato.
    
## <a name="accessing-the-diagnostic-report"></a>Accesso al report di diagnostica

È possibile accedere al report di diagnostica facendo clic sulla metrica rapporto di diagnostica (dettaglio) nel [report Dettagli sessione peer-to-peer in Skype for Business Server](peer-to-peer-session-detail-report.md) o nel report Dettagli conferenza.
  
## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report di diagnostica.
  
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica per ogni sessione.
  
**Metriche del report di diagnostica**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Tempo di report** <br/> |No  <br/> |Data e ora in cui il report è stato registrato.  <br/> |
|**Codice di risposta** <br/> |No  <br/> |Codice di risposta SIP inviato quando la sessione non è riuscita.  <br/> |
|**Tipo di richiesta** <br/> |No  <br/> |Tipo di richiesta SIP non riuscito. Ad esempio, invita, BYE o SERVICE.  <br/> |
|**Fonte** <br/> |No  <br/> |Origine dell'errore.  <br/> |
|**Da URI utente** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Dall'agente utente** <br/> |No  <br/> |Software usato dall'endpoint dell'utente che ha avviato la sessione.  <br/> |
|**ID diagnostica** <br/> |No  <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.  <br/> |
|**Tipo di contenuto** <br/> |No  <br/> |Tipo di contenuto multimediale non riuscito. Ad esempio, un tipo di contenuto comune è Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.  <br/> |
|**Applicazione** <br/> |No  <br/> |Applicazione coinvolta nell'errore.  <br/> |
|**All'URI utente** <br/> |No  <br/> |Indirizzo SIP dell'utente invitato alla sessione.  <br/> |
|**Orari di partecipazione alla conferenza (MS)** <br/> |No  <br/> |Intervallo di tempo (in millisecondi) che l'utente ha impiegato per partecipare alla conferenza.  <br/> |
|**Intestazione di diagnostica** <br/> |No  <br/> |Descrizione dell'ID di diagnostica.  <br/> |
   
Un elenco di errori di diagnostica può essere trovato nella [pagina di intestazione MS-Diagnostics](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).
  

