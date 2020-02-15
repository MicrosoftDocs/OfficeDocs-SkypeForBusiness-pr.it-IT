---
title: 'Lync Server 2013: configurazione e monitoraggio del servizio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f0fc9d65f1879c453c01813e09ad2ca0e8a99c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configurazione e monitoraggio del servizio di backup in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile utilizzare i seguenti comandi di Lync Server Management Shell per configurare e monitorare il servizio di backup.

<div>


> [!NOTE]  
> RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per eseguire <STRONG>Get-CsBackupServiceStatus</STRONG> per impostazione predefinita. Per utilizzare questo cmdlet, eseguire l'accesso come membro di questo gruppo. In alternativa, è possibile concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, utilizzando il cmdlet <STRONG>Set-CsBackupServiceConfiguration</STRONG>.



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Per visualizzare la configurazione del servizio di backup

Eseguire il seguente cmdlet:

    Get-CsBackupServiceConfiguration

Il valore predefinito per SyncInterval è due minuti.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Per impostare l'intervallo di sincronizzazione del servizio di backup

Eseguire il seguente cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Con il comando seguente ad esempio si imposta l'intervallo su tre minuti.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Benché sia possibile utilizzare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile modificare questo valore a meno che non sia assolutamente necessario, poiché l'intervallo di sincronizzazione ha un effetto significativo sulle prestazioni e sull''obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) del servizio di backup.



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Per ottenere lo stato del servizio di backup per un pool specifico

Eseguire il cmdlet seguente:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> Lo stato di sincronizzazione del servizio di backup è definito in modo unidirezionale da un pool (P1) per il relativo pool di backup (P2). Lo stato di sincronizzazione da P1 a P2 può essere diverso dallo stato di sincronizzazione da P2 a P1. Per la sincronizzazione da P1 a P2, il servizio di backup è in uno stato "stazionario" se tutte le modifiche apportate a P1 vengono interamente replicate in P2 nell'intervallo di sincronizzazione. Lo stato invece è "finale" se non sono presenti ulteriori modifiche da sincronizzare da P1 a P2. Entrambi gli stati indicano uno snapshot del servizio di backup effettuato al momento dell'esecuzione del cmdlet. Questo non implica che lo stato restituito resti invariato successivamente. In particolare, lo stato "finale" rimarrà tale solo se P1 non genera modifiche dopo l'esecuzione del cmdlet. Questo si verifica in caso di failover di P1 a P2 dopo l'attivazione della modalità di sola lettura per P1 come parte della logica di esecuzione di <STRONG>Invoke-CsPoolfailover</STRONG>.



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Per ottenere informazioni sulla relazione di backup per un pool specifico

Eseguire il seguente cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Per forzare una sincronizzazione del servizio di backup

Eseguire il cmdlet seguente:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

