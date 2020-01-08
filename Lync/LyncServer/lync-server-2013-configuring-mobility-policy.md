---
title: 'Lync Server 2013: Configurazione dei criteri per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="1e68f-102">Configurazione dei criteri per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e68f-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e68f-103">_**Argomento Ultima modifica:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="1e68f-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="1e68f-104">Lync Server 2013 offre criteri per la mobilità che determinano chi può usare le caratteristiche di mobilità, chiama tramite lavoro, Voice over IP (VoIP) o video e se il WiFi sarà necessario per il VoIP o il video.</span><span class="sxs-lookup"><span data-stu-id="1e68f-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="1e68f-105">La caratteristica chiamata tramite lavoro consente a un utente mobile di effettuare e ricevere chiamate su un telefono cellulare usando un numero di telefono dell'ufficio invece del numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="1e68f-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="1e68f-106">Questa caratteristica impedisce alla persona chiamata di visualizzare il numero di cellulare del chiamante e consente a un utente di evitare oneri per le chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="1e68f-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="1e68f-107">La configurazione di VoIP e video consente agli utenti di ricevere e effettuare chiamate VoIP e video.</span><span class="sxs-lookup"><span data-stu-id="1e68f-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="1e68f-108">Le impostazioni per l'utilizzo di WiFi definiscono se il dispositivo di un utente deve usare una rete WiFi tramite una rete dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="1e68f-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="1e68f-109">Per impostazione predefinita, la mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="1e68f-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="1e68f-110">Le impostazioni per richiedere il WiFi per VoIp e video sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="1e68f-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="1e68f-111">Gli amministratori possono determinare chi ha accesso a queste funzionalità eseguendo un cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1e68f-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="1e68f-112">È possibile disattivare le opzioni a livello globale, per sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="1e68f-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="1e68f-113">Per poter usare le caratteristiche di mobilità e la chiamata tramite lavoro, gli utenti devono soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e68f-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="1e68f-114">Gli utenti devono essere abilitati per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e68f-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="1e68f-115">Gli utenti devono essere abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1e68f-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="1e68f-116">Agli utenti deve essere assegnato un criterio di mobilità con l'opzione **EnableMobility** impostata su true.</span><span class="sxs-lookup"><span data-stu-id="1e68f-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="1e68f-117">Affinché gli utenti possano usare la chiamata tramite il lavoro, devono soddisfare i due prerequisiti aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e68f-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="1e68f-118">Agli utenti deve essere assegnato un criterio vocale con l'opzione **Abilita squillo simultaneo dei telefoni** selezionata.</span><span class="sxs-lookup"><span data-stu-id="1e68f-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="1e68f-119">Agli utenti deve essere assegnato un criterio di mobilità con l'opzione **EnableOutsideVoice** impostata su true.</span><span class="sxs-lookup"><span data-stu-id="1e68f-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e68f-120">Gli utenti che non sono abilitati per Enterprise Voice possono usare i loro dispositivi mobili per consentire a Lync di eseguire chiamate VoIP (Voice over IP) di Lync o possono partecipare a conferenze usando il collegamento fare clic per partecipare ai loro dispositivi mobili, se si assegnano gli utenti le opzioni appropriate per il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="1e68f-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="1e68f-121">Per informazioni dettagliate, vedere <A href="lync-server-2013-defining-your-mobility-requirements.md">definizione dei requisiti di mobilità per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1e68f-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1e68f-122">Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riattivare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="1e68f-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="1e68f-123">Per informazioni dettagliate sull'abilitazione degli utenti per VoIP aziendale, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="1e68f-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="1e68f-124">Per informazioni dettagliate sull'impostazione delle opzioni dei criteri vocali, vedere [modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="1e68f-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="1e68f-125">Per modificare i criteri di mobilità globale</span><span class="sxs-lookup"><span data-stu-id="1e68f-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="1e68f-126">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1e68f-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1e68f-127">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1e68f-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e68f-128">Disattivare l'accesso alla mobilità e chiamare tramite lavoro a livello globale.</span><span class="sxs-lookup"><span data-stu-id="1e68f-128">Turn off access to mobility and Call via Work globally.</span></span> <span data-ttu-id="1e68f-129">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="1e68f-129">At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e68f-130">È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="1e68f-130">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="1e68f-131">Tuttavia, non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="1e68f-131">However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="1e68f-132">Per modificare i criteri di mobilità per sito</span><span class="sxs-lookup"><span data-stu-id="1e68f-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="1e68f-133">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1e68f-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1e68f-134">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1e68f-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e68f-135">Creare un criterio a livello di sito e disattivare VoIP e video e abilitare Richiedi WiFi per l'audio IP e per il video IP per sito.</span><span class="sxs-lookup"><span data-stu-id="1e68f-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="1e68f-136">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="1e68f-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="1e68f-137">Per modificare i criteri di mobilità per utente</span><span class="sxs-lookup"><span data-stu-id="1e68f-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="1e68f-138">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1e68f-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="1e68f-139">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1e68f-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e68f-140">Creare criteri di mobilità a livello di utente e disattivare la mobilità e la chiamata tramite il lavoro da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1e68f-140">Create user level mobility policies and turn off mobility and Call via Work by user.</span></span> <span data-ttu-id="1e68f-141">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="1e68f-141">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="1e68f-142">È possibile disattivare la chiamata tramite lavoro senza disattivare l'accesso alla mobilità.</span><span class="sxs-lookup"><span data-stu-id="1e68f-142">You can turn off Call via Work without turning off access to mobility.</span></span> <span data-ttu-id="1e68f-143">Tuttavia, non è possibile disattivare la mobilità senza disattivare la chiamata anche tramite lavoro.</span><span class="sxs-lookup"><span data-stu-id="1e68f-143">However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="1e68f-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e68f-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e68f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e68f-145">See Also</span></span>


[<span data-ttu-id="1e68f-146">Disabilitare o riattivare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e68f-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="1e68f-147">Consentire agli utenti di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e68f-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="1e68f-148">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e68f-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="1e68f-149">Definizione dei requisiti per dispositivi mobili per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e68f-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="1e68f-150">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1e68f-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="1e68f-151">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1e68f-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="1e68f-152">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1e68f-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="1e68f-153">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1e68f-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="1e68f-154">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="1e68f-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

