---
title: Esclusioni di scansione antivirus per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074628"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Esclusioni di scansione antivirus per Skype for Business Server

Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.

Per assicurarsi che lo scanner antivirus non interferisca con il funzionamento di Skype for Business Server, è necessario escludere processi e directory specifici per ogni ruolo server o server Skype for Business Server in cui si esegue uno scanner antivirus. I processi e le directory seguenti devono essere esclusi:

> [!NOTE]
> Le posizioni di cartella e file elencate di seguito sono le posizioni predefinite per Skype for Business Server. Per qualsiasi posizione per cui non è stato usato l'impostazione predefinita, escludere i percorsi specificati per l'organizzazione anziché i percorsi predefiniti specificati in questo argomento.

> [!IMPORTANT]
> Tieni presente che alcuni programmi antivirus potrebbero avere bisogno di percorsi assoluti, non relativi, per l'elenco di esclusione.

- Processi di Skype for Business Server:

  - ABServer. exe

  - ASMCUSvc. exe

  - AVMCUSvc. exe

  - ChannelService. exe

  - ClsAgent. exe

  - ComplianceService. exe

  - DataMCUSvc. exe

  - Dataproxy. exe

  - FileTransferAgent. exe

  - HealthAgent. exe

  - IMMCUSvc. exe
  
  - LyncBackupService. exe

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

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- Processi di back-end di SQL Server:

    > [!NOTE]
    > Tieni presente che questi percorsi sono specifici della versione di SQL Server.

  - %Programmi%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %Programmi%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %Programmi%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- Processi front-end di SQL Server:

  - %Programmi%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %Programmi%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Istanza RTC di installazione di Standard Edition

  - %Programmi%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe

- Directory e file:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - GAC_MSIL%systemroot%\Microsoft.NET\assembly\

    > [!NOTE]
    > Tieni presente che questi percorsi sono specifici della versione di Skype for Business Server.

  - %programfiles%\Skype for Business Server 2015

  - Nodo%programfiles%\Common Skype for Business Server 2015 \ Watcher

  - %programfiles%\Common Skype for Business Server 2015

  - %programfiles%\Common Skype for business online

  - %SystemDrive%\RtcReplicaRoot

  - Archivio condivisione file (specificato in Generatore di topologia). Gli archivi di file sono specificati in Generatore di topologia.

  - Dati e file di log di SQL Server, inclusi quelli per il database back-end, l'archivio utenti, l'archivio archiviazione, l'archivio di monitoraggio e l'archivio applicazioni. I file di database e di log possono essere specificati in Generatore di topologie. Per informazioni dettagliate sui file di dati e di log per ogni database, inclusi i nomi predefiniti, vedere [dati di SQL Server e registrazione dei file](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) nella documentazione relativa alla distribuzione.

  - Dati e file di log di SQL Server, inclusi quelli per il database front-end, Skype for Business Store e RtcDatabase Store. In genere sono in%localdrive%\CSData.


