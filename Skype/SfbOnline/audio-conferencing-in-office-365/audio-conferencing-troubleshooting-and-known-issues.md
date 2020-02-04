---
title: Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Ottenere un elenco di problemi noti quando si usa Microsoft come provider di conferenze telefoniche con accesso esterno, stato e alcune soluzioni alternative. '
ms.openlocfilehash: 6c462fea8a6ff1ebdae25a09ef8471d82559f3eb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695771"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza

 **Questo articolo è per gli utenti di Skype for business che usano Microsoft come provider di servizi di audioconferenza. Non si applica ai clienti che usano un provider di servizi di audioconferenza di terze parti.**
  
## <a name="troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti

I servizi di audioconferenza che utilizzano Microsoft come provider hanno problemi correnti che vengono monitorati, sottoposti a indagine e possibilmente risolti nelle prossime versioni build di Office 365.
  
Per il momento, usa questo nome come riferimento per la risoluzione dei problemi potenziali con la configurazione e l'utilizzo di servizi di audioconferenza per le persone che usano Skype for business nell'organizzazione.

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'opzione che riproduce una notifica quando qualcuno accede a una riunione o l'abbandona è attiva all'avvio della riunione, ma viene disattivata subito dopo.  <br/> |Per impostazione predefinita, le notifiche di accesso o abbandono sono disattivate per le riunioni alle quali i partecipanti accedono dalle app Skype for Business e tramite telefono. Gli annunci possono essere attivati nelle **Opzioni riunione Skype** nel'app Skype for Business. Per una riunione alla quale tutti i partecipanti accedono tramite telefono, le notifiche di accesso o abbandono sono attive per impostazione predefinita, poiché i presenti non possono visualizzare l'elenco dei partecipanti. Quando viene avviata una riunione i cui partecipanti eseguono l'accesso solo tramite telefono, le notifiche di accesso o abbandono sono attive, ma vengono disattivate se un utente esegue l'accesso tramite una app Skype for Business. Se sono state disattivate, le notifiche possono essere attivate nuovamente mediante le **Opzioni riunione Skype** nell'app Skype for Business. <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Se, durante il provisioning iniziale, a un utente viene assegnata una licenza E5, è possibile che l'e-mail di benvenuto ai servizi di audioconferenza non sia stata recapitata in caso di mancata attivazione della cassetta postale.  <br/> |In tale evenienza è possibile inviare nuovamente le informazioni sui servizi di audioconferenza dell'utente utilizzando l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o mediante PowerShell. Vedere [abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di conferenza audio cambiano](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Per inviare nuovamente il PIN per l'audioconferenza all'utente, è necessario reimpostare il PIN. L'operazione può essere eseguita tramite l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o tramite PowerShell.          |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|La visualizzazione delle chiamate per i servizi di audioconferenza nei rapporti sull'utilizzo può richiedere fino a 24 ore.  <br/> |Nei prossimi aggiornamenti del servizio, ci impegniamo a introdurre miglioramenti in proposito.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Quando un chiamante accede a un bridge di conferenza tramite telefono dopo che la riunione è stata bloccata da un utente Skype for Business, nell'app Skype for Business non è presente alcuna notifica che indica che l'utente è in sala di attesa.  <br/> |Si tratta di un'impostazione inerente alla progettazione; tuttavia, alla luce dei feedback raccolti, abbiamo deciso di introdurre un supporto per questa funzionalità nei prossimi aggiornamenti del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Un utente di Skype for Business Server (on-Prem) assegnato alla licenza di audioconferenza prima del 1 ° marzo 2019 potrebbe non vedere la chiamata nelle coordinate degli inviti alle riunioni.  <br/> |Il provisioning degli utenti di Skype for Business Server per i servizi di audioconferenza per i team non è stato supportato fino a tale data. Ora è supportato ed è prima di tutto un componente delle [riunioni](https://docs.microsoft.com/microsoftteams/meetings-first). L'utente deve avere una licenza di teams.  <br/> |La pipeline di provisioning deve essere riattivata. Rimuovere la licenza per i servizi di audioconferenza dell'utente, attendere un paio di ore e riassegnare la licenza.  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
