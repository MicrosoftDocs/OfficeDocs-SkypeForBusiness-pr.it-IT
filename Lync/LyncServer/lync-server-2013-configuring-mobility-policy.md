---
title: 'Lync Server 2013: configurazione di criteri per dispositivi mobili'
description: 'Lync Server 2013: configurazione di criteri per dispositivi mobili.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbbf7f9db54c8436f2db24d593dbd7a1372d5e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570002"
---
# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="33d03-103">Configurazione di criteri per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d03-103">Configuring mobility policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33d03-104">_**Ultimo argomento modificato:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="33d03-104">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="33d03-105">Lync Server 2013 fornisce i criteri per dispositivi mobili che determinano gli utenti che possono utilizzare le funzionalità per dispositivi mobili, la chiamata tramite lavoro, il VoIP (Voice over IP) o il video e se la connessione WiFi sarà necessaria per VoIP o video.</span><span class="sxs-lookup"><span data-stu-id="33d03-105">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="33d03-106">La funzionalità di chiamata tramite lavoro consente a un utente di telefonia mobile di effettuare e ricevere chiamate su un telefono cellulare utilizzando un numero di telefono di lavoro invece del numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="33d03-106">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="33d03-107">Questa funzionalità impedisce alla parte chiamata di visualizzare il numero di telefono cellulare del chiamante e di evitare che i costi di chiamata in uscita vengano configurati da un utente.</span><span class="sxs-lookup"><span data-stu-id="33d03-107">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="33d03-108">La configurazione di VoIP e video rende possibile agli utenti di ricevere e fare chiamate VoIP e video.</span><span class="sxs-lookup"><span data-stu-id="33d03-108">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="33d03-109">Le impostazioni per l'utilizzo di Wi-Fi definiscono se il dispositivo di un utente dovrà utilizzare una rete WiFi su una rete di dati cellulare.</span><span class="sxs-lookup"><span data-stu-id="33d03-109">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="33d03-110">Per impostazione predefinita, la mobilità, la chiamata tramite lavoro e le funzionalità VoIP e video sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="33d03-110">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="33d03-111">Le impostazioni per richiedere il WiFi per VoIp e video sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="33d03-111">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="33d03-112">Gli amministratori possono stabilire chi ha accesso a tali funzionalità eseguendo un cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33d03-112">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="33d03-113">È possibile disattivare le opzioni globalmente, a livello di sito o a livello di singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="33d03-113">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="33d03-114">Per poter utilizzare le funzionalità di mobilità e Chiama da ufficio, gli utenti devono soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="33d03-114">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="33d03-115">Gli utenti devono essere abilitati per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33d03-115">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="33d03-116">Gli utenti devono essere abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="33d03-116">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="33d03-117">Agli utenti devono essere assegnati criteri di mobilità con l'opzione **EnableMobility** impostata su True.</span><span class="sxs-lookup"><span data-stu-id="33d03-117">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="33d03-118">Affinché gli utenti siano in grado di utilizzare Chiama da ufficio, è necessario che soddisfino i due prerequisiti aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="33d03-118">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="33d03-119">Agli utenti devono essere assegnati criteri vocali con l'opzione **Abilita squillo simultaneo dei telefoni** selezionata.</span><span class="sxs-lookup"><span data-stu-id="33d03-119">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="33d03-120">Agli utenti devono essere assegnati criteri di mobilità con l'opzione **EnableOutsideVoice** impostata su True.</span><span class="sxs-lookup"><span data-stu-id="33d03-120">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33d03-121">Gli utenti che non sono abilitati per VoIP aziendale possono utilizzare i propri dispositivi mobili per consentire a Lync di chiamare Lync Voice over IP, oppure possono partecipare a conferenze usando il collegamento fare clic per partecipare ai propri dispositivi mobili, se si assegnano a tali utenti le opzioni appropriate per i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="33d03-121">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="33d03-122">Per informazioni dettagliate, vedere <A href="lync-server-2013-defining-your-mobility-requirements.md">definizione dei requisiti per dispositivi mobili per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="33d03-122">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="33d03-123">Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riabilitare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="33d03-123">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="33d03-124">Per informazioni dettagliate sull'abilitazione degli utenti per VoIP aziendale, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="33d03-124">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="33d03-125">Per informazioni dettagliate sull'impostazione delle opzioni per i criteri vocali, vedere [Modify a Voice Policy e Configure PSTN Usage Records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span><span class="sxs-lookup"><span data-stu-id="33d03-125">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="33d03-126">Per modificare i criteri di mobilità globali</span><span class="sxs-lookup"><span data-stu-id="33d03-126">To modify global mobility policy</span></span>

1.  <span data-ttu-id="33d03-127">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33d03-127">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="33d03-128">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="33d03-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33d03-p105">Disattivare globalmente l'accesso alle funzionalità di mobilità e Chiama da ufficio. Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="33d03-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="33d03-p106">È possibile disattivare Chiama da ufficio senza disattivare l'accesso alla funzionalità di mobilità. Non è tuttavia possibile disattivare le funzionalità di mobilità senza disattivare anche Chiama da ufficio.</span><span class="sxs-lookup"><span data-stu-id="33d03-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="33d03-133">Per modificare i criteri di mobilità a livello di sito</span><span class="sxs-lookup"><span data-stu-id="33d03-133">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="33d03-134">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33d03-134">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="33d03-135">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="33d03-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33d03-136">Creare criteri a livello di sito e disattivare VoIP e video e abilitare Richiedi WiFi per l'audio IP e per il video IP per sito.</span><span class="sxs-lookup"><span data-stu-id="33d03-136">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="33d03-137">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="33d03-137">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="33d03-138">Per modificare i criteri di mobilità a livello di utente</span><span class="sxs-lookup"><span data-stu-id="33d03-138">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="33d03-139">Accedere a qualsiasi computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="33d03-139">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="33d03-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="33d03-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="33d03-p108">Creare nuovi criteri di mobilità a livello di utente e disattivare le funzionalità di mobilità e Chiama da ufficio per un utente specifico. Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="33d03-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="33d03-p109">È possibile disattivare Chiama da ufficio senza disattivare l'accesso alla funzionalità di mobilità. Non è tuttavia possibile disattivare le funzionalità di mobilità senza disattivare anche Chiama da ufficio.</span><span class="sxs-lookup"><span data-stu-id="33d03-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="33d03-145">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="33d03-145">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33d03-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33d03-146">See Also</span></span>


[<span data-ttu-id="33d03-147">Disabilitare o riabilitare l'account utente per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d03-147">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="33d03-148">Abilitare gli utenti per VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d03-148">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="33d03-149">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d03-149">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="33d03-150">Definizione dei requisiti per dispositivi mobili per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33d03-150">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="33d03-151">New-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="33d03-151">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="33d03-152">Set-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="33d03-152">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="33d03-153">Get-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="33d03-153">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="33d03-154">Grant-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="33d03-154">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="33d03-155">Remove-CsMobilityPolicy</span><span class="sxs-lookup"><span data-stu-id="33d03-155">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

