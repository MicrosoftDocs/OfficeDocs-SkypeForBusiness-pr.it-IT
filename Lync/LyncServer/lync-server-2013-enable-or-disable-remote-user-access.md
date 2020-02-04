---
title: "Lync Server 2013: Abilitare o disabilitare l'accesso degli utenti remoti"
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
ms.openlocfilehash: 476cc3b90a2fdb603303789f3f9bfceb67766f5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="15a90-102">Abilitare o disabilitare l'accesso degli utenti remoti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a90-102">Enable or disable remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a90-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="15a90-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="15a90-104">Gli utenti remoti sono utenti dell'organizzazione che hanno un'identità Active Directory persistente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="15a90-105">Gli utenti remoti spesso accedono a Lync Server dall'esterno della rete usando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-105">Remote users often sign in to Lync Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="15a90-106">Gli utenti remoti includono dipendenti che lavorano a casa o in viaggio e altri lavoratori remoti, ad esempio fornitori attendibili, a cui sono state concesse le credenziali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="15a90-107">Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15a90-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Lync Server.</span></span>

<span data-ttu-id="15a90-108">Per supportare l'accesso degli utenti remoti, è necessario abilitare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="15a90-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="15a90-109">Quando si Abilita l'accesso remoto agli utenti, è possibile abilitarlo per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="15a90-110">Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="15a90-111">Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15a90-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15a90-112">L'abilitazione dell'accesso degli utenti remoti specifica solo che i server che gestiscono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma gli utenti remoti non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non si configura anche in almeno un criterio per gestire l'uso dell'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="15a90-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="15a90-113">Le impostazioni dei criteri di Lync Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="15a90-113">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="15a90-114">La precedenza dei criteri di Lync Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="15a90-114">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="15a90-115">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="15a90-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="15a90-116">Per informazioni dettagliate sulla configurazione dei criteri per l'uso dell'accesso remoto agli utenti, vedere <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">configurare i criteri per il controllo dell'accesso degli utenti remoti in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15a90-116">For details about configuring policies for the use of remote user access, see <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure policies to control remote user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="15a90-117">Per abilitare o disabilitare l'accesso remoto agli utenti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="15a90-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="15a90-118">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="15a90-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="15a90-119">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15a90-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="15a90-120">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="15a90-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="15a90-121">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="15a90-121">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="15a90-122">Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="15a90-122">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="15a90-123">In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15a90-123">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="15a90-124">Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto agli utenti** .</span><span class="sxs-lookup"><span data-stu-id="15a90-124">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="15a90-125">Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto agli utenti** .</span><span class="sxs-lookup"><span data-stu-id="15a90-125">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="15a90-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="15a90-126">Click **Commit**.</span></span>

<span data-ttu-id="15a90-127">Per consentire agli utenti remoti di accedere ai server che utilizzano Lync Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="15a90-127">To enable remote users to sign in to your servers running Lync Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="15a90-128">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti remoti in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) nella documentazione relativa alla distribuzione o nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="15a90-128">For details, see [Configure policies to control remote user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="15a90-129">Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15a90-129">Enabling or Disabling Remote User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="15a90-130">L'accesso degli utenti remoti può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="15a90-130">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="15a90-131">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15a90-131">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="15a90-132">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="15a90-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="15a90-133">Per abilitare l'accesso remoto agli utenti</span><span class="sxs-lookup"><span data-stu-id="15a90-133">To enable remote user access</span></span>

  - <span data-ttu-id="15a90-134">Per abilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="15a90-134">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="15a90-135">Per disabilitare l'accesso remoto agli utenti</span><span class="sxs-lookup"><span data-stu-id="15a90-135">To disable remote user access</span></span>

  - <span data-ttu-id="15a90-136">Per disabilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="15a90-136">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

