---
title: Gestire le impostazioni di audioconferenza per un utente in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
description: "Gli amministratori di Microsoft 365 o Office 365 possono modificare le impostazioni per i servizi di audioconferenza di Skype for Business Online, come il provider, il numero a pagamento o verde predefinito, l'ID conferenza o il PIN, per un singolo utente dell'organizzazione. "
ms.openlocfilehash: 47ad2b0d6b5684d2a897055ad43e253e55c67109
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943849"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gestire le impostazioni di audioconferenza per un utente in Skype for Business online

> [!Note]
> Se si desidera gestire le impostazioni utente in Microsoft Teams, vedere Gestire le impostazioni [di audioconferenza per un utente in Microsoft Teams.](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)

Gli amministratori di Microsoft 365 o Office 365 possono modificare le impostazioni dei servizi di audioconferenza, come il provider, il numero a pagamento o verde predefinito, l'ID conferenza o il PIN per un singolo utente dell'organizzazione. Se desideri modificare le impostazioni per la tua organizzazione, vedi [Gestire le impostazioni di audioconferenza per la mia organizzazione.](manage-the-audio-conferencing-settings-for-my-organization.md)

 
1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Nell'interfaccia di amministrazione di Skype for Business, scegli **Utenti.**
    
4. Seleziona l'utente per il quale vuoi gestire le impostazioni, quindi nel riquadro Azioni fai clic su **Modifica**![Mostra l'icona Modifica](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Scegli **Audioconferenza** nel riquadro di spostamento sinistro, quindi nella pagina **Proprietà** dell'utente, modifica i seguenti campi:
    
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider nell'elenco.  <br/><br/> **Nota:** le altre impostazioni di questa tabella si applicano solo se selezioni Microsoft come provider di servizi di audioconferenza.           |
|**Numero a pagamento predefinito** (obbligatorio) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Numero verde predefinito** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Consenti l'utilizzo di numeri gratuiti nel ponte Microsoft della tua organizzazione per partecipare alle riunioni di questo utente** <br/> |Seleziona questa opzione se desideri consentire all'utente l'utilizzo di numeri gratuiti per partecipare alle riunioni.  <br/> |
|**Inviare informazioni sulla conferenza tramite posta elettronica** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID conferenza** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Consenti ai chiamanti non autenticati di essere le prime persone presenti a una riunione** <br/> |Seleziona questa opzione per consentire ai chiamanti non autenticati di essere i primi a partecipare alle riunioni.  <br/> |
|**Restrizioni sulla disconnessione dalle riunioni di questo utente** <br/> |Seleziona un'opzione dell'elenco se vuoi impedire solo le disconnessioni nazionali o se vuoi impedirle tutte dalle riunioni.  <br/> |
  
![Mostra la pagina Proprietà di Audioconferenza per un utente](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md)

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
