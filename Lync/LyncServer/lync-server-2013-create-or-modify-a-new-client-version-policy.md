---
title: 'Lync Server 2013: creare o modificare un nuovo criterio versione client'
description: 'Lync Server 2013: creare o modificare un nuovo criterio versione client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4d100e21591a27646784161614ff6c248dc6ae6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574612"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="98c40-103">Creare o modificare un nuovo criterio di versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c40-103">Create or modify a new client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c40-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="98c40-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="98c40-105">È possibile utilizzare i criteri versione client per specificare le versioni dei client supportati nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="98c40-105">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="98c40-106">L'utilizzo del controllo delle versioni client può contribuire a ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="98c40-106">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="98c40-107">È inoltre possibile migliorare l'esperienza complessiva degli utenti, perché quando le versioni precedenti e successive dei client interagiscono, le funzionalità disponibili possono essere limitate dalla versione precedente del client.</span><span class="sxs-lookup"><span data-stu-id="98c40-107">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="98c40-108">È possibile creare o modificare i criteri di versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="98c40-108">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="98c40-109">Per creare o modificare i criteri di versione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="98c40-109">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="98c40-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="98c40-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98c40-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98c40-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="98c40-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="98c40-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="98c40-113">Sulla barra di spostamento sinistra fare clic su **client**.</span><span class="sxs-lookup"><span data-stu-id="98c40-113">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c40-114">La scheda <STRONG>criteri versione client</STRONG> è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="98c40-114">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="98c40-115">Nella pagina **criteri versione client** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98c40-115">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="98c40-116">Per creare un criterio di versione client, fare clic su **nuovo**, selezionare **criteri sito**, **Criteri pool**o **criteri utente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c40-116">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="98c40-117">Per modificare il criterio globale o un altro criterio di versione client esistente, selezionare il criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="98c40-117">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="98c40-118">Nella pagina **modifica criteri versione client** creare o modificare regole come descritto in [creare o modificare una nuova regola di criteri di versione client in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="98c40-118">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98c40-119">Creazione o modifica di criteri di versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98c40-119">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="98c40-120">È possibile creare criteri versione client utilizzando il cmdlet **New-CsClientVersionPolicy** e modificarli utilizzando il cmdlet **Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="98c40-120">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="98c40-121">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98c40-121">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98c40-122">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="98c40-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="98c40-123">Per creare un nuovo criterio versione client con ambito sito</span><span class="sxs-lookup"><span data-stu-id="98c40-123">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="98c40-124">Il comando seguente consente di creare un nuovo criterio di versione client applicato al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="98c40-124">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="98c40-125">Poiché non sono specificati parametri aggiuntivi, il nuovo criterio utilizzerà le impostazioni predefinite della versione client.</span><span class="sxs-lookup"><span data-stu-id="98c40-125">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="98c40-126">Per creare un nuovo criterio di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="98c40-126">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="98c40-127">Per creare un criterio per utente, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="98c40-127">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="98c40-128">Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) e il cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="98c40-128">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

