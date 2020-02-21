---
title: 'Lync Server 2013: configurare una route vocale E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767f49aa0074e269de386b2db017dc183e4eb92d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="05b43-102">Configurare una route vocale E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05b43-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b43-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="05b43-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="05b43-104">Per distribuire il servizio E9-1-1, è innanzitutto necessario configurare una route vocale per le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="05b43-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="05b43-105">Per informazioni dettagliate sulla creazione di route vocali, vedere [Create a Voice Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="05b43-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="05b43-106">È possibile definire più di una route, ad esempio, se nella distribuzione sono inclusi un trunk SIP primario e un trunk SIP secondario.</span><span class="sxs-lookup"><span data-stu-id="05b43-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05b43-107">Per includere informazioni sulla posizione in un messaggio INVITE E9-1-1, è necessario configurare il trunk SIP per la connessione al provider di servizi E9-1-1 in modo che esegua il routing delle chiamate di emergenza attraverso il gateway.</span><span class="sxs-lookup"><span data-stu-id="05b43-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="05b43-108">A tale scopo, impostare il flag EnablePIDFLOSupport nel cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> su True.</span><span class="sxs-lookup"><span data-stu-id="05b43-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="05b43-109">Il valore predefinito per EnablePIDFLOSupport è False.</span><span class="sxs-lookup"><span data-stu-id="05b43-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="05b43-110">Per esempio:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="05b43-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="05b43-111">Non è necessario abilitare la ricezione delle posizioni per i gateway PSTN (Public Switched Telephone Network) di fallback e i gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="05b43-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="05b43-112">Per informazioni dettagliate sull'utilizzo delle route vocali, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="05b43-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="05b43-113">**Set-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="05b43-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="05b43-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="05b43-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="05b43-115">**New-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="05b43-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="05b43-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="05b43-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="05b43-117">**Set-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="05b43-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="05b43-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="05b43-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="05b43-119">Per configurare una route vocale E9-1-1</span><span class="sxs-lookup"><span data-stu-id="05b43-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="05b43-120">Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o del ruolo amministrativo CsVoiceAdministrator.</span><span class="sxs-lookup"><span data-stu-id="05b43-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="05b43-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="05b43-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="05b43-122">Eseguire il cmdlet seguente per creare un nuovo record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="05b43-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="05b43-123">Deve essere lo stesso nome che verrà utilizzato per l'impostazione **PSTN** nei criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="05b43-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="05b43-124">Anche se nella distribuzione reale saranno disponibili più record di utilizzo del telefono, nell'esempio seguente viene aggiunto "Emergency Usage" all'elenco corrente di utilizzi PSTN disponibili.</span><span class="sxs-lookup"><span data-stu-id="05b43-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="05b43-125">Per ulteriori informazioni, vedere [configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="05b43-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="05b43-126">Eseguire il cmdlet seguente per creare una nuova route vocale con il record di utilizzo PSTN creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="05b43-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="05b43-127">Il formato del numero deve essere lo stesso utilizzato nell'impostazione **Maschera di composizione di emergenza** nei criteri di percorso.</span><span class="sxs-lookup"><span data-stu-id="05b43-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="05b43-128">È necessario un segno "+" perché Lync aggiunge "+" alle chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="05b43-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="05b43-129">"Co1-pstngateway-1" è l'ID di servizio del trunk SIP per il provider di servizi E9-1-1 o l'ID di servizio del gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="05b43-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="05b43-130">Nell'esempio seguente viene utilizzato il nome "EmergencyRoute" per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="05b43-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="05b43-p105">Facoltativamente, per le connessioni trunk SIP è consigliabile eseguire il cmdlet seguente per creare una route locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1. Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="05b43-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="05b43-133">Nell'esempio seguente si presuppone che i criteri vocali dell'utente includano l'utilizzo 'Local'.</span><span class="sxs-lookup"><span data-stu-id="05b43-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

