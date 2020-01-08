---
title: 'Lync Server 2013: visualizzare informazioni sui singoli trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="ceea8-102">Visualizzare informazioni sui singoli trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ceea8-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceea8-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ceea8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ceea8-104">I trunk SIP vengono usati per connettere la rete Voice over IP di Lync Server 2013 con la rete telefonica pubblica commutata.</span><span class="sxs-lookup"><span data-stu-id="ceea8-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="ceea8-105">Nella versione precedente del prodotto Trunks veniva usato per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway era limitato a un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="ceea8-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="ceea8-106">Di conseguenza, un gateway PSTN e un trunk SIP erano essenzialmente identici.</span><span class="sxs-lookup"><span data-stu-id="ceea8-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="ceea8-107">Per gli amministratori, ciò significava che potevano visualizzare informazioni su un singolo trunk SIP semplicemente visualizzando le informazioni sul gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="ceea8-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="ceea8-108">In Lync Server 2013, tuttavia, è ora possibile assegnare più trunk a un singolo gateway PSTN. Ciò significa che i gateway e i trunk non sono più uno e lo stesso.</span><span class="sxs-lookup"><span data-stu-id="ceea8-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="ceea8-109">A sua volta, ciò significa che gli amministratori devono usare il nuovo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) per visualizzare informazioni su un singolo trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="ceea8-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="ceea8-110">Il cmdlet Get-CsTrunk può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ceea8-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ceea8-111">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="ceea8-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="ceea8-112">Per visualizzare le informazioni per tutti i trunk SIP</span><span class="sxs-lookup"><span data-stu-id="ceea8-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="ceea8-113">Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="ceea8-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="ceea8-114">Per visualizzare le informazioni relative a un trunk SIP specifico</span><span class="sxs-lookup"><span data-stu-id="ceea8-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="ceea8-115">Questo comando restituisce solo le informazioni per il trunk SIP con Identity PstnGateway: 192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="ceea8-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="ceea8-116">Visualizzazione di informazioni per tutti i trunk SIP assegnati a un pool</span><span class="sxs-lookup"><span data-stu-id="ceea8-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="ceea8-117">In questo esempio vengono restituite le informazioni per tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ceea8-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

