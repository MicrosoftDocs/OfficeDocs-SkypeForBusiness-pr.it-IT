---
title: Reimpostare i criteri globali per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Non è possibile eliminare completamente un criterio globale. L'uso dell'opzione **Elimina** nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818267"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Reimpostare il criterio globale per l'accesso degli utenti esterni in Skype for Business Server 

Se sono stati creati o configurati criteri di accesso degli utenti esterni che non si vuole più usare, è possibile eseguire le operazioni seguenti:

  - Eliminare qualsiasi criterio di sito o utente creato.

  - Reimpostare il criterio globale sulle impostazioni predefinite. Le impostazioni dei criteri globali predefinite negano l'accesso degli utenti esterni. Non è possibile eliminare il criterio globale.

Non è possibile eliminare completamente un criterio globale. L'uso dell'opzione **Elimina** nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Per reimpostare il criterio globale sulle impostazioni predefinite

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.

4.  Nella scheda **criteri di accesso esterno** fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Nella parte superiore della pagina viene visualizzato un messaggio che informa che il criterio globale è stato reimpostato.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Reimpostazione del criterio di accesso esterno globale con i cmdlet di Windows PowerShell

Il criterio di accesso esterno globale può essere reimpostato tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Per reimpostare i criteri di accesso esterno globale

  - Questo comando Reimposta il criterio di accesso esterno globale:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


