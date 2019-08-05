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
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194897"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Esclusioni di scansione antivirus per Skype for Business Server

Panoramica dell'interoperabilità dello scanner antivirus con Skype for Business Server.

Questo articolo contiene raccomandazioni che possono aiutare un amministratore a determinare la causa di un'instabilità potenziale in un computer che sta usando una versione supportata di Microsoft Windows quando viene usata con il software antivirus in un dominio Active Directory ambiente o in un ambiente aziendale gestito.

Ti consigliamo di applicare temporaneamente queste procedure per valutare un sistema. Se le prestazioni del sistema o la stabilità sono migliorate dalle raccomandazioni apportate in questo articolo, contattare il fornitore del software antivirus per istruzioni o per una versione aggiornata del software antivirus.

Questo articolo contiene informazioni che illustrano come semplificare la riduzione delle impostazioni di sicurezza o come disattivare temporaneamente le caratteristiche di sicurezza in un computer. È possibile apportare queste modifiche per comprendere la natura di un problema specifico. Prima di apportare queste modifiche, è consigliabile valutare i rischi associati all'implementazione di questa soluzione alternativa nell'ambiente specifico. Se si implementa questa soluzione alternativa, eseguire qualsiasi procedura complementare appropriata per proteggere il computer per i file che non vengono più analizzati dal software antivirus.

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

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

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


