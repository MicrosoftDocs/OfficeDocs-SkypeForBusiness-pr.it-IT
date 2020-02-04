---
title: 'Lync Server 2013: informazioni sui report creati da Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2262c490d84ec6f93ff395a9c8ec38d81c82e7de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Informazioni sui report creati dall'analizzatore delle procedure consigliate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-10_

Best Practices Analyzer offre più tipi di report organizzati per facilitare l'analisi e la risoluzione dei problemi. Analizzatore procedure consigliate identifica problemi come errori, avvisi e altre informazioni.

<div>

## <a name="reports"></a>Rapporti

È possibile accedere ai risultati di un'analisi visualizzando ognuno dei report seguenti:

  - ****   I report di elenco report elenco sono organizzati in base a criteri specifici. Puoi organizzare i risultati per classe, gravità o problema. Ad esempio, se organizzi i risultati per classe, i problemi relativi ai direttori sono inclusi nella sezione direttori del report. È possibile visualizzare tutti i problemi o solo gli elementi informativi. È possibile cercare un report elenco per elementi specifici, ad esempio la memoria. È anche possibile stampare il report o esportarlo.

  - ****   I report albero report albero sono organizzati dalle regole usate per eseguire l'analisi e altre opzioni specificate al momento dell'esecuzione dell'analisi. Ad esempio, i problemi relativi alle regole della topologia di test sono inclusi nella sezione topologia di test del report. È possibile visualizzare i dettagli di tutti i problemi o solo un riepilogo dei problemi. È possibile eseguire una ricerca in un report albero per elementi specifici, ad esempio la memoria. È anche possibile stampare il report o esportarlo.

  - **Altri**   elementi di report in altri report includono il log in fase di esecuzione delle attività incluse nell'analisi. È possibile cercare gli elementi in altri report per elementi specifici, ad esempio la memoria. È anche possibile stampare il report o esportarlo.

</div>

<div>

## <a name="issues"></a>Problemi

I report generati da Best Practices Analyzer indicano problemi specifici identificati durante la scansione dell'ambiente, inclusi i tipi di problemi seguenti:

  - **Errori**   critici che richiedono di apportare modifiche all'ambiente in questione. Ad esempio, se i componenti principali di Lync Server 2013 non sono installati, viene registrato un errore.
    
    I problemi classificati come errori vengono identificati nel report da un simbolo X rosso. Gli errori vengono visualizzati nella **scheda tutti i problemi** della visualizzazione **elenco report** e nella scheda **visualizzazione dettagliata** e nella scheda visualizzazione **Riepilogo** della visualizzazione **report albero** . Se non si vuole visualizzare un errore specifico in un report, è possibile specificare che l'errore non viene visualizzato per una singola istanza o per tutte le istanze di tale errore nel report. L'errore viene quindi visualizzato solo nella scheda **elementi nascosti** della visualizzazione **altro report** , a meno che non si modifichi l'impostazione e si specifichi che l'errore deve essere visualizzato nel report.

  - **Avvisi**   problemi che non sono coerenti con l'implementazione di una procedura consigliata. Questo può o non può indicare la necessità di una modifica nell'ambiente. Il problema potrebbe essere un problema noto con un'impostazione specifica che non è necessario modificare. Ad esempio, i servizi non avviati in un server vengono registrati come avvisi.
    
    I problemi classificati come avvisi vengono identificati nel report da un simbolo di avviso giallo triangolare. Gli avvisi vengono visualizzati nella scheda **tutti i problemi** della visualizzazione **Elenco rapporti** , nonché nella scheda **visualizzazione dettagliata** e nella scheda **visualizzazione Riepilogo** della visualizzazione **report albero** . Se non si vuole visualizzare un errore specifico in un report, è possibile specificare che l'errore non viene visualizzato per una singola istanza o per tutte le istanze di tale errore nel report. L'avviso viene quindi visualizzato solo nella scheda **elementi nascosti** della visualizzazione **altro report** , a meno che non si modifichi l'impostazione e si specifichi che l'avviso deve essere visualizzato nel report.

  - **Le informazioni**   includono tutti i problemi che non sono classificati come errori o avvisi. Ad esempio, il numero di oggetti server di Lync Server 2013 Standard Edition in servizi di dominio Active Directory è classificato come problema di informazioni.
    
    I problemi di informazioni vengono visualizzati nella scheda **tutti i problemi** della visualizzazione **elenco report** e nella scheda **visualizzazione dettagliata** della visualizzazione **report albero** .

Lync Server 2013, Best Practices Analyzer non apporta modifiche all'ambiente per risolvere i problemi. L'analisi rileva solo i potenziali problemi e fornisce report che contengono informazioni su come risolvere ogni problema.

Se si fa clic su un problema, vengono visualizzate una spiegazione e alcune opzioni per problemi specifici. È quindi possibile eseguire una delle operazioni seguenti:

  - Trovare informazioni più dettagliate sul problema e come risolverlo.

  - Interrompere la visualizzazione di problemi nei report:
    
      - Interrompi la visualizzazione dei problemi per l'istanza selezionata.
    
      - Interrompi la visualizzazione di problemi per tutte le istanze del problema.
    
    Per visualizzare i problemi che sono stati interrotti nei report, accedere alla scheda **elementi nascosti** della visualizzazione **altri report** . Da qui è possibile specificare per iniziare a visualizzare di nuovo i problemi nei report.

Per informazioni dettagliate sulla risoluzione di problemi specifici, vedere [analisi e risoluzione dei problemi identificati dall'analizzatore delle procedure consigliate in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

