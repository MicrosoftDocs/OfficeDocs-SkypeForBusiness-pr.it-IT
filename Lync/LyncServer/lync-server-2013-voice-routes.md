---
title: 'Lync Server 2013: route vocali'
description: 'Lync Server 2013: route vocali.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f3c548890c6d2a8c16808eebd9dd50e3ed2715
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554052"
---
# <a name="voice-routes-in-lync-server-2013"></a>Route vocali in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Route di chiamata specificare in che modo Lync Server gestisce le chiamate in uscita effettuate dagli utenti di VoIP aziendale. Quando un utente compone un numero, il front end Server normalizza la stringa di composizione nel formato E. 164, se necessario, e tenta di corrispondere a un URI SIP. Se il server non riesce a effettuare l'associazione, applica la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale della definizione della logica consiste nel creare una route di chiamata denominata separata per ogni insieme di numeri di telefono di destinazione elencati in ogni dial plan.

Prima di definire le route delle chiamate in uscita, è necessario completare le operazioni seguenti:

  - Distribuire uno o più trunk.

  - Creare dial plan in base alle necessità per siti, individui e oggetti contatto.

  - Creare record di utilizzo PSTN (Public Switched Telephone Network).

Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali. È possibile eseguire questa attività prima o dopo avere definito le route delle chiamate in uscita.

Per ogni route, è necessario specificare:

  - Un nome in base al quale la route possa essere facilmente identificata.

  - Una descrizione facoltativa per i casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.

  - Il formato di corrispondenza dell'espressione regolare per l'identificazione dei numeri di telefono di destinazione a cui è applicata la route e le eccezioni a cui il formato di corrispondenza non deve essere applicato.

  - Uno o più trunk che si desidera assegnare alla route.

  - I record di utilizzo PSTN di cui gli utenti devono disporre per chiamare i numeri corrispondenti all'espressione regolare dei numeri di telefono di destinazione.

È possibile specificare le route di chiamata nel pannello di controllo di Lync Server. Queste route di chiamata popolano la tabella di routing del server, che Lync Server utilizza per instradare le chiamate destinate alla rete PSTN.

<div>

## <a name="mn-trunk-support"></a>Supporto dei trunk M:N

Lync Server fornisce flessibilità per il modo in cui le chiamate vengono instradate alla rete PSTN. Una route vocale specifica un insieme di trunk alla rete PSTN che possono essere utilizzati per una determinata chiamata vocale. Un trunk associa un Mediation Server e un numero di porta con un gateway PSTN e un numero di porta di attesa. Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di disporre di più connessioni allo stesso gateway. Quando si definisce una route di chiamata, è necessario specificare i trunk associati a tale route, ma non si specifica quali Mediation Server sono associati alla route. Per creare trunk definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e Session Border Controller (SBCs), utilizzare il generatore di topologie.

</div>

<div>

## <a name="least-cost-routing"></a>Least Cost Routing

La possibilità di specificare i trunk verso cui vengono instradati diversi numeri consente di determinare quali route comportano i costi minori e di implementarle di conseguenza. In generale, per ridurre i costi delle chiamate interurbane, è consigliabile scegliere il trunk con il gateway più vicino alla località del numero di destinazione. Se ad esempio ci si trova a New York e si sta chiamando un numero a Roma, è possibile trasmettere la chiamata tramite la rete IP al trunk con il gateway nell'ufficio di Roma, sostenendo in questo modo solo i costi di una chiamata locale.

Per un esempio del modo in cui è possibile utilizzare il routing a costi minimi, prendere in considerazione quanto segue: Fabrikam decide di abilitare gli utenti tedeschi a comporre numeri statunitensi usando il trunk degli Stati Uniti. Anche Fabrikam desidera configurare il sistema in modo che tutte le chiamate provenienti da utenti di Lync Server statunitensi verso la Germania e i paesi/aree adiacenti terminano nel trunk con il gateway in Germania. Questo routing consente di risparmiare denaro, perché una chiamata dalla Germania all'Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti all'Austria.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Conversione delle stringhe di composizione in uscita

Lync Server 2013, come i suoi predecessori immediati, richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa). Per i trunk con gateway o PBX (Private Branch Exchange) che richiedono numeri tradotti nei formati di composizione locali, Lync Server 2013 consente di creare una o più regole che consentono di modificare il numero chiamato (ovvero l'URI della richiesta) prima di instradarlo al trunk. È ad esempio possibile scrivere una regola per rimuovere il prefisso +44 all'inizio di una stringa di composizione e sostituirlo con 0144.

Con Lync Server 2013, è possibile creare una o più regole che agevolano la manipolazione del numero di chiamata prima di instradarlo al trunk.

Nella pianificazione dei trunk che associano i gateway: coppie di porte con Mediation Server: coppie di porte, può essere utile raggruppare trunk con requisiti di composizione locali simili e quindi ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverle.

</div>

<div>

## <a name="configuring-caller-id"></a>Configurazione dell'ID chiamante

Lync Server consente di modificare l'ID chiamante per le chiamate in uscita. Ad esempio, se un'organizzazione desidera mascherare le estensioni di composizione diretta dei dipendenti e sostituirle con il numero generico aziendale o dipartimentale, un amministratore può eseguire tale operazione utilizzando il pannello di controllo di Lync Server per sopprimere l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato. Nella pianificazione della logica di routing considerare per quali singoli, gruppi o siti si desidera tale opzione oppure se deve essere applicata addirittura per tutti i dipendenti.

<div>


> [!NOTE]  
> Per le chiamate reinoltrate tramite PSTN, verrà visualizzato l'ID chiamante generico anziché quello originario. La chiamata potrebbe quindi ignorare eventuali impostazioni Non disturbare o di privacy configurate dal destinatario.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Logica di routing aggiuntiva

Durante la creazione delle route delle chiamate in uscita, tenere presente i fattori seguenti che influiscono sulla logica di routing:

  - Nelle situazioni in cui viene effettuata una chiamata attraverso un confine federato, la parte dell'URI relativa al dominio viene utilizzata per instradare la chiamata all'azienda responsabile dell'applicazione della logica di routing in uscita.

  - Se la parte dell'URI della richiesta relativa al dominio non contiene un dominio supportato per l'azienda, il componente di routing in uscita nel server non elabora la chiamata.

  - Se un utente non è abilitato per VoIP aziendale, il server applica un'altra logica di routing, a seconda dei casi.

  - Se una chiamata viene instradata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway rifiuta la chiamata e la logica di routing in uscita la reindirizza alla successiva route Least Cost Routing. È necessario valutare con attenzione questo aspetto perché un gateway adatto nelle dimensioni a una piccola sede all'estero, ad esempio Zurigo, potrebbe in realtà trasportare una quantità significativa di traffico non locale per le chiamate internazionali dirette in Svizzera. Se il gateway non presenta dimensioni adeguate a questo traffico aggiuntivo, le chiamate dirette in Svizzera potrebbero essere instradate mediante un gateway in Germania, con conseguenti tariffe più alte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

