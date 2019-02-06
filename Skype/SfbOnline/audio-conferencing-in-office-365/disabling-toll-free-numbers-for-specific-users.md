---
title: Disattivazione di numeri gratuiti per utenti specifici su Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Gli amministratori possono controllare come gli organizzatori utilizzano i numeri gratuiti per le riunioni.
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753759"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Disattivazione di numeri gratuiti per utenti specifici su Skype for Business online
 
> [!Note]
> Per informazioni sulla disattivazione dei numeri telefonici gratuiti per gli utenti di Teams, consulta [Disabilitazione numeri gratuiti per utenti specifici su Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.  

By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control. 

Quando i numeri gratuiti sono disabilitati per un determinato organizzatore: 
 - Un numero gratuito non verrà più incluso nel suo invito alle riunioni. 
 - I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni. 
 - I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione. 
 - Tutte le riunioni dell'organizzatore verranno ripianificate automaticamente e verrà rimosso il numero gratuito.  

    > [!IMPORTANT]
    > Quindi verranno inviati nuovamente tutti gli inviti di posta elettronica dell'organizzatore ai partecipanti di quelle riunioni. 

 - I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione dei numeri verdi per utenti specifici 

Dall' **interfaccia di amministrazione di team Microsoft che**:

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.

3. Impostare **includono numeri verdi nelle convocazioni da questo utente** su **disattivato**. 

4. Fare clic su **salvare.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utilizzo di PowerShell**  

Puoi utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo. Ad esempio: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
