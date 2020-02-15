---
title: 'Lync Server 2013: impostazione di un percorso di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b47a866b4ce1a731d282c78e09c1afb3c91af7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="6123a-102">Configurazione di un percorso di backup per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6123a-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6123a-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6123a-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="6123a-104">Prima di eseguire il primo backup di Lync Server, configurare l'hardware e il software necessari per l'archiviazione e la gestione dei backup.</span><span class="sxs-lookup"><span data-stu-id="6123a-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="6123a-105">È necessario ottenere l'accesso ai supporti e al contenuto appropriati e garantire la connettività di rete tra i singoli server da sottoporre a backup e il supporto di backup.</span><span class="sxs-lookup"><span data-stu-id="6123a-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="6123a-106">Il supporto e la posizione utilizzati devono essere definiti nella strategia di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="6123a-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="6123a-107">La posizione utilizzata per i backup regolari può essere locale o remota, ma deve essere sicura e deve essere accessibile sia per il backup che per il ripristino.</span><span class="sxs-lookup"><span data-stu-id="6123a-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="6123a-108">È consigliabile utilizzare una posizione remota per proteggersi da un evento catastrofico nel sito principale.</span><span class="sxs-lookup"><span data-stu-id="6123a-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="6123a-109">Dopo aver impostato e testato i singoli componenti, verificare l'accessibilità ai backup da ogni server.</span><span class="sxs-lookup"><span data-stu-id="6123a-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

