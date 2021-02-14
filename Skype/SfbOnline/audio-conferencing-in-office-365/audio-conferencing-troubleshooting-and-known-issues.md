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
description: "Ottenere un elenco dei problemi noti relativi all'uso di Microsoft come provider di conferenze telefoniche con accesso esterno, sullo stato e su alcune soluzioni alternative. "
ms.openlocfilehash: fba5bfff687121c7b1b64c0e51233ccb576497e2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164521"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza

 **Questo articolo è per gli utenti Skype for Business che usano Microsoft come provider di servizi di audioconferenza. Non si applicano ai clienti che utilizzano provider di servizi di audioconferenza di terze parti.**
  
## <a name="troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti

I servizi di audioconferenza che utilizzano Microsoft come provider di servizi di audioconferenza hanno problemi correnti che vengono monitorati e esaminati attivamente e saranno potenzialmente risolti nelle versioni future di Microsoft 365.
  
Per il momento, utilizzare questa opzione come riferimento per la risoluzione di potenziali problemi relativi alla configurazione e al funzionamento delle audioconferenze per gli utenti che usano Skype for Business nell'organizzazione.

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'opzione che riproduce una notifica quando qualcuno accede a una riunione o l'abbandona è attiva all'avvio della riunione, ma viene disattivata subito dopo.  <br/> |Per impostazione predefinita, le notifiche di accesso o abbandono sono disattivate per le riunioni alle quali i partecipanti accedono dalle app Skype for Business e tramite telefono. Gli annunci possono essere attivati nelle **Opzioni riunione Skype** nel'app Skype for Business. Per una riunione alla quale tutti i partecipanti accedono tramite telefono, le notifiche di accesso o abbandono sono attive per impostazione predefinita, poiché i presenti non possono visualizzare l'elenco dei partecipanti. Quando viene avviata una riunione i cui partecipanti eseguono l'accesso solo tramite telefono, le notifiche di accesso o abbandono sono attive, ma vengono disattivate se un utente esegue l'accesso tramite una app Skype for Business. Se sono state disattivate, le notifiche possono essere attivate nuovamente mediante le **Opzioni riunione Skype** nell'app Skype for Business. <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Se, durante il provisioning iniziale, a un utente viene assegnata una licenza E5, è possibile che l'e-mail di benvenuto ai servizi di audioconferenza non sia stata recapitata in caso di mancata attivazione della cassetta postale.  <br/> |In tale evenienza è possibile inviare nuovamente le informazioni sui servizi di audioconferenza dell'utente utilizzando l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o mediante PowerShell. Vedi [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di Audioconferenza vengono modificate.](enable-or-disable-sending-emails-when-their-settings-change.md)  <br/> **Nota:** Per inviare di nuovo il PIN di audioconferenza all'utente, è necessario reimpostarlo. L'operazione può essere eseguita tramite l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o tramite PowerShell.          |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|La visualizzazione delle chiamate per i servizi di audioconferenza nei rapporti sull'utilizzo può richiedere fino a 24 ore.  <br/> |Nei prossimi aggiornamenti del servizio, ci impegniamo a introdurre miglioramenti in proposito.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Quando un chiamante accede a un bridge di conferenza tramite telefono dopo che la riunione è stata bloccata da un utente Skype for Business, nell'app Skype for Business non è presente alcuna notifica che indica che l'utente è in sala di attesa.  <br/> |Si tratta di un'impostazione inerente alla progettazione; tuttavia, alla luce dei feedback raccolti, abbiamo deciso di introdurre un supporto per questa funzionalità nei prossimi aggiornamenti del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Un utente Skype for Business Server (locale) che ha assegnato la licenza per i servizi di audioconferenza prima del 1° marzo 2019 potrebbe non visualizzare le coordinate del telefono presenti negli inviti alle riunioni.  <br/> |Il provisioning degli utenti di Skype for Business Server per le audioconferenze di Teams non era supportato fino a tale data. Ora è supportato ed è un componente di [Meetings First.](https://docs.microsoft.com/microsoftteams/meetings-first) L'utente deve avere una licenza di Teams.  <br/> |La pipeline di provisioning deve essere riattivata. Rimuovi la licenza per i servizi di audioconferenza, attendi un paio d'ore e riassegna la licenza.  <br/> |3/1/2019  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
