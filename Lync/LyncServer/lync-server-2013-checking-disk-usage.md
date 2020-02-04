---
title: "Lync Server 2013: controllo dell'utilizzo del disco"
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
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="b5217-102">Controllo dell'utilizzo del disco in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5217-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5217-103">_**Argomento Ultima modifica:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="b5217-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="b5217-104">I dischi rigidi sono un componente importante della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5217-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b5217-105">Senza un sufficiente volume di disco libero, il sistema operativo e i database di Lync Server 2013 non possono funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="b5217-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="b5217-106">È necessario monitorare giornalmente le statistiche di database back-end di Lync Server 2013 per assicurarsi che i server non finiscano nello spazio su disco e si preparino ad aggiungere risorse di archiviazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="b5217-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="b5217-107">Oltre a controllare lo spazio sui dischi che ospitano il sistema operativo, i file di programma, il database e i registri delle transazioni (Lync Server 2013 back-end), è necessario monitorare anche l'uso del file System che include lo spazio su disco per le condivisioni di file che contengono le seguenti importanti dati</span><span class="sxs-lookup"><span data-stu-id="b5217-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="b5217-108">Contenuto della riunione</span><span class="sxs-lookup"><span data-stu-id="b5217-108">Meeting content</span></span>

  - <span data-ttu-id="b5217-109">Metadati del contenuto della riunione</span><span class="sxs-lookup"><span data-stu-id="b5217-109">Meeting content metadata</span></span>

  - <span data-ttu-id="b5217-110">Registri conformità delle riunioni</span><span class="sxs-lookup"><span data-stu-id="b5217-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="b5217-111">File di dati dell'applicazione (usati internamente dal componente server applicazioni)</span><span class="sxs-lookup"><span data-stu-id="b5217-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="b5217-112">Raggruppare le cartelle servizio Web Chat Server e conformità (per archiviare i file caricati nel servizio web chat di gruppo)</span><span class="sxs-lookup"><span data-stu-id="b5217-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="b5217-113">File XML di conformità della chat di gruppo (che contengono record di conformità di Group Chat)</span><span class="sxs-lookup"><span data-stu-id="b5217-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="b5217-114">Aggiornare i file (per il servizio di aggiornamento dei dispositivi)</span><span class="sxs-lookup"><span data-stu-id="b5217-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="b5217-115">File della Rubrica</span><span class="sxs-lookup"><span data-stu-id="b5217-115">Address Book files</span></span>

<span data-ttu-id="b5217-116">Lync Server 2013 richiede spazio su disco rigido per archiviare i propri database e i registri delle transazioni oltre ai file in condivisioni file elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b5217-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="b5217-117">È consigliabile monitorare regolarmente lo spazio su disco per verificare che la distribuzione di Lync Server 2013 non venga influenzata negativamente a causa di risorse di archiviazione insufficienti.</span><span class="sxs-lookup"><span data-stu-id="b5217-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="b5217-118">Confrontare e gestire le informazioni statistiche sullo spazio disponibile su disco in ogni volume di Lync Server 2013 e la crescita prevista dei database e i file di log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="b5217-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="b5217-119">Questo aiuta a pianificare la capacità e ad aggiungere spazio di archiviazione quando sono necessarie le risorse di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b5217-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="b5217-120">Per gestire la risoluzione dei problemi e il ripristino di emergenza, è consigliabile che lo spazio disponibile per il volume libero sia uguale o maggiore di 110% delle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="b5217-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="b5217-121">Per controllare lo spazio disponibile su disco, è possibile usare i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5217-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="b5217-122">**System Center Operations**   Manager System Center Operations Manager può essere usato per avvisare gli amministratori quando lo spazio del volume è vincolato.</span><span class="sxs-lookup"><span data-stu-id="b5217-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="b5217-123">**L'esecuzione di uno**   spazio su disco di monitor di script esegue uno script che invia un messaggio se lo spazio disponibile sul disco rigido scende al di sotto del 20%.</span><span class="sxs-lookup"><span data-stu-id="b5217-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="b5217-124">È possibile trovare uno script di esempio in Microsoft Script Center in TechNet, esaminare:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="b5217-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="b5217-125">**Esplora risorse**   USA Esplora risorse per verificare la quantità di spazio su disco nei volumi che archiviano i registri e i database di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5217-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

