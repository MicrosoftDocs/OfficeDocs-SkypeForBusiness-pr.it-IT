---
title: 'Lync Server 2013: utilizzo di Call me at con un telefono abilitato per Lync'
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
ms.openlocfilehash: 840089b2e65e158086d33f8ebfdfc6828e4e9317
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535823"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Utilizzo di Call me at con un telefono abilitato per Lync e Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-08-09_

La funzionalità Call me at in Lync consente agli utenti di partecipare alla parte audio di una conferenza utilizzando un telefono cellulare, "linea terrestre" o un altro dispositivo connesso alla rete PSTN (Public Switched Telephone Network). Quando si tenta di partecipare a una riunione utilizzando Lync, in genere viene visualizzata la finestra di dialogo **join meeting audio** :

![Utilizzo di Lync per partecipare a una schermata di audioconferenza della finestra riunione](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Utilizzo di Lync per partecipare a una schermata di audioconferenza della finestra riunione")

Se si seleziona **chiamami**, è possibile scegliere un numero di telefono dall'elenco a discesa. Lync Server 2013 invierà una chiamata al numero selezionato ed è quindi possibile utilizzare il telefono per partecipare alla parte audio della conferenza.

L'elenco a discesa è popolato dai numeri di telefono (per telefono cellulare, telefono di casa o altro telefono) immesso nella scheda **telefoni** della finestra di dialogo **Opzioni di Lync** :

![Configurazione delle opzioni per i telefoni Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Configurazione delle opzioni per i telefoni Lync")

Se non sono stati immessi numeri di telefono nella scheda **telefoni** , non saranno disponibili numeri nella casella a discesa. Tuttavia, è sempre possibile fare clic su **nuovo numero** e fare in modo che Lync Server chiami il numero di telefono desiderato:

![Schermata di chiamata di Lync join meeting audio Window](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Schermata di chiamata di Lync join meeting audio Window")

La funzione Call me at è estremamente adatta a condizione che venga utilizzata come previsto: se Lync Server chiama un numero di telefono PSTN. Tuttavia, è possibile eseguire un'esperienza meno che ottimale se si chiede a Lync Server di chiamarla in un endpoint abilitato per Lync, ad esempio un telefono in una sala riunioni. Di seguito è riportato il problema che potrebbe essere eseguito, oltre a due modi per risolvere il problema.

Per iniziare, ecco cosa succede quando si fornisce la funzionalità chiamami alla caratteristica con il numero di telefono di un telefono abilitato per Lync. Si supponga che Ken remario tenti di partecipare a una riunione facendo in modo che Lync Server lo chiami a 1-206-555-1219, un numero di telefono abilitato per Lync Server. Ken verrà inizialmente connesso alla riunione, ma dopo qualche secondo Lync visualizzerà la chiamata del messaggio **non è stata completata o è terminata**e Ken sembra essere stato eliminato dalla riunione:

![Schermata di Lync Call Conferencing Window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Schermata di Lync Call Conferencing Window")

Si noti, tuttavia, che vi è una discrepanza all'interno della finestra di conversazione di Lync. Ken è l'unico nome elencato sotto l'intestazione **partecipanti** . Tuttavia, se si guarda la barra del titolo della finestra, si noterà che la conferenza contiene un totale di 4 partecipanti.

Analogamente, se si cerca nella finestra di conversazione di qualsiasi altro partecipante alla conferenza, non verrà visualizzato nessun elenco di informazioni:

![Schermata della finestra elenco partecipanti di Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Schermata della finestra elenco partecipanti di Lync")

Eppure, allo stesso tempo, Ken è in grado di partecipare alla parte audio della chiamata utilizzando il suo telefono abilitato per Lync. La funzione Call me at ha effettivamente avuto esito positivo, ma l'utilizzo dell'utente è inferiore a quello ottimale.

Esistono almeno due modi per risolvere il problema. Se si è già entrati a far parte di una conferenza in questo modo, come ha fatto Ken, è in genere possibile risolvere il problema coinvolgendo una modalità diversa. Ad esempio, se si invia un messaggio istantaneo, la finestra di conversazione mostrerà tutti i partecipanti alla conferenza, tra cui:

![Schermata della conversazione di Lync e dell'elenco dei partecipanti](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Schermata della conversazione di Lync e dell'elenco dei partecipanti")

A questo punto, è necessario essere in grado di partecipare alla riunione nel modo previsto.

In alternativa, è possibile evitare il problema del tutto cambiando la modalità di partecipazione alla riunione. Se è necessario che Lync Server chiami un telefono abilitato per Lync Server, iniziare a partecipare alla riunione senza una connessione audio. A tale scopo, selezionare non aggiungere l'audio quando viene visualizzata la finestra di dialogo join meeting audio:

![Schermata di Lync Don ' t join the meeting audio Window](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Schermata di Lync Don ' t join the meeting audio Window")

Dopo aver correttamente connesso alla riunione, è ora possibile "invitare" il telefono abilitato per Lync Server anche per partecipare alla riunione. A tale scopo, posizionare il puntatore del mouse sull'icona persone e quindi fare clic su **invita altre persone**:

![Lync invitare altri partecipanti screenshot finestra](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invitare altri partecipanti screenshot finestra")

Verrà visualizzata la finestra di dialogo **Invia una chat** . Ignorare il titolo della finestra di dialogo (non si sta effettivamente inviando un messaggio istantaneo) e digitare il numero di telefono del telefono abilitato per Lync:

![Schermata Invia una finestra di dialogo di messaggistica istantanea](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Schermata Invia una finestra di dialogo di messaggistica istantanea")

Dopo aver fatto clic su **OK**, Lync Server chiamerà il numero immesso nella finestra di dialogo. Quando si effettua la connessione, si avranno funzionalità audio complete tramite il telefono abilitato per Lync e si sarà in grado di visualizzare e interagire con l'elenco completo delle conferenze.

</div>

<span> </span>

</div>

</div>

</div>

