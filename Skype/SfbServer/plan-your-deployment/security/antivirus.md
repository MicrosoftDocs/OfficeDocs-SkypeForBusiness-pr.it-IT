---
title: Esclusioni di scansione antivirus per Skype for Business Server
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
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Esclusioni di scansione antivirus per Skype for Business Server

Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.

Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni server Skype for Business Server o ruolo del server in cui si esegue uno scanner antivirus. È necessario escludere le directory e i processi seguenti:

> [!NOTE]
> Le posizioni dei file e delle cartelle elencate di seguito sono le posizioni predefinite per Skype for Business Server. Per tutti i percorsi per i quali non è stata utilizzata l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.

> [!IMPORTANT]
> Tenere presente che alcuni programmi antivirus potrebbero richiedere percorsi assoluti, non relativi, per l'elenco di esclusione.

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

  - % SystemRoot% \system32\inetsrv\w3wp.exe

  - % SystemRoot% \SysWOW64\inetsrv\w3wp.exe

- Processi di Back-End di SQL Server:

    > [!NOTE]
    > Tenere presente che questi percorsi sono specifici della versione di SQL Server.

  - %Programmi%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. Services\ReportServer\Bin\ReportingServicesService.exe di MSSQLSERVER\Reporting

  - %Programmi%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- Processi di Front-End di SQL Server:

  - %Programmi%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %Programmi%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Istanza RTC di installazione Standard Edition

  - %Programmi%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Directory e file:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - GAC_MSIL di%systemroot%\Microsoft.NET\assembly\

    > [!NOTE]
    > Si noti che questi percorsi sono specifici della versione di Skype for Business Server.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Skype for Business Server 2015 \ nodo Watcher

  - %programfiles%\Common Skype for Business Server 2015

  - %programfiles%\Common Skype for business online

  - %SystemDrive%\RtcReplicaRoot

  - Archivio condivisione file (specificato in Generatore di topologie). Gli archivi file sono specificati in Generatore di topologie.

  - File di registro e dati di SQL Server, inclusi quelli per il database back-end, l'archivio utente, l'archivio di archiviazione, l'archivio di monitoraggio e l'archivio applicazioni. I file di registro e di database possono essere specificati in Generatore di topologie. Per informazioni dettagliate sui dati e i file di registro per ogni database, inclusi i nomi predefiniti, vedere [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.

  - File di dati e di registro di SQL Server, compresi quelli per il database front-end, l'archivio di Skype for business e l'archivio di RtcDatabase. Sono in genere in%localdrive%\CSData.


