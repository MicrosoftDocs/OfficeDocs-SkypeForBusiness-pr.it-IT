---
title: 'Lync Server 2013: visualizzare informazioni sui singoli trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9663c6e762143eca572c0343ce21e91ad86b0b6d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="2f01e-102">Visualizzare informazioni sui singoli trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f01e-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f01e-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2f01e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2f01e-104">I trunk SIP vengono utilizzati per connettere la rete telefonica di Lync Server 2013 Voice over IP con la rete telefonica pubblica commutata.</span><span class="sxs-lookup"><span data-stu-id="2f01e-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="2f01e-105">Nella versione precedente del prodotto i trunk vengono utilizzati per instradare le chiamate in uscita da un Mediation Server a un gateway PSTN e ogni gateway è limitato a un singolo trunk.</span><span class="sxs-lookup"><span data-stu-id="2f01e-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="2f01e-106">Un gateway PSTN e un trunk SIP in questo caso pertanto sono essenzialmente identici.</span><span class="sxs-lookup"><span data-stu-id="2f01e-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="2f01e-107">Per gli amministratori, questo significa che possono visualizzare le informazioni relative a un trunk SIP semplicemente visualizzando le informazioni relative al gateway PSTN associato.</span><span class="sxs-lookup"><span data-stu-id="2f01e-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="2f01e-108">In Lync Server 2013, tuttavia, è ora possibile assegnare più trunk a un singolo gateway PSTN. Questo significa che i gateway e i trunk non sono più uguali.</span><span class="sxs-lookup"><span data-stu-id="2f01e-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="2f01e-109">Questo di conseguenza significa che gli amministratori devono utilizzare il nuovo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) per visualizzare le informazioni relative a un singolo trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="2f01e-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="2f01e-110">Il cmdlet Get-CsTrunk può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f01e-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f01e-111">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="2f01e-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="2f01e-112">Per visualizzare informazioni su tutti i trunk SIP</span><span class="sxs-lookup"><span data-stu-id="2f01e-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="2f01e-113">Il comando seguente restituisce informazioni su tutti i trunk SIP in uso nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2f01e-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="2f01e-114">Per visualizzare le informazioni relative a uno specifico trunk SIP</span><span class="sxs-lookup"><span data-stu-id="2f01e-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="2f01e-115">Questo comando restituisce informazioni solo sul trunk SIP con l'identità (Identity) PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="2f01e-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="2f01e-116">Visualizzazione delle informazioni relative a tutti i trunk SIP assegnati a un pool</span><span class="sxs-lookup"><span data-stu-id="2f01e-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="2f01e-117">In questo esempio vengono restituite le informazioni su tutti i trunk SIP assegnati al pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="2f01e-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

