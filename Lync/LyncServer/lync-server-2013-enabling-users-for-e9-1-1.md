---
title: 'Lync Server 2013: attivazione degli utenti per il servizio E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5550ec608b34b66a3e47ceb4535dd23ca7c9a7f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Abilitazione degli utenti per il servizio E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

Durante la registrazione client, Lync Server utilizza un criterio percorso per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale. In un criterio percorso sono contenute tutte le impostazioni che definiscono come verrà implementata la funzionalità E9-1-1. Ad esempio, il criterio percorso contiene informazioni quali la stringa di chiamata di emergenza e se un utente è tenuto a immettere manualmente una posizione se il servizio informazioni percorso non ne fornisce automaticamente una. Per una definizione completa dei criteri percorso, vedere [define the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server è in grado di assegnare un criterio percorso ai client basati sulla subnet o agli utenti in base a un criterio globale, per sito o per utente. Per decidere come abilitare gli utenti, è consigliabile innanzitutto tenere conto degli aspetti seguenti.

  - **Valutare se si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione**  
    È possibile assegnare una posizione a tutti gli utenti dell'organizzazione utilizzando un criterio percorso globale. Tuttavia, assegnando un criterio percorso a un sito di rete di Lync Server e quindi aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing di E9-1-1 per ogni singolo sito.

<!-- end list -->

  - **Valutare se si prevede di abilitare singoli utenti mediante un criterio utente**  
    È possibile assegnare criteri percorso direttamente a utenti specifici o a oggetti contatto di telefoni di area comune se si desidera personalizzare il relativo supporto E9-1-1.

<!-- end list -->

  - **Valutare se abilitare per E9-1-1 i client che effettuano il roaming all'esterno della rete o si connettono da una subnet non definita**  
    Se agli utenti viene assegnato un criterio percorso globale, sito o per utente, è possibile che venga richiesto di immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni percorso non è stato trovato. Per informazioni dettagliate, vedere [definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

