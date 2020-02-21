---
title: "Lync Server 2013: impostazione delle piattaforme di sistema per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c87f8b0994cc6022cd68bd7e42bb37ae8cb84d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurazione delle piattaforme di sistema per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Prima di iniziare la distribuzione di Archiviazione, è necessario installare il sistema operativo richiesto e gli altri componenti software prerequisiti in un'infrastruttura hardware che soddisfi i requisiti si sistema:

  - ****   Le distribuzioni di Lync Server 2013 Platform Lync Server 2013 non dispongono di server di archiviazione. Gli agenti di raccolta dati unificati vengono invece eseguiti nei front end server e nei server Standard Edition per acquisire i dati per l'archiviazione, pertanto non è necessaria alcuna piattaforma di sistema distinta per ospitare l'archiviazione.

  - **Piattaforma di archiviazione dei dati**   in Lync Server 2013, è possibile archiviare i dati utilizzando uno dei seguenti elementi:
    
      - **Integrazione di Microsoft Exchange**   se si desidera archiviare i dati di archiviazione di Lync Server 2013 utilizzando la distribuzione di Exchange 2013 anziché o oltre alla configurazione di un database distinto per l'archiviazione dei dati di archiviazione, è necessario che la distribuzione di Exchange esegua Exchange 2013. Per informazioni dettagliate sulla configurazione delle piattaforme di sistema per Exchange 2013, vedere la documentazione del prodotto Exchange.
    
      - **SQL Server**   se si desidera utilizzare un database di SQL Server separato per l'archiviazione dei dati di archiviazione, anziché o oltre a utilizzare l'integrazione di Microsoft Exchange, è necessario configurare la piattaforma di sistema per il database prima della distribuzione dell'archiviazione. I requisiti specifici della piattaforma di sistema variano a seconda che si utilizzi Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012 per il database di archiviazione. Per informazioni dettagliate sulla configurazione delle piattaforme di sistema per questi database, vedere la documentazione del prodotto Microsoft SQL Server 2008 R2 e Microsoft SQL Server 2012.

  - **Piattaforma file server**   Lync Server 2013 archivia file di archiviazione di Lync Server nello stesso percorso specificato per l'archiviazione dei file quando si configurano i Front End Server o i server Standard Edition. Non è possibile specificare una posizione separata per l'archiviazione dei file di archiviazione e pertanto non è richiesta una piattaforma di sistema separata per tale archiviazione. Se si utilizza l'integrazione di Microsoft Exchange, Exchange 2013 i file per le comunicazioni Lync archiviate sono archiviati nei server Exchange 2013 per gli utenti ospitati nei server di Exchange.

</div>

<span> </span>

</div>

</div>

</div>

