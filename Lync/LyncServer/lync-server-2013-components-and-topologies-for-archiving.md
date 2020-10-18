---
title: "Lync Server 2013: componenti e topologie per l'archiviazione"
description: "Lync Server 2013: componenti e topologie per l'archiviazione."
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
ms.openlocfilehash: f6ccb62993dc6a8dbc098d4a9c5f28b9b3f7fac9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576922"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a>Componenti e topologie per l'archiviazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

Se si desidera archiviare i contenuti di messaggistica istantanea e di conferenza di Lync Server 2013, è possibile implementare l'archiviazione in Lync Server.

<div>

## <a name="archiving-components"></a>Componenti di archiviazione

La funzionalità di archiviazione include i componenti seguenti:

  - **Agenti di archiviazione**. Gli agenti di archiviazione, noti anche come agenti di raccolta dati unificata, vengono installati e attivati automaticamente in ogni pool Front End e in ogni server Standard Edition. Anche se gli agenti di archiviazione vengono attivati automaticamente, l'acquisizione dei messaggi inizia solo dopo che l'archiviazione è stata abilitata e configurata in modo appropriato.

  - **Archivio dati di archiviazione**. L'archiviazione dei dati per Lync Server 2013 può essere una delle seguenti:
    
      - Archiviazione di Exchange 2013. Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate sul server Exchange 2013 utilizzano lo spazio di archiviazione di Exchange 2013 per i dati archiviati, ma solo se le cassette postali sono state inserite In-Place blocco.
    
      - Archiviazione di SQL Server. Se nella distribuzione sono presenti utenti che si trovano in Lync Server 2013, è possibile configurare i database di archiviazione che eseguono una versione supportata di SQL Server per abilitare l'archiviazione per tali utenti.

L'archiviazione richiede anche un archivio file, ma usa lo stesso archivio file dei Front End Server o del server Standard Edition.

Per un elenco dei requisiti hardware e software per l'archiviazione, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto dell'infrastruttura e del software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

È necessario distribuire la funzionalità di archiviazione in ogni pool in cui si trovano utenti che richiedono il supporto dell'archiviazione. L'archiviazione viene eseguita nei Front End Server nei pool Enterprise Edition e nei server Standard Edition. L'archivio dati di archiviazione può essere:

  - Integrazione con l'archiviazione di Exchange 2013

  - Distribuiti tramite database di SQL Server distinti

Se la distribuzione di Exchange 2013 non include tutti gli utenti nella distribuzione di Lync Server, è necessario utilizzare l'integrazione di Microsoft Exchange per gli utenti le cui cassette postali sono ospitate nei server Exchange 2013 ed è necessario distribuire database SQL Server distinti per tutti gli altri utenti di Lync da utilizzare per l'archiviazione.

</div>

<div>

## <a name="supported-collocation"></a>Collocazione supportata

Lync Server 2013 supporta diversi scenari di collocazione, consentendo la flessibilità per il salvataggio dei costi hardware eseguendo più componenti in un server (se si dispone di un'organizzazione di piccole dimensioni) o per eseguire singoli componenti in server diversi (se si dispone di un'organizzazione di dimensioni superiori che richiede scalabilità e prestazioni). Prima di decidere se collocare i componenti, è sicuramente importante considerare i fattori di scalabilità.

L'archiviazione viene distribuita nei front end server di un pool o di server Standard Edition. Per informazioni dettagliate sui componenti che possono essere collocati in tale posizione, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

Se si utilizzano database di SQL Server distinti per l'archiviazione, anziché o oltre all'integrazione dell'archiviazione con l'archiviazione di Exchange 2013, è possibile collocare il database di archiviazione con uno dei seguenti elementi:

  - Database di monitoraggio

  - Database back-end di un pool Enterprise Edition Front End

<div>


> [!NOTE]  
> Il server che ospita il database di archiviazione può ospitare altri database. Se, tuttavia, si desidera collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo non è consigliabile collocare il database di archiviazione con il database back-end.



</div>

Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza SQL per uno o per tutti i database o, in alternativa, usare un'istanza SQL separata per ogni database, con la limitazione seguente:

  - Ogni istanza SQL può contenere un singolo database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.

Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.

</div>

</div>

<span> </span>

</div>

</div>

</div>

