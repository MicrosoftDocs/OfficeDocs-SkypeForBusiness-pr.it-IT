---
title: 'Lync Server 2013: Pianificazione per il ripristino di emergenza del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a7da940f55574e1c6d50aeb06c0c80710bdbaad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Pianificazione per il ripristino di emergenza del parcheggio di chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-30_

In questa sezione vengono illustrati alcuni modi per preparare l'applicazione Call Park per il ripristino di emergenza e alcune considerazioni per il processo di ripristino di emergenza.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Preparazione per il ripristino di emergenza di Call Park

Quando si preparano e eseguono procedure di ripristino di emergenza, tenere presente quanto segue.

  - Pianificare il ripristino di emergenza quando si esegue la pianificazione della capacità. Per la capacità di ripristino di emergenza, ogni pool in un pool associato deve essere in grado di gestire i carichi di lavoro dei servizi di Call Park in entrambi i pool. Per informazioni dettagliate sulla pianificazione della capacità di parcheggio delle chiamate, vedere [pianificazione della capacità per il parcheggio delle chiamate in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Durante il ripristino di emergenza, gli utenti che sono stati reindirizzati al pool di backup come parte del processo di failover usano il servizio di parcheggio delle chiamate in esecuzione nel pool di backup. Pertanto, il supporto per il parcheggio delle chiamate durante il ripristino di emergenza richiede che l'applicazione Call Park venga distribuita e abilitata sia nel pool principale che nel pool di backup.

  - Ogni pool deve avere un intervallo valido di numeri di orbita per gli utenti residenti in tale pool da usare per le chiamate di parcheggio.

  - Mantenere sempre una copia di backup separata di qualsiasi musica personalizzata in attesa caricata per Call Park. Non è possibile eseguire il backup di questi file come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno perduti se i file caricati nel pool sono danneggiati, danneggiati o eliminati.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Considerazioni sul ripristino di disaster Park di Call

Puoi definire solo un set di impostazioni di configurazione delle applicazioni di Call Park e un file audio in blocco musicale personalizzato per ogni pool. Queste impostazioni includono la soglia di timeout, la musica in attesa, i tentativi di prelievo massimo delle chiamate e l'URI di timeout. Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsCpsConfiguration** . Per informazioni dettagliate sul cmdlet **Get-CsCpsConfiguration** , vedere [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Durante il ripristino di emergenza, Call Park USA l'applicazione Call Park nel pool di backup, quindi non è possibile eseguire il backup delle impostazioni nel pool principale. Se il pool principale non può essere recuperato e si distribuisce un nuovo pool in sostituzione del pool principale, le impostazioni del pool principale andranno perse ed è necessario riconfigurare le impostazioni del parcheggio delle chiamate e i file audio di musica in blocco personalizzati nel nuovo pool.

Se si distribuisce un nuovo pool con un nome di dominio completo diverso (FQDN) per sostituire il pool principale, è necessario riassegnare tutti gli intervalli di orbita del parcheggio di chiamata associati al pool principale al nome di dominio completo del nuovo pool. Per riassegnare gli intervalli orbit al nuovo pool, è possibile usare il pannello di controllo di Lync Server o il cmdlet **set-CsCallParkOrbit** . Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

