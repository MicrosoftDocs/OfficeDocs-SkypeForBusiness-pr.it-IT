---
title: 'Lync Server 2013: configurare il database della posizione'
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
ms.openlocfilehash: b2b15f0c679e9380a1f1a624f00f6c19384878fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a><span data-ttu-id="aa377-102">Configurare il database della posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa377-102">Configure the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa377-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="aa377-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="aa377-104">Per consentire ai client di rilevare automaticamente la propria posizione all'interno di una rete, è prima di tutto necessario configurare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="aa377-104">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> <span data-ttu-id="aa377-105">Se non si configura un database di posizione e la **posizione richiesta** nel criterio della posizione è impostata su **Sì** o su dichiarazione di non **responsabilità**, all'utente verrà richiesto di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="aa377-105">If you do not configure a location database, and **Location Required** in the location policy is set to **Yes** or **Disclaimer**, the user will be prompted to manually enter a location.</span></span>

<span data-ttu-id="aa377-106">Per configurare il database della posizione, verranno eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa377-106">To configure the location database, you will perform the following tasks:</span></span>

1.  <span data-ttu-id="aa377-107">Popolare il database con un mapping degli elementi di rete alle posizioni.</span><span class="sxs-lookup"><span data-stu-id="aa377-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="aa377-108">Se si usa un gateway ELIN (Emergency Location Identification Number), è necessario includere il numero ELIN nel \<campo\> CompanyName.</span><span class="sxs-lookup"><span data-stu-id="aa377-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>

2.  <span data-ttu-id="aa377-109">Convalidare gli indirizzi rispetto alla guida di indirizzo Master Street (stradario) gestita dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="aa377-109">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="aa377-110">Pubblicare il database aggiornato.</span><span class="sxs-lookup"><span data-stu-id="aa377-110">Publish the updated database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa377-111">In alternativa, è possibile definire un database di origine della posizione secondario che può essere usato nella posizione del database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="aa377-111">Alternately, you can define a secondary location source database that can be used in placed of the location database.</span></span> <span data-ttu-id="aa377-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-a-secondary-location-information-service.md">configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa377-112">For details, see <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa377-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="aa377-113">In This Section</span></span>

  - [<span data-ttu-id="aa377-114">Compilare il database della posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa377-114">Populate the location database in Lync Server 2013</span></span>](lync-server-2013-populate-the-location-database.md)

  - [<span data-ttu-id="aa377-115">Convalidare gli indirizzi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa377-115">Validate addresses in Lync Server 2013</span></span>](lync-server-2013-validate-addresses.md)

  - [<span data-ttu-id="aa377-116">Pubblicare il database della posizione da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa377-116">Publish the location database from Lync Server 2013</span></span>](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

