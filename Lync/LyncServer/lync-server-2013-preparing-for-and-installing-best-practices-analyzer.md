---
title: 'Lync Server 2013: preparazione e installazione di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58d1d2f86b579bfb0259c8ad3e4b26b051b47a8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a>Preparazione e installazione di Best Practices Analyzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Per eseguire le attività descritte in questo argomento, è necessario avere effettuato l'accesso come membro del gruppo Administrators.

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a>Requisiti di sistema per l'installazione di Best Practices Analyzer

Per eseguire Lync Server 2013, Best Practices Analyzer per analizzare l'ambiente, è necessario che il computer esegua una versione a 64 bit di uno dei sistemi operativi seguenti:

  - Windows Server 2008 R2 con il sistema operativo standard Service Pack 1 (SP1)

  - Sistema operativo Windows Server 2008 R2 con SP1 Enterprise

  - Sistema operativo Windows Server 2008 R2 con SP1 Datacenter

  - Sistema operativo Windows Server 2012 Datacenter

  - Sistema operativo standard di Windows Server 2012

  - Sistema operativo Windows Server 2012 Enterprise

  - Sistema operativo Windows Server 2012 R2 Datacenter

  - Sistema operativo Windows Server 2012 R2 Standard

  - Sistema operativo Windows Server 2012 R2 Enterprise

  - Sistema operativo Windows 8

  - Sistema operativo Windows 7

Il computer deve eseguire anche le operazioni seguenti:

  - Microsoft .NET Framework 4,5. Per Lync Server 2013 è necessario installare manualmente l'edizione a 64 bit di Microsoft .NET Framework 4,5 nel server prima di installare Lync Server 2013.

  - Lync Server 2013, componenti principali.

  - Pacchetto compatibilità con le versioni precedenti di WMI. Per informazioni dettagliate, vedere [installare il pacchetto compatibilità con le versioni precedenti di WMI](install-wmi-backward-compatibility-package.md) nella documentazione relativa alla migrazione.

  - Windows PowerShell 3,0. Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) nella documentazione relativa alla distribuzione.

È possibile installare Best Practices Analyzer nei computer con un sistema operativo supportato che non esegue Lync Server 2013, componenti principali o un pacchetto di compatibilità con le versioni precedenti di WMI, ma è possibile usare le procedure consigliate in questi computer solo per visualizzare i report e non per eseguire le analisi.

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a>Scelta di un computer per l'installazione

È consigliabile installare Lync Server 2013, Best Practices Analyzer in un computer dedicato a Lync Server 2013 Management. È possibile installare lo strumento in un server che utilizza Lync Server 2013 o un computer amministrativo che gestisce gli strumenti di amministrazione di Lync Server 2013. Se si installa lo strumento in un server che esegue Lync Server, è consigliabile usare lo strumento per analizzare solo il server.

</div>

<div>

## <a name="installing-best-practices-analyzer"></a>Installazione di Best Practices Analyzer

È possibile scaricare l'analizzatore delle procedure consigliate per Lync [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)Server 2013.

Per installare Best Practices Analyzer, avviare il file di Microsoft Installer RtcBPA. msi nel computer in cui si vuole installare lo strumento e quindi seguire le istruzioni visualizzate. Il percorso predefinito per l'installazione dei file di \<programma è\>\\System Drive\\Program Files Lync\\Server 2013 BPA.

</div>

</div>

<span> </span>

</div>

</div>

</div>

