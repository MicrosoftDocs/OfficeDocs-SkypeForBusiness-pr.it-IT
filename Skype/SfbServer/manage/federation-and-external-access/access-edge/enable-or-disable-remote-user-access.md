---
title: Abilitare o disabilitare l'accesso utente remoto
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono su Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni che utilizzano Skype for Business Server.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817396"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="079e3-103">Abilitazione o disabilitazione dell'accesso degli utenti remoti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="079e3-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="079e3-104">Gli utenti remoti sono utenti dell'organizzazione che dispongono di un'identità Active Directory permanente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="079e3-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="079e3-105">Gli utenti remoti spesso accedono a Skype for Business Server dall'esterno della rete utilizzando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="079e3-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="079e3-106">Tra gli utenti remoti sono inclusi i dipendenti che lavorano dalla propria abitazione o in viaggio e altri lavoratori remoti, ad esempio fornitori considerati attendibili a cui sono state concesse credenziali aziendali.</span><span class="sxs-lookup"><span data-stu-id="079e3-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="079e3-107">Se si Abilita l'accesso utente remoto per gli utenti remoti, gli utenti remoti supportati si connettono su Internet e non devono connettersi utilizzando una VPN per collaborare con gli utenti interni che utilizzano Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="079e3-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="079e3-p102">Per supportare l'accesso degli utenti remoti, è necessario abilitarlo. Quando si abilita l'accesso degli utenti remoti, tale impostazione si applica all'intera organizzazione. Se successivamente si desidera impedire, in modo temporaneo o permanente, l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione. Attenersi alla procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="079e3-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="079e3-112">Abilitando l'accesso degli utenti remoti, si specifica soltanto che i server che eseguono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma questi ultimi non possono utilizzare la messaggistica istantanea o partecipare a conferenze nell'organizzazione finché non si configura almeno un criterio per la gestione dell'utilizzo dell'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="079e3-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="079e3-113">Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sovrascrivere le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="079e3-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="079e3-114">La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza).</span><span class="sxs-lookup"><span data-stu-id="079e3-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="079e3-115">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="079e3-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="079e3-116">Per informazioni dettagliate sulla configurazione dei criteri per l'utilizzo dell'accesso degli utenti remoti, vedere [Configure policies to Control Remote User Access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="079e3-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="079e3-117">Per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="079e3-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="079e3-118">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="079e3-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="079e3-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="079e3-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="079e3-120">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="079e3-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="079e3-121">Nella pagina **Configurazione Access Edge** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="079e3-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="079e3-122">In **Modifica configurazione Access Edge** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="079e3-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="079e3-123">Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto utenti**.</span><span class="sxs-lookup"><span data-stu-id="079e3-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="079e3-124">Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto utenti**.</span><span class="sxs-lookup"><span data-stu-id="079e3-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="079e3-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="079e3-125">Click **Commit**.</span></span>

<span data-ttu-id="079e3-126">Per consentire agli utenti remoti di accedere ai server che eseguono Skype for Business Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="079e3-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="079e3-127">Per ulteriori informazioni, vedere [Configure policies to Control Remote User Access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="079e3-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="079e3-128">Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="079e3-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="079e3-129">È possibile gestire l'accesso degli utenti remoti tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="079e3-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="079e3-130">Questo cmdlet può essere eseguito da Skype for Business Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="079e3-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="079e3-131">Per abilitare l'accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="079e3-131">To enable remote user access</span></span>

  - <span data-ttu-id="079e3-132">Per abilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="079e3-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="079e3-133">Per disabilitare l'accesso degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="079e3-133">To disable remote user access</span></span>

  - <span data-ttu-id="079e3-134">Per disabilitare l'accesso degli utenti remoti, impostare il valore della proprietà **AllowOutsideUsers** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="079e3-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


