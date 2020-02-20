---
title: 'Lync Server 2013: pubblicare il database delle posizioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb7fef480a5b9a53706cca9f76408fbd58f28be
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="8f889-102">Pubblicare il database delle posizioni da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f889-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f889-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="8f889-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="8f889-104">Le nuove posizioni aggiunte al database delle posizioni non vengono rese disponibili per il client finché non vengono pubblicate.</span><span class="sxs-lookup"><span data-stu-id="8f889-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="8f889-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8f889-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="8f889-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="8f889-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="8f889-107">Se si utilizzano gateway ELIN (Emergency Location Identification Number), è necessario inoltre caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="8f889-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="8f889-108">Il gestore della rete PSTN può richiedere di utilizzare un formato specifico per i record ELIN.</span><span class="sxs-lookup"><span data-stu-id="8f889-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="8f889-109">Contattarlo per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="8f889-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="8f889-110">È possibile esportare i record dal database del servizio informazioni percorso e formattarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="8f889-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="8f889-111">Per pubblicare il database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="8f889-111">To publish the location database</span></span>

  - <span data-ttu-id="8f889-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8f889-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="8f889-113">Per pubblicare il database delle posizioni, eseguire il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="8f889-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

