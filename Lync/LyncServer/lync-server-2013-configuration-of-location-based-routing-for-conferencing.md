---
title: 'Lync Server 2013: configurazione del routing Location-Based per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507803"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="bbe36-102">Configurazione del routing Location-Based per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbe36-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbe36-103">_**Ultimo argomento modificato:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="bbe36-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="bbe36-104">L'applicazione Location-Based routing Conferencing si basa sulla configurazione del routing Location-Based Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbe36-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="bbe36-105">Le configurazioni principali sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbe36-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="bbe36-106">La posizione dei partecipanti che partecipano a una riunione è determinata in base al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="bbe36-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="bbe36-107">Un sito di rete e le subnet di rete associate devono essere definite in Lync Server per applicare il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="bbe36-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="bbe36-108">Per applicare il routing Location-Based alle riunioni, i partecipanti di Lync devono essere abilitati per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="bbe36-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="bbe36-109">Per applicare il routing Location-Based degli endpoint PSTN che uniscono le riunioni, è necessario configurare il trunk SIP utilizzato per connettere gli endpoint PSTN per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="bbe36-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="bbe36-110">Per ulteriori informazioni sulla distribuzione e sulla configurazione di Lync Server 2013 Location-Based routing, fare riferimento a configurazione del [routing in base alla posizione](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="bbe36-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="bbe36-111">Abilitazione dell'applicazione per il routing di Location-Based Conferencing</span><span class="sxs-lookup"><span data-stu-id="bbe36-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="bbe36-112">Per impostazione predefinita, l'applicazione di conferenza di routing Location-Based è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="bbe36-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="bbe36-113">Prima di abilitare questa applicazione, è necessario determinare la priorità giusta da assegnare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bbe36-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="bbe36-114">Per determinare questa priorità, eseguire il cmdlet seguente in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="bbe36-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

<span data-ttu-id="bbe36-115">In questo cmdlet, \<Pool FQDN\> è il pool in cui deve essere abilitata l'applicazione di conferenza di Routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="bbe36-115">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="bbe36-116">Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Lync Server e il valore di priorità per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="bbe36-116">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="bbe36-117">L'applicazione di routing per le conferenze di Location-Based deve essere assegnata a un valore di priorità più grande dell'applicazione "UdcAgent" e più piccola delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="bbe36-117">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="bbe36-118">Si consiglia di assegnare l'applicazione di conferenza di routing Location-Based un valore di priorità maggiore di un punto rispetto al valore di priorità dell'applicazione "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="bbe36-118">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="bbe36-119">Ad esempio, se l'applicazione "UdcAgent" ha un valore di priorità pari a "2", l'applicazione "DefaultRouting" ha un valore di priorità "8", l'applicazione "ExumRouting" ha un valore di priorità di "9" e l'applicazione "OutboundRouting" ha un valore di priorità pari a "10", quindi è necessario assegnare l'applicazione di conferenza di routing Location-Based un valore prioritario</span><span class="sxs-lookup"><span data-stu-id="bbe36-119">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="bbe36-120">In questo modo la priorità delle applicazioni verrà eseguita nell'ordine seguente: altre applicazioni (priorità: 0 a 1), "UdcAgent" (priorità: 2), Location-Based applicazione per le conferenze di routing (priorità: 3), altre applicazioni (priorità: 4 a 8), "DefaultRouting" (priorità: 9), "ExumRouting" (priorità: 10) e "OutboundRouting" (priorità: 11).</span><span class="sxs-lookup"><span data-stu-id="bbe36-120">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="bbe36-121">Dopo aver individuato il valore di priorità corretto per l'applicazione di conferenza di routing Location-Based, digitare il seguente cmdlet per ogni pool di Front-End o server Standard Edition in cui gli utenti di Homes sono abilitati per il routing Location-Based:</span><span class="sxs-lookup"><span data-stu-id="bbe36-121">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="bbe36-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bbe36-122">For example:</span></span>

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

<span data-ttu-id="bbe36-123">Dopo aver utilizzato questo cmdlet, riavviare tutti i Front End Server nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione di conferenza di routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="bbe36-123">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bbe36-124">Location-Based l'applicazione di routing alle conferenze o ai trasferimenti consultivi non verrà applicata finché non vengono riavviati tutti i Front End Server nei pool o nei server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bbe36-124">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="bbe36-125">Dopo che l'applicazione di routing per la Location-Based di distribuzione è stata abilitata e tutti i server Lync applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Lync abilitate per Location-Based il routing verranno monitorate per impedire il bypass a pedaggio PSTN</span><span class="sxs-lookup"><span data-stu-id="bbe36-125">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

