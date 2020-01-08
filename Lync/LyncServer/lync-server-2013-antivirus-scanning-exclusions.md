---
title: "Lync Server 2013: Esclusioni dall'analisi antivirus"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Esclusioni dall'analisi antivirus per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-11-02_

Per assicurarsi che lo scanner antivirus non interferisca con l'operazione di Lync Server 2013, è necessario escludere processi e directory specifici per ogni ruolo server o server di Lync Server 2013 in cui si esegue uno scanner antivirus. I processi e le directory seguenti devono essere esclusi:

<div>


> [!NOTE]  
> Le posizioni di cartella e file elencate di seguito sono le posizioni predefinite per Lync Server 2013. Per qualsiasi posizione per cui non è stato usato l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.



</div>

<div>


> [!IMPORTANT]  
> Tieni presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.



</div>

  - Processi di Lync Server 2013:
    
      - ABServer. exe
    
      - AcpMcuSvc. exe
    
      - ASMCUSvc. exe
    
      - AVMCUSvc. exe
    
      - ChannelService. exe
    
      - ClsAgent. exe
    
      - ComplianceService. exe
    
      - DataMCUSvc. exe
    
      - Dataproxy. exe
    
      - FileTransferAgent. exe
    
      - IMMCUSvc. exe
    
      - LysSvc. exe
    
      - MasterReplicatorAgent. exe
    
      - MediaRelaySvc. exe
    
      - MediationServerSvc. exe
    
      - MRASSvc. exe
    
      - OcsAppServerHost. exe
    
      - ReplicaReplicatorAgent. exe
    
      - ReplicationApp. exe
    
      - RtcHost. exe
    
      - RTCSrv. exe
    
      - XmppProxy. exe
    
      - XmppTGW. exe

  - Processi del servizio host di Windows Fabric:
    
      - Fabric. exe
    
      - FabricDCA. exe
    
      - FabricHost. exe

  - Processi di IIS:
    
      - % SystemRoot%\\system32\\inetsrv\\w3wp. exe
    
      - % SystemRoot%\\SysWow64\\inetsrv\\w3wp. exe

  - Processi di back-end di SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\contenitori\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\di Reporting\\Services\\ReportServer\\bin ReportingServicesService. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSMDSrv\\.\\exe\\di MSSQLSERVER OLAP bin

  - Processi front-end di SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\contenitori\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\contenitori\\sqlservr. exe

  - Directory e file:
    
      - file di log\\di\\% SystemRoot% system32
    
      - file di log\\di\\SysWow64% SystemRoot%
    
      - % SystemRoot%\\Microsoft.NET\\assembly\\MSIL\_GAC
    
      - % ProgramFiles%\\Microsoft Lync Server 2013
    
      - Nodo di Watcher\\di\\Microsoft Lync Server 2013\\per% programmi% comuni
    
      - % programmi%\\file\\comuni Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - Archivio condivisione file (specificato in Generatore di topologia). Gli archivi di file sono specificati in Generatore di topologia.
    
      - Dati e file di log di SQL Server, inclusi quelli per il database back-end, l'archivio utenti, l'archivio archiviazione, l'archivio di monitoraggio e l'archivio applicazioni. I file di database e di log possono essere specificati in Generatore di topologie. Per informazioni dettagliate sui file di dati e di log per ogni database, inclusi i nomi predefiniti, vedere [dati di SQL Server e il posizionamento dei file di log per Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) nella documentazione relativa alla distribuzione.
    
      - Dati e file di log di SQL Server, inclusi quelli per il database front-end, Lync Store e RtcDatabase Store. In genere sono in% UnitàLocale%\\CSData.

</div>

<span> </span>

</div>

</div>

</div>

