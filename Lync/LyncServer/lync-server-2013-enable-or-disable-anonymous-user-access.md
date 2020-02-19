---
title: "Lync Server 2013: abilitare o disabilitare l'accesso degli utenti anonimi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c873953b16004f514871c0cf4b4708ad41c0117
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="c9eaa-102">Abilitazione o disabilitazione dell'accesso degli utenti anonimi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9eaa-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9eaa-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c9eaa-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c9eaa-104">Gli utenti anonimi sono utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma possono essere invitati a partecipare in remoto in una conferenza locale.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="c9eaa-105">Consentendo la partecipazione anonima alle riunioni, si consente agli utenti anonimi, ovvero agli utenti la cui identità viene verificata solo mediante la chiave riunione o conferenza, di partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="c9eaa-106">A tale scopo, è necessario abilitare la partecipazione anonima per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="c9eaa-p102">Se successivamente si desidera impedire temporaneamente o definitivamente l'accesso da parte di utenti anonimi, è possibile disabilitarlo per l'organizzazione. Eseguire la procedura illustrata in questa sezione per abilitare o disabilitare l'accesso utente anonimo per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9eaa-109">Abilitando l'accesso utente anonimo per l'organizzazione, si specifica solo che i server che eseguono il servizio Access Edge supportano l'accesso da parte di utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="c9eaa-110">Tali utenti non possono partecipare alle riunioni dell'organizzazione finché non viene configurato e applicato almeno un criterio di conferenza a uno o più utenti o gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="c9eaa-111">Gli unici utenti che possono invitare utenti anonimi alle riunioni sono quelli a cui è stato assegnato il criterio di conferenza configurato per supportare l'invito di utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="c9eaa-112">Per informazioni dettagliate sulla configurazione dei criteri di conferenza per supportare l'invito degli utenti anonimi, vedere <A href="lync-server-2013-conferencing-policies.md">Conferencing Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="c9eaa-113">Per abilitare o disabilitare l'accesso utente anonimo per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c9eaa-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="c9eaa-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9eaa-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c9eaa-116">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c9eaa-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c9eaa-117">Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="c9eaa-118">Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c9eaa-119">In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9eaa-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9eaa-120">Per abilitare l'accesso utente anonimo per l'organizzazione, selezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="c9eaa-121">Per disabilitare l'accesso utente anonimo per l'organizzazione, deselezionare la casella di controllo **Abilita comunicazioni con utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="c9eaa-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c9eaa-123">Abilitazione o disabilitazione dell'accesso degli utenti anonimi tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9eaa-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c9eaa-124">È possibile gestire l'accesso degli utenti anonimi utilizzando Windows PowerShell e il cmdlet **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c9eaa-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="c9eaa-125">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c9eaa-126">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="c9eaa-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="c9eaa-127">Per abilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="c9eaa-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="c9eaa-128">Per abilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="c9eaa-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="c9eaa-129">Per disabilitare l'accesso degli utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="c9eaa-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="c9eaa-130">Per disabilitare l'accesso utente anonimo, impostare il valore della proprietà **AllowAnonymousUsers** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="c9eaa-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9eaa-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9eaa-131">See Also</span></span>


[<span data-ttu-id="c9eaa-132">Informazioni di riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9eaa-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

