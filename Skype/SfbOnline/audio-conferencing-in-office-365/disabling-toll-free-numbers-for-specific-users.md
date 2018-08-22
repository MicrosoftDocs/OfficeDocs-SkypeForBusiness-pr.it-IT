---
title: Disattivazione di numeri verdi per specifico Skype per gli utenti aziendali Online
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
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Gli amministratori possono controllare gli organizzatori utilizzo numeri verdi per le riunioni.
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490546"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Disattivazione di numeri verdi per specifico Skype per gli utenti aziendali Online

> [!Note]
> Per informazioni sulla disattivazione numeri strumento gratuito per gli utenti di team, vedere [Disabilitazione numeri verdi per utenti specifici in team](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

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

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione dei numeri verdi per utenti specifici 


1. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili. 

2. In the Action pane, click **Edit**. 

3. Deselezionare **Consenti utilizzo di numeri verdi per partecipare alle riunioni di questo utente**. 
 
4. Fai clic su **Salva**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utilizzo di PowerShell**  

È possibile utilizzare il parametro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser per abilitare o disabilitare questo controllo. Ad esempio: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
