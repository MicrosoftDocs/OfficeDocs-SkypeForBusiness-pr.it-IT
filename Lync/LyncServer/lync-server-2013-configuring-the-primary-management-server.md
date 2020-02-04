---
title: 'Lync Server 2013: configurazione del server di gestione principale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configurazione del server di gestione principale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-19_

Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse negli amministratori di Microsoft Lync Server 2013, è necessario prima di tutto designare un computer per fungere da server di gestione principale. in tale computer è necessario installare System Center Operations Manager 2007 R2 o System Center Operations Manager 2012. È inoltre necessario installare una versione supportata di SQL Server in modo che funzioni come database back-end di Operations Manager. Se si usa System Center Operations Manager 2012, è possibile usare una delle versioni seguenti di SQL Server come database back-end:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Se si usa System Center Operations Manager 2007 R2, è consigliabile installare SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3. È anche possibile usare SQL Server 2008 R2 come database back-end per System Center Operations Manager 2007 R2. Per altre informazioni sulla configurazione di SQL Server 2008 R2 per l'utilizzo di System Center Operations Manager 2007 R2, vedere l'appendice 1 della presente documentazione.

Quando si installa System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, è necessario installare tutti i componenti di tale prodotto, tra cui:

  - Database operativo

  - Server

  - Console

  - Cmdlet di Windows PowerShell

  - Console Web

  - Reporting

  - Data warehouse

Questi componenti e la relativa installazione non verranno discussi in dettaglio in questo documento. Per informazioni dettagliate su System Center Operations Manager 2007 R2, vedere la documentazione di Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 all'indirizzo e la documentazione di System Center <http://go.microsoft.com/fwlink/p/?linkid=257527>Operations Manager 2012. Seguire queste istruzioni se si intende usare SQL Server 2005 o SQL Server 2008 Service Pack 1 come database back-end.

Se si usa System Center Operations Manager 2012, è possibile usare SQL Server 2012 come database back-end. Per informazioni dettagliate su SQL Server 2012, vedere la documentazione online per SQL Server [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)2012 at.

Tieni presente che puoi avere solo un singolo server di gestione principale per la distribuzione di Lync Server. Anche se è possibile usare System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, non è possibile eseguire contemporaneamente le due applicazioni, ma è necessario sceglierne una o l'altra. Ad esempio, se si esegue System Center Operations Manager 2012, è necessario che tutti gli agenti del centro di sistema eseguano anche System Center Operations Manager 2012. Non è possibile avere alcuni agenti che gestiscono System Center Operations Manager 2012 e altri agenti che utilizzano System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

