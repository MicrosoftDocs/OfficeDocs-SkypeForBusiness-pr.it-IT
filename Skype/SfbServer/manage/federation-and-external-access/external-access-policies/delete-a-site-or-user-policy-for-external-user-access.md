---
title: Eliminare criteri sito o utente per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: È possibile eliminare qualsiasi criterio sito o utente elencato nel Pannello di controllo di Skype for Business Server nella pagina Criteri di accesso esterno.
ms.openlocfilehash: 136b7f612dc2dcc0625e7f844ecf6ad38aba0c37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834224"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminare criteri sito o utente per l'accesso degli utenti esterni

Se sono stati creati o configurati criteri di accesso utente esterno che non si desidera più utilizzare, è possibile eseguire il metodo seguente:

  - Eliminare gli eventuali criteri a livello di sito o utente creati.

  - Ripristinare le impostazioni predefinite per i criteri globali che negano qualsiasi tipo di accesso agli utenti esterni. I criteri globali non possono essere eliminati.


È possibile eliminare qualsiasi criterio sito o utente elencato nel Pannello di controllo di Skype for Business Server nella **pagina Criteri di accesso** esterno. L'eliminazione del criterio globale non lo elimina effettivamente, ma lo reimposta solo alle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni. Per informazioni dettagliate sulla reimpostazione del criterio globale, vedere [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Per eliminare criteri sito o utente per l'accesso utente esterno

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello Skype for Business Server controllo. 

3.  Fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella scheda **Criteri di accesso esterno** fare clic sui criteri sito o utente che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri PIN tramite Windows PowerShell cmdlet

I criteri di accesso esterno possono essere eliminati utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy.External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Per rimuovere un criterio di accesso esterno specifico

  - Questo comando rimuove i criteri di accesso esterno applicati al sito Redmond:<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito "per utente":<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Per rimuovere tutti i criteri di accesso esterno in cui l'accesso utente esterno è disabilitato

  - Questo comando elimina tutti i criteri di accesso esterno dove l'accesso esterno dell'utente è stato disattivato:<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
