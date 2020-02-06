---
title: Attivazione e disattivazione del bypass multimediale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817545"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="a5424-103">Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5424-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="a5424-104">Usare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale tramite il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="a5424-105">Abilitare il bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="a5424-105">Enable network media bypass</span></span> 

<span data-ttu-id="a5424-106">Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a5424-107">Il bypass multimediale consente alle chiamate di aggirare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a5424-108">Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a5424-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="a5424-109">È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="a5424-110">Per abilitare e configurare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a5424-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="a5424-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a5424-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5424-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5424-113">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="a5424-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a5424-114">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="a5424-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a5424-115">Esiste sempre una sola configurazione ed è sempre denominata globale.</span><span class="sxs-lookup"><span data-stu-id="a5424-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a5424-116">Nel menu **modifica** fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a5424-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a5424-117">Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="a5424-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a5424-118">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5424-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="a5424-119">**Ignora sempre seleziona**   questa opzione per provare il bypass multimediale in tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="a5424-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="a5424-120">Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato.</span><span class="sxs-lookup"><span data-stu-id="a5424-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="a5424-121">Se CAC non è abilitato, selezionare questa opzione nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5424-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="a5424-122">Non è necessario il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="a5424-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="a5424-123">Non c'è bisogno di una configurazione a grana fine per determinare quando deve avvenire il bypass.</span><span class="sxs-lookup"><span data-stu-id="a5424-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="a5424-124">Esiste una connettività completa tra gateway e client.</span><span class="sxs-lookup"><span data-stu-id="a5424-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="a5424-125">**Usare i siti e la configurazione**   dell'area se è abilitato CAC, questa opzione è selezionata per impostazione predefinita e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="a5424-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="a5424-126">Quando questa opzione è selezionata, i siti e le aree di configurazione della rete verranno usati per determinare quando il bypass multimediale è possibile.</span><span class="sxs-lookup"><span data-stu-id="a5424-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="a5424-127">Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati.</span><span class="sxs-lookup"><span data-stu-id="a5424-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="a5424-128">Fare clic sulla casella **di controllo Abilita esclusione per i siti non mappati** solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, e si hanno anche alcuni siti di succursale associati alla stessa area geografica con vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="a5424-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="a5424-129">Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale e non è necessario specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="a5424-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="a5424-130">È consigliabile non selezionare la casella di controllo **Abilita esclusione per i siti non mappati** se è abilitato CAC.</span><span class="sxs-lookup"><span data-stu-id="a5424-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="a5424-131">Fare clic su **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a5424-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="a5424-132">Disabilitare il bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="a5424-132">Disable network media bypass</span></span>

<span data-ttu-id="a5424-133">Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="a5424-134">Il bypass multimediale consente alle chiamate di aggirare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a5424-135">Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificare il bypass multimediale](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a5424-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="a5424-136">È possibile disabilitare il bypass multimediale dal pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="a5424-137">Per disabilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="a5424-137">To disable media bypass</span></span>

1.  <span data-ttu-id="a5424-138">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a5424-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a5424-139">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5424-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a5424-140">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="a5424-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a5424-141">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="a5424-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="a5424-142">Esiste sempre una sola configurazione ed è sempre denominata globale.</span><span class="sxs-lookup"><span data-stu-id="a5424-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a5424-143">Nel menu **modifica** fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a5424-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a5424-144">Nella pagina **Modifica impostazioni globali** deselezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="a5424-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a5424-145">Fare clic su **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a5424-145">Click **Commit** to save your changes.</span></span>

  
