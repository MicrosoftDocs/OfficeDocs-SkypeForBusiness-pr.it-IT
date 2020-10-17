---
title: 'Lync Server 2013: configurare il database delle posizioni'
description: 'Lync Server 2013: configurare il database delle posizioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877c83976ca0db9abc3a9e57d4a1cf5adaa1291a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544932"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="509ec-103">Configurare il database delle posizioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="509ec-103">Configure the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="509ec-104">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="509ec-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="509ec-p101">Per consentire ai client di individuare automaticamente la propria posizione in una rete, è necessario innanzitutto configurare il database delle posizioni. Se non si configura un database delle posizioni e l'opzione **Posizione necessaria** nei criteri percorso è impostata su **Sì** o su **Dichiarazione di non responsabilità**, verrà chiesto all'utente di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="509ec-p101">To enable clients to automatically detect their location within a network, you first need to configure the location database. If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="509ec-107">Per configurare un database delle posizioni, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="509ec-107">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="509ec-108">Popolare il database con il mapping degli elementi di rete ai percorsi.</span><span class="sxs-lookup"><span data-stu-id="509ec-108">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="509ec-109">Se si utilizza un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<CompanyName\> campo.</span><span class="sxs-lookup"><span data-stu-id="509ec-109">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="509ec-110">Convalidare gli indirizzi in base allo stradario generale gestito dal provider di servizi di emergenza.</span><span class="sxs-lookup"><span data-stu-id="509ec-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="509ec-111">Pubblicare il database aggiornato.</span><span class="sxs-lookup"><span data-stu-id="509ec-111">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="509ec-112">In alternativa, è possibile definire un database di origine delle posizioni secondario che può essere utilizzato al posto del database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="509ec-112">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="509ec-113">Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a Secondary Location Information Service in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="509ec-113">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="509ec-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="509ec-114">In This Section</span></span>

  - [<span data-ttu-id="509ec-115">Popolare il database delle posizioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="509ec-115">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="509ec-116">Convalidare gli indirizzi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="509ec-116">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="509ec-117">Pubblicare il database delle posizioni da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="509ec-117">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

