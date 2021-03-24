---
title: Reimpostare il criterio globale per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Non è possibile eliminare completamente i criteri globali. Utilizzando l'opzione **Elimina** per i criteri globali vengono solo reimpostate le impostazioni predefinite dei criteri, che non includono il supporto per opzioni di accesso utente esterno.
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098972"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Reimpostare i criteri globali per l'accesso degli utenti esterni in Skype for Business Server 

Se sono stati creati o configurati criteri di accesso per gli utenti esterni che non si desidera più utilizzare, è possibile eseguire le operazioni seguenti:

  - Eliminare gli eventuali criteri a livello di sito o utente creati.

  - Ripristinare le impostazioni predefinite per i criteri globali che negano qualsiasi tipo di accesso agli utenti esterni. I criteri globali non possono essere eliminati.

Non è possibile eliminare completamente i criteri globali. Utilizzando l'opzione **Elimina** per i criteri globali vengono solo reimpostate le impostazioni predefinite dei criteri, che non includono il supporto per opzioni di accesso utente esterno.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Per reimpostare le impostazioni predefinite dei criteri globali

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella scheda **Criteri di accesso esterno** fare clic sui criteri globali, quindi su **Modifica** e infine su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Verrà visualizzato un messaggio nella parte superiore della pagina che informa che i criteri globali sono stati reimpostati.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Reimpostazione dei criteri di accesso esterno globale tramite Windows PowerShell cmdlet

Il criterio di accesso esterno globale può essere reimpostato utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy locale. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Per reimpostare il criterio di accesso esterno globale

  - Questo comando reimposta i criteri globali per l'accesso esterno
    
        Remove-CsExternalAccessPolicy -Identity "global"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)