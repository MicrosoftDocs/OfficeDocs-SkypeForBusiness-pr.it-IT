---
title: 'Lync Server 2013: gestione della qualità del servizio (QoS)'
description: 'Lync Server 2013: gestione della qualità del servizio (QoS).'
ms.reviewer: ''
f1.keywords:
- NOCSH
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
ms.openlocfilehash: df0e84389cc030cd63fe04c46929bd981a074aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552722"
---
# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="8ce17-103">Gestione della qualità del servizio (QoS) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ce17-103">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ce17-104">_**Ultimo argomento modificato:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8ce17-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8ce17-105">Quality of Service (QoS) è una tecnologia di rete utilizzata in alcune organizzazioni per fornire un'esperienza utente ottimale per le comunicazioni audio e video.</span><span class="sxs-lookup"><span data-stu-id="8ce17-105">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="8ce17-106">La funzionalità QoS è più comunemente utilizzata nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in competizione per una quantità relativamente ridotta di larghezza di banda disponibile, la qualità del servizio consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video.</span><span class="sxs-lookup"><span data-stu-id="8ce17-106">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="8ce17-107">Assegnando a questi pacchetti una priorità più elevata, è probabile che le comunicazioni audio e video vengano completate più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come il trasferimento di file, la navigazione web o i backup dei database.</span><span class="sxs-lookup"><span data-stu-id="8ce17-107">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="8ce17-108">Ciò è dovuto al fatto che i pacchetti di rete utilizzati per i trasferimenti di file o i backup dei database sono assegnati come priorità "Best Effort".</span><span class="sxs-lookup"><span data-stu-id="8ce17-108">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ce17-109">Come regola generale, la qualità del servizio si applica solo alle sessioni di comunicazione sulla rete interna.</span><span class="sxs-lookup"><span data-stu-id="8ce17-109">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="8ce17-110">Quando si implementa QoS, i server e i router vengono configurati in modo da supportare la marcatura dei pacchetti. Tuttavia, è necessario configurare questi dispositivi per supportare il contrassegno dei pacchetti in un modo specifico.</span><span class="sxs-lookup"><span data-stu-id="8ce17-110">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="8ce17-111">Non è possibile presumere che la qualità del servizio sarà supportata su Internet o su altre reti.</span><span class="sxs-lookup"><span data-stu-id="8ce17-111">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="8ce17-112">Anche se la qualità se il servizio è supportato su altre reti, non vi è alcuna garanzia che QoS venga configurato nello stesso modo in cui è stato configurato il servizio sulla rete.</span><span class="sxs-lookup"><span data-stu-id="8ce17-112">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="8ce17-113">Microsoft Lync Server 2013 non richiede la qualità del servizio. Se attualmente non si utilizza QoS, non è necessario installare il servizio prima di installare Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ce17-113">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="8ce17-114">Se si verifica una notevole quantità di perdita di pacchetti sulla rete, il modo consigliato per alleviare questo problema consiste nell'aggiungere ulteriore larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="8ce17-114">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="8ce17-115">Se non è possibile aggiungere più larghezza di banda, potrebbe essere necessario implementare invece la qualità del servizio.</span><span class="sxs-lookup"><span data-stu-id="8ce17-115">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="8ce17-116">Lync Server 2013 offre supporto completo per la qualità del servizio: ciò significa che le organizzazioni che utilizzano già QoS possono integrare facilmente Lync Server nell'infrastruttura di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="8ce17-116">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="8ce17-117">A tale scopo, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ce17-117">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="8ce17-118">[Abilitazione del QoS in Lync Server 2013 per dispositivi che non sono basati su Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-118">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="8ce17-119">Per impostazione predefinita, QoS è disabilitata per i computer e altri dispositivi (ad esempio iPhones) che eseguono altri sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="8ce17-119">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="8ce17-120">Anche se è possibile utilizzare Lync Server per abilitare e disabilitare la qualità del servizio per i dispositivi, non è in genere possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8ce17-120">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="8ce17-121">[Configurazione degli intervalli di porte in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-121">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="8ce17-122">È necessario riservare un insieme univoco di porte per diversi tipi di pacchetti, ad esempio audio e video.</span><span class="sxs-lookup"><span data-stu-id="8ce17-122">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="8ce17-123">Con Lync Server 2013 non è possibile abilitare o disabilitare la qualità del servizio, ad esempio, l'impostazione di un valore della proprietà su true o su false.</span><span class="sxs-lookup"><span data-stu-id="8ce17-123">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="8ce17-124">In alternativa, è possibile abilitare la qualità del servizio configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="8ce17-124">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="8ce17-125">Se in seguito si decide di non utilizzare QoS, è possibile "disabilitare" la qualità del servizio semplicemente rimuovendo gli oggetti Criteri di gruppo corretti.</span><span class="sxs-lookup"><span data-stu-id="8ce17-125">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="8ce17-126">[Configurazione degli intervalli di porte per i server perimetrali in Lync server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-126">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="8ce17-127">Sebbene non sia necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server.</span><span class="sxs-lookup"><span data-stu-id="8ce17-127">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="8ce17-128">[Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-128">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="8ce17-129">Questi intervalli di porte si applicano solo ai computer client e in genere non corrispondono agli intervalli di porte configurati nei server.</span><span class="sxs-lookup"><span data-stu-id="8ce17-129">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="8ce17-130">[Configurazione dei criteri di qualità del servizio in Lync server 2013 per i servizi di conferenza, applicazione e Mediation Server](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-130">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="8ce17-131">Questi criteri determinano i codici DSCP applicati ai diversi tipi di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="8ce17-131">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="8ce17-132">[Configurazione dei criteri di qualità del servizio per i server a/V Edge in Lync server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-132">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="8ce17-133">Tale operazione deve essere completata solo per il lato interno dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="8ce17-133">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="8ce17-134">Ciò è dovuto al fatto che la qualità del servizio è progettata per essere utilizzata sulla rete interna e non su Internet.</span><span class="sxs-lookup"><span data-stu-id="8ce17-134">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="8ce17-135">[Configurazione dei criteri di qualità del servizio in Lync Server 2013 per i client in esecuzione in Windows 7 o Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-135">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="8ce17-136">Si noti che Microsoft Lync Server 2013 non supporta QoS per altri sistemi operativi Windows, ad esempio Windows Vista o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="8ce17-136">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="8ce17-137">[Configurazione della qualità del servizio nei dispositivi Microsoft Lync Phone Edition in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="8ce17-137">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="8ce17-138">Per impostazione predefinita, QoS è abilitata per i dispositivi Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="8ce17-138">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="8ce17-139">Tuttavia, potrebbe essere necessario modificare il valore DSCP predefinito per assicurarsi che tutti i pacchetti audio nell'organizzazione utilizzino lo stesso codice DSCP.</span><span class="sxs-lookup"><span data-stu-id="8ce17-139">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ce17-140">Se si utilizza Microsoft Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessato al nuovo set di cmdlet di Windows PowerShell disponibili per la gestione della qualità del servizio su tale piattaforma.</span><span class="sxs-lookup"><span data-stu-id="8ce17-140">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="8ce17-141">Per ulteriori informazioni, vedere cmdlet per la qualità dei servizi di rete in Windows PowerShell all'indirizzo [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps) .</span><span class="sxs-lookup"><span data-stu-id="8ce17-141">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

