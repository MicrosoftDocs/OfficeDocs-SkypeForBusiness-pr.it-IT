---
title: 'Lync Server 2013: Panoramica del prelievo delle chiamate di gruppo'
description: 'Lync Server 2013: Panoramica del prelievo delle chiamate di gruppo.'
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
ms.openlocfilehash: c968ac466c7242253cb5a9594e1942d86031494d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562882"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a>Panoramica del prelievo delle chiamate di gruppo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-12_

Prelievo delle chiamate di gruppo, una nuova caratteristica negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, consente agli utenti di rispondere alle chiamate in arrivo ai propri colleghi tramite i propri telefoni. Questa nuova funzionalità aumenta la disponibilità della linea di un utente consentendo ad altri utenti di rispondere a una chiamata in arrivo componendo un numero di gruppo di prelievo di chiamata. Quando viene distribuito il prelievo delle chiamate di gruppo, il numero di chiamate in arrivo instradate alla segreteria telefonica può essere ridotto significativamente, il che è particolarmente utile per le chiamate provenienti da clienti esterni all'organizzazione.

La funzionalità di prelievo delle chiamate di gruppo è stata progettata in particolare per le unità aziendali in ambienti Office aperti. Le chiamate in arrivo non sono di disturbo perché squillano solo nella destinazione prevista. Tuttavia, gli altri utenti che ascoltano l'anello possono comunque prendere la chiamata semplicemente componendo il numero del gruppo.

Negli ambienti in cui gli utenti non sono ubicati in un layout Open Office o in cui gli utenti che condividono una responsabilità comune sono distribuiti geograficamente, il team Call presenta la soluzione più adatta. La differenza principale tra il prelievo di chiamate di gruppo e la chiamata del team consiste nel fatto che, con il prelievo delle chiamate di gruppo, una chiamata in arrivo squilla solo nella destinazione prevista, ma chiunque può comunque scegliere di rispondere componendo un numero di gruppo. Con il team di chiamata, la chiamata squilla a tutti i telefoni dei membri del team e tutti gli utenti del team possono prendere il telefono per rispondere alla chiamata. Un'ulteriore differenza tra il prelievo di chiamate di gruppo e la chiamata del team è che il prelievo delle chiamate di gruppo è gestito da un amministratore, tramite Lync Server. Con la chiamata del team, gli utenti finali gestiscono la funzionalità utilizzando il client Lync. Con il prelievo delle chiamate di gruppo, pertanto, questo aspetto della gestione delle chiamate può essere centralizzato.

Il prelievo delle chiamate di gruppo è basato sull'applicazione Parcheggio di chiamata. Quando si distribuisce il prelievo delle chiamate di gruppo, è possibile configurare la tabella orbit del parcheggio di chiamata con intervalli distinti di numeri di interno designati come numeri del gruppo di prelievo delle chiamate. Analogamente ai numeri dell'orbita del parcheggio di chiamata, i numeri del gruppo di prelievo delle chiamate devono essere estensioni virtuali a cui non è assegnato alcun utente o telefono. Ogni pool Front end in cui si distribuisce il prelievo delle chiamate di gruppo può avere uno o più intervalli di numeri del gruppo di prelievo delle chiamate. Gli intervalli di numeri di gruppo devono essere univoci a livello globale nella distribuzione di Lync Server.

<div>


> [!NOTE]  
> Gli intervalli di numeri designati come numeri di prelievo delle chiamate di gruppo nella tabella di orbit del parcheggio di chiamata non possono essere gestiti o visualizzati utilizzando il pannello di controllo di Lync Server. L'unico modo per visualizzare tutti gli intervalli di numeri nella tabella di orbit del parcheggio di chiamata è l'utilizzo di Lync Server Management Shell. Analogamente, l'unico modo per aggiungere, modificare o rimuovere i numeri di prelievo delle chiamate di gruppo consiste nell'utilizzare Lync Server Management Shell.



