---
title: 'Lync Server 2013: configurazione del routing in base alla posizione per le conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="eb987-102">Configurazione del routing in base alla posizione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb987-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb987-103">_**Argomento Ultima modifica:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="eb987-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="eb987-104">L'applicazione di conferenza di routing basata sulla posizione si basa sulla configurazione del routing basato sulla posizione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eb987-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="eb987-105">Le configurazioni principali sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb987-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="eb987-106">La posizione dei partecipanti che partecipano a una riunione viene determinata in base al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="eb987-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="eb987-107">Un sito di rete e le subnet di rete associate devono essere definiti in Lync Server per applicare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb987-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="eb987-108">Per applicare il routing basato sulla posizione delle riunioni, i partecipanti di Lync devono essere abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb987-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="eb987-109">Per applicare il routing basato sulla posizione degli endpoint PSTN che partecipano alle riunioni, il trunk SIP usato per connettere gli endpoint PSTN deve essere configurato per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb987-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="eb987-110">Per altre informazioni sulla distribuzione e configurazione del routing basato sulla posizione di Lync Server 2013, vedere Configurazione del [routing basato sulla posizione](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="eb987-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="eb987-111">Abilitazione dell'applicazione per i servizi di conferenza di routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="eb987-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="eb987-112">L'applicazione di conferenza di routing basata sulla posizione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eb987-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="eb987-113">Prima di abilitare questa applicazione, devi determinare la priorità giusta da assegnare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb987-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="eb987-114">Per determinare questa priorità, eseguire il cmdlet seguente in Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="eb987-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="eb987-115">Get-CsServerApplication-Identity Service: Registrar\<: FQDN del pool\></span><span class="sxs-lookup"><span data-stu-id="eb987-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="eb987-116">In questo cmdlet il \<nome di\> dominio completo del pool è il pool in cui deve essere abilitata l'applicazione per i servizi di conferenza di routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb987-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="eb987-117">Questo cmdlet restituirà l'elenco delle applicazioni ospitate da Lync Server e il valore di priorità per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="eb987-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="eb987-118">All'applicazione per i servizi di conferenza di routing basato sulla posizione deve essere assegnato un valore di priorità maggiore dell'applicazione "UdcAgent" e minore delle applicazioni "DefaultRouting", "ExumRouting" e "OutboundRouting".</span><span class="sxs-lookup"><span data-stu-id="eb987-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="eb987-119">Ti consigliamo di assegnare l'applicazione per i servizi di conferenza di routing basato sulla posizione un valore prioritario di un punto superiore al valore di priorità dell'applicazione "UdcAgent".</span><span class="sxs-lookup"><span data-stu-id="eb987-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="eb987-120">Ad esempio, se l'applicazione "UdcAgent" ha un valore Priority di "2", l'applicazione "DefaultRouting" ha un valore Priority "8", l'applicazione "ExumRouting" ha un valore Priority di "9" e l'applicazione "OutboundRouting" ha un valore di priorità "10" quindi Devi assegnare l'applicazione per i servizi di conferenza di routing basato sulla posizione un valore prioritario "3".</span><span class="sxs-lookup"><span data-stu-id="eb987-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="eb987-121">In questo modo la priorità delle applicazioni viene applicata nell'ordine seguente: altre applicazioni (priorità: da 0 a 1), "UdcAgent" (priorità: 2), applicazione per i servizi di conferenza di routing basato sulla posizione (priorità: 3), altre applicazioni (priorità: da 4 a 8), " DefaultRouting "(priorità: 9)," ExumRouting "(priorità: 10) e" OutboundRouting "(priorità: 11).</span><span class="sxs-lookup"><span data-stu-id="eb987-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="eb987-122">Dopo aver trovato il valore di priorità corretto per l'applicazione di conferenza di routing basata sulla posizione, digitare il cmdlet seguente per ogni pool Front-end o server Standard Edition che gli utenti di Homes hanno abilitato per il routing basato sulla posizione:</span><span class="sxs-lookup"><span data-stu-id="eb987-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="eb987-123">New-CsServerApplication-Identity Service: Registrar\<: FQDN\>del pool/LBRouting \<-Priority\> Application Priority-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="eb987-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="eb987-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eb987-124">For example:</span></span>

<span data-ttu-id="eb987-125">New-CsServerApplication-Identity Service Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-Urihttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="eb987-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="eb987-126">Dopo aver usato questo cmdlet, riavviare tutti i server front-end nel pool o nei server Standard Edition in cui è stata abilitata l'applicazione per i servizi di conferenza di routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="eb987-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eb987-127">Le imposte di routing basate sulla posizione su conferenze o trasferimenti consultivi non verranno applicate fino a quando non vengono riavviati tutti i server front-end nei pool o i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="eb987-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="eb987-128">Dopo che l'applicazione per i servizi di conferenza di routing basato sulla posizione è stata abilitata e tutti i server Lync applicabili sono stati riavviati, tutte le conferenze organizzate dagli utenti di Lync abilitate per il routing basato sulla posizione verranno monitorate per evitare il bypass a pedaggio PSTN</span><span class="sxs-lookup"><span data-stu-id="eb987-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

