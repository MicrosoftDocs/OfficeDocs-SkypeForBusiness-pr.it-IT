---
title: 'Lync Server 2013: monitoraggio dei file di registro di traccia delle richieste IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eb64fe83eb6f80c6470ba4173bcc968d44fb54a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Monitoraggio dei file di registro di traccia delle richieste IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Quando si Abilita l'analisi delle richieste di Internet Information Services (IIS) per il servizio per dispositivi mobili di Lync Server (MCX), i file di registro generati possono utilizzare fino a tre gigabyte di spazio su disco al giorno. La registrazione della traccia IIS è abilitata per impostazione predefinita. È necessario monitorare i Front End Server per assicurarsi che non si esaurisca lo spazio su disco.

Per impostazione predefinita, i file di registro vengono archiviati in%\\SystemDrive\\%\\Inetpub logs.

Per disattivare la traccia delle richieste di IIS per un intero server, digitare il comando seguente alla riga di comando:

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

Per informazioni dettagliate sul comando **HttpLogging** , vedere [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927).

</div>

<span> </span>

</div>

</div>

</div>

