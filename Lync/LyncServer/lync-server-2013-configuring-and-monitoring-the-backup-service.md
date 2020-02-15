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

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="33748-102">Configurazione e monitoraggio del servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33748-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33748-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="33748-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="33748-104">È possibile utilizzare i seguenti comandi di Lync Server Management Shell per configurare e monitorare il servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="33748-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33748-105">RTCUniversalServerAdmins è l'unico gruppo che dispone delle autorizzazioni per eseguire <STRONG>Get-CsBackupServiceStatus</STRONG> per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="33748-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="33748-106">Per utilizzare questo cmdlet, eseguire l'accesso come membro di questo gruppo.</span><span class="sxs-lookup"><span data-stu-id="33748-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="33748-107">In alternativa, è possibile concedere l'accesso a questo comando ad altri gruppi, ad esempio CSAdministrator, utilizzando il cmdlet <STRONG>Set-CsBackupServiceConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="33748-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="33748-108">Per visualizzare la configurazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="33748-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="33748-109">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33748-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="33748-110">Il valore predefinito per SyncInterval è due minuti.</span><span class="sxs-lookup"><span data-stu-id="33748-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="33748-111">Per impostare l'intervallo di sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="33748-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="33748-112">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33748-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="33748-113">Con il comando seguente ad esempio si imposta l'intervallo su tre minuti.</span><span class="sxs-lookup"><span data-stu-id="33748-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="33748-114">Benché sia possibile utilizzare questo cmdlet per modificare l'intervallo di sincronizzazione predefinito per il servizio di backup, non è consigliabile modificare questo valore a meno che non sia assolutamente necessario, poiché l'intervallo di sincronizzazione ha un effetto significativo sulle prestazioni e sull''obiettivo in termini di punto di ripristino (RPO, Recovery Point Objective) del servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="33748-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="33748-115">Per ottenere lo stato del servizio di backup per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="33748-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="33748-116">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="33748-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="33748-117">Lo stato di sincronizzazione del servizio di backup è definito in modo unidirezionale da un pool (P1) per il relativo pool di backup (P2).</span><span class="sxs-lookup"><span data-stu-id="33748-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="33748-118">Lo stato di sincronizzazione da P1 a P2 può essere diverso dallo stato di sincronizzazione da P2 a P1.</span><span class="sxs-lookup"><span data-stu-id="33748-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="33748-119">Per la sincronizzazione da P1 a P2, il servizio di backup è in uno stato "stazionario" se tutte le modifiche apportate a P1 vengono interamente replicate in P2 nell'intervallo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="33748-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="33748-120">Lo stato invece è "finale" se non sono presenti ulteriori modifiche da sincronizzare da P1 a P2.</span><span class="sxs-lookup"><span data-stu-id="33748-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="33748-121">Entrambi gli stati indicano uno snapshot del servizio di backup effettuato al momento dell'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33748-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="33748-122">Questo non implica che lo stato restituito resti invariato successivamente.</span><span class="sxs-lookup"><span data-stu-id="33748-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="33748-123">In particolare, lo stato "finale" rimarrà tale solo se P1 non genera modifiche dopo l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33748-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="33748-124">Questo si verifica in caso di failover di P1 a P2 dopo l'attivazione della modalità di sola lettura per P1 come parte della logica di esecuzione di <STRONG>Invoke-CsPoolfailover</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="33748-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="33748-125">Per ottenere informazioni sulla relazione di backup per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="33748-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="33748-126">Eseguire il seguente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="33748-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="33748-127">Per forzare una sincronizzazione del servizio di backup</span><span class="sxs-lookup"><span data-stu-id="33748-127">To force a Backup Service sync</span></span>

<span data-ttu-id="33748-128">Eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="33748-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

