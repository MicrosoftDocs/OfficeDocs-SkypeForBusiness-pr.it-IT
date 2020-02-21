---
title: 'Lync Server 2013: creare e verificare record DNS SRV'
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
ms.openlocfilehash: c7faf0cd00b59d5df5bab1650a28eff8b9563f91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Creare e verificare record DNS SRV in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.

In questo argomento viene descritto come configurare i record DNS (Domain Name System) necessari per la creazione nelle distribuzioni di Lync Server 2013 e quelli necessari per l'accesso automatico dei client. Quando si crea un pool Front End, il programma di installazione crea gli oggetti e le impostazioni di Active Directory per il pool, incluso il nome di dominio completo (FQDN) del pool. Gli oggetti e le impostazioni simili vengono creati per un server Standard Edition. Affinché i client siano in grado di connettersi al pool o al server Standard Edition, il nome di dominio completo del pool o del server Standard Edition deve essere registrato in DNS. È necessario creare record DNS SRV nel sistema DNS interno per ogni dominio SIP. Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Per configurare un record DNS SRV

1.  Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.

2.  Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio SIP in cui verrà installato Lync Server 2013.

3.  Fare clic su **Altri nuovi record**.

4.  In **Selezionare tipo di record di risorsa** fare clic su **Posizione servizio (SRV)** e quindi su **Crea record**.

5.  Fare clic su **servizio**e quindi digitare ** \_sipinternaltls**.

6.  Fare clic su **protocollo**e quindi digitare ** \_TCP**.

7.  Fare clic su **Numero porta** e quindi digitare **5061**.

8.  Fare clic su **host che offre questo servizio**e quindi digitare il nome di dominio completo del pool o del server Standard Edition.

9.  Fare clic su **OK** e quindi su **Fine**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Per verificare la creazione di un record DNS SRV

1.  Accedere a un computer client nel dominio con un account membro del gruppo Authenticated Users o con autorizzazioni equivalenti.

2.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

3.  Nella casella **Apri** digitare **cmd** e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare **nslookup** e quindi premere INVIO.

5.  Digitare **set type=srv** e quindi premere INVIO.

6.  Digitare ** \_sipinternaltls.\_ tcp.contoso.com**e quindi premere INVIO. L'output visualizzato per il record TSL (Transport Layer Security) è il seguente:
    
    Server: \<DNS server\>. contoso.com
    
    Indirizzo: \<indirizzo IP del server DNS\>
    
    Risposta da un server non autorevole:
    
    \_sipinternaltls. \_posizione del servizio TCP.contoso.com SRV:
    
    priorità = 0
    
    Peso = 0
    
    porta = 5061
    
    svr hostname = poolname.contoso.com (o il server Standard Edition A record)
    
    poolname.contoso.com Internet Address = \<indirizzo IP virtuale del bilanciamento del\> carico o \<dell'indirizzo IP di un singolo server Enterprise Edition per i pool con un solo server\> Enterprise Edition \<o un indirizzo IP del server Standard Edition\>

7.  Al termine, digitare **exit** al prompt dei comandi e quindi premere INVIO.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto

1.  Accedere a un computer client nel dominio.

2.  Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

3.  Nella casella **Apri** digitare **cmd** e quindi fare clic su **OK**.

4.  Al prompt dei comandi digitare FQDN **nslookup** \<del pool\> front end o \<FQDN del server\>Standard Edition e quindi premere INVIO.

5.  Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

