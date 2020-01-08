---
title: 'Lync Server 2013: procedure consigliate per gli ambienti Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00dbbf95990875b8366ce5a03f1d2d70e6652828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-lync-server-2013-environments"></a>Procedure consigliate per gli ambienti di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-04_

I principi generali seguenti devono essere applicati alle operazioni in corso del sistema:

  - **Comprendere e utilizzare MOF**   MOF è una raccolta di procedure consigliate, principi e modelli che offrono alle organizzazioni indicazioni tecniche sulla gestione degli asset IT, ad esempio le operazioni quotidiane di Lync Server 2013. Le linee guida MOF seguenti consentono di raggiungere l'affidabilità, la disponibilità, la supportabilità e la gestibilità del sistema di produzione mission-critical per i prodotti Microsoft. Per altre informazioni, vedere [Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939).

  - **Informazioni sulle procedure consigliate per Lync Server 2013**   è consigliabile implementare una procedura pratica e collaudata per la gestione di Lync Server 2013. L'uso di metodi provati, testati e documentati per la gestione delle operazioni può essere più efficiente rispetto allo sviluppo di metodi personalizzati.

  - **Le operazioni separate in processi giornalieri, settimanali e mensili**   documentano le attività operative necessarie che verrà eseguita regolarmente. La documentazione su come eseguire le attività consente di verificare che le informazioni vengano mantenute quando si verifica un cambiamento nell'ambiente operativo, ad esempio quando vengono distribuite nuove tecnologie o si presentano modifiche del personale. È consigliabile separare le attività operative in carichi di lavoro gestibili in cui le attività vengono eseguite giornalmente, settimanalmente e mensilmente. Le attività quotidiane consentiranno di concentrare gli sforzi sul funzionamento di un sistema e le attività mensili consentiranno di garantire l'integrità a lungo termine di un sistema.
    
    Questo documento può essere usato in ambienti che distribuiscono solo componenti di messaggistica istantanea/presenza (IM/P) o messaggistica istantanea/P con VoIP aziendale. Quando le attività o gli elementi di elenco di controllo sono specifici di Enterprise Voice, viene menzionato e se l'ambiente in cui l'utente non include VoIP aziendale la parte può essere ignorata.

  - **Distribuire gli strumenti necessari per il funzionamento di Lync Server 2013**   sono disponibili molti strumenti per la risoluzione dei problemi, l'automatizzazione delle attività e la guida e il monitoraggio e la gestione dell'ambiente Lync Server 2013. Definire un set standard di strumenti per l'organizzazione in modo che le attività eseguite dal team operativo vengano eseguite in modo accurato, efficiente, coerente e controllato. Dovresti anche implementare i processi per tenere traccia degli incidenti e delle principali modifiche alla configurazione.

<div>

## <a name="reference"></a>Riferimenti

A vantaggio dei lettori che non hanno già familiarità con le nozioni di base sulla gestione dei server in generale, forniamo una panoramica delle procedure di gestione dei server. I lettori che hanno già familiarità con la gestione del server possono scegliere di ignorare questa sezione.

Le procedure consigliate sono consigli basati sulla conoscenza e l'esperienza acquisita dai professionisti IT in molti ambienti. Le procedure standard per le attività tipiche degli amministratori di Lync Server devono essere eseguite giornalmente e elencare gli strumenti da usare per gestire un ambiente Lync Server.

Le attività tipiche per gli amministratori di Lync includono le seguenti:

  - **La gestione**   della capacità e della disponibilità definisce come e cosa misurare per prevedere i requisiti di capacità futura e per segnalare la capacità, l'affidabilità e la disponibilità dei sistemi. È necessario verificare che i server che esegue Lync Server siano dimensionati per gestire il carico nel sistema e che i tempi di inattività non pianificati vengano mantenuti sotto i livelli definiti nel contratto di servizio (SLA). Inoltre, dovrai aggiornare l'hardware per continuare a soddisfare i requisiti definiti.

  - **Cambiare il controllo della gestione e della gestione**   della configurazione in che modo vengono apportate modifiche ai sistemi it. Questo dovrebbe includere test, feedback delle applicazioni e piani di emergenza, documentazione di tutte le modifiche e approvazione da gestione se si verificano problemi. Conservare un record degli asset software e hardware e delle relative configurazioni.

  - ****   I metodi standard di amministrazione di sistema per eseguire attività amministrative come l'amministrazione di database e l'amministrazione del sito.

  - **L'amministrazione**   della sicurezza ha un criterio e un piano dettagliati che proteggono la riservatezza dei dati, l'integrità dei dati e la disponibilità dei dati dell'infrastruttura IT. Questo include le attività quotidiane e le attività correlate alla manutenzione e alla regolazione dell'infrastruttura di sicurezza IT.

  - ****   Metodi per la risoluzione dei problemi di sistema per gestire i problemi imprevisti, inclusi i passaggi per evitare problemi simili in futuro.

  - **I contratti**   a livello di servizio mantengono un set di obiettivi per le prestazioni dei sistemi IT e misurano regolarmente le prestazioni rispetto a questi obiettivi.

  - **Documentation Document procedure**standard, ad esempio informazioni sulla configurazione e lezioni apprese, e renderle disponibili per i membri del personale che ne hanno bisogno.    In base alle modifiche apportate alla configurazione, aggiornare la documentazione di conseguenza.

</div>

<div>

## <a name="related-sections"></a>Sezioni correlate

Esaminare gli argomenti seguenti relativi alle operazioni di sistema prima di procedere:

  - [Gestione della capacità e della disponibilità in Lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Gestione delle modifiche in Lync Server 2013](lync-server-2013-change-management.md)

  - [Gestione della configurazione in Lync Server 2013](lync-server-2013-configuration-management.md)

  - [Amministrazione di sistema in Lync Server 2013](lync-server-2013-system-administration.md)

  - [Contratti a livello di servizio in Lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Documentazione in Lync Server 2013](lync-server-2013-documentation.md)

  - [Procedure standard in Lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Procedure di emergenza in Lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Microsoft Operations Framework 4,0](http://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

