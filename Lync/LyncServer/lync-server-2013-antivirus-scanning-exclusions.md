---
title: 'Lync Server 2013: esclusioni di analisi antivirus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f3e9afc3bd17f5cba4caa7619cb562be069942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Esclusioni di analisi antivirus per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-11-02_

Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Lync Server 2013, è necessario escludere processi e directory specifici per ogni server Lync Server 2013 o ruolo del server in cui si esegue uno scanner antivirus. È necessario escludere le directory e i processi seguenti:

<div>


> [!NOTE]  
> Le posizioni dei file e delle cartelle elencate di seguito sono le posizioni predefinite per Lync Server 2013. Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.



</div>

<div>


> [!IMPORTANT]  
> Tenere presente che alcuni programmi antivirus potrebbero richiedere percorsi assoluti, non relativi, per l'elenco di esclusione.



</div>

  - Lync Server 2013 processi:
    
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

  - Processi del servizio host Windows Fabric:
    
      - Fabric. exe
    
      - FabricDCA. exe
    
      - FabricHost. exe

  - Processi IIS:
    
      - % SystemRoot%\\system32\\inetsrv\\w3wp. exe
    
      - % SystemRoot%\\SysWow64\\inetsrv\\w3wp. exe

  - Processi back-end di SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\contenitori\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\ReportServer\\bin\\ReportingServicesService. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSMDSrv\\.\\exe\\(MSSQLSERVER OLAP bin)

  - Processi front-end di SQL Server:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\contenitori\\sqlservr. exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\contenitori\\sqlservr. exe

  - Directory e file:
    
      - file di log\\di\\% SystemRoot% system32
    
      - file di registro\\%\\SystemRoot% SysWow64
    
      - % SystemRoot%\\Microsoft.NET\\assembly\\MSIL\_GAC
    
      - % ProgramFiles%\\Microsoft Lync Server 2013
    
      - % ProgramFiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher node
    
      - % ProgramFiles%\\file\\comuni Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - Archivio condivisione file (specificato in Generatore di topologie). Gli archivi file sono specificati in Generatore di topologie.
    
      - File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni. I file di registro e di database possono essere specificati in Generatore di topologie. Per informazioni dettagliate sui file di dati e di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and log file Placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) nella documentazione relativa alla distribuzione.
    
      - File di dati e di registro di SQL Server, inclusi quelli per il database front-end, l'archivio Lync e l'archivio di RtcDatabase. Sono in genere in% UnitàLocale%\\CSData.

</div>

<span> </span>

</div>

</div>

</div>

