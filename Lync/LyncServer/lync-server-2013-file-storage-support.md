---
title: "Lync Server 2013: Supporto dell'archiviazione di file"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a>Supporto dell'archiviazione di file in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-16_

Lync Server 2013 usa lo stesso archivio di file per tutti gli archivi. Il supporto per l'archiviazione dei file include le operazioni seguenti:

  - Condivisione di file in un ambiente di archiviazione Direct Attached (DAS) o in una rete di archiviazione (SAN), incluso il file System distribuito (DFS) e in una matrice ridondante di dischi indipendenti (RAID) per archivi di file. Per informazioni dettagliate sui requisiti di archiviazione, vedere [requisiti tecnici per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) e [i requisiti hardware e software per il Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sul sistema operativo DFS per Windows Server 2008, vedere la guida dettagliata a [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)DFS per windows Server 2008.

  - Un cluster condiviso per la condivisione file. Se si usa un cluster condiviso, è consigliabile usare i server cluster che usano Windows Server 2008 o Windows Server 2008 R2. L'uso di server cluster in cui è in esecuzione una versione precedente di Windows può causare problemi di autorizzazione che impediscono la disponibilità di alcune funzionalità. Usare l'amministratore del cluster per creare le condivisioni file. Per informazioni dettagliate sull'uso dell'amministratore del cluster, vedere l'articolo 284838 della Microsoft Knowledge Base "come creare una condivisione file del [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)cluster di server con cluster. exe".

</div>

<span> </span>

</div>

</div>

</div>

