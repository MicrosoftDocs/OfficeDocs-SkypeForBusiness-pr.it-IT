---
title: Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Ottenere un elenco di problemi noti quando si utilizza Microsoft come i provider di conferenza telefonica, lo stato e alcune soluzioni alternative. '
ms.openlocfilehash: 3748c6f60c04ea34f327eb371ba16f112a124287
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="audio-conferencing-troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti relativi ai servizi di audioconferenza

 [] **Questo articolo è rivolto ai clienti Skype for Business e Microsoft Teams che usano Microsoft come provider per audioconferenze. Non interessa i clienti che usano provider per audioconferenze di terzi (ACP).**
  
## <a name="troubleshooting-and-known-issues"></a>Risoluzione dei problemi e problemi noti

I servizi di audioconferenza che utilizzano Microsoft come provider hanno problemi correnti che vengono monitorati, sottoposti a indagine e possibilmente risolti nelle prossime versioni build di Office 365.
  
Per risolvere potenziali problemi durante la configurazione e il funzionamento dei servizi di audioconferenza per gli utenti dell'organizzazione che usano le app Skype for Business o Microsoft Teams, fai riferimento al presente articolo.
  
### <a name="microsoft-teams-app"></a>App Microsoft Teams

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|I chiamanti PSTN con lo stesso numero "Da" sono indicati come medesimo utente nell'elenco dei partecipanti alle riunioni.  <br/> |Quando più chiamanti PSTN partecipano a una riunione e i loro ID chiamanti sono identificati come singolo numero, verranno visualizzati come un singolo chiamante nell'elenco dei partecipanti alle riunioni.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Il pannello Info riunione a volte non viene visualizzato.  <br/> |Il pannello Info riunione può non essere visualizzato nel client Teams quando gli utenti eseguono una ricerca per numero di telefono bridge conferenze o ID conferenze.  <br/> |Consultare i dettagli della riunione o il calendario di Outlook per vedere il numero di telefono bridge conferenza o l'ID conferenza.  <br/> |25/9/2017  <br/> |
|Gli inviti alle riunioni per il componente aggiuntivo Outlook mostrano caratteri senza significato per le coordinate PSTN per le localizzazioni diverse da US.  <br/> |Quando si programmano riunioni private con il componente aggiuntivo Outlook per Microsoft Teams in computer con localizzazione non US, le coordinate PSTN possono contenere caratteri senza significato.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|L'accesso verso l'esterno richiede 5 cifre o più.  <br/> |Gli utenti che cercano di effettuare una chiamata verso l'esterno da una riunione devono digitare 5 o più cifre anche se è disponibile una regola di normalizzazione del piano di chiamata per normalizzare la composizione breve a E.164.  <br/> |Effettuare la chiamata con il numero DID o locale completo invece del numero interno.  <br/> |25/9/2017  <br/> |
|Il controllo per le chiamate esterne a volte non viene visualizzato.  <br/> |Il controllo per le chiamate esterne può non essere visibile nel pannello Info riunione.  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Gli ID conferenza statici non sono supportati per le riunioni Microsoft Teams.  <br/> |Se l'amministratore sostituisce l'impostazione standard di ID conferenza dinamico con l'impostazione ID conferenza statico, questo non ha effetto per le riunioni di Microsoft Teams. Vedere [ID dinamico tramite servizi di conferenza Audio all'interno dell'organizzazione](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Non ci sono soluzioni alternative.  <br/> |25/9/2017  <br/> |
|Le coordinate riunione PSTN non sono disponibili per Skype per gli utenti locali aziendali  <br/> |Se l'utente è un Skype per utente locale aziendale, assegnati con Skype per Business Online, conferenze Audio e le licenze di team, tutte le riunioni pianificate con team non includerà le coordinate riunione PSTN. <br/> |Non ci sono soluzioni alternative.  <br/> |1/2/2018  <br/> |
   
### <a name="skype-for-business-app"></a>App Skype for Business

|**Problema**|**Comportamento/sintomi**|**Soluzione alternativa nota**|**Data di scoperta**|
|:-----|:-----|:-----|:-----|
|L'opzione che riproduce una notifica quando qualcuno accede a una riunione o l'abbandona è attiva all'avvio della riunione, ma viene disattivata subito dopo.  <br/> |Per impostazione predefinita, le notifiche di accesso o abbandono sono disattivate per le riunioni alle quali i partecipanti accedono dalle app Skype for Business e tramite telefono. Gli annunci possono essere attivati nelle **Opzioni riunione Skype** nel'app Skype for Business. Per una riunione alla quale tutti i partecipanti accedono tramite telefono, le notifiche di accesso o abbandono sono attive per impostazione predefinita, poiché i presenti non possono visualizzare l'elenco dei partecipanti. Quando viene avviata una riunione i cui partecipanti eseguono l'accesso solo tramite telefono, le notifiche di accesso o abbandono sono attive, ma vengono disattivate se un utente esegue l'accesso tramite una app Skype for Business. Se sono state disattivate, le notifiche possono essere attivate nuovamente mediante le **Opzioni riunione Skype** nell'app Skype for Business. <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Se, durante il provisioning iniziale, a un utente viene assegnata una licenza E5, è possibile che l'e-mail di benvenuto ai servizi di audioconferenza non sia stata recapitata in caso di mancata attivazione della cassetta postale.  <br/> |In tale evenienza è possibile inviare nuovamente le informazioni sui servizi di audioconferenza dell'utente utilizzando l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o mediante PowerShell. Vedere [abilitare o disabilitare l'invio messaggi di posta elettronica quando modificano le impostazioni di conferenza Audio](enable-or-disable-sending-emails-when-their-settings-change.md).  <br/> **Nota:** Per inviare nuovamente il PIN di conferenza audio all'utente, deve reimpostare il PIN. L'operazione può essere eseguita tramite l'opzione **Servizi di audioconferenza** nell'UNRESOLVED_TOKEN_VAL(Skype for Business admin center) o tramite PowerShell.          |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|La visualizzazione delle chiamate per i servizi di audioconferenza nei rapporti sull'utilizzo può richiedere fino a 24 ore.  <br/> |Nei prossimi aggiornamenti del servizio, ci impegniamo a introdurre miglioramenti in proposito.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
|Quando un chiamante accede a un bridge di conferenza tramite telefono dopo che la riunione è stata bloccata da un utente Skype for Business, nell'app Skype for Business non è presente alcuna notifica che indica che l'utente è in sala di attesa.  <br/> |Si tratta di un'impostazione inerente alla progettazione; tuttavia, alla luce dei feedback raccolti, abbiamo deciso di introdurre un supporto per questa funzionalità nei prossimi aggiornamenti del servizio.  <br/> |Non ci sono soluzioni alternative.  <br/> |30/8/2017  <br/> |
   
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
