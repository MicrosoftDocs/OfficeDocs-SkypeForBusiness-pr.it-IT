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
description: Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale utilizzando il Pannello di controllo di Skype for Business Server.
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816496"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="0cbcb-103">Abilitazione e disabilitazione del bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cbcb-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="0cbcb-104">Utilizzare le procedure descritte in questo articolo per abilitare o disabilitare il bypass multimediale utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="0cbcb-105">Abilitare il bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="0cbcb-105">Enable network media bypass</span></span> 

<span data-ttu-id="0cbcb-106">Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="0cbcb-107">Il bypass multimediale consente alle chiamate di ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="0cbcb-108">Per informazioni dettagliate su quando usare il bypass multimediale, vedi [Pianificare il bypass multimediale.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="0cbcb-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="0cbcb-109">È possibile abilitare e configurare il bypass multimediale dal Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="0cbcb-110">Per abilitare e configurare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="0cbcb-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="0cbcb-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0cbcb-112">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0cbcb-113">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Globale.**</span><span class="sxs-lookup"><span data-stu-id="0cbcb-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0cbcb-p102">Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="0cbcb-116">Scegliere  **Mostra dettagli** dal menu  **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="0cbcb-117">Nella pagina **Modifica impostazione globale** fare clic sulla casella di controllo Abilita **bypass** multimediale.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="0cbcb-118">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbcb-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="0cbcb-119">**Ignora sempre**   Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="0cbcb-120">Questa opzione non sarà disponibile se il servizio Controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="0cbcb-121">Se il servizio Controllo di ammissione di chiamata non è abilitato, selezionare questa opzione nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cbcb-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="0cbcb-122">Non è necessario il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="0cbcb-123">Non è necessaria una configurazione specifica per determinare quando deve verificarsi il bypass.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="0cbcb-124">Esiste una connettività completa tra gateway e client.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="0cbcb-125">**Usare la configurazione di siti e aree**   Se il servizio Controllo di ammissione di chiamata è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="0cbcb-126">Quando questa opzione è selezionata, i siti e le aree di configurazione di rete verranno utilizzati per determinare quando è possibile il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="0cbcb-127">Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="0cbcb-128">Selezionare la casella di controllo Abilita bypass per i siti **non** mappati solo se alla stessa area sono associati uno o più siti di grandi dimensioni che non dispongono di vincoli di larghezza di banda(ad esempio, un sito centrale di grandi dimensioni) e alcuni siti di succursale sono associati alla stessa area con vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="0cbcb-129">Quando si abilita il bypass per i siti non mappati, la configurazione è semplificata perché si specificano solo le subnet associate ai siti di succursale anziché è necessario specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="0cbcb-130">È consigliabile non selezionare la casella di controllo Abilita bypass per i siti **non** mappati se il servizio Controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="0cbcb-131">Fare clic su  **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="0cbcb-132">Disabilitare il bypass multimediale di rete</span><span class="sxs-lookup"><span data-stu-id="0cbcb-132">Disable network media bypass</span></span>

<span data-ttu-id="0cbcb-133">Le impostazioni di bypass multimediale si applicano a livello globale in una distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="0cbcb-134">Il bypass multimediale consente alle chiamate di ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="0cbcb-135">Per informazioni dettagliate su quando usare il bypass multimediale, vedi [Pianificare il bypass multimediale.](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="0cbcb-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="0cbcb-136">È possibile disabilitare il bypass multimediale dal Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="0cbcb-137">Per disabilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="0cbcb-137">To disable media bypass</span></span>

1.  <span data-ttu-id="0cbcb-138">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0cbcb-139">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0cbcb-140">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Globale.**</span><span class="sxs-lookup"><span data-stu-id="0cbcb-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="0cbcb-p106">Nella pagina  **Globale** fare clic sulla scheda della configurazione  **Globale**. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="0cbcb-143">Scegliere  **Mostra dettagli** dal menu  **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="0cbcb-144">Nella pagina  **Modifica impostazioni globali** deselezionare la casella di controllo  **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="0cbcb-145">Fare clic su  **Commit** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0cbcb-145">Click **Commit** to save your changes.</span></span>

  
