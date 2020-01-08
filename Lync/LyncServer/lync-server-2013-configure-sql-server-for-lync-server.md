---
title: 'Lync Server 2013: Configurare SQL Server per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configurare SQL Server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-08-12_

Gli argomenti di questa sezione illustrano come distribuire e configurare SQL Server per l'uso in una distribuzione aziendale di Lync Server. I server Standard Edition usano una versione di SQL Server Express di SQL Server collocata di dimensioni adeguate per i carichi di lavoro di un server Standard Edition.

Lync Server 2013 Central Management store contiene i dati utente per tutti i server Enterprise Edition in un pool ed è progettato per essere posizionato in un server back-end basato su SQL Server. Come repository centralizzato, il Central Management store non può essere installato nello stesso computer di qualsiasi altro ruolo di Lync Server 2013. L'Central Management store non può risiedere in un server Enterprise Edition nel pool. L'archivio di gestione centralizzato viene creato automaticamente quando si pubblica la topologia per la prima volta e si seleziona per creare i database. Il computer designato come server back-end deve già eseguire il software di database di SQL Server in modo che l'installazione abbia successo.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Posizionamento dei file di log e dei file di dati di SQL Server per Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

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

