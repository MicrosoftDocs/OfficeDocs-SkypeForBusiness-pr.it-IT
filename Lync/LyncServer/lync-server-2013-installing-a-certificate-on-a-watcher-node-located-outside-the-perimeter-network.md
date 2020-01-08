---
title: "Lync Server 2013: installazione di un certificato in un nodo Watcher situato all'esterno della rete perimetrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1479ffdd7f6652b96f3015e047194d76bf1e8978
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="2e6f1-102">Installazione di un certificato in un nodo Watcher situato all'esterno della rete perimetrale di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e6f1-102">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e6f1-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2e6f1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2e6f1-104">Gli agenti di System Center Operations Manager eseguiti in una rete perimetrale, ad esempio un server Edge Lync Server, all'esterno dell'organizzazione, ad esempio un nodo di Watcher delle transazioni sintetiche esterne o in un limite di attendibilità dei servizi di dominio Active Directory, potrebbero richiedere la configurazione di un server gateway di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2e6f1-104">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="2e6f1-105">Questo ruolo del server consente agli agenti che non hanno una relazione di trust con il server di gestione radice di generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="2e6f1-105">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="2e6f1-106">Per informazioni dettagliate, vedere "gestione dei server gateway in Operations Manager 2007" nella raccolta TechNet di System Center Operations [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703)Manager.</span><span class="sxs-lookup"><span data-stu-id="2e6f1-106">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="2e6f1-107">Se si distribuisce un agente in una di queste posizioni, sarà anche necessario richiedere e configurare un certificato che consenta al nodo Watcher di inviare avvisi a System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2e6f1-107">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="2e6f1-108">Per semplificare questo processo, il team di Operations Manager ha creato un set di utilità che consentono di richiedere e installare il tipo corretto di certificato nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="2e6f1-108">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="2e6f1-109">Per informazioni dettagliate e per scaricare queste utilità, vedere l'articolo su [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)Blog "ottenere i certificati per gli agenti non appartenenti a un dominio con la creazione guidata di certificati".</span><span class="sxs-lookup"><span data-stu-id="2e6f1-109">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

