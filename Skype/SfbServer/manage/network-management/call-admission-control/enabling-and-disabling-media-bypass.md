---
title: Abilitazione e disabilitazione del bypass multimediale
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
description: Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816496"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="b54b1-103">Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b54b1-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="b54b1-104">Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="b54b1-105">Abilitare il bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="b54b1-105">Enable network media bypass</span></span> 

<span data-ttu-id="b54b1-106">Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="b54b1-107">Il bypass multimediale consente alle chiamate di bypassare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="b54b1-108">Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Plan for Media Bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b54b1-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="b54b1-109">È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="b54b1-110">Per abilitare e configurare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="b54b1-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="b54b1-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b54b1-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b54b1-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b54b1-113">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="b54b1-p102">Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="b54b1-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="b54b1-116">Scegliere  **Mostra dettagli** dal menu  **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="b54b1-117">Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita bypass multimediale** .</span><span class="sxs-lookup"><span data-stu-id="b54b1-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="b54b1-118">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b54b1-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="b54b1-119">**Ignora sempre**   Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="b54b1-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="b54b1-120">Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato.</span><span class="sxs-lookup"><span data-stu-id="b54b1-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="b54b1-121">Se il servizio di controllo di ammissione non è abilitato, selezionare questa opzione nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b54b1-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="b54b1-122">Non è necessario il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="b54b1-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="b54b1-123">Non è necessario disporre di una configurazione fine per determinare quando dovrebbe verificarsi un bypass.</span><span class="sxs-lookup"><span data-stu-id="b54b1-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="b54b1-124">La connettività tra gateway e client è completa.</span><span class="sxs-lookup"><span data-stu-id="b54b1-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="b54b1-125">**Utilizzare la configurazione dei siti e delle aree**   geografiche   Se il servizio di controllo di ammissione è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="b54b1-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="b54b1-126">Quando questa opzione è selezionata, i siti e le aree di configurazione di rete verranno utilizzati per determinare quando è possibile il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="b54b1-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="b54b1-127">Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati.</span><span class="sxs-lookup"><span data-stu-id="b54b1-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="b54b1-128">Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si dispone di uno o più siti di grandi dimensioni associati alla stessa area che non dispongono di vincoli di larghezza di banda (ad esempio, un sito centrale di grandi dimensioni) e si dispone anche di alcuni siti di succursale associati alla stessa area in cui sono presenti vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="b54b1-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="b54b1-129">Quando si Abilita il bypass per i siti non mappati, la configurazione viene semplificata perché sono state specificate solo le subnet associate ai siti di succursale anziché la necessità di specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="b54b1-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="b54b1-130">Si consiglia di non selezionare la casella **di controllo Abilita bypass per i siti non mappati** se è abilitato CAC.</span><span class="sxs-lookup"><span data-stu-id="b54b1-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="b54b1-131">Fare clic su  **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b54b1-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="b54b1-132">Disattiva bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="b54b1-132">Disable network media bypass</span></span>

<span data-ttu-id="b54b1-133">Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="b54b1-134">Il bypass multimediale consente alle chiamate di bypassare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="b54b1-135">Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Plan for Media Bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b54b1-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="b54b1-136">È possibile disabilitare il bypass multimediale dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="b54b1-137">Per disabilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="b54b1-137">To disable media bypass</span></span>

1.  <span data-ttu-id="b54b1-138">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b54b1-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b54b1-139">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b54b1-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b54b1-140">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="b54b1-p106">Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="b54b1-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="b54b1-143">Scegliere  **Mostra dettagli** dal menu  **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="b54b1-144">Nella pagina  **Modifica impostazioni globali** deselezionare la casella di controllo  **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="b54b1-145">Fare clic su  **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b54b1-145">Click **Commit** to save your changes.</span></span>

  
