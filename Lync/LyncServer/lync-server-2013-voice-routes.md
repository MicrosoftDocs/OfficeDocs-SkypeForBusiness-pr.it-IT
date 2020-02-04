---
title: 'Lync Server 2013: Route vocali'
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
ms.openlocfilehash: 42aa810f40a6c00c7f2779acdf39caf39d7b2f07
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Route vocali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Le route di chiamata specificano il modo in cui Lync Server gestisce le chiamate in uscita poste dagli utenti VoIP aziendale. Quando un utente compone un numero, il server front-end normalizza la stringa di chiamata in formato E. 164, se necessario, e tenta di associarla a un URI SIP. Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale per definire la logica consiste nel creare una route di chiamata separata denominata per ogni set di numeri di telefono di destinazione elencati in ogni dial plan.

Prima di definire le route di chiamata in uscita, è necessario eseguire la procedura seguente:

  - Distribuire uno o più trunk.

  - Creare piani di chiamata in base alle esigenze per siti, singoli e oggetti contatto.

  - Creare record di utilizzo PSTN (Public Switched Telephone Network).

Per abilitare il routing delle chiamate in uscita, è inoltre necessario creare e assegnare uno o più criteri vocali. Questa operazione può essere eseguita prima o dopo la definizione delle route di chiamata in uscita.

Per ogni route devi specificare:

  - Nome con cui la route può essere facilmente identificata.

  - Descrizione facoltativa nei casi in cui il nome da solo potrebbe non essere sufficiente per descrivere la route.

  - Modello di corrispondenza delle espressioni regolari che identifica i numeri di telefono di destinazione a cui viene applicata la route, insieme alle eccezioni a cui non deve essere applicato il modello corrispondente.

  - Uno o più trunk che si desidera assegnare alla route.

  - I record di utilizzo PSTN che gli utenti devono avere per chiamare i numeri corrispondenti all'espressione regolare numero di telefono di destinazione.

Puoi specificare le route di chiamata nel pannello di controllo di Lync Server. Queste route di chiamata popolano la tabella di routing del server, che Lync Server usa per instradare le chiamate destinate alla rete PSTN.

<div>

## <a name="mn-trunk-support"></a>Supporto di M:N trunk

Lync Server offre flessibilità per il modo in cui le chiamate vengono instradate alla rete PSTN. Una route vocale specifica un set di trunk alla rete PSTN che può essere usato per una determinata chiamata vocale. Un trunk associa un Mediation Server e un numero di porta con un gateway PSTN e un numero di porta in ascolto. Questa associazione logica consente a un Mediation Server di essere associato a più gateway e di avere più connessioni allo stesso gateway. Quando si definisce una route di chiamata, è necessario specificare i trunk associati alla route, ma non si specificano i server di mediazione associati alla route. Per creare Trunks definendo le relazioni tra Mediation Server e gateway PSTN, IP-PBX e Session Border Controller (SBCs), usare il generatore di topologie.

</div>

<div>

## <a name="least-cost-routing"></a>Routing con costi minimi

La possibilità di specificare i trunk a cui vengono instradati i vari numeri consente di determinare quali Route incorrono i costi più bassi e di implementarle di conseguenza. La regola generale nella selezione di Trunks consiste nel scegliere il trunk con il gateway più vicino alla posizione del numero di destinazione per ridurre al minimo le spese interurbane. Ad esempio, se ci si trova a New York e si chiama un numero a Roma, è necessario portare la chiamata tramite la rete IP verso il trunk con il gateway nell'ufficio di Roma, in modo da incorrere in una tariffa solo per una chiamata locale.

Per un esempio di come potrebbe essere usato il routing con costi minimi, tenere presente quanto segue: Fabrikam decide di consentire agli utenti tedeschi di chiamare i numeri statunitensi usando il trunk degli Stati Uniti. Fabrikam vuole anche configurare il sistema in modo che tutte le chiamate dagli utenti di Lync Server statunitensi alla Germania e i paesi/aree geografiche adiacenti interrompano il trunk con il gateway in Germania. Questo routing consente di risparmiare denaro, perché una chiamata da Germania a Austria, ad esempio, è meno costosa di una chiamata dagli Stati Uniti in Austria.

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>Traduzione di stringhe di chiamata in uscita

Lync Server 2013, come i suoi predecessori immediati, richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Per i trunk con gateway o PBX (Private Branch Exchange) che richiedono numeri tradotti in formati di chiamata locali, Lync Server 2013 consente di creare una o più regole che aiutano a manipolare il numero chiamato (ad esempio, l'URI della richiesta) prima di instradarlo al tronco. Ad esempio, è possibile scrivere una regola per rimuovere + 44 dalla testa di una stringa di chiamata e sostituirla con 0144.

Con Lync Server 2013 è possibile creare una o più regole che aiutano a manipolare il numero chiamante prima di instradarlo al trunk.

Nella pianificazione dei trunk che associano gateway: coppie di porte con Mediation Server: coppie di porte, può essere utile raggruppare trunk con requisiti di chiamata locali simili e quindi ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.

</div>

<div>

## <a name="configuring-caller-id"></a>Configurazione dell'ID chiamante

Lync Server offre un modo per modificare l'ID chiamante per le chiamate in uscita. Ad esempio, se un'organizzazione vuole mascherare le estensioni della chiamata diretta dei dipendenti e sostituirle con il numero generico aziendale o dipartimentale, un amministratore può eseguire questa operazione usando il pannello di controllo di Lync Server per eliminare l'ID chiamante e sostituirlo con un ID chiamante alternativo specificato. Per pianificare la logica di routing, valutare quali utenti, gruppi, siti è consigliabile usare, magari per tutti i dipendenti.

<div>


> [!NOTE]  
> Per le chiamate che vengono reinstradate tramite la rete PSTN, l'ID chiamante generico verrà presentato al posto dell'ID chiamante originale. In questo modo, la chiamata al bypass non disturba o le impostazioni di privacy che il chiamato può configurare.



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>Logica di routing aggiuntiva

Per creare route di chiamata in uscita, è necessario tenere presenti i fattori seguenti che possono influire sulla logica di routing:

  - Quando viene stabilita una chiamata su un contorno federato, viene usata la parte Domain dell'URI per instradare la chiamata all'organizzazione responsabile dell'applicazione della logica di routing in uscita.

  - Se la parte relativa al dominio dell'URI della richiesta non contiene un dominio supportato per l'organizzazione, il componente di routing in uscita nel server non elabora la chiamata.

  - Se un utente non è abilitato per VoIP aziendale, il server applica altre logiche di routing, a seconda delle esigenze.

  - Se una chiamata viene indirizzata a un gateway completamente occupato (tutte le linee di trunk sono occupate), il gateway respinge la chiamata e la logica di routing in uscita reindirizza la chiamata alla route di costo inferiore successiva. Prestare questa considerazione, poiché un gateway dimensionato per un piccolo ufficio oltremare (ad esempio Zurigo) può effettivamente trasportare una quantità significativa di traffico non locale per le chiamate internazionali in Svizzera. Se il gateway non è dimensionato correttamente per il traffico aggiuntivo, le chiamate in Svizzera possono essere instradate tramite un gateway in Germania, con conseguente pagamento di pedaggio più ampio.

</div>

</div>

<span> </span>

</div>

</div>

</div>

