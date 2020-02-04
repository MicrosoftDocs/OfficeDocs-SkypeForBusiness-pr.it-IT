---
title: 'Lync Server 2013: creare o modificare un nuovo criterio di versione client'
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
ms.openlocfilehash: 1469bb017f9597bcd1fffba54f39e62dc0bd6e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="d9536-102">Creare o modificare un nuovo criterio di versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9536-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9536-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d9536-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d9536-104">È possibile usare i criteri di versione client per specificare le versioni dei client supportate nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9536-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="d9536-105">L'uso del controllo delle versioni dei client consente di ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="d9536-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="d9536-106">Può anche migliorare l'esperienza utente complessiva, perché quando le versioni precedenti e successive dei client interagiscono, le funzionalità disponibili possono essere limitate dalla versione precedente del client.</span><span class="sxs-lookup"><span data-stu-id="d9536-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="d9536-107">È possibile creare o modificare i criteri di versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d9536-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="d9536-108">Per creare o modificare i criteri di versione client tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d9536-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d9536-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="d9536-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9536-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9536-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9536-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d9536-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9536-112">Sulla barra di spostamento sinistra fare clic su **client**.</span><span class="sxs-lookup"><span data-stu-id="d9536-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9536-113">La scheda <STRONG>criteri versione client</STRONG> è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9536-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="d9536-114">Nella pagina **criteri di versione client** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9536-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d9536-115">Per creare un criterio di versione client, fare clic su **nuovo**, selezionare **criteri sito**, **criteri di pool**o **criteri utente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9536-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d9536-116">Per modificare il criterio globale o un altro criterio di versione client esistente, selezionare il criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d9536-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d9536-117">Nella pagina **modifica criteri di versione client** creare o modificare le regole come descritto in [creare o modificare una nuova regola dei criteri di versione client in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="d9536-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d9536-118">Creazione o modifica di criteri di versione client con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d9536-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d9536-119">È possibile creare criteri di versione client usando il cmdlet **New-CsClientVersionPolicy** e modificarli usando il cmdlet **Set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="d9536-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="d9536-120">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9536-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9536-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="d9536-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="d9536-122">Per creare un nuovo criterio di versione del client con ambito sito</span><span class="sxs-lookup"><span data-stu-id="d9536-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="d9536-123">Il comando seguente crea un nuovo criterio di versione client applicato al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="d9536-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="d9536-124">Dato che non sono specificati parametri aggiuntivi, il nuovo criterio utilizzerà le impostazioni della versione client predefinite.</span><span class="sxs-lookup"><span data-stu-id="d9536-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="d9536-125">Per creare un nuovo criterio di versione client per utente</span><span class="sxs-lookup"><span data-stu-id="d9536-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="d9536-126">Per creare un criterio per utente, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d9536-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="d9536-127">Per informazioni dettagliate, vedere gli argomenti della Guida relativi al cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) e al cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="d9536-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

