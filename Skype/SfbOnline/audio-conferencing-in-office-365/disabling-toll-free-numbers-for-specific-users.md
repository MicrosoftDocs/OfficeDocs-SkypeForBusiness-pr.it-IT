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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare come gli organizzatori utilizzano i numeri gratuiti per le riunioni.
ms.openlocfilehash: aabc72f5e413b8f760981b8fac364afc836be5ce058d5999e2c19f96109141b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310275"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Disattivazione di numeri gratuiti per utenti specifici su Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> Per informazioni sulla disattivazione dei numeri telefonici gratuiti per gli utenti di Teams, consulta [Disabilitazione numeri gratuiti per utenti specifici su Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.  

Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri gratuiti, ovvero questi numeri, se disponibili, possono essere utilizzati dai partecipanti per partecipare alle riunioni. Se desideri che alcuni utenti all'interno dell'organizzazione siano esclusi, puoi limitare l'uso di tali numeri relativi alle riunioni per utenti specifici tramite un controllo di attivazione dei numeri gratuiti. 

Quando i numeri gratuiti sono disabilitati per un determinato organizzatore: 
 - Un numero gratuito non verrà più incluso nel suo invito alle riunioni. 
 - I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni. 
 - I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione. 
 - Tutte le riunioni dell'organizzatore verranno ripianificate automaticamente e verrà rimosso il numero gratuito.  

    > [!IMPORTANT]
    > Quindi verranno inviati nuovamente tutti gli inviti di posta elettronica dell'organizzatore ai partecipanti di quelle riunioni. 

 - I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione dei numeri verdi per utenti specifici 

**Nell'Microsoft Teams di amministrazione:**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Accanto a **Audioconferenza** fare clic su **Modifica.**

3. Impostare **Includi numeri verde nelle convocazioni di riunione di questo utente su** **Disattivato.** 

4. Fare clic **su Salva.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utilizzo di PowerShell**  

Puoi utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo. Ad esempio: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