</div>

Dopo aver configurato i numeri del gruppo di prelievo delle chiamate, è possibile assegnare gli utenti a un gruppo di prelievo delle chiamate. Tutti gli utenti a cui è assegnato un gruppo di prelievo di chiamata possono rispondere alle chiamate di altri utenti. Quando una chiamata viene rilasciata a un utente assegnato a un gruppo di prelievo di chiamata, qualsiasi altro utente che nota la chiamata può rispondere manualmente componendo il numero del gruppo di prelievo delle chiamate. L'utente che preleva la chiamata non deve necessariamente essere un membro del gruppo. Quando una chiamata viene rilevata da un altro utente, viene inviata una notifica al numero originariamente chiamato.

<div>


> [!NOTE]  
> Un utente può essere membro di un solo gruppo di prelievo delle chiamate.



</div>

<div>


> [!NOTE]  
> Anche se qualsiasi utente nella distribuzione di Lync Server può rispondere a una chiamata a un membro del gruppo di prelievo di chiamata, la persona che risponde alla chiamata deve conoscere il numero del gruppo di prelievo di chiamata corretto da comporre.



</div>

Se un utente compone un numero di gruppo di prelievo di chiamata per rispondere a una chiamata quando si squillano più telefoni del gruppo, l'utente risponde alla chiamata che ha squillato più a lungo.

Le impostazioni di squillo simultaneo funzioneranno per gli utenti che dispongono del prelievo delle chiamate di gruppo. Vale a dire che una chiamata effettuata a un utente con prelievo di chiamata di gruppo suonerà per tutte le destinazioni configurate e un altro utente potrà rispondere alla chiamata. L'eccezione a questa regola è quella in cui l'utente configura lo squillo simultaneo per chiamare tutti i membri del team.

Non è possibile utilizzare il prelievo delle chiamate di gruppo per rispondere ai tipi di chiamate seguenti:

  - Chiamate a una riga privata

  - Chiamate da un contatto a cui è stata assegnata la relazione amici e familiari sulla privacy
    
    <div>
    

    > [!TIP]  
    > Un utente membro di un gruppo di prelievo di chiamata può impedire che determinate chiamate vengano recuperate tramite il prelievo delle chiamate di gruppo contrassegnando il contatto come contatto personale nel client Lync. Per contrassegnare un contatto come contatto personale, impostare la relazione di privacy per il contatto con gli amici e la famiglia. Qualsiasi chiamata in arrivo da contatti con la relazione di privacy impostata su amici e familiari non può essere recuperata tramite il prelievo delle chiamate di gruppo.

    
    </div>

  - Parte video delle chiamate audio/video
    
    <div>
    

    > [!NOTE]  
    > Se un utente risponde a una chiamata audio/video, l'utente riceverà solo l'audio. La chiamata di persona o la persona che risponde alla chiamata può inoltrare la richiesta di aggiunta di un video.

    
    </div>

  - Chiamate di chiamata simultanee che vengono instradate ai membri delle chiamate del team

  - Chiamate instradate a un delegato

  - Chiamate instradate a un Response Group

I seguenti tipi di utenti non possono partecipare al ritiro delle chiamate di gruppo. Vale a dire che non devono essere inclusi in un gruppo di prelievo di chiamata di gruppo e non possono rispondere alle chiamate per gli utenti che dispongono del prelievo di chiamata di gruppo abilitato.

  - Utenti ospitati online in una distribuzione ibrida

  - Utenti che non sono ospitati in un pool di Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 in una distribuzione locale

Se non si risponde a una chiamata a un membro di un gruppo di prelievo di chiamata, la chiamata viene instradata come specificato nelle impostazioni client. Vale a dire che la chiamata viene inviata alla segreteria telefonica o viene inoltrata a una destinazione diversa, come specificato nelle impostazioni del client.

</div>

<span> </span>

</div>

</div>

</div>

