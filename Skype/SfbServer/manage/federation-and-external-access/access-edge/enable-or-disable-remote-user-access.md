---
title: Abilitare o disabilitare l'accesso degli utenti remoti
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se si Abilita l'accesso remoto agli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Skype for Business Server.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188867"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="36dbc-103">Abilitare o disabilitare l'accesso remoto agli utenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36dbc-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="36dbc-104">Gli utenti remoti sono utenti dell'organizzazione che hanno un'identità Active Directory persistente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="36dbc-105">Gli utenti remoti spesso accedono a Skype for Business Server dall'esterno della rete usando una rete privata virtuale (VPN) quando non sono connessi alla rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="36dbc-106">Gli utenti remoti includono dipendenti che lavorano a casa o in viaggio e altri lavoratori remoti, ad esempio fornitori attendibili, a cui sono state concesse le credenziali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="36dbc-107">Se si Abilita l'accesso remoto agli utenti remoti, gli utenti remoti supportati si connettono tramite Internet e non devono connettersi tramite una VPN per collaborare con utenti interni tramite Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dbc-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="36dbc-108">Per supportare l'accesso degli utenti remoti, è necessario abilitare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="36dbc-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="36dbc-109">Quando si Abilita l'accesso remoto agli utenti, è possibile abilitarlo per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="36dbc-110">Se in seguito si vuole impedire temporaneamente o definitivamente l'accesso degli utenti remoti, è possibile disabilitarlo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="36dbc-111">Usare la procedura descritta in questa sezione per abilitare o disabilitare l'accesso degli utenti remoti per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36dbc-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="36dbc-112">L'abilitazione dell'accesso degli utenti remoti specifica solo che i server che gestiscono il servizio Access Edge supportano le comunicazioni con gli utenti remoti, ma gli utenti remoti non possono partecipare alla messaggistica istantanea o alle conferenze dell'organizzazione fino a quando non si configura anche in almeno un criterio per gestire l'uso dell'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="36dbc-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="36dbc-113">Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="36dbc-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="36dbc-114">La precedenza dei criteri di Skype for Business Server è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="36dbc-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="36dbc-115">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="36dbc-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="36dbc-116">Per informazioni dettagliate sulla configurazione dei criteri per l'uso dell'accesso remoto agli utenti, vedere [configurare i criteri per il controllo dell'accesso degli utenti remoti in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="36dbc-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="36dbc-117">Per abilitare o disabilitare l'accesso remoto agli utenti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="36dbc-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="36dbc-118">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="36dbc-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36dbc-119">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dbc-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="36dbc-120">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="36dbc-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="36dbc-121">Nella pagina **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="36dbc-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="36dbc-122">In **modifica configurazione di Access Edge**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36dbc-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="36dbc-123">Per abilitare l'accesso degli utenti remoti per l'organizzazione, selezionare la casella di controllo **Abilita accesso remoto agli utenti** .</span><span class="sxs-lookup"><span data-stu-id="36dbc-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="36dbc-124">Per disabilitare l'accesso degli utenti remoti per l'organizzazione, deselezionare la casella di controllo **Abilita accesso remoto agli utenti** .</span><span class="sxs-lookup"><span data-stu-id="36dbc-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="36dbc-125">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="36dbc-125">Click **Commit**.</span></span>

<span data-ttu-id="36dbc-126">Per consentire agli utenti remoti di accedere ai server che utilizzano Skype for Business Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="36dbc-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="36dbc-127">Per informazioni dettagliate, vedere [configurare i criteri per controllare l'accesso degli utenti remoti in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="36dbc-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="36dbc-128">Abilitazione o disabilitazione dell'accesso degli utenti remoti tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="36dbc-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="36dbc-129">L'accesso degli utenti remoti può essere gestito tramite Windows PowerShell e il cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="36dbc-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="36dbc-130">Questo cmdlet può essere eseguito da Skype for Business Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36dbc-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="36dbc-131">Per abilitare l'accesso remoto agli utenti</span><span class="sxs-lookup"><span data-stu-id="36dbc-131">To enable remote user access</span></span>

  - <span data-ttu-id="36dbc-132">Per abilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="36dbc-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="36dbc-133">Per disabilitare l'accesso remoto agli utenti</span><span class="sxs-lookup"><span data-stu-id="36dbc-133">To disable remote user access</span></span>

  - <span data-ttu-id="36dbc-134">Per disabilitare l'accesso remoto agli utenti, imposta il valore della proprietà **AllowOutsideUsers** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="36dbc-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


