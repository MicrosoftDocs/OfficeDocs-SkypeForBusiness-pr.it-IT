---
title: 'Lync Server 2013: aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a93e4bda396cb684ee15e5ee8dcd2c90ae09542
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="cefc2-102">Aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc2-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cefc2-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cefc2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cefc2-104">Le *aree di rete* sono gli hub di rete o gli backbone utilizzati nella configurazione del controllo di ammissione di chiamata, E9-1-1 e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="cefc2-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="cefc2-105">Utilizzare le procedure seguenti per visualizzare, creare o modificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="cefc2-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="cefc2-106">Ad esempio, se sono già state create aree di rete per una caratteristica vocale, non è necessario creare nuove aree di rete. altre funzionalità di VoIP aziendale avanzate utilizzeranno le stesse aree di rete.</span><span class="sxs-lookup"><span data-stu-id="cefc2-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="cefc2-107">Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="cefc2-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="cefc2-108">Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale.</span><span class="sxs-lookup"><span data-stu-id="cefc2-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="cefc2-109">Per ulteriori informazioni, vedere [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="cefc2-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cefc2-110">Tutti i requisiti specifici per particolari funzionalità per le definizioni delle aree di rete sono documentati negli argomenti relativi alla distribuzione per la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cefc2-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cefc2-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="cefc2-111">In This Section</span></span>

  - [<span data-ttu-id="cefc2-112">Visualizzazione delle informazioni sulle aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc2-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="cefc2-113">Creazione o modifica di aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc2-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="cefc2-114">Eliminazione di aree di rete esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc2-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="cefc2-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="cefc2-115">Reference</span></span>

[<span data-ttu-id="cefc2-116">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cefc2-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

