---
title: 'Lync Server 2013: configurare SQL Server per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c35f1d82913c71523412c791d9b6a945f443e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535133"
---
# <a name="configure-sql-server-for-lync-server-2013"></a>Configurare SQL Server per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-08-12_

Negli argomenti di questa sezione viene illustrato come distribuire e configurare SQL Server per l'utilizzo in una distribuzione aziendale di Lync Server. I server Standard Edition utilizzano una versione di SQL Server Express collocata di SQL Server di dimensioni adeguate per i carichi di lavoro di un server Standard Edition.

L'archivio di gestione centrale di Lync Server 2013 contiene i dati utente per tutti i server Enterprise Edition all'interno di un pool ed è stato creato per essere posizionato su un server back-end basato su SQL Server. Poiché si tratta di un archivio centralizzato, l'archivio di gestione centrale non può essere installato nello stesso computer di qualsiasi altro ruolo Lync Server 2013. L'archivio di gestione centrale non può trovarsi in un server Enterprise Edition del pool. L'archivio di gestione centrale viene creato automaticamente quando si pubblica la topologia per la prima volta e si sceglie di creare i database. Il computer che si desidera definire come server back-end deve già eseguire il software di database di SQL Server in modo che l'installazione abbia esito positivo.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Disposizione dei file di registro e di dati di SQL Server per Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurare SQL Server in Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Autorizzazioni di distribuzione per SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installazione di database mediante Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Informazioni sui requisiti del firewall per SQL Server con Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurare il clustering di SQL Server per Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

