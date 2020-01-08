---
title: 'Lync Server 2013: amministrazione di sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62526daf43308b4ed38538e5ea16e15b271fc9a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Amministrazione di sistema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-18_

L'amministrazione di sistema include le attività amministrative quotidiane, sia pianificate che su richiesta, necessarie per garantire un funzionamento agevole del sistema IT. In genere, le attività di amministrazione del sistema sono coperte da procedure scritte. Queste procedure consentono di verificare che gli stessi strumenti e metodi standard vengano usati da tutto il personale di supporto.

In un ambiente Lync le attività tipiche di amministrazione del sistema includono il backup e l'archiviazione di pool, il monitoraggio dei log, la creazione e la gestione degli utenti e l'aggiornamento del software antivirus.

<div>

## <a name="system-troubleshooting"></a>Risoluzione dei problemi di sistema

Un'organizzazione deve essere pronta a gestire problemi imprevisti e deve avere una procedura per la gestione dei problemi dal momento in cui vengono segnalati fino alla risoluzione. Informazioni sul modo in cui il personale del supporto diagnostico ha diagnosticato un problema deve essere registrato e usato in futuro per evitare inutili ripetizioni del lavoro completato.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Processo di risoluzione dei problemi del sistema

Il diagramma seguente mostra il processo di risoluzione dei problemi del sistema e le interazioni con altri ruoli delle operazioni.

**Diagramma di flusso di risoluzione dei problemi di sistema**

![](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagramma") di flusso per la risoluzione dei problemi del sistema

  - **Classificazione e assegnazione delle priorità**   questa attività viene in genere eseguita dal Service Desk. Ad esempio, un problema può essere raggruppato come problema software o hardware. Il problema viene quindi indirizzato al team di supporto appropriato per l'analisi. Le regole per determinare la priorità di un problema, insieme al tempo necessario per rispondere e il tempo di risoluzione, sono in genere definite nell'SLA.

  - **Esaminare e diagnosticare**   il team di supporto appropriato per diagnosticare il problema e proporre le modifiche per risolvere il problema. Se la soluzione è semplice e non richiede il controllo delle modifiche, la soluzione può essere applicata immediatamente. Se la soluzione non è semplice, deve essere generata una richiesta di modifica e il lavoro proposto deve essere gestito dal processo di gestione delle modifiche, spesso in una procedura "Fast-Track". Tutte le modifiche apportate devono essere registrate con il processo di gestione della configurazione.

  - **Chiudere e registrare**   dopo il test della risoluzione, il problema deve essere chiuso. Se sono presenti lezioni da trarre dal problema, è necessario creare una voce nella Knowledge base.

  - **Revisione e analisi**   di tendenza le recensioni periodiche dei problemi recenti devono essere eseguite per identificare le tendenze del problema. Ad esempio, se gli utenti riscontrano frequenti problemi con gli accessi lenti ai siti Lync, potrebbe essere la causa di problemi di larghezza di banda della rete. I tempi di risoluzione dei problemi e l'effetto di eventuali interruzioni sulla disponibilità del sistema devono essere rivisti e confrontati con lo SLA. La persona che mantiene il cliente in caso di problemi di servizio, ad esempio un account Manager, deve essere informata di eventuali problemi significativi.

</div>

<div>

## <a name="issue-management-tools"></a>Strumenti di gestione dei problemi

Gli strumenti di Service Desk consentono al personale di registrare, classificare e dare priorità ai nuovi problemi. Gli strumenti forniranno quindi i processi del flusso di lavoro per gestire la richiesta di servizio problema tramite indagini e diagnosi, spesso da più team di supporto. Gli strumenti, che spesso forniranno report sui tempi di risoluzione e sulle tendenze storiche, possono includere anche un database di Knowledge base, che può essere usato per eseguire ricerche in precedenti problemi.

La Microsoft Knowledge base è un utile record di problemi di supporto che sono stati rilevati da Microsoft. Per altre informazioni, vedere il sito Web del supporto<http://go.microsoft.com/fwlink/?linkid=14898>tecnico Microsoft ().

Il software di terze parti richiede in genere la personalizzazione in base alle esigenze dell'organizzazione, ad esempio l'organizzazione di Team, i requisiti per la creazione di report e le misure richieste dall'SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Amministrazione centralizzata e decentralizzata

I ruoli e le responsabilità per l'esecuzione di attività di amministrazione del sistema variano a seconda che l'organizzazione segua un modello centralizzato, un modello decentralizzato o una combinazione di entrambi.

  - **Modello centralizzato**   in un modello centralizzato, uno o più gruppi amministrativi mantengono il controllo completo dell'intero ambiente Lync Server. Questo modello amministrativo è simile a un centro dati in cui tutte le attività di amministrazione vengono eseguite da un singolo gruppo di tecnologie informative. I ruoli e le responsabilità all'interno del team devono essere definiti in base a esperienza e competenza.

  - ****   Le organizzazioni decentralizzate del modello decentralizzato si trovano in più posizioni geografiche e hanno funzioni di server e team di amministratori di Lync in posizioni diverse. Ad esempio, è possibile che il personale di amministrazione locale e uno o più server eseguano Lync Server 2013 per ogni paese/area geografica. In alternativa, potrebbe essere presente un pool di server che esegue Lync Server 2013 e un team amministrativo per il Nord America e uno per l'Europa. A volte è consigliabile che gli amministratori siano responsabili solo per la propria area geografica e limitano le autorizzazioni per l'amministrazione delle risorse in altre aree.

Lync Server consente inoltre di delegare specifiche attività amministrative a persone o gruppi specifici tramite il controllo di accesso basato sui ruoli (RBAC). RBAC consente agli amministratori di delegare diritti utente specifici e autorizzazioni ad altri amministratori per eseguire un sottoinsieme delle attività amministrative possibili. Usando RBAC, la capacità dell'utente di eseguire attività amministrative specifiche dipende dai ruoli RBAC assegnati all'utente. RBAC fornisce un elenco di cmdlet che l'utente può eseguire in base ai ruoli RBAC di cui l'utente è membro.

</div>

</div>

<span> </span>

</div>

</div>

</div>

