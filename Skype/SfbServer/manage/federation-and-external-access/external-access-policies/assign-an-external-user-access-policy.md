---
title: Assegnare criteri di accesso per gli utenti esterni
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso remoto degli utenti e la connettività messaggistica istantanea pubblica nel pannello di controllo di Skype for Business Server applicando i criteri appropriati a utenti specifici.
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818327"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Assegnare un criterio di accesso degli utenti esterni a un utente abilitato per Skype for business

Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso remoto degli utenti e la connettività messaggistica istantanea pubblica nel pannello di controllo di Skype for Business Server applicando i criteri appropriati a utenti specifici. Ad esempio, se hai creato un criterio per supportare l'accesso degli utenti remoti, devi applicarlo all'utente prima che l'utente possa connettersi a Skype for Business Server da una posizione remota e collaborare con utenti interni dalla posizione remota.


> [!NOTE]  
> Per supportare l'accesso degli utenti esterni, è necessario abilitare il supporto per ogni tipo di accesso utente esterno che si vuole supportare e configurare i criteri appropriati e altre opzioni per controllarne l'utilizzo. Per informazioni dettagliate, vedere [gestione della Federazione e accesso esterno a Skype for Business Server](../managing-federation-and-external-access.md).


Usare la procedura descritta in questo argomento per applicare un criterio di accesso utente esterno creato in precedenza a uno o più account utente.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Per applicare un criterio utente esterno a un account utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.

5.  In **modifica utenti di Skype for Business Server** in **criteri di accesso esterno**Selezionare i criteri utente che si desidera applicare.
     
> [!NOTE]  
> Le impostazioni di ** \<>automatico** applicano le impostazioni predefinite del server o dei criteri globali.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Assegnazione di criteri di accesso esterno per utente tramite i cmdlet di Windows PowerShell

I criteri di accesso esterno per utente possono essere assegnati tramite Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Per assegnare un criterio di accesso esterno per utente a un singolo utente

  - Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Per assegnare un criterio di accesso esterno per utente a più utenti

  - Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che hanno account nell'UO degli Stati Uniti in Active Directory. Per altre informazioni sul parametro OU usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Per annullare l'assegnazione di un criterio di accesso esterno per utente

  - Questo comando Annulla l'assegnazione di qualsiasi criterio di accesso esterno per utente assegnato in precedenza a Ken. Dopo che il criterio per utente non è stato assegnato, Ken è gestito automaticamente tramite il criterio globale oppure, se disponibile, il criterio del sito locale. Un criterio di sito ha la precedenza sui criteri globali.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


