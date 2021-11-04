---
title: Reimpostare il criterio globale per l'accesso degli utenti esterni
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Non è possibile eliminare completamente un criterio globale. Se si **utilizza l'opzione** Elimina nel criterio globale, vengono ripristinate solo le impostazioni predefinite del criterio globale, che non includono il supporto per le opzioni di accesso degli utenti esterni.
ms.openlocfilehash: b3748ee6a2e8bcfde9cec58a45db48f73bbabcc3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765434"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Reimpostare i criteri globali per l'accesso degli utenti esterni in Skype for Business Server 

Se sono stati creati o configurati criteri di accesso utente esterno che non si desidera più utilizzare, è possibile utilizzare i metodi seguenti:

  - Eliminare gli eventuali criteri a livello di sito o utente creati.

  - Ripristinare le impostazioni predefinite del criterio globale. Le impostazioni predefinite dei criteri globali negano qualsiasi accesso utente esterno. Il criterio globale non può essere eliminato.

Non è possibile eliminare completamente un criterio globale. **L'opzione** Elimina nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Per reimpostare le impostazioni predefinite dei criteri globali

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins o con diritti utente equivalenti o assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella scheda **Criteri di accesso esterno** fare clic sui criteri globali, quindi su **Modifica** e infine su **Elimina**.

5.  Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Verrà visualizzato un messaggio nella parte superiore della pagina che informa che i criteri globali sono stati reimpostati.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Reimpostazione dei criteri di accesso esterno globale tramite Windows PowerShell cmdlet

Il criterio di accesso esterno globale può essere reimpostato utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Per reimpostare il criterio di accesso esterno globale

  - Questo comando reimposta i criteri globali per l'accesso esterno<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
