---
title: 'Lync Server 2013: sostituzione di XMLAdapter con una scheda di conformità del server Chat persistente personalizzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa0c1e001270e7a51e35d857625c77146f9a62e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="7913f-102">Sostituzione di XMLAdapter con una scheda di conformità del server Chat persistente personalizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7913f-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7913f-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7913f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7913f-104">È possibile scrivere un adattatore personalizzato anziché utilizzare XmlAdapter installato con il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7913f-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="7913f-105">A tale scopo, è necessario fornire un assembly .NET Framework che contenga una classe pubblica che implementi l'interfaccia **IComplianceAdapter** .</span><span class="sxs-lookup"><span data-stu-id="7913f-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="7913f-106">È necessario inserire questo assembly nella cartella di installazione del server Chat persistente di ogni server nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="7913f-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="7913f-107">Uno qualsiasi dei server di conformità è in grado di fornire i dati di conformità alla scheda, ma i server di conformità non forniranno i dati di conformità duplicati a più istanze della scheda.</span><span class="sxs-lookup"><span data-stu-id="7913f-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="7913f-108">Implementazione dell'interfaccia IComplianceAdapter</span><span class="sxs-lookup"><span data-stu-id="7913f-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="7913f-109">L'interfaccia è definita nell'assembly Compliance. dll nello spazio dei `Microsoft.Rtc.Internal.Chat.Server.Compliance`nomi.</span><span class="sxs-lookup"><span data-stu-id="7913f-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="7913f-110">L'interfaccia definisce due metodi che devono essere implementati dall'adattatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7913f-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="7913f-111">Il server di conformità di Persistent Chat chiamerà questo metodo al primo caricamento dell'adapter.</span><span class="sxs-lookup"><span data-stu-id="7913f-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="7913f-112">`AdapterConfig` Contiene la configurazione di conformità di Persistent Chat pertinente per la scheda di conformità.</span><span class="sxs-lookup"><span data-stu-id="7913f-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="7913f-113">Il server di conformità di Persistent Chat chiama questo metodo a intervalli periodici finché sono presenti nuovi dati da tradurre.</span><span class="sxs-lookup"><span data-stu-id="7913f-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="7913f-114">Questo intervallo di tempo è uguale a `RunInterval` quello impostato nella configurazione di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="7913f-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="7913f-115">`ConversationCollection` Contiene le informazioni di conversazione raccolte dall'ultima volta che è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="7913f-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

