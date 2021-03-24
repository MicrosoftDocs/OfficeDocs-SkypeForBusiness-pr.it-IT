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
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="b9134-104">Reimpostare i criteri globali per l'accesso degli utenti esterni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9134-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="b9134-105">Se sono stati creati o configurati criteri di accesso per gli utenti esterni che non si desidera più utilizzare, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9134-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="b9134-106">Eliminare gli eventuali criteri a livello di sito o utente creati.</span><span class="sxs-lookup"><span data-stu-id="b9134-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="b9134-p102">Ripristinare le impostazioni predefinite per i criteri globali che negano qualsiasi tipo di accesso agli utenti esterni. I criteri globali non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="b9134-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="b9134-p103">Non è possibile eliminare completamente i criteri globali. Utilizzando l'opzione **Elimina** per i criteri globali vengono solo reimpostate le impostazioni predefinite dei criteri, che non includono il supporto per opzioni di accesso utente esterno.</span><span class="sxs-lookup"><span data-stu-id="b9134-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="b9134-112">Per reimpostare le impostazioni predefinite dei criteri globali</span><span class="sxs-lookup"><span data-stu-id="b9134-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="b9134-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b9134-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b9134-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b9134-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b9134-115">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="b9134-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b9134-116">Nella scheda **Criteri di accesso esterno** fare clic sui criteri globali, quindi su **Modifica** e infine su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b9134-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b9134-p104">Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**. Verrà visualizzato un messaggio nella parte superiore della pagina che informa che i criteri globali sono stati reimpostati.</span><span class="sxs-lookup"><span data-stu-id="b9134-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9134-119">Reimpostazione dei criteri di accesso esterno globale tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b9134-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b9134-120">Il criterio di accesso esterno globale può essere reimpostato utilizzando Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy locale.</span><span class="sxs-lookup"><span data-stu-id="b9134-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b9134-121">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9134-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="b9134-122">Per reimpostare il criterio di accesso esterno globale</span><span class="sxs-lookup"><span data-stu-id="b9134-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="b9134-123">Questo comando reimposta i criteri globali per l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="b9134-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="b9134-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="b9134-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>