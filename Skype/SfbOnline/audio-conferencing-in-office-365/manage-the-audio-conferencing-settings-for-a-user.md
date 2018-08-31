---
title: Gestire le impostazioni di Audioconferenza per un utente di Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "In qualità di amministratore di Office 365, puoi modificare le impostazioni di Audioconferenza di Skype for Business online, ad esempio il provider, il numero predefinito a pagamento o gratuito, l'ID conferenza o il PIN per un singolo utente nell'organizzazione. "
ms.openlocfilehash: 11ab14b3ebba54e1af8125c2d2f6c2acbd0730b7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779056"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Gestire le impostazioni di Audioconferenza per un utente di Skype for Business online

> [!Note]
> Se desideri gestire le impostazioni utente di Microsoft Teams, consulta la pagina [Gestire le impostazioni di Audioconferenza di un utente in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

In qualità di amministratore di Office 365, puoi modificare le impostazioni di Audioconferenza, ad esempio il provider, il numero predefinito a pagamento o gratuito, l'ID conferenza o il PIN per un singolo utente nell'organizzazione. Se desideri modificare le impostazioni per l'organizzazione, consulta la pagina [Gestire le impostazioni di Audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Nell'interfaccia di amministrazione di Skype for Business scegli **Utenti**.
    
4. Seleziona l'utente per il quale vuoi gestire le impostazioni, quindi nel riquadro Azioni fai clic su **Modifica**![Mostra l'icona Modifica](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Scegli **Audioconferenza** nel riquadro di spostamento sinistro, quindi nella pagina **Proprietà** dell'utente, modifica i seguenti campi:
    
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegli il provider dall'elenco.  <br/><br/> **Nota:** le altre impostazioni di questa tabella si applicano solo se selezioni Microsoft come provider di servizi di audioconferenza.           |
|**Numero a pagamento predefinito** (obbligatorio) <br/> |Per i provider di terze parti, questi numeri di telefono sono quelli forniti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formatta i numeri come desideri che vengano visualizzati negli inviti alle riunioni di Skype for Business e Microsoft Teams.  <br/> |
|**Numero gratuito predefinito** <br/> |Per i provider di terze parti, questi numeri di telefono sono quelli forniti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formatta i numeri come desideri che vengano visualizzati negli inviti alle riunioni di Skype for Business e Microsoft Teams.  <br/> |
|**Consenti l'utilizzo di numeri gratuiti nel ponte Microsoft della tua organizzazione per partecipare alle riunioni di questo utente** <br/> |Seleziona questa opzione se desideri consentire all'utente l'utilizzo di numeri gratuiti per partecipare alle riunioni.  <br/> |
|**Invia informazioni sulla conferenza tramite posta elettronica** <br/> |Fai clic su questo collegamento solo se desideri inviare immediatamente un messaggio di posta elettronica all'utente con il suo ID conferenza e numero di telefono. (Questo messaggio di posta elettronica non include il PIN). Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID conferenza** <br/> |Seleziona **Reimposta** se desideri reimpostare l'ID conferenza per l'utente. Per ulteriori informazioni, consulta [Reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Seleziona **Reimposta** se desideri reimpostare il PIN per l'utente. Per ulteriori informazioni, consulta [Reimpostare il PIN per Audioconferenza](reset-the-audio-conferencing-pin.md).  <br/> |
|**Consenti ai chiamanti non autenticati di essere le prime persone presenti a una riunione** <br/> |Seleziona questa opzione per consentire ai chiamanti non autenticati di essere i primi a partecipare alle riunioni.  <br/> |
|**Restrizioni sulla disconnessione dalle riunioni di questo utente** <br/> |Seleziona un'opzione dell'elenco se vuoi impedire solo le disconnessioni nazionali o se vuoi impedirle tutte dalle riunioni.  <br/> |
  
![Mostra la pagina Proprietà di Audioconferenza per un utente](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Argomenti correlati

[Gestire le impostazioni di Audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md)

[Domande ricorrenti su Audioconferenza](/MicrosoftTeams/audio-conferencing-common-questions)
