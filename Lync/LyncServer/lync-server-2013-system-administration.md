---
title: 'Lync Server 2013: amministrazione di sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Amministrazione di sistema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-18_

L'amministrazione del sistema include le attività amministrative quotidiane, sia pianificate sia su richiesta, che sono necessarie per mantenere un funzionamento del sistema IT senza problemi. Le attività di amministrazione del sistema vengono in genere analizzate tramite procedure scritte. Queste procedure consentono di garantire che gli stessi strumenti e metodi standard siano utilizzati da tutto il personale di supporto.

In un ambiente Lync le attività tipiche di amministrazione del sistema includono il backup e l'archiviazione di pool, il monitoraggio dei log, la creazione e la gestione degli utenti e l'aggiornamento del software antivirus.

<div>

## <a name="system-troubleshooting"></a>Risoluzione dei problemi del sistema

Un'organizzazione deve essere preparata per gestire i problemi imprevisti e deve disporre di una procedura per la gestione dei problemi dal momento in cui vengono segnalati fino alla risoluzione. Informazioni sul modo in cui gli addetti al supporto diagnostici hanno diagnosticato un problema devono essere registrati e usati in futuro per evitare inutili ripetendo il lavoro completato.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processo di risoluzione dei problemi del sistema

Nel diagramma seguente viene illustrato il processo di risoluzione dei problemi del sistema e le interazioni con altri ruoli operativi.

**Diagramma di flusso di risoluzione dei problemi del sistema**

![Diagramma di flusso di risoluzione dei problemi del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagramma di flusso di risoluzione dei problemi del sistema")

  - **Classificazione e assegnazione di priorità**   questa attività viene in genere eseguita dal Service Desk. Ad esempio, un problema può essere raggruppato come problema software o hardware. Il problema viene quindi instradato al team di supporto appropriato per l'analisi. Le regole per determinare la priorità di un problema, insieme al tempo di risposta e al tempo di risoluzione, vengono in genere definite nel contratto di servizio.

  - **Esaminare e diagnosticare**   il team di supporto appropriato per la diagnosi del problema e propone le modifiche per risolvere il problema. Se la soluzione è semplice e non richiede il controllo delle modifiche, la soluzione può essere applicata immediatamente. Se la soluzione non è semplice, è necessario che venga generata una richiesta di modifica e che il lavoro proposto venga gestito dal processo di gestione delle modifiche, spesso in base a una procedura "Fast-Track". Tutte le modifiche apportate devono essere registrate utilizzando il processo di gestione della configurazione.

  - **Chiudi e registra**   dopo aver testato la risoluzione, il problema dovrebbe essere chiuso. Se è possibile trarre lezioni dal problema, è necessario creare una voce nella Knowledge base.

  - **Revisione e analisi**   delle tendenze le recensioni periodiche dei problemi recenti devono essere eseguite per identificare i trend del problema. Ad esempio, se gli utenti riscontrano problemi frequenti con gli accessi lenti ai propri siti Lync, potrebbe essere la causa di problemi relativi alla larghezza di banda di rete. I tempi di risoluzione dei problemi e l'effetto di eventuali interruzioni sulla disponibilità del sistema devono essere esaminati e confrontati con il contratto di servizio. La persona che mantiene con il cliente in merito ai problemi del servizio, ad esempio un responsabile account, deve essere informata su eventuali problemi significativi.

</div>

<div>

## <a name="issue-management-tools"></a>Strumenti di gestione dei problemi

Gli strumenti di Service Desk consentono al personale di registrare, classificare e assegnare una priorità ai nuovi problemi. Gli strumenti forniranno quindi i processi del flusso di lavoro per gestire la richiesta di servizio di problema tramite indagini e diagnosi, spesso da più di un team di supporto. Gli strumenti, che forniscono spesso report sui tempi di risoluzione e le tendenze storiche, possono includere anche un database della Knowledge base, che può essere utilizzato per eseguire ricerche nei problemi precedenti.

La Microsoft Knowledge base è un utile record di problemi di supporto che sono stati rilevati da Microsoft. Per ulteriori informazioni, vedere il sito Web del supporto<https://go.microsoft.com/fwlink/?linkid=14898>tecnico Microsoft ().

Il software di terze parti in genere richiede la personalizzazione in base alle esigenze dell'organizzazione, ad esempio l'organizzazione di Team, i requisiti per la creazione di report e le misure richieste dal contratto di servizio.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Amministrazione centralizzata e decentralizzata

I ruoli e le responsabilità per l'esecuzione delle attività di amministrazione del sistema dipendono dal fatto che l'organizzazione segua un modello centralizzato, un modello decentralizzato o una combinazione di entrambi.

  - **Modello centralizzato**   in un modello centralizzato, uno o più gruppi amministrativi mantengono il controllo completo dell'intero ambiente Lync Server. Questo modello amministrativo è simile a un centro dati in cui tutte le attività di amministrazione vengono eseguite da un singolo gruppo di tecnologie informative. I ruoli e le responsabilità interni al team devono essere definiti in base a esperienze e competenze.

  - ****   Le organizzazioni decentralizzate del modello decentralizzato sono situate in diverse posizioni geografiche e dispongono di server e team di amministratori di Lync Server in posizioni diverse. Ad esempio, è possibile che vi sia personale di amministrazione locale e uno o più server che eseguono Lync Server 2013 per ogni paese/area geografica. In alternativa, può essere presente un pool di server che eseguono Lync Server 2013 e un team amministrativo per il Nord America e uno per l'Europa. A volte, potrebbe essere necessario che gli amministratori siano responsabili solo per la propria area geografica e limitare le autorizzazioni per amministrare le risorse in altre aree.

Lync Server consente inoltre di delegare specifiche attività amministrative a specifiche persone o gruppi tramite il controllo di accesso basato sui ruoli (RBAC). RBAC consente agli amministratori di delegare diritti utente e autorizzazioni specifici ad altri amministratori per eseguire un sottoinsieme delle attività amministrative possibili. Tramite RBAC, la capacità dell'utente di eseguire attività amministrative specifiche dipende dai ruoli RBAC assegnati all'utente. RBAC fornisce un elenco di cmdlet che l'utente può eseguire in base ai ruoli RBAC di cui l'utente è membro.

</div>

</div>

<span> </span>

</div>

</div>

</div>

