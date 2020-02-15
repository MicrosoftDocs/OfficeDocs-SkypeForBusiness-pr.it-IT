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
ms.openlocfilehash: 7fc2aac99251c0b2e5bc950b3dc11e8e2044b440
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Procedure consigliate per il backup e il ripristino di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

In questa sezione sono descritti due tipi di procedure consigliate:

  - Procedure consigliate per il backup e il ripristino.

  - Procedure consigliate per ridurre al minimo l'impatto di un'emergenza.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Procedure consigliate per il backup e il ripristino

Per semplificare il processo di backup e ripristino, applicare le procedure consigliate riportate di seguito quando si esegue il backup o il ripristino dei dati:

  - Eseguire backup regolari a intervalli appropriati. Il tipo di backup e il piano di rotazione più semplici e comunemente utilizzati corrispondono a un backup notturno completo dell'intero database di SQL Server. Se quindi è necessario il ripristino, il processo di ripristino richiede un solo backup e non devono essere persi più di un giorno.

  - Se si utilizzano i cmdlet o il pannello di controllo di Lync Server per apportare modifiche alla configurazione, utilizzare il cmdlet **Export-CsConfiguration** per eseguire un backup snapshot del file di configurazione della topologia (XDS. MDF) dopo aver apportato le modifiche, in modo che le modifiche non vengano perse se è necessario ripristinare i database. Si noti che la configurazione è stata sottoposta a backup in formato XML e compressa come file ZIP.

  - Verificare che la cartella condivisa che si intende utilizzare per il backup di Lync Server disponga di spazio sufficiente su disco per contenere tutti i dati di cui è stato eseguito il backup.

  - Pianificare i backup quando l'utilizzo di Lync Server è in genere basso, per migliorare le prestazioni del server e l'esperienza utente.

  - Verificare che il percorso in cui si esegue il backup dei dati sia sicuro (si consiglia una posizione remota).

  - Mantenere i file di backup in cui saranno disponibili, nel caso in cui sia necessario ripristinare i dati.

  - Pianificare e pianificare periodici test dei processi di ripristino supportati dall'organizzazione.

  - Convalidare i processi di backup e ripristino in anticipo per assicurarsi che funzionino come previsto.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Procedure consigliate per ridurre al minimo le conseguenze di un'emergenza

La strategia migliore per gestire le interruzioni di servizio disastrose (causate da eventi non gestibili, ad esempio guasti dell'alimentazione o errori hardware improvvisi) è quella di presumere che si verifichino e pianificare di conseguenza.

Se i servizi Lync, con un minimo di disturbo e interruzioni, sono fondamentali per l'organizzazione, è consigliabile implementare pool associati di front end server, come descritto in [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Se uno di questi pool presenta un evento di emergenza, un amministratore può quindi cambiare gli utenti del pool in modo che vengano serviti dall'altro pool, con un minimo di tempo di inattività.

I piani di gestione di emergenza sviluppati nell'ambito della strategia di backup e ripristino dovrebbero includere gli elementi seguenti:

  - Mantenere il supporto software e gli aggiornamenti del software e del firmware facilmente disponibili.

  - Gestione di record dell'hardware e del software.

  - Eseguire regolarmente il backup dei dati e monitorarne l'integrità.

  - Formazione del personale sul ripristino di emergenza e sulla documentazione delle procedure ed esecuzione di esercitazioni di simulazione.

  - Tenere a disposizione l'hardware di scorta o, se si dispone di un contratto di servizio (SLA, Service Level Agreement), stipulare contratti con i fornitori di hardware per richiedere sostituzioni rapide.

  - Luoghi separati per la conservazione dei file di registro delle transazioni (con estensione ldf) e dei file di database (con estensione mdf).

</div>

</div>

<span> </span>

</div>

</div>

</div>

