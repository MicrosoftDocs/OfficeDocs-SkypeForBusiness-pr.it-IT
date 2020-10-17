---
title: Verificare l'ambiente Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify Lync Server 2010 environment
ms:assetid: bfc7c620-556a-43cd-b1ed-2c268ec2b5cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205231(v=OCS.15)
ms:contentKeyID: 48185301
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a98bdaa5b97193ad20a78939560190a413a87161
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515973"
---
# <a name="verify-lync-server-2010-environment"></a>Verificare l'ambiente Lync Server 2010

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario verificare che i servizi di Lync Server 2010 siano stati configurati e avviati. È importante identificare i servizi e le funzionalità principali presenti nell'ambiente legacy, prima di distribuire un pool pilota di Lync Server 2013. Prima di distribuire Microsoft Lync Server 2013 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare quale partner federato supporta la configurazione di XMPP legacy. La verifica della distribuzione di Lync Server 2010 legacy comporta quanto segue:

  - Verificare che i servizi di Lync Server 2010 siano stati avviati

  - Revisione della topologia e degli utenti in Lync Server 2010.

  - Verificare le impostazioni di federazione e server perimetrali.

  - Verificare i servizi e i partner federati XMPP.

**Verificare che i servizi Lync Server 2010 siano stati avviati**

1.  Dal front end server di Lync Server 2010 passare all'applet servizi di amministrazione degli strumenti \\ .

2.  Verificare che i servizi seguenti siano in esecuzione nel Front End Server:
    
    ![Elenco dei servizi in esecuzione nel front end server](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Elenco dei servizi in esecuzione nel front end server")

**Esaminare la topologia di Lync Server 2010 nel pannello di controllo di Lync Server**

1.  Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.

2.  Aprire il Pannello di controllo di Lync Server.

3.  Selezionare **Topologia**. Verificare che siano elencati i vari server della distribuzione di Lync Server 2010.
    
    ![Pagina della topologia del pannello di controllo di Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Pagina della topologia del pannello di controllo di Lync Server 2010")

**Per esaminare gli utenti di Lync Server 2010 nel pannello di controllo di Lync Server**

1.  Aprire il Pannello di controllo di Lync Server.

2.  Selezionare **Utenti** e quindi fare clic su **Trova**.

3.  Verificare che la colonna **pool di registrazione** punti al pool Lync Server 2010 per ogni utente elencato.
    
    ![Pannello di controllo di Lync Server 2010 che elenca gli utenti](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Pannello di controllo di Lync Server 2010 che elenca gli utenti")

**Per verificare le impostazioni di Federazione e Edge di Lync Server 2010**

1.  Avviare Generatore di topologie.

2.  Selezionare **Scarica topologia dalla distribuzione esistente**.

3.  Scegliere un nome di file e salvare la topologia come tipo di file predefinito, ovvero con l'estensione tbxml.

4.  Espandere il nodo Lync Server 2010 per rivelare i diversi ruoli del server nella distribuzione.

5.  Selezionare il nodo del sito e verificare se è impostato un valore **Assegnazione route federazione sito**.
    
    ![Generatore di topologie, route di Federazione del sito](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generatore di topologie, route di Federazione del sito")

6.  Selezionare quindi lo Standard Edition Front End Server o il pool Enterprise Edition Front End. Determinare se è stato configurato un pool di server perimetrali (per componenti multimediali) in **Associazioni**.
    
    ![Generatore di topologie che Mostra server e pool](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generatore di topologie che Mostra server e pool")

7.  Selezionare infine il pool di server perimetrali e identificare se è configurato un pool hop successivo in **Selezione hop successivo**.
    
    ![Generatore di topologie, selezione dell'hop successivo](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generatore di topologie, selezione dell'hop successivo")

**Verificare la configurazione del partner federato XMPP legacy**

1.  Dal server XMPP legacy, accedere all'applet servizi di amministrazione degli strumenti \\ .

2.  Verificare che il servizio Office Communications Server XMPP Gateway sia stato avviato.
    
    ![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

