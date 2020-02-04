---
title: 'Lync Server 2013: pubblicare il database della posizione'
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
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a><span data-ttu-id="c98fc-102">Pubblicare il database della posizione da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c98fc-102">Publish the location database from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c98fc-103">_**Argomento Ultima modifica:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c98fc-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c98fc-104">I nuovi percorsi aggiunti al database della posizione non verranno resi disponibili al client finché non saranno stati pubblicati.</span><span class="sxs-lookup"><span data-stu-id="c98fc-104">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>

<span data-ttu-id="c98fc-105">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="c98fc-105">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="c98fc-106">**Publish-CsLisConfiguration**</span><span class="sxs-lookup"><span data-stu-id="c98fc-106">**Publish-CsLisConfiguration**</span></span>

<span data-ttu-id="c98fc-107">Se si usano i gateway ELIN (Emergency Location Identification Number), è anche necessario caricare i numeri ELINs nel database di identificazione automatica della posizione (ALI) del gestore della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="c98fc-107">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="c98fc-108">Il gestore PSTN può richiedere l'uso di un formato specifico per i record ELIN.</span><span class="sxs-lookup"><span data-stu-id="c98fc-108">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="c98fc-109">Per informazioni dettagliate, contattare il gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="c98fc-109">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="c98fc-110">È possibile esportare i record dal database del servizio informazioni sulla posizione e formattarli in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c98fc-110">You can export the records from the Location Information service database and format them as required.</span></span>

<div>

## <a name="to-publish-the-location-database"></a><span data-ttu-id="c98fc-111">Per pubblicare il database della posizione</span><span class="sxs-lookup"><span data-stu-id="c98fc-111">To publish the location database</span></span>

  - <span data-ttu-id="c98fc-112">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c98fc-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

  - <span data-ttu-id="c98fc-113">Eseguire il cmdlet seguente per pubblicare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="c98fc-113">Run the following cmdlet to publish the location database.</span></span>
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

