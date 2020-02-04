---
title: 'Lync Server 2013: Panoramica del ritiro delle chiamate di gruppo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Panoramica del ritiro delle chiamate di gruppo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-12_

Raccolta di chiamate di gruppo, una nuova funzionalità degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi dal proprio telefono. Questa nuova caratteristica aumenta la disponibilità della linea di un utente, consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di pick-up chiamata. Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo indirizzate alla segreteria telefonica può essere notevolmente ridotto, particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.

La caratteristica raccolta chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti. Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista. Tuttavia, gli altri utenti che sentono l'anello possono comunque prendere la chiamata semplicemente componendo il numero di gruppo.

In ambienti in cui gli utenti non si trovano in un layout Office aperto o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, la chiamata del team presenta la soluzione più appropriata. La differenza principale tra il pick-up delle chiamate di gruppo e la chiamata del team consiste nel fatto che, con il ritiro delle chiamate di gruppo, una chiamata in arrivo viene squillata solo nella destinazione desiderata, ma chiunque può comunque scegliere di rispondere chiamando un numero di gruppo. Con la chiamata del team, la chiamata squilla in tutti i telefoni dei membri del team e qualsiasi utente del team può prendere il telefono per rispondere alla chiamata. Una differenza aggiuntiva tra il ritiro delle chiamate di gruppo e la chiamata del team consiste nel fatto che il ritiro delle chiamate di gruppo viene gestito da un amministratore tramite Lync Server. Con la chiamata del team, gli utenti finali gestiscono la funzionalità usando il client Lync. Con il pick-up delle chiamate di gruppo, quindi, questo aspetto della gestione delle chiamate può essere centralizzato.

Il ritiro delle chiamate di gruppo viene compilato nell'applicazione Call Park. Quando si distribuisce il pickup di una chiamata di gruppo, è possibile configurare la tabella Orbit di Call Park con intervalli distinti di numeri di interno designati come numeri di gruppo di pick-up delle chiamate. Come i numeri delle orbite di Call Park, i numeri dei gruppi di pickup delle chiamate devono essere estensioni virtuali che non hanno un utente o un telefono assegnato. Ogni pool Front end in cui si distribuisce il pickup di una chiamata di gruppo può avere uno o più intervalli di numeri di gruppo di prelievo chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale in tutta la distribuzione di Lync Server.

<div>


> [!NOTE]  
> Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella Orbit di parcheggio delle chiamate non possono essere gestiti o visualizzati tramite il pannello di controllo di Lync Server. L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella Orbit di Call Park consiste nell'usare Lync Server Management Shell. Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'usare Lync Server Management Shell.



</div>

Dopo aver configurato i numeri dei gruppi di raccolta chiamate, assegnare gli utenti a un gruppo di raccolta chiamate. Qualsiasi utente assegnato a un gruppo di raccolta chiamate può rispondere alle chiamate di altri utenti. Quando una chiamata viene fornita a un utente assegnato a un gruppo di raccolta chiamate, qualsiasi altro utente che nota la chiamata può rispondere manualmente chiamando il numero del gruppo di raccolta chiamate. L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo. Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.

<div>


> [!NOTE]  
> Un utente può essere un membro di un solo gruppo di raccolta chiamate.



</div>

<div>


> [!NOTE]  
> Anche se qualsiasi utente nella distribuzione di Lync Server può rispondere a una chiamata a un membro del gruppo di prelievo delle chiamate, la persona che risponde alla chiamata deve conoscere il numero del gruppo di pick-up chiamata corretto.



</div>

Se un utente compone un numero di gruppo di pick-up chiamata per rispondere a una chiamata quando si squillano più telefoni nel gruppo, l'utente risponde alla chiamata che ha squillato il più a lungo.

Le impostazioni di chiamata simultanee funzionano per gli utenti che hanno un pick-up delle chiamate di gruppo. Vale a dire che una chiamata effettuata a un utente che ha un pickup per la chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente può rispondere alla chiamata. L'eccezione a questa regola è quando l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.

Non è possibile usare il pick-up per rispondere ai tipi di chiamata seguenti:

  - Chiamate a una riga privata

  - Chiamate di un contatto a cui sono stati assegnati gli amici e la relazione di privacy della famiglia
    
    <div>
    

    > [!TIP]  
    > Un utente che fa parte di un gruppo di raccolta chiamate può impedire che determinate chiamate vengano recuperate tramite il ritiro delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Lync. Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con amici e familiari. Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite raccolta chiamate di gruppo.

    
    </div>

  - Parte video delle chiamate audio/video
    
    <div>
    

    > [!NOTE]  
    > Se un utente risponde a una chiamata audio/video, l'utente riceve solo l'audio. La chiamata di persona o la persona che risponde alla chiamata può escalation per l'aggiunta di un video.

    
    </div>

  - Chiamate di chiamata simultanee instradate ai membri delle chiamate del team

  - Chiamate instradate a un delegato

  - Chiamate instradate a un gruppo di risposte

I tipi di utenti seguenti non possono partecipare al ritiro delle chiamate di gruppo. Vale a dire che non devono essere inclusi in un gruppo di raccolta chiamate di gruppo e non possono raccogliere le chiamate per gli utenti che hanno abilitato il pick-up delle chiamate di gruppo.

  - Utenti residenti online in una distribuzione ibrida

  - Utenti non residenti in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale

Se non si risponde a una chiamata a un membro di un gruppo di raccolta chiamate, la chiamata viene instradata come specificato nelle impostazioni del client. Vale a dire che la chiamata passa alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.

</div>

<span> </span>

</div>

</div>

</div>

