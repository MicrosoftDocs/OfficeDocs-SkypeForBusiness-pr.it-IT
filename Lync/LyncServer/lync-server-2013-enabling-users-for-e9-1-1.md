---
title: 'Lync Server 2013: Abilitazione degli utenti per il E9-1-1'
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
ms.openlocfilehash: 86d5032defc7322e96662dcfe6357bd30c598e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a>Abilitazione degli utenti per E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Durante la registrazione del client, Lync Server usa un criterio di posizione per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale. Questo criterio contiene le impostazioni che definiscono la modalità di implementazione di E9-1-1. Ad esempio, il criterio di posizione contiene informazioni come la stringa di chiamata di emergenza e se un utente deve immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente uno. Per una definizione completa di un criterio di posizione, vedere [definizione dei criteri di posizione per Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server può assegnare un criterio di posizione ai client in base alla subnet o agli utenti in base a un criterio globale, per sito o per utente. Per decidere come abilitare gli utenti, è necessario prima rispondere alle domande seguenti.

  - **Si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione?**  
    È possibile assegnare una posizione a tutti gli utenti dell'organizzazione usando un criterio di posizione globale. Tuttavia, assegnando un criterio di posizione a un sito di rete di Lync Server e aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing di E9-1-1 per ogni singolo sito.

<!-- end list -->

  - **Si prevede di abilitare singoli utenti tramite un criterio utente?**  
    Per personalizzare il supporto di E9-1-1, è possibile assegnare i criteri di posizione direttamente a utenti specifici o oggetti contatto telefonico di area comune.

<!-- end list -->

  - **Quando i client vagano all'esterno della rete o si connettono da una subnet non definita, i client devono essere ancora abilitati per E9-1-1?**  
    Se agli utenti viene assegnato un criterio di posizione globale, sito o per utente, è possibile che sia necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni sulla posizione non è stato trovato. Per informazioni dettagliate, vedere [definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

</div>

<span> </span>

</div>

</div>

</div>

