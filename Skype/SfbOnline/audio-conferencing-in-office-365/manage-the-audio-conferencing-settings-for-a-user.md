---
title: Gestire le impostazioni di audioconferenza per un utente in Skype for Business Online
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
description: "Gli amministratori di Microsoft 365 o Office 365 possono modificare le impostazioni di audioconferenza online di Skype for Business, ad esempio il provider, il numero verde o il numero verde predefinito, l'ID conferenza o il PIN, per un singolo utente dell'organizzazione. "
ms.openlocfilehash: 648bb27ce8e6745d765b8fc400494188fd43b5e866ecf0cf927f36fd4d7ca676
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335716"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gestire le impostazioni di audioconferenza per un utente in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Per gestire le impostazioni utente in Microsoft Teams, vedere Gestire le impostazioni di audioconferenza per un utente [in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

Gli amministratori di Microsoft 365 o Office 365 possono modificare le impostazioni di audioconferenza, ad esempio il provider, il numero verde o il numero verde predefinito, l'ID conferenza o il PIN, per un singolo utente dell'organizzazione. Per modificare le impostazioni per l'organizzazione, vedere [Gestire le impostazioni di audioconferenza per l'organizzazione.](manage-the-audio-conferencing-settings-for-my-organization.md)

 
1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Nell'Skype for Business di amministrazione scegliere **Utenti.**
    
4. Seleziona l'utente per il quale vuoi gestire le impostazioni, quindi nel riquadro Azioni fai clic su **Modifica**![Mostra l'icona Modifica](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Scegli **Audioconferenza** nel riquadro di spostamento sinistro, quindi nella pagina **Proprietà** dell'utente, modifica i seguenti campi:
    
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider nell'elenco.  <br/><br/> **Nota:** le altre impostazioni di questa tabella si applicano solo se selezioni Microsoft come provider di servizi di audioconferenza.           |
|**Numero a pagamento predefinito** (obbligatorio) <br/> |Per i provider di terze parti, questi numeri di telefono sono quelli forniti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.  <br/> |
|**Numero verde predefinito** <br/> |Per i provider di terze parti, questi numeri di telefono sono quelli forniti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.  <br/> |
|**Consenti l'utilizzo di numeri gratuiti nel ponte Microsoft della tua organizzazione per partecipare alle riunioni di questo utente** <br/> |Seleziona questa opzione se desideri consentire all'utente l'utilizzo di numeri gratuiti per partecipare alle riunioni.  <br/> |
|**Inviare informazioni sulla conferenza tramite posta elettronica** <br/> |Fai clic su questo collegamento solo se desideri inviare immediatamente un messaggio di posta elettronica all'utente con il suo ID conferenza e numero di telefono. (Questo messaggio di posta elettronica non include il PIN). Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID conferenza** <br/> |Seleziona **Reimposta** se desideri reimpostare l'ID conferenza per l'utente. Per ulteriori informazioni, consulta [Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Seleziona **Reimposta** se desideri reimpostare il PIN per l'utente. Per ulteriori informazioni, consulta [Reimpostare il PIN per Audioconferenza](reset-the-audio-conferencing-pin.md).  <br/> |
|**Consenti ai chiamanti non autenticati di essere le prime persone presenti a una riunione** <br/> |Seleziona questa opzione per consentire ai chiamanti non autenticati di essere i primi a partecipare alle riunioni.  <br/> |
|**Restrizioni sulla disconnessione dalle riunioni di questo utente** <br/> |Seleziona un'opzione dell'elenco se vuoi impedire solo le disconnessioni nazionali o se vuoi impedirle tutte dalle riunioni.  <br/> |
  
![Mostra la pagina Proprietà di Audioconferenza per un utente](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md)

[Domande ricorrenti sulle audioconferenze](/MicrosoftTeams/audio-conferencing-common-questions)
