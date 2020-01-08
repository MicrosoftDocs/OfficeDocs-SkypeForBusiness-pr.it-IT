---
title: 'Lync Server 2013: gestire la qualità del servizio (QoS)'
ms.reviewer: ''
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96f25d35f0d96c9e1681c6b4d2c2c3b3079aad34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="13a7e-102">Gestione della qualità del servizio (QoS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13a7e-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13a7e-103">_**Argomento Ultima modifica:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="13a7e-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="13a7e-104">La qualità del servizio (QoS) è una tecnologia di rete usata in alcune organizzazioni per offrire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="13a7e-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="13a7e-105">Il QoS viene usato più comunemente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete che competono per una quantità relativamente piccola di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più alte ai pacchetti trasporto di dati audio o video.</span><span class="sxs-lookup"><span data-stu-id="13a7e-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="13a7e-106">Assegnando a questi pacchetti una priorità più alta, le comunicazioni audio e video possono essere completate più rapidamente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come i trasferimenti di file, la navigazione web o i backup di database.</span><span class="sxs-lookup"><span data-stu-id="13a7e-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="13a7e-107">Il motivo è che i pacchetti di rete usati per i trasferimenti di file o i backup di database hanno la priorità "migliore sforzo".</span><span class="sxs-lookup"><span data-stu-id="13a7e-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13a7e-108">Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="13a7e-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="13a7e-109">Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti. Tuttavia, configuri questi dispositivi per supportare il contrassegno dei pacchetti in modo particolare.</span><span class="sxs-lookup"><span data-stu-id="13a7e-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="13a7e-110">Non si può presupporre che la qualità del servizio sarà supportata su Internet o su altre reti.</span><span class="sxs-lookup"><span data-stu-id="13a7e-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="13a7e-111">Anche se la qualità se il servizio è supportato in altre reti, non c'è alcuna garanzia che la QoS venga configurata allo stesso modo in cui il servizio è stato configurato nella rete.</span><span class="sxs-lookup"><span data-stu-id="13a7e-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="13a7e-112">Microsoft Lync Server 2013 non richiede la qualità del servizio; Se attualmente non si usa QoS, non è necessario installare il servizio prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13a7e-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="13a7e-113">Se si verifica una notevole quantità di perdita di pacchetti nella rete, il metodo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="13a7e-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="13a7e-114">Se non è possibile aggiungere più larghezza di banda, è consigliabile implementare invece la qualità del servizio.</span><span class="sxs-lookup"><span data-stu-id="13a7e-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="13a7e-115">Lync Server 2013 offre il supporto completo per la qualità del servizio: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Lync Server nell'infrastruttura di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="13a7e-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="13a7e-116">A tale scopo, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="13a7e-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="13a7e-117">[Abilitazione del QoS in Lync Server 2013 per i dispositivi che non sono basati su Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="13a7e-118">Per impostazione predefinita, QoS è disabilitato per i computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="13a7e-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="13a7e-119">Anche se è possibile usare Lync Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile usare il prodotto per modificare i codici DSCP usati da questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="13a7e-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="13a7e-120">[Configurazione di intervalli di porte in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="13a7e-121">È necessario prenotare un set di porte univoco per tipi di pacchetto diversi, ad esempio audio e video.</span><span class="sxs-lookup"><span data-stu-id="13a7e-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="13a7e-122">Con Lync Server 2013 non è possibile abilitare o disabilitare la qualità del servizio, ad esempio impostando un valore di proprietà su true o su false.</span><span class="sxs-lookup"><span data-stu-id="13a7e-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="13a7e-123">Puoi invece abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="13a7e-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="13a7e-124">Se in seguito si decide di non usare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo appropriati.</span><span class="sxs-lookup"><span data-stu-id="13a7e-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="13a7e-125">[Configurazione degli intervalli di porte per gli Edge Server in Lync server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="13a7e-126">Anche se non è necessario, è possibile configurare gli Edge Server in modo da usare gli stessi intervalli di porte degli altri server.</span><span class="sxs-lookup"><span data-stu-id="13a7e-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="13a7e-127">[Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="13a7e-128">Questi intervalli di porte si applicano solo ai computer client e in genere non corrispondono agli intervalli di porte configurati nei server.</span><span class="sxs-lookup"><span data-stu-id="13a7e-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="13a7e-129">[Configurazione di un criterio di qualità dei servizi in Lync server 2013 per le conferenze, le applicazioni e i server di mediazione](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="13a7e-130">Questi criteri determinano i codici DSCP applicati a tipi di pacchetto diversi.</span><span class="sxs-lookup"><span data-stu-id="13a7e-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="13a7e-131">[Configurazione di un criterio di qualità dei servizi per i server a/V Edge in Lync server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="13a7e-132">Questa operazione deve essere eseguita solo per il lato interno degli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="13a7e-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="13a7e-133">Questo perché la qualità del servizio è progettata per l'uso nella rete interna e non in Internet.</span><span class="sxs-lookup"><span data-stu-id="13a7e-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="13a7e-134">[Configurare i criteri di qualità dei servizi in Lync Server 2013 per i client in uso in Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="13a7e-135">Tieni presente che Microsoft Lync Server 2013 non supporta QoS per altri sistemi operativi Windows, come Windows Vista o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="13a7e-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="13a7e-136">[Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="13a7e-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="13a7e-137">Per impostazione predefinita, QoS è abilitato per i dispositivi Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="13a7e-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="13a7e-138">Tuttavia, potresti voler cambiare il valore di DSCP predefinito per assicurarti che tutti i pacchetti audio dell'organizzazione usino lo stesso codice DSCP.</span><span class="sxs-lookup"><span data-stu-id="13a7e-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13a7e-139">Se si usa Microsoft Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessante il nuovo set di cmdlet di Windows PowerShell disponibili per la gestione della qualità del servizio su tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="13a7e-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="13a7e-140">Per altre informazioni, vedere cmdlet per la qualità della rete di servizi in Windows [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)PowerShell at.</span><span class="sxs-lookup"><span data-stu-id="13a7e-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

