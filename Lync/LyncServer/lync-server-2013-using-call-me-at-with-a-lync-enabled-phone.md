---
title: 'Lync Server 2013: usare Chiamami con un telefono abilitato per Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d4b117970cec1e40b4d18928f82bc0cf2831eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Uso di Call me at con un telefono abilitato per Lync e Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-08-09_

La funzionalità chiamami at in Lync consente agli utenti di partecipare alla parte audio di una conferenza utilizzando un telefono cellulare, "linea di terra" o un altro dispositivo connesso alla rete PSTN (Public Switched Telephone Network). Quando si tenta di partecipare a una riunione usando Lync, viene in genere visualizzata la finestra di dialogo **partecipa all'audio della riunione** :

![Cattura di schermata della finestra per partecipare all'audio della riunione tramite Lync](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Cattura di schermata della finestra per partecipare all'audio della riunione tramite Lync")

Se si seleziona **chiama**, è possibile selezionare un numero di telefono nell'elenco a discesa. Lync Server 2013 effettua una chiamata telefonica al numero selezionato ed è quindi possibile usare il telefono per partecipare alla parte audio della conferenza.

L'elenco a discesa viene popolato dai numeri di telefono (per cellulare, telefono di casa o altro telefono) immesso nella scheda **telefoni** nella finestra di dialogo **Lync-Opzioni** :

![Cattura di schermata delle opzioni di configurazione di Lync Phone](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Cattura di schermata delle opzioni di configurazione di Lync Phone")

Se non sono stati immessi numeri di telefono nella scheda **telefoni** , non saranno disponibili numeri nella casella a discesa. Tuttavia, è sempre possibile fare clic su **nuovo numero** e far eseguire la chiamata di Lync Server a qualsiasi numero di telefono desiderato:

![Cattura di schermata della finestra Chiama per partecipare all'audio della riunione di Lync](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Cattura di schermata della finestra Chiama per partecipare all'audio della riunione di Lync")

La caratteristica chiamami at funziona molto bene a condizione che la usi come previsto: avendo Lync Server chiama un numero di telefono PSTN. Puoi tuttavia eseguire un'esperienza meno che ottimale se Chiedi a Lync Server di chiamarti presso un endpoint abilitato per Lync, ad esempio un telefono in una sala riunioni. Di seguito è riportato il problema che potrebbe essere eseguito, oltre a due modi per aggirare il problema.

Per iniziare, ecco cosa succede quando si specifica la funzionalità chiamami at con il numero di telefono di un telefono abilitato per Lync. Supponiamo che Ken si tenti di partecipare a una riunione facendolo chiamare da Lync Server in 1-206-555-1219, un numero di telefono abilitato per Lync Server. Ken verrà inizialmente connesso alla riunione, ma dopo pochi secondi Lync visualizzerà la chiamata al messaggio **non è stata completata o è terminata**e Ken sembrerà essere stato eliminato dalla riunione:

![Cattura di schermata della finestra della conferenza telefonica Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Cattura di schermata della finestra della conferenza telefonica Lync")

Si noti tuttavia che c'è una discrepanza all'interno della finestra di conversazione di Lync. Ken è l'unico nome elencato sotto l'intestazione **partecipanti** . Tuttavia, se si guarda nella barra del titolo della finestra, si noterà che la conferenza contiene un totale di 4 partecipanti.

Allo stesso modo, se si cerca nella finestra di conversazione di uno degli altri partecipanti alla conferenza, non verrà visualizzato nessun altro elenco:

![Cattura di schermata della finestra dell'elenco dei partecipanti di Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Cattura di schermata della finestra dell'elenco dei partecipanti di Lync")

Eppure, allo stesso tempo, Ken è in grado di partecipare alla parte audio della chiamata usando il suo telefono abilitato per Lync. La funzionalità chiamami at ha effettivamente funzionato, ma l'esperienza utente è meno che ottimale.

Esistono almeno due modi per aggirare il problema. Se si è già partecipato a una conferenza in questo modo (come ha fatto Ken reparti), in genere è possibile risolvere il problema applicando una modalità diversa. Ad esempio, se si invia un messaggio istantaneo, la finestra di conversazione mostrerà tutti i partecipanti alla conferenza, incluso il personale:

![Cattura di schermata della conversazione di Lync e dell'elenco dei partecipanti](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Cattura di schermata della conversazione di Lync e dell'elenco dei partecipanti")

A questo punto dovresti essere in grado di partecipare alla riunione in modo atteso.

In alternativa, è possibile evitare tutto questo problema modificando il modo in cui si partecipa alla riunione. Se è necessario che Lync Server chiami un telefono abilitato per Lync Server, iniziare a partecipare alla riunione senza una connessione audio. A tale scopo, selezionare non partecipare all'audio quando viene visualizzata la finestra di dialogo partecipa all'audio della riunione:

![Cattura di schermata della finestra per non partecipare all'audio della riunione di Lync](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Cattura di schermata della finestra per non partecipare all'audio della riunione di Lync")

Dopo aver completato la connessione alla riunione, è ora possibile "invitare" il telefono abilitato per Lync Server anche per partecipare alla riunione. A tale scopo, posizionare il puntatore del mouse sull'icona persone e quindi fare clic su **invita altre persone**:

![Cattura di schermata della finestra per invitare altri partecipanti di Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Cattura di schermata della finestra per invitare altri partecipanti di Lync")

Verrà visualizzata la finestra di dialogo **Invia un messaggio istantaneo** . Ignorare il titolo della finestra di dialogo (in realtà non si sta inviando un messaggio istantaneo) e digitare il numero di telefono del telefono abilitato per Lync:

![Cattura di schermata della finestra di dialogo Invia un messaggio istantaneo](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Cattura di schermata della finestra di dialogo Invia un messaggio istantaneo")

Dopo aver fatto clic su **OK**, Lync Server chiamerà il numero immesso nella finestra di dialogo. Quando si effettua la connessione, si avranno funzionalità audio complete tramite il telefono abilitato per Lync e sarà possibile vedere e interagire con l'elenco completo delle conferenze.

</div>

<span> </span>

</div>

</div>

</div>

