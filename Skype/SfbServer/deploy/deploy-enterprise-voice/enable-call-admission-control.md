---
title: Abilitare il controllo di ammissione alle chiamate in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Abilitare il controllo di ammissione alle chiamate in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e88c0e87f9c920420ce2091ac2d75d04db6ca98f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002566"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="8166d-103">Abilitare il controllo di ammissione alle chiamate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8166d-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="8166d-104">Abilitare il controllo di ammissione alle chiamate in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="8166d-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8166d-105">Dopo aver configurato le impostazioni di rete per la distribuzione del controllo di ammissione alle chiamate, è necessario abilitare CAC per applicare i criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="8166d-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8166d-106">Per abilitare il controllo dell'ammissione alle chiamate usando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8166d-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8166d-107">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8166d-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8166d-108">Eseguire il cmdlet Set-CsNetworkConfiguration per abilitare CAC nella rete.</span><span class="sxs-lookup"><span data-stu-id="8166d-108">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network.</span></span> <span data-ttu-id="8166d-109">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8166d-109">For example, run:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="8166d-110">Se si vuole disabilitare CAC nella rete, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8166d-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8166d-111">Per abilitare il controllo dell'ammissione tramite chiamata tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8166d-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8166d-112">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8166d-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8166d-113">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="8166d-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="8166d-114">Fare clic sul pulsante di spostamento **globale** .</span><span class="sxs-lookup"><span data-stu-id="8166d-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="8166d-115">Fare clic su **globale** nell'elenco e quindi selezionare **Mostra dettagli** dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="8166d-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="8166d-116">Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** .</span><span class="sxs-lookup"><span data-stu-id="8166d-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8166d-117">Se si vuole disabilitare il controllo di ammissione delle chiamate durante la distribuzione, deselezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8166d-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="8166d-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8166d-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="8166d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8166d-119">See also</span></span>

[<span data-ttu-id="8166d-120">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8166d-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="8166d-121">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8166d-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="8166d-122">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8166d-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
