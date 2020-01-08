---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e171e821d2fcf5c773321ada3a5b107b28314699
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Aggiornare i record SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

Questo argomento descrive come aggiornare i record DNS (Domain Name System) dopo la migrazione a Lync Server 2013. Dopo che tutti gli utenti sono stati spostati in Lync Server 2013, ma prima che il pool o il Director legacy Lync Server 2010 venga disattivati, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP. Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.

**Per configurare un record SRV DNS**

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**, espandere il dominio SIP in cui è installato Lync Server 2013 e passare all'impostazione ** \_TCP** .

3.  Nel riquadro destro fare clic con il pulsante destro del mouse su ** \_sipinternaltls** e scegliere **proprietà**.

4.  In **host che offre questo servizio**aggiornare il nome di dominio completo dell'host per posizionare il puntatore sul pool di Lync Server 2013.

5.  Fare clic su **OK**.

**Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto**

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

3.  Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare il nome di dominio completo **nslookup** \<del pool\> di \<front end o il nome di\>dominio completo del server Standard Edition, quindi premere INVIO.

5.  Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.

</div>

<span> </span>

</div>

</div>

</div>

