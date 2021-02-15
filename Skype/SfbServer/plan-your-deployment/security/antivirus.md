---
title: Esclusioni dell'analisi antivirus per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832266"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Esclusioni dell'analisi antivirus per Skype for Business Server

Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.

Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni server o ruolo del server di Skype for Business Server in cui si esegue uno scanner antivirus. È necessario escludere le directory e i processi seguenti:

> [!NOTE]
> Le cartelle e i percorsi dei file elencati di seguito sono i percorsi predefiniti per Skype for Business Server. Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.

> [!IMPORTANT]
> Tenere presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.

- Processi di Skype for Business Server:

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

  - LysSvc.exe

  - MasterReplicatorAgent.exe

  - MediaRelaySvc.exe

  - MediationServerSvc.exe

  - MRASSvc.exe

  - OcsAppServerHost.exe

  - ReplicaReplicatorAgent.exe

  - ReplicationApp.exe

  - RtcHost.exe

  - RTCSrv.exe

  - XmppProxy.exe

  - XmppTGW.exe

- Processi del servizio host Windows Fabric:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Processi IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End processi seguenti:

    > [!NOTE]
    > Si noti che questi percorsi sono specifici della SQL Server versione.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End processi seguenti:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Istanza RTC di installazione Standard Edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Directory e file:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Si noti che questi percorsi sono specifici della versione di Skype for Business Server.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Archivio condivisione file (specificato in Generatore di topologie). Gli archivi file sono specificati in Generatore di topologie.

  - File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni. I file di registro e di database possono essere specificati in Generatore di topologie. Per informazioni dettagliate sui dati e i file di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.

  - SQL Server file di dati e di registro, inclusi quelli per il database front-end, l'archivio Skype for Business e l'archivio RtcDatabase. In genere sono in %localdrive%\CSData.


