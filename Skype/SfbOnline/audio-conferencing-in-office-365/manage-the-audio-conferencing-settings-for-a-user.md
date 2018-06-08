---
title: Gestire le impostazioni di conferenze Audio per un utente
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Come un amministratore di Office 365, è possibile modificare le impostazioni di conferenza Audio, ad esempio il provider, a pagamento predefinito o numero verde, ID conferenza o PIN, per un singolo utente nell'organizzazione. Se si desidera modificare le impostazioni per l'organizzazione, vedere Manage conferenze Audio le impostazioni per l'organizzazione.
ms.openlocfilehash: 064625919cab532c10cdadd16ad95e144d301419
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703375"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user"></a>Gestire le impostazioni di conferenze Audio per un utente

Come un amministratore di Office 365, è possibile modificare le impostazioni di conferenza Audio, ad esempio il provider, a pagamento predefinito o numero verde, ID conferenza o PIN, per un singolo utente nell'organizzazione. Se si desidera modificare le impostazioni per l'organizzazione, vedere [gestire le impostazioni di conferenze Audio per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. In **Servizi di conferenza Audio**, modificare uno dei seguenti:

|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Audioconferenze con accesso esterno**|Per attivare servizi di conferenza audio o disattivato per l'utente, fare clic su **Edit** accanto a **Conferenze Audio**e quindi nel riquadro di **Audioconferenza** , passare **all'audioconferenza** attivato o disattivato.|
|**Inviare informazioni conferenza nella posta elettronica**  |Fare clic su questo collegamento solo se si desidera inviare immediatamente un messaggio di posta elettronica all'utente con il proprio ID e il telefono numero di conferenza. (Questo messaggio di posta elettronica non include il PIN). Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md).  |
|**ID conferenza**  |Se si desidera reimpostare l'ID conferenza per utente, fare clic su **Reimposta ID conferenza** . Per ulteriori informazioni, vedere [reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).  |
|**PIN** |Se si desidera reimpostare il PIN per utente, fare clic su **Reimposta PIN** . Per ulteriori informazioni, vedere [reimpostare il PIN per le conferenze Audio](reset-the-audio-conferencing-pin.md). |
|**Numero di telefono a pagamento per conferenze predefinito** (obbligatorio) |Questi saranno numeri che vengono impostati su ponte per conferenze audio. Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione. Per modificare il numero a pagamento predefinito, fare clic su **Edit** accanto ai **servizi di conferenza Audio** e nel riquadro di **Conferenze Audio** , selezionare un numero in **numero a pagamento**. |
|**Gli inviti da questo utente possono includere numero verde**|Per modificare questa impostazione, fare clic su **Edit** accanto a **Servizi di conferenza Audio** e nel riquadro di **Conferenze Audio** , attivare e disattivare **includono numeri verdi nelle convocazioni da questo utente** attivato o disattivato. |
|**Autorizzazioni di chiamata in uscita**|Per modificare questa impostazione, fare clic su **Edit** accanto a **Servizi di conferenza Audio** e nel riquadro di **Conferenze Audio** , scegliere un'opzione in **autorizzazioni di chiamata in uscita dalle riunioni**.|

![Visualizza le impostazioni di conferenza Audio di un utente](../images/sfbaudioconf-usersettings.png)
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
 
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegliere **Admin Center** > **Skype per le aziende**.
    
3. Skype per interfaccia di amministrazione di Business, scegliere **utenti**.
    
4. Selezionare l'utente per il quale si desidera gestire le impostazioni e quindi nel riquadro azioni fare clic su **Modifica**![verrà visualizzata l'icona Modifica](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Scegliere **audioconferenze** nel riquadro di spostamento sinistro e quindi nella pagina **proprietà** dell'utente, modificare uno dei seguenti:
    
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider dall'elenco.  <br/><br/> **Nota:** Le altre impostazioni in questa tabella sono applicano solo se si seleziona Microsoft come provider di servizi di conferenza audio.           |
|**Numero verde predefinito** (obbligatorio) <br/> |Per un provider di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio. Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, queste saranno numeri che vengono impostati su ponte per conferenze audio. Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.  <br/> |
|**Umero numero verde predefinito** <br/> |Per un provider di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio. Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, queste saranno numeri che vengono impostati su ponte per conferenze audio. Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.  <br/> |
|**Consentire l'utilizzo di numeri verdi nel bridge Microsoft dell'organizzazione di partecipare alle riunioni di questo utente** <br/> |Selezionare questa opzione se si desidera consentire all'utente di numeri verdi per partecipare alle riunioni.  <br/> |
|**Inviare informazioni conferenza tramite posta elettronica** <br/> |Fare clic su questo collegamento solo se si desidera inviare immediatamente un messaggio di posta elettronica all'utente con il proprio ID e il telefono numero di conferenza. (Questo messaggio di posta elettronica non include il PIN). Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**ID conferenza** <br/> |Selezionare **Reimposta** se si desidera reimpostare l'ID conferenza per utente. Per ulteriori informazioni, vedere [reimpostare un ID conferenza per un utente](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Selezionare **Reimposta** se è necessario reimpostare il PIN dell'utente. Per ulteriori informazioni, vedere [reimpostare il PIN per le conferenze Audio](reset-the-audio-conferencing-pin.md).  <br/> |
|**Consentire ai chiamanti non autenticati di essere il prima persone a una riunione** <br/> |Selezionare questa opzione per consentire ai chiamanti non autenticati di essere la prima di partecipare alle riunioni.  <br/> |
|**Restrizioni alla connessione-outs dalle riunioni di questo utente** <br/> |Se si desidera limitare dial-outs a solo o se si desidera impedire a tutti i dial-outs dalle riunioni, selezionare un'opzione nell'elenco.  <br/> |
  
![Mostra la pagina delle proprietà di conferenze Audio per un utente](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>See also

[Gestire le impostazioni di audioconferenza per l'organizzazione](manage-the-audio-conferencing-settings-for-my-organization.md)

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
