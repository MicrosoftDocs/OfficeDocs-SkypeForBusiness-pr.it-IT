---
title: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer'
description: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005c5ac372a3564e74af549832830ebae899e9d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549932"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Preparazione e installazione di Best Practices Analyzer in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

Per eseguire le attività descritte in questo argomento è necessario accedere con un account membro del gruppo Administrators.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Requisiti di sistema per l'installazione di Best Practices Analyzer

Per eseguire Lync Server 2013, Best Practices Analyzer per analizzare l'ambiente in uso, è necessario che il computer esegua un'edizione a 64 bit di uno dei sistemi operativi seguenti:

  - Sistema operativo Windows Server 2008 R2 con Service Pack 1 (SP1) standard

  - Sistema operativo Windows Server 2008 R2 con SP1 Enterprise

  - Sistema operativo Windows Server 2008 R2 con SP1 Datacenter

  - Sistema operativo Windows Server 2012 Datacenter

  - Sistema operativo Windows Server 2012 standard

  - Sistema operativo Windows Server 2012 Enterprise

  - Sistema operativo Windows Server 2012 R2 Datacenter

  - Sistema operativo Windows Server 2012 R2 Standard

  - Sistema operativo Windows Server 2012 R2 Enterprise

  - Sistema operativo Windows 8

  - Sistema operativo Windows 7

Nel computer deve inoltre essere in esecuzione il software seguente:

  - Microsoft .NET Framework 4.5. Per Lync Server 2013, è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 sul server prima di installare Lync Server 2013.

  - Lync Server 2013, componenti di base.

  - Pacchetto di compatibilità con le versioni precedenti di Strumentazione gestione Windows (WMI). Per ulteriori informazioni, vedere Installare il pacchetto di compatibilità con le [versioni precedenti di WMI](install-wmi-backward-compatibility-package.md) nella documentazione relativa alla migrazione.

  - Windows PowerShell 3.0. Per ulteriori informazioni, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) nella documentazione relativa alla distribuzione.

È possibile installare Best Practices Analyzer nei computer con un sistema operativo supportato che non esegue Lync Server 2013, componenti di base o un pacchetto di compatibilità con le versioni precedenti di WMI, ma è possibile utilizzare Best Practices Analyzer nei computer solo per visualizzare i report, non per eseguire le analisi.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Scelta del computer per l'installazione

È consigliabile installare Lync Server 2013, Best Practices Analyzer su un computer dedicato alla gestione di Lync Server 2013. È possibile installare lo strumento su un server che esegue Lync Server 2013 o un computer amministrativo che esegue gli strumenti di amministrazione di Lync Server 2013. Se si installa lo strumento su un server che esegue Lync Server, è consigliabile utilizzare lo strumento per analizzare solo quel server.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installazione di Best Practices Analyzer

È possibile scaricare l'Analizzatore procedure consigliate per Lync Server 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) .

Per installare Best Practices Analyzer, avviare il file di Microsoft Installer RtcBPA.msi nel computer in cui si vuole installare lo strumento e quindi seguire le istruzioni sullo schermo. Il percorso predefinito per l'installazione dei file di programma è \<system drive\> \\ file di programma \\ Lync Server 2013 \\ BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

