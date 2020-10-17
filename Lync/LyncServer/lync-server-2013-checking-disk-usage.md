---
title: "Lync Server 2013: controllo dell'utilizzo del disco"
description: "Lync Server 2013: controllo dell'utilizzo del disco."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571002"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="5c37c-103">Controllo dell'utilizzo del disco in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c37c-103">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c37c-104">_**Ultimo argomento modificato:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="5c37c-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="5c37c-105">I dischi rigidi sono un componente importante della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c37c-105">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="5c37c-106">Senza un sufficiente volume di disco libero, non è possibile che il sistema operativo e i database di Lync Server 2013 funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="5c37c-106">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="5c37c-107">È necessario monitorare giornalmente le statistiche di database back-end di Lync Server 2013 per garantire che i server non si esauriscono nello spazio su disco e per prepararsi ad aggiungere risorse di archiviazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5c37c-107">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="5c37c-108">Oltre a controllare lo spazio sui dischi che ospitano il sistema operativo, i file di programma, i database e i registri delle transazioni (Lync Server 2013 back-end), è necessario monitorare anche l'utilizzo del file System che include lo spazio su disco per le condivisioni di file che contengono i dati importanti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c37c-108">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="5c37c-109">Contenuto della riunione</span><span class="sxs-lookup"><span data-stu-id="5c37c-109">Meeting content</span></span>

  - <span data-ttu-id="5c37c-110">Soddisfare i metadati del contenuto</span><span class="sxs-lookup"><span data-stu-id="5c37c-110">Meeting content metadata</span></span>

  - <span data-ttu-id="5c37c-111">Registri di conformità per le riunioni</span><span class="sxs-lookup"><span data-stu-id="5c37c-111">Meeting compliance logs</span></span>

  - <span data-ttu-id="5c37c-112">File di dati dell'applicazione (utilizzati internamente dal componente del server applicazioni)</span><span class="sxs-lookup"><span data-stu-id="5c37c-112">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="5c37c-113">Group Chat Server Web Service and Compliance Folders (per archiviare i file caricati nel servizio Web Group Chat)</span><span class="sxs-lookup"><span data-stu-id="5c37c-113">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="5c37c-114">File XML di conformità di Group Chat (che contengono record di conformità di Group Chat)</span><span class="sxs-lookup"><span data-stu-id="5c37c-114">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="5c37c-115">Aggiornare i file (per il servizio aggiornamento dispositivi)</span><span class="sxs-lookup"><span data-stu-id="5c37c-115">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="5c37c-116">File della Rubrica</span><span class="sxs-lookup"><span data-stu-id="5c37c-116">Address Book files</span></span>

<span data-ttu-id="5c37c-117">Lync Server 2013 richiede spazio su disco rigido per l'archiviazione dei database e dei registri delle transazioni, oltre ai file in condivisioni di file elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5c37c-117">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="5c37c-118">È necessario monitorare periodicamente lo spazio su disco per garantire che la distribuzione di Lync Server 2013 non venga influenzata negativamente a causa di risorse di archiviazione insufficienti.</span><span class="sxs-lookup"><span data-stu-id="5c37c-118">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="5c37c-119">Confrontare e gestire informazioni statistiche sullo spazio disponibile su disco su ogni volume di Lync Server 2013 e la crescita prevista dei database e i file di registro delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="5c37c-119">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="5c37c-120">Questo aiuta a pianificare la capacità e ad aggiungere spazio di archiviazione quando sono necessarie le risorse di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5c37c-120">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="5c37c-121">Per risolvere la risoluzione dei problemi e le situazioni di ripristino di emergenza, è consigliabile che lo spazio disponibile su volume libero sia uguale o superiore al 110% delle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="5c37c-121">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="5c37c-122">Per controllare lo spazio libero sul disco, è possibile utilizzare i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="5c37c-122">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="5c37c-123">**System Center Operations Manager**     System Center Operations Manager può essere utilizzato per avvisare gli amministratori quando è vincolato lo spazio del volume.</span><span class="sxs-lookup"><span data-stu-id="5c37c-123">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="5c37c-124">**Esecuzione di uno script**     Monitorare lo spazio su disco eseguendo uno script che invia un messaggio se lo spazio disponibile sul disco rigido scende al di sotto del 20%.</span><span class="sxs-lookup"><span data-stu-id="5c37c-124">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="5c37c-125">È possibile trovare uno script di esempio su Microsoft Script Center su TechNet, esaminare quanto segue: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="5c37c-125">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="5c37c-126">**Esplora risorse**     di Windows Utilizzare Esplora risorse per controllare lo spazio su disco dei volumi che archiviano i log e i database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c37c-126">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

