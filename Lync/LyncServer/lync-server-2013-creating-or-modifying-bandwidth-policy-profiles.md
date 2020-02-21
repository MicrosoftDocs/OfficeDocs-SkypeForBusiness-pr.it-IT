---
title: 'Lync Server 2013: creazione o modifica di profili di criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="424ed-102">Creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="424ed-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="424ed-103">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="424ed-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="424ed-104">In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità.</span><span class="sxs-lookup"><span data-stu-id="424ed-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="424ed-105">In Microsoft Lync Server 2013, è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="424ed-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="424ed-106">È possibile impostare limitazioni della larghezza di banda globali o per le sessioni.</span><span class="sxs-lookup"><span data-stu-id="424ed-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="424ed-107">È possibile utilizzare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="424ed-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="424ed-108">Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete.</span><span class="sxs-lookup"><span data-stu-id="424ed-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="424ed-109">Utilizzare le procedure seguenti per creare o modificare un profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="424ed-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="424ed-110">Per eliminare un profilo dei criteri di larghezza di banda, vedere [eliminazione dei profili di criteri larghezza di banda di rete in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="424ed-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="424ed-111">Per creare un nuovo profilo di criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="424ed-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="424ed-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="424ed-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="424ed-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="424ed-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="424ed-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="424ed-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="424ed-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="424ed-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="424ed-116">Nella pagina **criteri larghezza di banda** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="424ed-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="424ed-117">In **nuovo profilo dei criteri di larghezza di banda**Digitare un nome nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="424ed-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="424ed-118">Questo nome deve essere univoco tra tutti i profili dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="424ed-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="424ed-119">Nel campo **limite audio** Digitare un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="424ed-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="424ed-120">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni audio espresse in kbps.</span><span class="sxs-lookup"><span data-stu-id="424ed-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="424ed-121">Immettere un valore numerico nel campo **limite sessione audio** .</span><span class="sxs-lookup"><span data-stu-id="424ed-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="424ed-122">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione audio, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="424ed-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="424ed-123">Questo valore deve essere 40 o superiore.</span><span class="sxs-lookup"><span data-stu-id="424ed-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="424ed-124">Immettere un valore numerico nel campo **limite video** .</span><span class="sxs-lookup"><span data-stu-id="424ed-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="424ed-125">Questo valore è la quantità massima di larghezza di banda da allocare per tutte le connessioni video espresse in kbps.</span><span class="sxs-lookup"><span data-stu-id="424ed-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="424ed-126">Immettere un valore numerico nel campo **limite sessione video** .</span><span class="sxs-lookup"><span data-stu-id="424ed-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="424ed-127">Questo valore è la quantità massima di larghezza di banda da allocare per una singola connessione video, espressa in kbps.</span><span class="sxs-lookup"><span data-stu-id="424ed-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="424ed-128">Questo valore deve essere 100 o superiore.</span><span class="sxs-lookup"><span data-stu-id="424ed-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="424ed-129">Optional Digitare un valore nel campo **Descrizione** per fornire ulteriori informazioni sul profilo dei criteri di larghezza di banda che non è possibile esprimere solo con il nome.</span><span class="sxs-lookup"><span data-stu-id="424ed-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="424ed-130">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="424ed-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="424ed-131">La creazione di un nuovo profilo di criteri di larghezza di banda non impone automaticamente restrizioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="424ed-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="424ed-132">È necessario innanzitutto associare il profilo dei criteri a un sito.</span><span class="sxs-lookup"><span data-stu-id="424ed-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="424ed-133">Per informazioni dettagliate su come associare un profilo dei criteri a un sito, vedere <A href="lync-server-2013-creating-or-modifying-network-sites.md">creazione o modifica di siti di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="424ed-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="424ed-134">Per modificare un profilo di criteri della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="424ed-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="424ed-135">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="424ed-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="424ed-136">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="424ed-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="424ed-137">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="424ed-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="424ed-138">Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="424ed-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="424ed-139">Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="424ed-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="424ed-140">Scegliere **Mostra dettagli** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="424ed-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="424ed-141">Nella pagina **modifica profilo dei criteri di larghezza di banda** modificare i campi in base alle esigenze (per informazioni dettagliate, vedere la sezione "per creare un profilo dei criteri di larghezza di banda" più indietro in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="424ed-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="424ed-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="424ed-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="424ed-143">Quando si modifica il profilo dei criteri di larghezza di banda, verranno aggiornate immediatamente le limitazioni della larghezza di banda di tutti i siti di rete associati al profilo del criterio di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="424ed-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="424ed-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="424ed-144">See Also</span></span>


[<span data-ttu-id="424ed-145">Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="424ed-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="424ed-146">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="424ed-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="424ed-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="424ed-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="424ed-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="424ed-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="424ed-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="424ed-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

