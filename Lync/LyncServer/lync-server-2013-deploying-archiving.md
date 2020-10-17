---
title: "Lync Server 2013: distribuzione dell'archiviazione"
description: "Lync Server 2013: distribuzione dell'archiviazione."
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
ms.openlocfilehash: c4ba38b7dcde0c72469e361f59ade7cb7f6ebb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558502"
---
# <a name="deploying-archiving-in-lync-server-2013"></a><span data-ttu-id="13c90-103">Distribuzione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c90-103">Deploying Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c90-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="13c90-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="13c90-105">Lync Server 2013 fornisce una soluzione per l'archiviazione del contenuto di messaggistica istantanea e delle comunicazioni di conferenza in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13c90-105">Lync Server 2013 provides a solution for archiving instant messaging (IM) content and conferencing communications in Lync Server.</span></span> <span data-ttu-id="13c90-106">È possibile implementare il supporto per l'archiviazione mediante l'integrazione dell'archiviazione di archiviazione con l'archiviazione di Exchange 2013, utilizzando i database di SQL Server per l'archiviazione dei dati di archiviazione di Lync Server 2013 oppure utilizzando Lync Server 2013 ed Exchange 2013 storage.</span><span class="sxs-lookup"><span data-stu-id="13c90-106">You can implement archiving support by integrating archiving storage with Exchange 2013 storage, by using SQL Server databases for storage of Lync Server 2013 archiving data, or by using both Lync Server 2013 and Exchange 2013 storage.</span></span> <span data-ttu-id="13c90-107">È possibile controllare il modo in cui i dati vengono archiviati utilizzando criteri e configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="13c90-107">You control how data is archived using policies and archiving configurations.</span></span> <span data-ttu-id="13c90-108">Per informazioni dettagliate, vedere [Planning for archiving in Lync server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione e [modalità di funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="13c90-108">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation and [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<span data-ttu-id="13c90-109">È possibile utilizzare le informazioni di questa sezione per impostare e configurare inizialmente l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="13c90-109">You can use the information in this section to set up and configure Archiving initially.</span></span> <span data-ttu-id="13c90-110">Dopo la distribuzione, è possibile modificare le impostazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="13c90-110">After deployment, you can change Archiving settings.</span></span> <span data-ttu-id="13c90-111">Per informazioni dettagliate sull'implementazione del supporto per l'archiviazione per la gestione quotidiana o per soddisfare i nuovi requisiti nell'organizzazione, vedere [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="13c90-111">For details about how you implement archiving support for day-to-day management or to meet new requirements in your organization, see [Managing Lync Server 2013 Archiving](lync-server-2013-managing-archiving.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13c90-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="13c90-112">In This Section</span></span>

  - [<span data-ttu-id="13c90-113">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c90-113">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)

  - [<span data-ttu-id="13c90-114">Elenco di controllo di distribuzione per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c90-114">Deployment checklist for Archiving in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-archiving.md)

  - [<span data-ttu-id="13c90-115">Configurazione dei sistemi e dell'infrastruttura per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c90-115">Setting up systems and infrastructure for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md)

  - [<span data-ttu-id="13c90-116">Aggiunta di database di archiviazione a una distribuzione di Lync Server 2013 esistente</span><span class="sxs-lookup"><span data-stu-id="13c90-116">Adding Archiving databases to an existing Lync Server 2013 Deployment</span></span>](lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md)

  - [<span data-ttu-id="13c90-117">Configurazione del supporto per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13c90-117">Configuring support for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-archiving.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

