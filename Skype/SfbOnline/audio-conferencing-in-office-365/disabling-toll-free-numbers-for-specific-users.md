---
title: Disattivazione di numeri verdi per utenti specifici
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare gli organizzatori utilizzo numeri verdi per le riunioni.
ms.openlocfilehash: a63078256ac9ac52b3d405bd3cf1b63120fb77ce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione di numeri verdi per utenti specifici

Se l'organizzazione dispone di numeri verdi nel relativo Audio Conferencing Bridge Microsoft, è possibile consentire o impedire loro utilizzo in riunioni degli organizzatori specifici.  

Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri verdi, ovvero i numeri, se disponibile, possono essere utilizzati dai partecipanti per partecipare alle riunioni. Se non è il comportamento desiderato per alcuni utenti all'interno dell'organizzazione, è possibile limitare gli utenti specifici di utilizzare tali numeri relativi alle riunioni tramite un controllo di attivazione dei numerico verdi. 

Numeri verdi quando sono disabilitati per organizzare una determinata: 
 - Un numero verde non verrà non è più incluso nel suo o verrà invita. 
 - Non è più numeri verdi verranno elencati nella pagina "Trova un numero locale" viene fatto riferimento nel suo o verrà invita. 
 - I partecipanti saranno in grado di partecipare alla riunione dell'organizzatore determinato se è comporre un numero verde dell'organizzazione. 
 - Tutte le riunioni dell'organizzatore ripianificate automaticamente e verrà rimossa il numero verde.  

    > [!IMPORTANT]
    > Si verrà nuovamente tutti gli inviti di posta elettronica dell'organizzatore inviato a tutti i partecipanti delle riunioni. 

 - I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a tariffa. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione di numeri verdi per utenti specifici 

![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**

1. Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.

2. Nella parte superiore della pagina, fare clic su **Modifica**.

3. Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Modifica** nell'elenco a discesa.

4. Nel riquadro dei **provider di ponte conferenza** , disattiva **Consenti utilizzo di numeri verdi di ponte per conferenze della propria organizzazione di partecipare alle riunioni di questo utente**. 

5. Fare clic su **si applicano.** 

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**

1. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili. 

2. In the Action pane, click **Edit**. 

3. Deselezionare **Consenti utilizzo di numeri verdi per partecipare alle riunioni di questo utente**. 
 
4. Fai clic su **Salva**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utilizzo di PowerShell**  

È possibile utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo. Ad esempio: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
