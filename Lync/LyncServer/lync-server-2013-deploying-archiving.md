---
title: "Lync Server 2013: Distribuzione dell'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Archiving
ms:assetid: a89edd16-12d5-4602-ad2f-194b47d1188e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205147(v=OCS.15)
ms:contentKeyID: 48185031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86b1394df9bb52502e1e0c605bedb05a0579042e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="e9b57-102">Distribuzione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b57-102">Deploying Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9b57-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e9b57-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e9b57-104">Lync Server 2013 offre una soluzione per l'archiviazione di contenuti di messaggistica istantanea e comunicazioni di conferenza in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9b57-104">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="e9b57-105">Puoi implementare il supporto dell'archiviazione integrando lo spazio di archiviazione di archiviazione con lo spazio di archiviazione di Exchange 2013, usando i database di SQL Server per l'archiviazione dei dati di archiviazione di Lync Server 2013 o usando sia Lync Server 2013 che Exchange 2013 storage.</span><span class="sxs-lookup"><span data-stu-id="e9b57-105">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="e9b57-106">Puoi controllare il modo in cui vengono archiviati i dati usando i criteri e le configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e9b57-106">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="e9b57-107">Per informazioni dettagliate, vedere [pianificazione per l'archiviazione in Lync server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione e funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione sulla distribuzione o alla documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="e9b57-107">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="e9b57-108">È possibile usare le informazioni in questa sezione per configurare inizialmente l'archiviazione e configurarla.</span><span class="sxs-lookup"><span data-stu-id="e9b57-108">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="e9b57-109">Dopo la distribuzione, è possibile modificare le impostazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e9b57-109">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="e9b57-110">Per informazioni dettagliate su come implementare il supporto dell'archiviazione per la gestione giornaliera o per soddisfare i nuovi requisiti dell'organizzazione, vedere Gestione dell' [archiviazione di Lync Server 2013](lync-server-2013-managing-archiving.md) nella documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e9b57-110">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9b57-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e9b57-111">In This Section</span></span>

  - [<span data-ttu-id="e9b57-112">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b57-112">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="e9b57-113">Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b57-113">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="e9b57-114">Configurazione di sistemi e infrastrutture per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b57-114">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="e9b57-115">Aggiunta di database di archiviazione a una distribuzione di Lync Server 2013 esistente</span><span class="sxs-lookup"><span data-stu-id="e9b57-115">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="e9b57-116">Configurazione del supporto per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9b57-116">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

