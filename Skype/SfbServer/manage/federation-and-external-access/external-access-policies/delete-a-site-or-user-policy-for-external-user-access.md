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
localization_priority: Normal
description: Puoi eliminare qualsiasi criterio di sito o utente elencato nel pannello di controllo di Skype for Business Server nella pagina dei criteri di accesso esterno.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188813"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminare criteri di sito o utente per l'accesso degli utenti esterni

Se sono stati creati o configurati criteri di accesso degli utenti esterni che non si vuole più usare, è possibile eseguire le operazioni seguenti:

  - Eliminare qualsiasi criterio di sito o utente creato.

  - Reimpostare il criterio globale sulle impostazioni predefinite. Le impostazioni dei criteri globali predefinite negano l'accesso degli utenti esterni. Non è possibile eliminare il criterio globale.


Puoi eliminare qualsiasi criterio di sito o utente elencato nel pannello di controllo di Skype for Business Server nella pagina dei **criteri di accesso esterno** . L'eliminazione del criterio globale in realtà non lo elimina, ma lo reimposta solo sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni. Per informazioni dettagliate su come reimpostare il criterio globale, vedere [reimpostare il criterio globale per l'accesso degli utenti esterni](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Per eliminare un sito o un criterio utente per l'accesso degli utenti esterni

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.

4.  Nella scheda **criteri di accesso esterno** fare clic sul sito o sui criteri degli utenti da eliminare, fare clic su **modifica**e quindi su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell

I criteri di accesso esterno possono essere eliminati tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Per rimuovere un criterio di accesso esterno specifico

  - Questo comando rimuove il criterio di accesso esterno applicato al sito Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Per rimuovere tutti i criteri di accesso esterno applicati all'ambito per utente

  - Questo comando rimuove tutti i criteri di accesso esterno configurati nell'ambito per utente:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Per rimuovere tutti i criteri di accesso esterno in cui l'utente esterno è disabilitato

  - Questo comando Elimina tutti i criteri di accesso esterno in cui l'accesso esterno dell'utente è stato disabilitato:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
