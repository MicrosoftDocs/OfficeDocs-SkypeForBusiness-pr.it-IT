---
title: 'Lync Server 2013: informazioni sui report creati da Best Practices Analyzer'
description: 'Lync Server 2013: informazioni sui report creati da Best Practices Analyzer.'
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
ms.openlocfilehash: 5fbb84cdffe6e6e6f079c2d72aba4799f5538776
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542372"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Informazioni sui report creati da Best Practices Analyzer in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-10_

Best Practices Analyzer fornisce diversi tipi di rapporto organizzati in modo da favorire l'analisi e la risoluzione dei problemi tramite l'identificazione di errori, avvisi e altre informazioni.

<div>

## <a name="reports"></a>Report

È possibile accedere ai risultati di un'analisi visualizzando i seguenti tipi di rapporto:

  - **Rapporti elenco**     I rapporti elenco sono organizzati secondo criteri specifici. È possibile disporre i risultati in base alla classe, alla gravità o al problema. Ad esempio, se si organizzano i risultati in base alla classe, i problemi relativi ai direttori sono inclusi nella sezione direttori del rapporto. È possibile visualizzare tutti i problemi o solo gli elementi informativi. È possibile eseguire una ricerca in un rapporto elenco per elementi specifici, ad esempio la memoria. È inoltre possibile stampare o esportare il rapporto.

  - **Rapporti sugli alberi**     I report dell'albero sono organizzati dalle regole utilizzate per eseguire l'analisi e altre opzioni specificate al momento dell'esecuzione dell'analisi. Ad esempio, i problemi relativi alle regole di topologia di test sono inclusi nella sezione topologia di test del report. È possibile visualizzare i dettagli di tutti i problemi o solo un riepilogo dei problemi. È possibile eseguire una ricerca in un rapporto di albero per elementi specifici, ad esempio la memoria. È inoltre possibile stampare o esportare il rapporto.

  - **Altri rapporti**     Gli elementi in altri report includono il registro di runtime delle attività incluse nell'analisi. È possibile cercare specifici elementi contenuti in altri rapporti, ad esempio la memoria. È inoltre possibile stampare o esportare il rapporto.

</div>

<div>

## <a name="issues"></a>Problemi

I rapporti generati da Best Practices Analyzer indicano specifici problemi identificati durante l'analisi dell'ambiente, tra cui i seguenti tipi:

  - **Errori**     Problemi critici che richiedono di apportare modifiche all'ambiente. Ad esempio, se i componenti di base di Lync Server 2013 non sono installati, viene registrato un errore.

    I problemi classificati come errore sono identificati dalla presenza di un simbolo X rosso nel rapporto. Gli errori sono visualizzati nella scheda **All Issues** della visualizzazione **List Reports** e nelle schede **Detailed View** e **Summary View** della visualizzazione **Tree Reports**. Qualora non si desideri visualizzare uno specifico errore in un rapporto, è possibile specificare che non venga mostrata una singola istanza o tutte le istanze dell'errore in questione. In tal caso, l'errore sarà visualizzato solo nella scheda **Hidden Items** della visualizzazione **Other Reports** , a meno che non si modifichi l'impostazione e si specifichi di visualizzare l'errore nel rapporto.

  - **Avvisi**     Problemi che non sono coerenti con l'implementazione di una procedura consigliata. Questo può o non può indicare la necessità di una modifica nell'ambiente. Il problema potrebbe essere un problema noto con un'impostazione specifica che non è necessario modificare. Ad esempio, i servizi non avviati in un server vengono registrati come avvisi.

    I problemi classificati come avvisi sono segnalati nel rapporto dalla presenza di un simbolo di avviso triangolare giallo. Gli avvisi vengono visualizzati nella scheda **All Issues** della visualizzazione **List Reports**  e nelle schede **Detailed View** e **Summary View** della visualizzazione **Tree Reports**. Qualora non si desideri visualizzare uno specifico errore in un rapporto, è possibile specificare che non venga mostrata una singola istanza o tutte le istanze dell'errore in questione. In tal caso, l'avviso sarà visualizzato solo nella scheda  **Hidden Items** della visualizzazione **Other Reports**,  a meno che non si modifichi l'impostazione e si specifichi di visualizzare l'errore nel rapporto.

  - **Informazioni**     su Include tutti i problemi che non sono classificati come errori o avvisi. Ad esempio, il numero di oggetti server di Lync Server 2013 Standard Edition in servizi di dominio Active Directory è classificato come un problema di informazioni.

    I problemi di informazioni sono visualizzati nella scheda **All Issues** della visualizzazione **List Reports** e nella scheda **Detailed View** della visualizzazione **Tree Reports**.

Lync Server 2013, Best Practices Analyzer non apporta modifiche all'ambiente per risolvere i problemi. L'analisi rileva solo potenziali problemi e fornisce rapporti che contengono informazioni su come risolvere ogni problema.

Facendo clic su un problema, si visualizzano una spiegazione e alcune opzioni relative a specifici problemi ed è possibile eseguire una delle operazioni seguenti:

  - Trovare informazioni più dettagliate sul problema e sulla modalità di risoluzione.

  - Non visualizzare più problemi nei rapporti:

      - Non visualizzare più problemi per l'istanza selezionata.

      - Non visualizzare più problemi per tutte le istanze relative a un determinato problema.

    Affinché i problemi non siano più visualizzati nei rapporti, accedere alla scheda **Hidden Items** della visualizzazione **Other Reports**. Nello stesso percorso è possibile specificare di mostrare nuovamente i problemi nei rapporti.

Per informazioni dettagliate sulla risoluzione di problemi specifici, vedere [analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>
