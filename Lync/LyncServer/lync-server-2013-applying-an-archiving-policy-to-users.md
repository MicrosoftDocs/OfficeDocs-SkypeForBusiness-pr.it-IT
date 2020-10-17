---
title: 'Lync Server 2013: applicazione di un criterio di archiviazione agli utenti'
description: 'Lync Server 2013: applicazione di criteri di archiviazione per gli utenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544972"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="494ca-103">Applicazione di un criterio di archiviazione agli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="494ca-103">Applying an Archiving policy to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="494ca-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="494ca-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="494ca-105">Se un utente è stato abilitato per Lync Server 2013 ed è stato creato uno o più criteri utente per l'archiviazione per gli utenti ospitati in Lync Server 2013, è possibile implementare il supporto per l'archiviazione per utenti specifici applicando i criteri adatti a tali utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="494ca-105">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="494ca-106">Ad esempio, se si crea un criterio per il supporto dell'archiviazione delle comunicazioni interne, è possibile applicarlo ad almeno un utente o un gruppo di utenti per supportare l'archiviazione delle comunicazioni di Lync Server 2013 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="494ca-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="494ca-107">Se è stata abilitata l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange 2013 e le relative cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="494ca-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="494ca-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">impostazione dei criteri per l'archiviazione in Lync server 2013 quando si utilizza l'integrazione di Exchange Server</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="494ca-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="494ca-109">Specificare tutte le opzioni appropriate nelle configurazioni di archiviazione prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="494ca-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="494ca-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 per l'organizzazione, i siti e i pool</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="494ca-110">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="494ca-111">Utilizzare la procedura in questo argomento per applicare criteri di archiviazione a livello utente creati in precedenza a uno o più account utente o gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="494ca-111">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="494ca-112">Per applicare criteri di archiviazione a livello di utente a un account utente</span><span class="sxs-lookup"><span data-stu-id="494ca-112">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="494ca-113">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="494ca-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="494ca-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="494ca-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="494ca-115">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="494ca-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="494ca-116">Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="494ca-116">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="494ca-117">Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="494ca-117">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="494ca-118">In **modifica utente di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="494ca-118">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="494ca-119">Le impostazioni <STRONG> &lt; automatiche &gt; </STRONG> applicano le impostazioni di installazione predefinite del server.</span><span class="sxs-lookup"><span data-stu-id="494ca-119">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="494ca-120">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="494ca-120">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="494ca-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="494ca-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="494ca-122">Assegnazione di un criterio di archiviazione Per-User tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="494ca-122">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="494ca-123">I criteri di archiviazione per utente possono essere assegnati utilizzando Windows PowerShell e il cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="494ca-123">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="494ca-124">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="494ca-124">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="494ca-125">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="494ca-125">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="494ca-126">Per assegnare criteri di archiviazione per utente a un singolo utente</span><span class="sxs-lookup"><span data-stu-id="494ca-126">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="494ca-127">Il comando seguente assegna il criterio di archiviazione per utente RedmondArchivingPolicy all'utente Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="494ca-127">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="494ca-128">Per assegnare criteri di archiviazione per utente a più utenti</span><span class="sxs-lookup"><span data-stu-id="494ca-128">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="494ca-129">Questo comando consente di assegnare i criteri di archiviazione per utente denominati RedmondArchivingPolicy a tutti gli utenti con account ospitati nel pool di registrazione atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="494ca-129">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="494ca-130">Per informazioni dettagliate sul parametro Filter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="494ca-130">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="494ca-131">Per assegnare criteri di archiviazione per utente</span><span class="sxs-lookup"><span data-stu-id="494ca-131">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="494ca-p108">Il comando seguente annulla l'assegnazione di qualsiasi criterio di archiviazione per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione dei criteri per utente, Ken Myer verrà gestito automaticamente mediante l'utilizzo dei criteri globali o dei criteri del sito locale, se esistenti. I criteri del sito hanno la precedenza sui criteri globali.</span><span class="sxs-lookup"><span data-stu-id="494ca-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="494ca-135">Per informazioni dettagliate, vedere la documentazione relativa al cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="494ca-135">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="494ca-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="494ca-136">See Also</span></span>


[<span data-ttu-id="494ca-137">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="494ca-137">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="494ca-138">Assegnazione di criteri per utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="494ca-138">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

