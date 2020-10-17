---
title: 'Lync Server 2013: pianificazione per il ripristino di emergenza del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f221947975c00eccefe50cb5ca72b264c9596014
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497753"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Pianificazione del ripristino di emergenza del parcheggio di chiamata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-30_

In questa sezione vengono illustrati alcuni modi per preparare l'applicazione Parcheggio di chiamata per il ripristino di emergenza e alcune considerazioni per il processo di ripristino di emergenza.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparazione per il ripristino di emergenza del parcheggio di chiamata

Quando si preparano e si eseguono le procedure di ripristino di emergenza, tenere presenti gli aspetti seguenti:

  - Pianificare il ripristino di emergenza in fase di pianificazione della capacità. Per la capacità di ripristino di emergenza, ogni pool in un pool associato dovrebbe essere in grado di gestire i carichi di lavoro dei servizi parcheggio di chiamata in entrambi i pool. Per informazioni dettagliate sulla pianificazione della capacità del parcheggio di chiamata, vedere [pianificazione della capacità per il parcheggio di chiamata in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante il ripristino di emergenza gli utenti che sono stati reindirizzati al pool di backup durante il processo di failover, utilizzano il servizio Parcheggio di chiamata nel pool di backup. Pertanto, il supporto per il parcheggio di chiamata durante il ripristino di emergenza richiede che l'applicazione Parcheggio di chiamata venga distribuita e abilitata sia nel pool primario che nel pool di backup.

  - È necessario che tutti i pool dispongano di un intervallo valido di numeri di codici orbit per gli utenti che sono ospitati nel pool da utilizzare per il parcheggio delle chiamate.

  - Mantenere sempre una copia di backup separata di qualsiasi musica personalizzata in attesa che sia stata caricata per il parcheggio di chiamata. Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considerazioni sul ripristino di emergenza del parcheggio di chiamata

È possibile definire un solo set di impostazioni di configurazione dell'applicazione Parcheggio di chiamata e un file audio personalizzato per pool. Queste impostazioni includono la soglia di timeout, la musica in attesa, il numero massimo di tentativi di risposta alle chiamate e l'URI di timeout. Per visualizzare le impostazioni di configurazione, eseguire il cmdlet **Get-CsCpsConfiguration**. Per informazioni dettagliate sul cmdlet **Get-CsCpsConfiguration** , vedere [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante il ripristino di emergenza, il parcheggio di chiamata utilizza l'applicazione Parcheggio di chiamata nel pool di backup, pertanto non è stato eseguito il backup delle impostazioni del pool primario. Se il pool primario non può essere ripristinato e si distribuisce un nuovo pool per sostituire il pool primario, le impostazioni del pool primario vengono perse ed è necessario riconfigurare le impostazioni del parcheggio di chiamata e gli eventuali file audio di musica di attesa personalizzati nel nuovo pool.

Se si distribuisce un nuovo pool con un nome di dominio completo (FQDN) diverso per sostituire il pool primario, è necessario riassegnare tutti gli intervalli di orbit del parcheggio di chiamata che sono stati associati al pool primario all'FQDN del nuovo pool. Per riassegnare gli intervalli di Orbit al nuovo pool, è possibile utilizzare il pannello di controllo di Lync Server o il cmdlet **set-CsCallParkOrbit** . Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

