---
title: Eliminare criteri di sito o utente per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: È possibile eliminare tutti i criteri di sito o utente elencati nel pannello di controllo di Skype for Business Server nella pagina Criteri di accesso esterno.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041235"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminare criteri di sito o utente per l'accesso degli utenti esterni

Se sono stati creati o configurati criteri di accesso per gli utenti esterni che non si desidera più utilizzare, è possibile eseguire le operazioni seguenti:

  - Eliminare gli eventuali criteri a livello di sito o utente creati.

  - Ripristinare le impostazioni predefinite per i criteri globali che negano qualsiasi tipo di accesso agli utenti esterni. I criteri globali non possono essere eliminati.


È possibile eliminare tutti i criteri di sito o utente elencati nel pannello di controllo di Skype for Business Server nella pagina **criteri di accesso esterno** . L'eliminazione di criteri globali non ne implica l'effettiva rimozione, ma solo il ripristino delle impostazioni predefinite, che non includono il supporto per alcuna opzione di accesso utente esterno. Per informazioni dettagliate sulla reimpostazione dei criteri globali, vedere [reimpostare i criteri globali per l'accesso degli utenti esterni](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Per eliminare criteri sito o utente per l'accesso utente esterno

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 

3.  Fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella scheda **Criteri di accesso esterno** fare clic sui criteri sito o utente che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri del PIN tramite i cmdlet di Windows PowerShell

È possibile eliminare i criteri di accesso esterno utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Per rimuovere un criterio di accesso esterno specifico

  - Questo comando rimuove i criteri di accesso esterno applicati al sito Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito "per utente":
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Per rimuovere tutti i criteri di accesso esterno a cui è disabilitato l'accesso utente esterno

  - Questo comando elimina tutti i criteri di accesso esterno dove l'accesso esterno dell'utente è stato disattivato:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .
