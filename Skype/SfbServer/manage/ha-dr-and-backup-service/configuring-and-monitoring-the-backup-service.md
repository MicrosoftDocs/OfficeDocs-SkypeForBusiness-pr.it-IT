---
title: Configurazione e monitoraggio del servizio di backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puoi usare i comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup.
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195535"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurazione e monitoraggio del servizio di backup in Skype for Business Server

Puoi usare i seguenti comandi di Skype for Business Server Management Shell per configurare e monitorare il servizio di backup. Per ripristinare le informazioni sulla conferenza archiviate nell'archivio di un pool di front-end, vedere [ripristinare il contenuto della conferenza tramite il servizio di backup](#restore-conference-contents-using-the-backup-service), di seguito.

> [!NOTE]  
> Il gruppo RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per l'esecuzione di **Get-CsBackupServiceStatus** per impostazione predefinita. Per usare questo cmdlet, accedere come membro di questo gruppo. In alternativa, puoi concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, usando il cmdlet **set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Per visualizzare la configurazione del servizio di backup

Eseguire il cmdlet seguente:

    Get-CsBackupServiceConfiguration

L'impostazione predefinita per SyncInterval è due minuti.

## <a name="to-set-the-backup-service-sync-interval"></a>Per impostare l'intervallo di sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Ad esempio, il seguente imposta l'intervallo su tre minuti.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Anche se è possibile usare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile farlo, a meno che non sia assolutamente necessario, dato che l'intervallo di sincronizzazione ha un impatto notevole sulle prestazioni del servizio di backup e sull'obiettivo del punto di ripristino (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Per ottenere lo stato del servizio di backup per un determinato pool

Eseguire il cmdlet seguente:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> Lo stato di sincronizzazione del servizio di backup è definito in maniera unidirezionale da un pool (P1) al relativo pool di backup (P2). Lo stato di sincronizzazione da P1 a P2 può essere diverso da quello da P2 a P1. Per P1-P2, il servizio di backup si trova in uno stato "costante" se tutte le modifiche apportate in P1 vengono completamente replicate in P2 nell'intervallo di sincronizzazione. Si trova nello stato "Final" se non ci sono più modifiche da sincronizzare da P1 a P2. Entrambi gli Stati indicano uno snapshot del servizio di backup al momento dell'esecuzione del cmdlet. Non implica che lo stato restituito rimarrà come in seguito. In particolare, lo stato "finale" continuerà a contenere solo se P1 non genera alcuna modifica dopo l'esecuzione del cmdlet. Questo vale in caso di mancanza di P1 oltre a P2 dopo che P1 viene inserito nella modalità di sola lettura come parte della logica di esecuzione **Invoke-CsPoolFailOver** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Per ottenere informazioni sulla relazione di backup per un determinato pool

Eseguire il cmdlet seguente:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Per forzare una sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Ripristinare il contenuto della conferenza tramite il servizio di backup 

Se le informazioni sulla conferenza archiviate nell'archivio di file di un pool Front-end diventano non disponibili, è necessario ripristinare queste informazioni in modo che gli utenti ospitati nel pool mantengono i dati della conferenza. Se il pool Front-end che ha perso i dati della conferenza è associato a un altro pool Front-End, è possibile usare il servizio di backup per ripristinare i dati.

È necessario eseguire questa operazione anche se un intero pool non è riuscito e non è necessario superare gli utenti in un pool di backup. Quando questi utenti non vengono riattivati nel pool originale, è necessario usare questa procedura per copiare il contenuto della conferenza anche di nuovo nel pool originale.

Supponiamo che pool1 sia associato a Pool2 e che i dati della conferenza in pool1 vengano persi. Puoi usare il cmdlet seguente per richiamare il servizio di backup per ripristinare il contenuto:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il ripristino del contenuto della conferenza può richiedere del tempo, a seconda delle dimensioni. Puoi usare il cmdlet seguente per controllare lo stato del processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Il processo viene eseguito quando questo cmdlet restituisce il valore di stato costante per il modulo conferenza dati.
