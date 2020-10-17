---
title: "Lync Server 2013: abilitare o disabilitare l'accesso degli utenti remoti"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f02281bdb47fc043d372f5b6e3842a70fe39316
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515549"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="02d24-102">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d24-102">Enable or disable remote user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02d24-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="02d24-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="02d24-104">Gli utenti remoti sono utenti dell'organizzazione che dispongono di un'identità Active Directory permanente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02d24-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="02d24-105">Gli utenti remoti spesso accedono a Lync Server dall'esterno della rete utilizzando una rete privata virtuale (VPN, Virtual Private Network) quando non sono connessi alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02d24-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="02d24-106">Tra gli utenti remoti sono inclusi i dipendenti che lavorano dalla propria abitazione o in viaggio e altri lavoratori remoti, ad esempio fornitori considerati attendibili a cui sono state concesse credenziali aziendali.</span><span class="sxs-lookup"><span data-stu-id="02d24-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="02d24-107">Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono su Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni utilizzando Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02d24-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="02d24-p102">Per supportare l'accesso degli utenti remoti, è necessario abilitarlo. Quando si abilita l'accesso degli utenti remoti, tale impostazione si applica all'intera organizzazione. Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="02d24-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02d24-112">Abilitando l'accesso degli utenti remoti, si specifica soltanto che i server che eseguono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma questi ultimi non possono utilizzare la messaggistica istantanea o partecipare a conferenze nell'organizzazione finché non si configura almeno un criterio per la gestione dell'utilizzo dell'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="02d24-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="02d24-113">Le impostazioni criteri di Lync Server applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="02d24-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="02d24-114">La precedenza dei criteri di Lync Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="02d24-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="02d24-115">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="02d24-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="02d24-116">Per informazioni dettagliate sulla configurazione dei criteri per l'utilizzo dell'accesso degli utenti remoti, vedere <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to Control Remote User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02d24-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="02d24-117">Per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="02d24-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="02d24-118">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="02d24-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02d24-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02d24-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="02d24-120">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="02d24-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="02d24-121">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="02d24-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="02d24-122">Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="02d24-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="02d24-123">In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02d24-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="02d24-124">Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto utenti**.</span><span class="sxs-lookup"><span data-stu-id="02d24-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="02d24-125">Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto utenti**.</span><span class="sxs-lookup"><span data-stu-id="02d24-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="02d24-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="02d24-126">Click **Commit**.</span></span>

<span data-ttu-id="02d24-127">Per consentire agli utenti remoti di accedere ai server che eseguono Lync Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="02d24-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="02d24-128">Per informazioni dettagliate, vedere [Configure policies to Control Remote User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="02d24-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02d24-129">Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02d24-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02d24-130">È possibile gestire l'accesso degli utenti remoti tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="02d24-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="02d24-131">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02d24-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02d24-132">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="02d24-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="02d24-133">Per abilitare l'accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="02d24-133">To enable remote user access</span></span>

  - <span data-ttu-id="02d24-134">Per abilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="02d24-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="02d24-135">Per disabilitare l'accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="02d24-135">To disable remote user access</span></span>

  - <span data-ttu-id="02d24-136">Per disabilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="02d24-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

