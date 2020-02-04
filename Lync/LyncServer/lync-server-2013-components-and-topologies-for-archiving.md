---
title: "Lync Server 2013: Componenti e topologie per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componenti e topologie per l'archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

Se si vuole archiviare il contenuto di messaggistica istantanea e di conferenza di Lync Server 2013, è possibile implementare l'archiviazione in Lync Server.

<div>

## <a name="archiving-components"></a>Archiviazione di componenti

La caratteristica archiviazione include i componenti seguenti:

  - **Agenti di archiviazione**. Gli agenti di archiviazione (noti anche come agenti di raccolta dati unificati) vengono installati e attivati automaticamente in tutti i pool Front-end e nel server Standard Edition. Anche se gli agenti di archiviazione vengono attivati automaticamente, nessun messaggio viene effettivamente acquisito finché l'archiviazione non viene abilitata e configurata in modo appropriato.

  - Archiviazione **dei dati archiviati**. L'archiviazione dei dati per Lync Server 2013 può essere una delle opzioni seguenti:
    
      - Archiviazione di Exchange 2013. Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate nel server di Exchange 2013 usano lo spazio di archiviazione di Exchange 2013 per i dati archiviati, ma solo se le cassette postali sono state messe sul posto.
    
      - Archiviazione di SQL Server. Se si hanno utenti nella distribuzione ospitati in Lync Server 2013, è possibile configurare i database di archiviazione che eseguono una versione supportata di SQL Server per consentire l'archiviazione per tali utenti.

L'archiviazione richiede anche l'archiviazione dei file, ma l'archiviazione usa lo stesso spazio di archiviazione dei file del front end server o del server Standard Edition.

Per un elenco dei requisiti hardware e software per l'archiviazione, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto per software e infrastruttura server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

Si distribuisce l'archiviazione in ogni pool che include utenti che richiedono il supporto dell'archiviazione. L'archiviazione viene eseguita nei server front-end nei pool Enterprise Edition e nei server Standard Edition. L'archiviazione dei dati di archiviazione può essere la seguente:

  - Integrazione con lo spazio di archiviazione di Exchange 2013

  - Distribuiti tramite database di SQL Server distinti

Se la distribuzione di Exchange 2013 non include tutti gli utenti nella distribuzione di Lync Server, è necessario usare l'integrazione di Microsoft Exchange per gli utenti le cui cassette postali sono presenti nei server di Exchange 2013 ed è necessario distribuire database di SQL Server distinti per tutti gli altri Utenti di Lync da usare per l'archiviazione.

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Lync Server 2013 supporta diversi scenari di collocazione, consentendo la flessibilità per il salvataggio dei costi hardware eseguendo più componenti in un server (se si ha una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si ha un numero maggiore organizzazione che richiede scalabilità e prestazioni). I fattori di scalabilità dovrebbero certamente essere presi in considerazione prima di decidere se collocare i componenti.

L'archiviazione viene distribuita nei server front-end di un pool o di server Standard Edition. Per informazioni dettagliate sui componenti che possono essere collocati in questa posizione, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Se si usano database di SQL Server distinti per l'archiviazione, anziché o oltre ad integrare lo spazio di archiviazione con lo spazio di archiviazione di Exchange 2013, è possibile collocare il database di archiviazione con uno degli elementi seguenti:

  - Database di monitoraggio

  - Database back-end di un pool di front-end Enterprise Edition

<div>


> [!NOTE]  
> Il server che ospita il database di archiviazione può ospitare altri database. Tuttavia, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può essere molto elevato. Per questo motivo, non è consigliabile collocare il database di archiviazione con il database back-end.



</div>

Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza di SQL per uno o tutti i database oppure è possibile usare un'istanza SQL separata per ogni database, con le operazioni seguenti limitazione

  - Ogni istanza di SQL può contenere solo un database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.

Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

