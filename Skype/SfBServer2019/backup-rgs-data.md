---
title: Backup dei dati RGS (Response Group Service) in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Informazioni su come eseguire il backup dei dati di Response Group Service (RGS) in Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824070"
---
# <a name="back-up-response-group-service-rgs-data"></a>Eseguire il backup dei dati di Response Group Service (RGS)

Con l'aggiornamento cumulativo di Skype for Business Server 2019 luglio è stata inclusa la possibilità di includere i dati RGS come parte del backup standard.

## <a name="rgs-data-replication"></a>Replica dati RGS

Per provare la funzionalità di replica dei dati RGS, eseguire la procedura seguente:

1. Installare l'aggiornamento cumulativo di luglio in tutti i front-end (FEs) del pool associato.
1. Installare il database RGS in entrambi i membri del pool associato:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Eseguire il cmdlet seguente in entrambi i pool per replicare i dati RGS esistenti nelle tabelle di backup in modo che i dati possano essere raccolti da RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Abilita RGSBackupService (questo consentirà a RGSBackupService globalmente. Se questo parametro è impostato su true, RGSBackupService inizierà a sincronizzare i dati RGS nei pool associati (entrambi i pool devono essere CU1). Attendere alcuni minuti per iniziare. Inizialmente, lo stato di RGS BackupService sarà NotInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Per controllare BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Per controllare la replica tramite i pool, usare questi cmdlet (questi cmdlet mostrano solo i dati del pool di proprietari):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Per controllare i dati del pool di proprietari RGS e i relativi dati di backup:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio al flusso di lavoro.
1. Failover del pool di proprietari RGS.
1. Verificare la funzionalità del flusso di lavoro effettuando una chiamata audio al flusso di lavoro.
1. Failback del pool.
1. Aggiornare i dati RGS nel pool di origine ed eseguire un altro failover per verificare che le modifiche vengano applicate al pool di backup. RGS deve comportarsi allo stesso modo in cui si comporta prima del failover.

> [!TIP]
> È consigliabile eseguire questi passaggi su un blocco di dati e eseguire frequenti operazioni di failover e failbacks. Qualsiasi nuovo RGS creato dopo l'aggiornamento di CU deve essere replicato.

## <a name="rgs-cmdlets"></a>Cmdlet RGS

- Per controllare BackupServiceStatus (lo stato di esportazione deve essere nello stato finale o stabile. Lo stato di importazione deve essere nello stato Normal. RGSBackupservice deve essere abilitato.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Per sincronizzare completamente i dati RGS nel pool di backup (verranno sincronizzati i dati completi di RGS nel pool di backup.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Per sincronizzare completamente il FileStore RGS nel pool di backup (verranno sincronizzati i dati completi di RGS nel pool di backup.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Per sincronizzare i dati Delta di RGS nel pool di backup (verranno sincronizzati solo i dati Delta nel pool di backup per RGS.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Per sincronizzare tutti i dati del modulo, tra cui RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Per disabilitare RGSBackupService (verrà disabilitato RGSBackupService globalmente. Se questo parametro è impostato su true, RGSBackupService verrà disabilitato in tutti i pool associati.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
