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
localization_priority: Normal
description: Non è possibile eliminare completamente un criterio globale. L'uso dell'opzione **Elimina** nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188801"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="b1964-104">Reimpostare il criterio globale per l'accesso degli utenti esterni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b1964-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="b1964-105">Se sono stati creati o configurati criteri di accesso degli utenti esterni che non si vuole più usare, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b1964-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="b1964-106">Eliminare qualsiasi criterio di sito o utente creato.</span><span class="sxs-lookup"><span data-stu-id="b1964-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="b1964-107">Reimpostare il criterio globale sulle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="b1964-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="b1964-108">Le impostazioni dei criteri globali predefinite negano l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="b1964-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="b1964-109">Non è possibile eliminare il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="b1964-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="b1964-110">Non è possibile eliminare completamente un criterio globale.</span><span class="sxs-lookup"><span data-stu-id="b1964-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="b1964-111">L'uso dell'opzione **Elimina** nel criterio globale reimposta solo il criterio globale sulle impostazioni predefinite, che non includono il supporto per le opzioni di accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="b1964-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="b1964-112">Per reimpostare il criterio globale sulle impostazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="b1964-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="b1964-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b1964-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1964-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b1964-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b1964-115">Sulla barra di spostamento sinistra fare clic su **accesso utente esterno**, fare clic su **criteri di accesso esterno**.</span><span class="sxs-lookup"><span data-stu-id="b1964-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b1964-116">Nella scheda **criteri di accesso esterno** fare clic sul criterio globale, scegliere **modifica**e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b1964-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b1964-117">Quando viene richiesto di confermare l'eliminazione, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1964-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="b1964-118">Nella parte superiore della pagina viene visualizzato un messaggio che informa che il criterio globale è stato reimpostato.</span><span class="sxs-lookup"><span data-stu-id="b1964-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b1964-119">Reimpostazione del criterio di accesso esterno globale con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1964-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b1964-120">Il criterio di accesso esterno globale può essere reimpostato tramite Windows PowerShell e il cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="b1964-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b1964-121">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1964-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="b1964-122">Per reimpostare i criteri di accesso esterno globale</span><span class="sxs-lookup"><span data-stu-id="b1964-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="b1964-123">Questo comando Reimposta il criterio di accesso esterno globale:</span><span class="sxs-lookup"><span data-stu-id="b1964-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="b1964-124">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="b1964-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


