---
title: Abilitazione del controllo dell'ammissione alle chiamate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Dopo aver configurato la rete di controllo di ammissione chiamata (CAC), è necessario abilitare CAC per applicare le limitazioni della larghezza di banda."
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188588"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="5cd47-103">Abilitazione del controllo di ammissione alle chiamate in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cd47-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="5cd47-104">Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile.</span><span class="sxs-lookup"><span data-stu-id="5cd47-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="5cd47-105">Dopo aver configurato la rete CAC, è necessario abilitare CAC per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="5cd47-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="5cd47-106">Per eseguire questa operazione, è possibile usare il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5cd47-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="5cd47-107">Per abilitare CAC dal pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5cd47-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5cd47-108">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5cd47-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5cd47-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5cd47-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5cd47-110">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="5cd47-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="5cd47-111">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="5cd47-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="5cd47-112">Solo una rete può essere configurata per qualsiasi distribuzione di Skype for Business Server, quindi non ci saranno mai più configurazioni di rete nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5cd47-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="5cd47-113">Non è possibile rinominare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="5cd47-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="5cd47-114">Nel menu **modifica** fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5cd47-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5cd47-115">Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** e quindi fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="5cd47-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="5cd47-116">Quando si fa clic su **commit**, si esegue un test della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5cd47-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="5cd47-117">La finestra di dialogo **Modifica impostazioni globali** viene chiusa, tornando alla pagina **globale** .</span><span class="sxs-lookup"><span data-stu-id="5cd47-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="5cd47-118">Verrà visualizzato un messaggio di avviso in caso di errori o incongruenze individuati nella configurazione di rete che ne impediscono il corretto funzionamento, ad esempio se ogni area geografica non è connessa a tutte le altre aree geografiche tramite una route interregion.</span><span class="sxs-lookup"><span data-stu-id="5cd47-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="5cd47-119">Se si apportano modifiche alla configurazione di rete, è possibile eseguire di nuovo il controllo di convalida aprendo la configurazione globale e facendo clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="5cd47-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="5cd47-120">Non è necessario disabilitare prima CAC: tenere selezionata la casella di controllo e fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="5cd47-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="5cd47-121">Puoi eseguire questa operazione in qualsiasi momento senza apportare modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="5cd47-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cd47-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cd47-122">See Also</span></span>

[<span data-ttu-id="5cd47-123">Pianificazione del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="5cd47-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="5cd47-124">Configurare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="5cd47-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="5cd47-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cd47-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="5cd47-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cd47-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="5cd47-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cd47-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
