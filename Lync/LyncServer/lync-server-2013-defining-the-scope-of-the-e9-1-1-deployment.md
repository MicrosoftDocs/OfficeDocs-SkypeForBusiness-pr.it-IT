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
ms.openlocfilehash: 96f5ac1fb747a3e64be6cc84c44b390de8ce821c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Definizione dell'ambito della distribuzione di E9-1-1 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Prima di configurare Microsoft Lync Server 2013 per E9-1-1, è necessario pianificare la distribuzione di E9-1-1. Alcune delle domande da prendere in considerazione includono:

  - **Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il E9-1-1?**  
    I requisiti legali di E9-1-1 per i PBX (detti sistemi telefonici multilinea o MLTS, in E9-1-1) sono diversi da stato a stato. È consigliabile rivolgersi al proprio team legale per comprendere gli obblighi che possono essere applicati alla distribuzione di Lync Server nelle relative aree geografiche.

<!-- end list -->

  - **Quali aree all'interno dell'organizzazione devono essere abilitate per il E9-1-1?**  
    È possibile abilitare E9-1-1 per l'intera organizzazione o per le posizioni selezionate. Ad esempio, potresti avere requisiti di E9-1-1 diversi per gli uffici in diversi Stati oppure vuoi escludere i siti al di fuori degli Stati Uniti.

<!-- end list -->

  - **Come si distribuisce E9-1-1 a siti di succursale?**  
    La resilienza vocale è un concetto importante da comprendere quando si distribuisce E9-1-1 in un sito di succursale. Se sono presenti trunk SIP e-9-1-1 centralizzati e si verifica un'interruzione WAN, i client che accedono potrebbero non essere in grado di ottenere un percorso dal servizio informazioni sulla posizione o connettersi al provider di servizi di emergenza. Lync Server offre diverse strategie per gestire la resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni ramo o spingere le chiamate di emergenza al gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).

<!-- end list -->

  - **Si Abilita E9-1-1 per gli utenti che lavorano all'esterno della rete?**  
    L'acquisizione automatica della posizione è disponibile solo per i client che si trovano all'interno della rete dell'organizzazione, quindi l'organizzazione deve decidere se supportare le chiamate E9-1-1 effettuate dai client Lync in locale. Ad esempio, puoi consentire agli utenti di inserire chiamate di emergenza se lavorano da casa o da un sito del cliente? Se un client si trova all'esterno della rete aziendale, il client può essere configurato per richiedere all'utente una posizione. Tuttavia, dato che questi percorsi forniti dall'utente non possono essere convalidati rispetto alla guida per gli indirizzi master Street (stradario), il dispatcher del provider di servizi di emergenza dovrà confermare la validità della posizione verbalmente con il chiamante prima del routing chiamata al punto di risposta della sicurezza pubblica (PSAP).
    
    <div>
    

    > [!NOTE]  
    > I client Lync degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni interne sull'indirizzo IP, ma poiché questi indirizzi non possono essere usati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dalla Servizio informazioni sulla posizione.

    
    </div>

<!-- end list -->

  - **Si desidera specificare il routing delle chiamate di emergenza ai siti esterni agli Stati Uniti?**  
    Potrebbe essere necessario disporre di un routing di emergenza per le aree della società non gestite da un provider di servizi di emergenza (ad esempio, posizioni internazionali). A questo scopo, crea un nuovo sito e quindi Assegna criteri vocali ai siti che fanno riferimento a un uso PSTN che instrada la chiamata tramite il gateway PSTN locale.

</div>

<span> </span>

</div>

</div>

</div>

