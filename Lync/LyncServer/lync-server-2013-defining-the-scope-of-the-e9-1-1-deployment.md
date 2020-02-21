---
title: "Lync Server 2013: definizione dell'ambito della distribuzione di E9-1-1"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed4a5fb3e34192aab9c94d72a3bc79b733828e3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-06_

Prima di configurare Microsoft Lync Server 2013 per il servizio E9-1-1, è necessario pianificare la distribuzione di E9-1-1. Di seguito sono riportati alcuni aspetti di cui tenere conto:

  - **Politica aziendale e vincoli di tipo legale dell'organizzazione per il servizio E9-1-1**  
    Le disposizioni legali del servizio E9-1-1 per i PBX (denominati sistemi telefonici multilinea, o MLTS, nella terminologia relativa a E9-1-1) variano a seconda delle località. È consigliabile rivolgersi al proprio team legale per capire gli obblighi che possono essere applicati alla distribuzione di Lync Server nelle rispettive aree geografiche.

<!-- end list -->

  - **Aree dell'organizzazione che devono essere abilitate per il servizio E9-1-1**  
    È possibile abilitare il servizio E9-1-1 per l'intera organizzazione o solo per località selezionate. È ad esempio possibile applicare requisiti E9-1-1 diversi per gli uffici di stati diversi oppure escludere le sedi al di fuori degli Stati Uniti.

<!-- end list -->

  - **Modalità di distribuzione del servizio E9-1-1 nei siti di succursale**  
    La resilienza vocale è un concetto importante di cui tenere conto quando si distribuisce il servizio E9-1-1 in un sito di succursale. Se si dispone di trunk SIP e-9-1-1 centralizzato e si verifica un'interruzione della rete WAN, i client che effettuano l'accesso potrebbero non essere in grado di ottenere un percorso dal servizio informazioni percorso o connettersi al provider di servizi di emergenza. In Lync Server sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni branch o la pressione delle chiamate di emergenza verso il gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Possibilità di abilitare il servizio E9-1-1 per gli utenti che lavorano all'esterno della rete**  
    L'acquisizione automatica della posizione è disponibile solo per i client all'interno della rete aziendale. L'organizzazione deve pertanto decidere se supportare le chiamate E9-1-1 effettuate da client Lync non locali, ad esempio se consentire agli utenti di effettuare chiamate di emergenza quando lavorano dalla propria abitazione o dalla sede di un cliente. Se è posizionato all'esterno di una rete aziendale, un client può essere configurato per richiedere la posizione a un utente. Poiché tuttavia queste posizioni fornite dagli utenti non possono essere precedentemente convalidate a fronte dello stradario generale, il dispatcher del provider di servizi di emergenza dovrà verificare la validità della posizione verbalmente con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).
    
    <div>
    

    > [!NOTE]  
    > I client Lync degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni sull'indirizzo IP interno, ma poiché questi indirizzi non possono essere utilizzati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dal Servizio informazioni percorso.

    
    </div>

<!-- end list -->

  - **Possibilità di fornire il routing delle chiamate di emergenza per siti al di fuori degli Stati Uniti**  
    È possibile offrire il routing delle chiamate di emergenza per aree dell'azienda non servite dal provider di servizi di emergenza, ad esempio sedi internazionali. A tale scopo, creare un nuovo sito e quindi assegnare i criteri vocali ai siti che fanno riferimento a un utilizzo PSTN che instrada le chiamate tramite il gateway PSTN locale.

</div>

<span> </span>

</div>

</div>

</div>

