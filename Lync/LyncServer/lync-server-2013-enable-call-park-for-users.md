---
title: 'Lync Server 2013: abilitare il parcheggio di chiamata per gli utenti'
description: 'Lync Server 2013: abilitare il parcheggio di chiamata per gli utenti.'
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
ms.openlocfilehash: c7f9ab23b9fa71943efafd588b8c57a2af781b08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561032"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="9ae22-103">Abilitare il parcheggio di chiamata per gli utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ae22-103">Enable Call Park for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ae22-104">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9ae22-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9ae22-105">Gli utenti non possono parcheggiare le chiamate o recuperare le chiamate parcheggiate finché non sono abilitate per il parcheggio di chiamata nel criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="9ae22-105">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ae22-106">Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9ae22-106">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="9ae22-107">È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9ae22-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="9ae22-108">L'ambito utente ha la precedenza rispetto all'ambito a livello di sito, che a sua volta ha la precedenza rispetto all'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="9ae22-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="9ae22-109">Se si dispone di più criteri vocali, esaminare tutti i criteri per abilitare il parcheggio di chiamata, non solo il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="9ae22-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="9ae22-110">Per utilizzare il pannello di controllo di Lync Server per abilitare il parcheggio di chiamata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="9ae22-110">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="9ae22-111">Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="9ae22-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ae22-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ae22-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9ae22-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ae22-114">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="9ae22-115">Fare clic sulla scheda **Criteri vocali**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-115">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="9ae22-116">Fare doppio clic su un criterio esistente per aprire la finestra di dialogo **Modifica criterio vocale**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-116">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="9ae22-117">In **Funzionalità di chiamata** selezionare **Abilita parcheggio di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-117">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="9ae22-118">Fare clic su **OK** per salvare il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="9ae22-118">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="9ae22-119">Per utilizzare i cmdlet per abilitare il parcheggio di chiamata per gli utenti</span><span class="sxs-lookup"><span data-stu-id="9ae22-119">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="9ae22-120">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo amministrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ae22-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="9ae22-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9ae22-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9ae22-122">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="9ae22-122">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="9ae22-123">Ad esempio, per abilitare il parcheggio di chiamata per il criterio vocale globale predefinito:</span><span class="sxs-lookup"><span data-stu-id="9ae22-123">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9ae22-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ae22-124">See Also</span></span>


[<span data-ttu-id="9ae22-125">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ae22-125">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

