---
title: Abilitazione del controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Una volta configurata la rete di controllo di ammissione di chiamata, è necessario abilitare CAC per applicare le limitazioni della larghezza di banda."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816506"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="65c14-103">Abilitazione del controllo di ammissione di chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65c14-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="65c14-104">Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile.</span><span class="sxs-lookup"><span data-stu-id="65c14-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="65c14-105">Dopo avere configurato tale rete, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="65c14-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="65c14-106">Per eseguire questa operazione, è possibile utilizzare il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65c14-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="65c14-107">Per abilitare CAC dal pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65c14-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="65c14-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="65c14-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65c14-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65c14-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65c14-110">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="65c14-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="65c14-111">Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**.</span><span class="sxs-lookup"><span data-stu-id="65c14-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="65c14-112">Solo una rete può essere configurata per qualsiasi distribuzione di Skype for Business Server, quindi non vi sarà mai più di una configurazione di rete nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="65c14-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="65c14-113">Non è possibile rinominare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="65c14-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="65c14-114">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="65c14-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="65c14-115">Nella pagina **Modifica Impostazioni globali** selezionare la casella di controllo **Abilita il controllo di ammissione di chiamata** e quindi fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="65c14-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="65c14-p103">Quando si fa clic su **Commit**, si esegue un test della configurazione. La finestra di dialogo **Modifica Impostazioni globali** si chiude e si torna alla pagina **Globale**. Si riceverà un avviso se nella configurazione di rete vengono rilevati eventuali errori o incongruenze che ne impediscono il corretto funzionamento, ad esempio se non tutte le aree sono connesse a tutte le altre aree mediante una route tra aree.</span><span class="sxs-lookup"><span data-stu-id="65c14-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="65c14-p104">Se si apportano modifiche alla configurazione di rete, sarà possibile eseguire di nuovo la convalida aprendo la configurazione globale e facendo clic su **Commit**. Non è necessario disabilitare prima il controllo di ammissione di chiamata, perciò lasciare selezionata la casella di controllo e fare clic su **Commit**. È possibile procedere in questo modo in qualsiasi momento senza apportare modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="65c14-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="65c14-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c14-122">See Also</span></span>

[<span data-ttu-id="65c14-123">Pianificare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="65c14-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="65c14-124">Distribuire il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="65c14-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="65c14-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="65c14-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="65c14-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="65c14-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="65c14-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="65c14-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
