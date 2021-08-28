---
title: Assegnare criteri di accesso per gli utenti esterni
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica nel Pannello di controllo di Skype for Business Server applicando i criteri appropriati a utenti specifici.
ms.openlocfilehash: 4a5f6bfe13c27360c535957cefcfd4093b6a1bad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587020"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Assegnare un criterio di accesso utente esterno a un Skype for Business abilitato

Se un utente è stato abilitato per Skype for Business Server, è possibile configurare la federazione SIP, l'accesso degli utenti remoti e la connettività di messaggistica istantanea pubblica nel Pannello di controllo di Skype for Business Server applicando i criteri appropriati a utenti specifici. Ad esempio, se è stato creato un criterio per supportare l'accesso degli utenti remoti, è necessario applicarlo all'utente prima che l'utente possa connettersi a Skype for Business Server da una posizione remota e collaborare con gli utenti interni dalla posizione remota.


> [!NOTE]  
> Per supportare l'accesso utente esterno, è necessario abilitare il supporto per ogni tipo di accesso utente esterno desiderato e configurare i criteri appropriati e altre opzioni per il controllo. Per informazioni dettagliate, vedere [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).


Utilizzare la procedura contenuta in questo argomento per applicare criteri di accesso utente esterno creati in precedenza a uno o più account utente.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Per applicare criteri di accesso utente esterno a un account utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.

4.  Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.

5.  In **Modifica Skype for Business Server utente** in Criteri di accesso **esterno** selezionare il criterio utente che si desidera applicare.
     
> [!NOTE]  
> Le **\<Automatic>** impostazioni applicano le impostazioni predefinite del server o dei criteri globali.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Assegnazione Per-User criteri di accesso esterno tramite Windows PowerShell cmdlet

I criteri di accesso esterno per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet Grant-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Per assegnare un criterio di accesso esterno per utente a un singolo utente

  - Questo comando assegna il criterio di accesso esterno per utente RedmondExternalAccessPolicy all'utente Ken Myer.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Per assegnare un criterio di accesso esterno per utente a più utenti

  - Questo comando assegna il criterio di accesso esterno per utente USAExternalAccessPolicy a tutti gli utenti che dispongono di account nell'unità organizzativa UnitedStates in Active Directory. Per ulteriori informazioni sul parametro OU utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser.](/powershell/module/skype/Get-CsUser)<br/><br/>Get-CsUser -OU "ou=United States,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Per annullare l'assegnazione di un criterio di accesso esterno per utente

  - Questo comando annulla l'assegnazione di tutti i criteri di accesso esterno per utente precedentemente assegnati a Ken Myer. Dopo l'annullamento del criterio per utente, Ken Myer sarà gestito automaticamente dal criterio globale oppure dall'eventuale criterio del sito locale, che ha la precedenza sul criterio globale.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null


Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Grant-CsExternalAccessPolicy)
