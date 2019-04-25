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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Ottenere un elenco di problemi noti quando si utilizza Microsoft come i provider di conferenza telefonica, lo stato e alcune soluzioni alternative. '
ms.openlocfilehash: 997cc5007df35b307cb714b891bc60764bd4a645
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229185"
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza

 **In questo articolo è per Skype per gli utenti aziendali che utilizzano Microsoft come i provider di servizi di conferenza audio. Non si applica ai clienti che utilizzano un provider di servizi di conferenza audio di terze parti (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti

I servizi di audioconferenza che utilizzano Microsoft come provider hanno problemi correnti che vengono monitorati, sottoposti a indagine e possibilmente risolti nelle prossime versioni build di Office 365.
  
Per ora, utilizzare questo come riferimento durante la risoluzione di problemi potenziali Guida audioconferenze impostare e utilizzo per gli utenti nell'organizzazione, utilizza Skype per le aziende.

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'opzione che riproduce una notifica quando qualcuno accede a una riunione o l'abbandona è attiva all'avvio della riunione, ma viene disattivata subito dopo.  <br/> |Per impostazione predefinita, le notifiche di accesso o abbandono sono disattivate per le riunioni alle quali i partecipanti accedono dalle app Skype for Business e tramite telefono. Gli annunci possono essere attivati nelle **Opzioni riunione Skype** nel'app Skype for Business. Per una riunione alla quale tutti i partecipanti accedono tramite telefono, le notifiche di accesso o abbandono sono attive per impostazione predefinita, poiché i presenti non possono visualizzare l'elenco dei partecipanti. Quando viene avviata una riunione i cui partecipanti eseguono l'accesso solo tramite telefono, le notifiche di accesso o abbandono sono attive, ma vengono disattivate se un utente esegue l'accesso tramite una app Skype for Business. Se sono state disattivate, le notifiche possono essere attivate nuovamente mediante le **Opzioni riunione Skype** nell'app Skype for Business. <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Se, durante il provisioning iniziale, a un utente viene assegnata una licenza E5, è possibile che l'e-mail di benvenuto ai servizi di audioconferenza non sia stata recapitata in caso di mancata attivazione della cassetta postale.  <br/> |In tale evenienza è possibile inviare nuovamente le informazioni sui servizi di audioconferenza dell'utente utilizzando l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o mediante PowerShell. Vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Per inviare nuovamente il PIN di conferenza audio all'utente, deve reimpostare il PIN. L'operazione può essere eseguita tramite l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o tramite PowerShell.          |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|La visualizzazione delle chiamate per i servizi di audioconferenza nei rapporti sull'utilizzo può richiedere fino a 24 ore.  <br/> |Nei prossimi aggiornamenti del servizio, ci impegniamo a introdurre miglioramenti in proposito.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Quando un chiamante accede a un bridge di conferenza tramite telefono dopo che la riunione è stata bloccata da un utente Skype for Business, nell'app Skype for Business non è presente alcuna notifica che indica che l'utente è in sala di attesa.  <br/> |Si tratta di un'impostazione inerente alla progettazione; tuttavia, alla luce dei feedback raccolti, abbiamo deciso di introdurre un supporto per questa funzionalità nei prossimi aggiornamenti del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
