---
title: 'Lync Server 2013: procedure consigliate per gli ambienti Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f65e7d210c069a5b629e0fbf093e3abea291ce6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513023"
---
# <a name="best-practices-for-lync-server-2013-environments"></a>Procedure consigliate per gli ambienti di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-04_

I seguenti principi generali devono essere applicati alle operazioni in continuo del sistema:

  - **Comprendere e utilizzare MOF**     MOF è una raccolta di procedure consigliate, principi e modelli che forniscono alle organizzazioni informazioni tecniche sulla gestione delle risorse IT, ad esempio le operazioni quotidiane di Lync Server 2013. Le seguenti linee guida MOF consentono di raggiungere l'affidabilità, la disponibilità, la supportabilità e la gestibilità del sistema di produzione mission-critical per i prodotti Microsoft. Per ulteriori informazioni, vedere [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).

  - Informazioni **sulle procedure consigliate per Lync Server 2013**     È consigliabile implementare procedure pratiche e collaudate per la gestione di Lync Server 2013. L'utilizzo di metodi sperimentati, testati e documentati per la gestione delle operazioni può essere più efficace rispetto allo sviluppo di metodi personalizzati.

  - **Separare le operazioni in processi giornalieri, settimanali e mensili**     Documentare le attività operative necessarie che verranno eseguite regolarmente. Documentare la modalità di esecuzione delle attività consente di verificare che le informazioni vengano conservate quando si verifica una modifica nell'ambiente operativo, ad esempio quando vengono distribuite nuove tecnologie o se vengono apportate modifiche del personale. È consigliabile separare le attività operative in carichi di lavoro gestibili, in cui le attività vengono eseguite giornalmente, settimanalmente e mensilmente. Le attività quotidiane concentreranno gli sforzi sul funzionamento di un sistema e le attività mensili si concentreranno maggiormente sul garantire l'integrità a lungo termine di un sistema.
    
    Questo documento può essere utilizzato in ambienti che distribuiscono solo i componenti di messaggistica istantanea/presenza (IM/P) o IM/P con VoIP aziendale. Quando le attività o gli elementi di elenco di controllo sono specifici di VoIP aziendale, questo viene menzionato e se l'ambiente in uso non include VoIP aziendale, la parte potrebbe essere ignorata.

  - **Distribuire gli strumenti necessari per l'utilizzo di Lync Server 2013**     Sono disponibili numerosi strumenti per la risoluzione dei problemi, l'automazione delle attività e la guida del monitoraggio e la gestione dell'ambiente Lync Server 2013. Definire un insieme standard di strumenti per l'organizzazione, in modo che le attività eseguite dal team operativo vengano eseguite in modo accurato, efficiente, coerente e controllato. È inoltre consigliabile implementare processi per tenere traccia degli incidenti e delle principali modifiche alla configurazione.

<div>

## <a name="reference"></a>Riferimenti

A vantaggio dei lettori che non hanno già familiarità con le nozioni di base della gestione dei server in generale, viene fornita una panoramica delle procedure di gestione dei server. I lettori che hanno già familiarità con la gestione del server possono scegliere di ignorare questa sezione.

Le procedure consigliate sono consigli che si basano sulla conoscenza e sull'esperienza acquisita dai professionisti IT in molti ambienti. Essi forniscono procedure standard per le attività tipiche che gli amministratori di Lync Server devono eseguire giornalmente e elencano gli strumenti da utilizzare per la gestione di un ambiente Lync Server.

Di seguito sono riportate le attività tipiche per gli amministratori di Lync:

  - **Gestione della disponibilità e della capacità**     Definire come e cosa misurare per prevedere i requisiti di capacità futuri e per segnalare la capacità, l'affidabilità e la disponibilità dei sistemi. È necessario verificare che i server in cui è in esecuzione Lync Server siano dimensionati per gestire il carico del sistema e che i tempi di inattività non pianificati siano conservati nei livelli definiti nel contratto di servizio (SLA, Service Level Agreement). Inoltre, è necessario aggiornare l'hardware per continuare a soddisfare i requisiti definiti.

  - Gestione **della configurazione**     e della gestione delle modifiche Controllare il modo in cui vengono apportate le modifiche ai sistemi IT. Questo dovrebbe includere i test, i commenti e i piani di emergenza, la documentazione di tutte le modifiche e l'approvazione dalla gestione se si verificano problemi. Tenere traccia di un record delle risorse hardware e software e delle relative configurazioni.

  - **Amministrazione**     del sistema Strutturare metodi standard per eseguire attività amministrative quali l'amministrazione di database e l'amministrazione del sito.

  - **Amministrazione**     della sicurezza Disporre di un criterio dettagliato e di una pianificazione che protegga la riservatezza dei dati, l'integrità dei dati e la disponibilità dei dati dell'infrastruttura IT. Ciò include attività quotidiane e attività correlate alla gestione e alla modifica dell'infrastruttura di sicurezza IT.

  - **Risoluzione dei problemi**     del sistema Metodi di struttura per la gestione di problemi imprevisti, inclusi i passaggi per evitare problemi simili in futuro.

  - Contratti a livello di **servizio**     Mantenere un insieme di obiettivi per le prestazioni dei sistemi IT e misurare periodicamente le prestazioni in base a tali obiettivi.

  - **Documentazione**     Procedure standard del documento, ad esempio le informazioni di configurazione e gli insegnamenti appresi, e renderli disponibili per i membri del personale che ne hanno bisogno. Quando vengono apportate modifiche alla configurazione, aggiornare la documentazione di conseguenza.

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


[Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

