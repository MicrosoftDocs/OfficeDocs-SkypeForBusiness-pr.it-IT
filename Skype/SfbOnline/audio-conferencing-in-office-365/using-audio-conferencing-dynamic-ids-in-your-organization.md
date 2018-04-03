---
title: Utilizzo degli ID dinamici audioconferenze all'interno dell'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
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
description: 'Il servizio di conferenza Audio viene viene aggiornato per fornire ogni Skype per Business e Microsoft Teams riunione con gli ID conferenza diversi. ID conferenza dinamici sono un miglioramento significativo tramite conferenza statico ID, in quanto forniscono:'
ms.openlocfilehash: 418e6f486b8108791930c7843bfed8bdc56e83ef
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a>Utilizzo degli ID dinamici audioconferenze all'interno dell'organizzazione

Il servizio di conferenza Audio viene viene aggiornato per fornire ogni Skype per Business e Microsoft Teams riunione con gli ID conferenza diversi. ID conferenza dinamici sono un miglioramento significativo tramite conferenza statico ID, in quanto forniscono:
  
- **Protezione avanzata** La conferenza ID sono univoci per ogni Skype per riunione Business o Microsoft Teams e vengono generati quando viene programmato in base alla riunione.
    
- **Una migliore esperienza per le riunioni vicine l'una all'altra** Alle riunioni di un singolo organizzatore sono trasmesse informazioni specifiche sul numero da chiamare che impediscono ai partecipanti telefonici di una riunione di essere confusi con i partecipanti di un'altra quando sono pianificate una vicino all'altra.
    
- **Una transizione fluida** Quando la tua organizzazione è abilitata agli ID conferenza dinamici, tutte le riunioni che sono già state pianificate nella tua organizzazione con ID conferenza statici continueranno ad essere attive.
    
> [!TIP]
> ID dinamici sono disponibili solo per gli utenti abilitati per * * Audio Conferencing * * in modo che Microsoft impostato come i provider di servizi di conferenza audio. È possibile [Assegnare Microsoft come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md) per gli utenti.
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a>Quali modifiche verranno visualizzato agli utenti nell'organizzazione?

Dopo l'ID conferenza dinamici sono stati abilitati per l'organizzazione, qualsiasi nuova Skype per Business o Microsoft Teams riunioni che è pianificato per gli utenti nell'organizzazione abilitati per conferenze Audio avrà gli ID che sarà diversa dalla conferenza la ID conferenza statica aveva prima. Gli organizzatori con statica ID conferenza prima necessario ricordare gli utenti di partecipare alle riunioni che ora devono utilizzare un nuovo ID conferenza nell'invito della riunione prima di consentire loro di partecipare.
  
> [!NOTE]
> Riunioni pianificate da un utente con gli ID conferenza statico prima che l'organizzazione è stato abilitato per conferenza dinamico che ID continuerà a disporre gli ID conferenza statico, in modo che continuino a pianificare riunioni senza alcun impatto. 
  
Negli esempi seguenti la nuova esperienza per due Skype per le riunioni aziendali che sono stati organizzate dall'utente stesso, ma entrambi ora avranno due ID conferenza diversi: 
  
 La **riunione n. 1** è stata pianificata dalle 09.00 alle 10.00 e ha 93907123 come proprio ID conferenza:
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 La **riunione n. 2** è stata pianificata dallo stesso utente dalle 10.00 alle 11.00 e ha 16353789 come proprio ID conferenza:
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a>See also

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
