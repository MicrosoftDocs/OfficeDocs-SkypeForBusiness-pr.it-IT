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
ms.openlocfilehash: 18ec967418effe53399070bc8e6f414cd2d927cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configurazione del server di gestione principale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-19_

Per sfruttare al meglio le nuove funzionalità di monitoraggio dell'integrità incluse negli amministratori di Microsoft Lync Server 2013, è necessario prima di tutto designare un computer che funga da server di gestione principale. in quel computer è necessario installare System Center Operations Manager 2007 R2 o System Center Operations Manager 2012. Inoltre, è necessario installare una versione supportata di SQL Server per funzionare come database back-end di Operations Manager. Se si utilizza System Center Operations Manager 2012, è possibile utilizzare una delle seguenti versioni di SQL Server come database back-end:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Se si utilizza System Center Operations Manager 2007 R2, è consigliabile installare SQL Server 2005 Service Pack 4 o SQL Server 2008 Service Pack 3. È inoltre possibile utilizzare SQL Server 2008 R2 come database back-end per System Center Operations Manager 2007 R2. Vedere l'appendice 1 di questa documentazione per ulteriori informazioni sulla configurazione di SQL Server 2008 R2 per l'utilizzo con System Center Operations Manager 2007 R2.

Quando si installa System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, è necessario installare tutti i componenti del prodotto, tra cui:

  - Database operativo

  - Server

  - Console

  - Cmdlet di Windows PowerShell

  - Console Web

  - Reporting

  - Data warehouse

Questi componenti e la relativa installazione non verranno esaminati in dettaglio in questo documento. Per informazioni dettagliate su System Center Operations Manager 2007 R2, vedere la documentazione di Operations Manager 2007 <https://go.microsoft.com/fwlink/p/?linkid=257526> R2 all'indirizzo e la documentazione di System Center <https://go.microsoft.com/fwlink/p/?linkid=257527>Operations Manager 2012 all'indirizzo. Se si intende utilizzare SQL Server 2005 o SQL Server 2008 Service Pack 1 come database back-end, è consigliabile attenersi alle istruzioni riportate di seguito.

Se si utilizza System Center Operations Manager 2012, è possibile utilizzare SQL Server 2012 come database back-end. Per informazioni dettagliate su SQL Server 2012, vedere la documentazione online per SQL Server [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)2012 all'indirizzo.

Tenere presente che è possibile disporre di un solo server di gestione primario per la distribuzione di Lync Server. Inoltre, sebbene sia possibile utilizzare System Center Operations Manager 2012 o System Center Operations Manager 2007 R2, non è possibile eseguire contemporaneamente le due applicazioni: è necessario sceglierne una o un'altra. Ad esempio, se si esegue System Center Operations Manager 2012, tutti gli agenti del System Center devono anche eseguire System Center Operations Manager 2012. Non è possibile disporre di alcuni agenti che eseguono System Center Operations Manager 2012 e altri agenti che eseguono System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

