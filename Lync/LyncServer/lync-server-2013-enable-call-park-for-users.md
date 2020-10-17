---
title: 'Lync Server 2013: abilitare il parcheggio di chiamata per gli utenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528783"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="872d6-102">Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="872d6-102">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="872d6-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="872d6-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="872d6-104">Gli utenti non possono parcheggiare le chiamate o recuperare le chiamate parcheggiate finché non sono abilitate per il parcheggio di chiamata nel criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="872d6-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="872d6-105">Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="872d6-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="872d6-106">È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="872d6-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="872d6-107">L'ambito utente ha la precedenza rispetto all'ambito a livello di sito, che a sua volta ha la precedenza rispetto all'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="872d6-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="872d6-108">Se si dispone di più criteri vocali, esaminare tutti i criteri per abilitare il parcheggio di chiamata, non solo il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="872d6-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="872d6-109">Per utilizzare il pannello di controllo di Lync Server per abilitare il parcheggio di chiamata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="872d6-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="872d6-110">Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="872d6-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="872d6-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="872d6-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="872d6-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="872d6-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="872d6-113">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="872d6-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="872d6-114">Fare clic sulla scheda **Criteri vocali**.</span><span class="sxs-lookup"><span data-stu-id="872d6-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="872d6-115">Fare doppio clic su un criterio esistente per aprire la finestra di dialogo **Modifica criterio vocale**.</span><span class="sxs-lookup"><span data-stu-id="872d6-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="872d6-116">In **Funzionalità di chiamata** selezionare **Abilita parcheggio di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="872d6-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="872d6-117">Fare clic su **OK** per salvare il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="872d6-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="872d6-118">Per utilizzare i cmdlet per abilitare il parcheggio di chiamata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="872d6-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="872d6-119">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo amministrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="872d6-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="872d6-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="872d6-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="872d6-121">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="872d6-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="872d6-122">Ad esempio, per abilitare il parcheggio di chiamata per il criterio vocale globale predefinito:</span><span class="sxs-lookup"><span data-stu-id="872d6-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="872d6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="872d6-123">See Also</span></span>


[<span data-ttu-id="872d6-124">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="872d6-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

