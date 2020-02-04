---
title: 'Lync Server 2013: eliminazione dei profili dei criteri di larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d01bdea6efb632d95a15c631715e9ebe0c9a3bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="646ae-102">Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="646ae-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="646ae-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="646ae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="646ae-104">Nell'ambito del controllo di ammissione di chiamata (CAC) viene usato un criterio di larghezza di banda per definire le limitazioni della larghezza di banda per determinate modalità.</span><span class="sxs-lookup"><span data-stu-id="646ae-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="646ae-105">In Microsoft Lync Server 2013 solo le modalità audio e video possono essere assegnate alle limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="646ae-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="646ae-106">Puoi impostare limitazioni generali della larghezza di banda e limitazioni della sessione.</span><span class="sxs-lookup"><span data-stu-id="646ae-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="646ae-107">È possibile usare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri.</span><span class="sxs-lookup"><span data-stu-id="646ae-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="646ae-108">Usare le procedure seguenti per eliminare i profili dei criteri di larghezza di banda di rete.</span><span class="sxs-lookup"><span data-stu-id="646ae-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="646ae-109">Per informazioni dettagliate sulla creazione o la modifica di un profilo dei criteri di larghezza di banda della rete, vedere [creazione o modifica dei profili dei criteri di larghezza di banda in Lync 2013 server](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="646ae-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="646ae-110">Per eliminare un profilo dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="646ae-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="646ae-111">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="646ae-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="646ae-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="646ae-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="646ae-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="646ae-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="646ae-114">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **criteri larghezza di banda**.</span><span class="sxs-lookup"><span data-stu-id="646ae-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="646ae-115">Nella pagina **criteri di larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="646ae-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="646ae-116">È possibile eliminare più di un profilo alla volta.</span><span class="sxs-lookup"><span data-stu-id="646ae-116">You can delete more than one profile at a time.</span></span> <span data-ttu-id="646ae-117">Per eseguire questa operazione, premere CTRL e selezionare più profili tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="646ae-117">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="646ae-118">In alternativa, per selezionare tutti i profili, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="646ae-118">Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="646ae-119">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="646ae-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="646ae-120">Non è possibile eliminare un profilo dei criteri di larghezza di banda associato a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="646ae-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="646ae-121">Prima di poter eliminare il profilo, devi prima rimuovere l'associazione con il sito di rete.</span><span class="sxs-lookup"><span data-stu-id="646ae-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="646ae-122">Per informazioni dettagliate su come modificare il sito di rete, vedere <A href="lync-server-2013-creating-or-modifying-network-sites.md">creazione o modifica di siti di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="646ae-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="646ae-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="646ae-123">See Also</span></span>


[<span data-ttu-id="646ae-124">Creazione o modifica dei profili dei criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="646ae-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="646ae-125">Visualizzazione delle informazioni del profilo dei criteri di larghezza di banda di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="646ae-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="646ae-126">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="646ae-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="646ae-127">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="646ae-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

