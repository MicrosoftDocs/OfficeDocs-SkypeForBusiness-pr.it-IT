---
title: 'Lync Server 2013: procedure consigliate per il backup e il ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Procedure consigliate per il backup e il ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Questa sezione include due tipi di procedure consigliate:

  - Procedure consigliate per il backup e il ripristino.

  - Procedure consigliate per ridurre al minimo l'impatto di un disastro.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Procedure consigliate per il backup e il ripristino

Per facilitare il processo di backup e ripristino, applicare le procedure consigliate seguenti per eseguire il backup o il ripristino dei dati:

  - Eseguire backup regolari a intervalli appropriati. Il tipo di backup più semplice e più comunemente usato e la pianificazione della rotazione sono un backup completo e notturno dell'intero database di SQL Server. Quindi, se è necessario il ripristino, il processo di ripristino richiede un solo backup e non devono essere persi più dati di un giorno.

  - Se si usano i cmdlet o il pannello di controllo di Lync Server per apportare modifiche alla configurazione, usare il cmdlet **Export-CsConfiguration** per eseguire il backup dello snapshot del file di configurazione della topologia (XDS. MDF) dopo aver apportato le modifiche, in modo da non perdere le modifiche se è necessario ripristinare i database. Tieni presente che questa configurazione viene sottoposta a backup in formato XML e compresso come file ZIP.

  - Verificare che la cartella condivisa che si prevede di usare per il backup di Lync Server disponga di spazio sufficiente per contenere tutti i dati di cui è stato eseguito il backup.

  - Pianificare i backup quando l'utilizzo di Lync Server è in genere basso, per migliorare le prestazioni del server e l'esperienza utente.

  - Verificare che la posizione in cui eseguire il backup dei dati sia sicura (si consiglia una posizione remota).

  - Conservare i file di backup in cui saranno disponibili, in caso sia necessario ripristinare i dati.

  - Pianificare e pianificare i test periodici dei processi di ripristino supportati dall'organizzazione.

  - Convalidare i processi di backup e ripristino in anticipo per assicurarsi che funzionino come previsto.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Procedure consigliate per ridurre al minimo l'impatto di un disastro

La strategia migliore per gestire interruzioni di servizio disastrose (causate da eventi non gestiti, come interruzioni di corrente o errori hardware improvvisi) è presupporre che si verifichino e pianificare di conseguenza.

Se i servizi Lync, con un minimo di interruzioni e interruzione, sono critici per le aziende per l'organizzazione, è consigliabile implementare i pool associati di server front-end, come descritto in [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Quindi, se uno di questi pool ha un disastro, un amministratore può cambiare gli utenti di tale pool per essere serviti dall'altro pool, con un minimo di tempo di inattività.

I piani di gestione dei disastri sviluppati nell'ambito della strategia di backup e ripristino devono includere i seguenti:

  - Mantenere i contenuti multimediali del software e gli aggiornamenti del software e del firmware, facilmente disponibili.

  - Manutenzione dei record hardware e software.

  - Eseguire il backup regolare dei dati e monitorare l'integrità dei backup.

  - Formazione del personale nel ripristino di emergenza, documentazione delle procedure e implementazione delle esercitazioni di simulazione per il ripristino di emergenza.

  - Mantenere disponibile l'hardware di ricambio oppure, se si ha un contratto di servizio (SLA, Service Level Agreement), contraendo fornitori e fornitori di hardware per le sostituzioni rapide.

  - Separare la posizione dei file di log delle transazioni (file con estensione ldf) e i file di database (file con estensione MDF).

</div>

</div>

<span> </span>

</div>

</div>

</div>

