---
title: 'Lync Server 2013: Creare e verificare record DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Creare e verificare record DNS SRV in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

Questo argomento descrive come configurare i record DNS (Domain Name System) necessari per la creazione nelle distribuzioni di Lync Server 2013 e quelle necessarie per l'accesso automatico del client. Quando si crea un pool Front-End, il programma di installazione crea oggetti e impostazioni di Active Directory per il pool, incluso il nome di dominio completo (FQDN) del pool. Gli oggetti e le impostazioni simili vengono creati per un server Standard Edition. Per consentire ai client di connettersi al pool o al server Standard Edition, il nome di dominio completo del pool o del server Standard Edition deve essere registrato in DNS. È necessario creare record SRV DNS nel DNS interno per ogni dominio SIP. Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Per configurare un record SRV DNS

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio SIP in cui verrà installato Lync Server 2013.

3.  Fare clic su **altri nuovi record**.

4.  In **selezionare un tipo di record delle risorse**fare clic su **posizione servizio (SRV)** e quindi su **Crea record**.

5.  Fare clic su **servizio**e quindi digitare ** \_sipinternaltls**.

6.  Fare clic su **protocollo**e quindi digitare ** \_TCP**.

7.  Fare clic su **numero di porta**e quindi digitare **5061**.

8.  Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo del pool o del server Standard Edition.

9.  Fare clic su **OK**e quindi su **fine**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Per verificare la creazione di un record SRV DNS

1.  Accedere a un computer client nel dominio con un account membro del gruppo Authenticated Users o con autorizzazioni equivalenti.

2.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

3.  Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare **nslookup**e quindi premere INVIO.

5.  Digitare **set type = srv**e quindi premere INVIO.

6.  Digitare ** \_sipinternaltls.\_ tcp.contoso.com**e quindi premere INVIO. L'output visualizzato per il record TLS (Transport Layer Security) è il seguente:
    
    Server: \<DNS server\>. contoso.com
    
    Indirizzo: \<indirizzo IP del server DNS\>
    
    Risposta non autorevole:
    
    \_sipinternaltls. \_posizione del servizio SRV di TCP.contoso.com:
    
    Priority = 0
    
    Peso = 0
    
    porta = 5061
    
    svr hostname = poolname.contoso.com (o Standard Edition Server A record)
    
    Indirizzo Internet poolname.contoso.com = \<indirizzo IP virtuale del bilanciamento del\> carico o \<dell'indirizzo IP di un singolo server Enterprise Edition per i pool con un solo server\> Enterprise o \<un indirizzo IP del server Standard Edition\>

7.  Al termine, al prompt dei comandi digitare **Exit**e quindi premere INVIO.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start**e quindi su **Esegui**.

3.  Nella casella **Apri** Digitare **cmd**e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare il nome di dominio completo **nslookup** \<del pool\> di \<front end o il nome di\>dominio completo del server Standard Edition, quindi premere INVIO.

5.  Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

