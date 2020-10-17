---
title: Configurazione di Lync Server per l'utilizzo con System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150b240fe0c2be769e407cacecd8440bd4596ae5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506233"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Configurazione di Lync Server 2013 per l'utilizzo con System Center Operations Manager

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Per configurare l'infrastruttura di Microsoft Lync Server 2013 in modo che funzioni con System Center Operations Manager, è necessario eseguire tre operazioni:

  - Identificare e configurare il server di gestione di System Center Operations Manager principale. La configurazione del server di gestione include l'installazione di System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, nonché la configurazione di un database back-end tramite SQL Server. La versione effettiva di SQL Server che è necessario utilizzare dipende dalla versione di System Center Operations Manager in uso. Per informazioni dettagliate, vedere [Configuring the primary Management Server in Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identificare e configurare i computer Lync Server che si desidera monitorare. Per monitorare un computer Lync Server tramite System Center Operations Manager, è necessario installare i file dell'agente System Center Operations Manager e configurare ogni server affinché funga da proxy.

  - Identificare e configurare i computer che si desidera utilizzare come *nodi di monitoraggio*di Lync Server. I nodi Watcher sono computer che eseguono periodicamente transazioni sintetiche di Lync Server, ovvero cmdlet di Windows PowerShell che verificano che i componenti principali di Lync Server, ad esempio la possibilità di accedere al sistema o la possibilità di scambiare messaggi istantanei funzionino come previsto.

Negli argomenti di questa sezione sono contenute le istruzioni per eseguire ognuna di queste attività.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione del server di gestione principale in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installazione dei Management Pack di Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configurazione dei computer Lync Server che verranno monitorati in Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installazione e configurazione di nodi Watcher in Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

