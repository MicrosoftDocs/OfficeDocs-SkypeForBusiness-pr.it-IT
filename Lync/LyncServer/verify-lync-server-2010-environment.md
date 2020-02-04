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
ms.openlocfilehash: 2a871955f53515491ed09ece5e5da21ef7a9fef8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-lync-server-2010-environment"></a>Verificare l'ambiente Lync Server 2010

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Prima di distribuire Lync Server 2013 in uno stato di coesistenza con Lync Server 2010, è necessario verificare che i servizi di Lync Server 2010 siano stati configurati e avviati. È importante identificare i servizi e le caratteristiche principali presenti nell'ambiente legacy, prima di distribuire un pool di piloti di Lync Server 2013. Prima di distribuire Microsoft Lync Server 2013 XMPP in uno stato di coesistenza con una distribuzione XMPP legacy, è necessario verificare che i servizi XMPP legacy siano stati configurati e avviati e identificare il partner federativo supportato dalla configurazione XMPP legacy. Per verificare la distribuzione legacy di Lync Server 2010, è richiesto quanto segue:

  - La verifica dei servizi di Lync Server 2010 viene avviata

  - Revisione della topologia e degli utenti in Lync Server 2010.

  - Verificare le impostazioni della Federazione e del server perimetrale.

  - Verificare i servizi XMPP e i partner federati.

**Verificare che i servizi di Lync Server 2010 siano avviati**

1.  Dal server front-end di Lync Server 2010 passare all'applet strumenti\\di amministrazione di servizi.

2.  Verificare che i servizi seguenti siano in uso nel server front-end:
    
    ![Elenco dei servizi in esecuzione nel server Front End](images/JJ205231.639f2729-b759-4d8e-b4ad-59d7f68adcd2(OCS.15).jpg "Elenco dei servizi in esecuzione nel server Front End")

**Esaminare la topologia di Lync Server 2010 nel pannello di controllo di Lync Server**

1.  Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.

2.  Aprire il pannello di controllo di Lync Server.

3.  Selezionare **topologia**. Verificare che siano elencati i vari server della distribuzione di Lync Server 2010.
    
    ![Pagina della topologia del Pannello di controllo di Lync Server 2010](images/JJ205231.338ce4fb-2162-4176-a249-ec4ae021fa6a(OCS.15).jpg "Pagina della topologia del Pannello di controllo di Lync Server 2010")

**Per esaminare gli utenti di Lync Server 2010 nel pannello di controllo di Lync Server**

1.  Aprire il pannello di controllo di Lync Server.

2.  Selezionare **utenti** e quindi fare clic su **trova**.

3.  Verificare che la colonna del **pool di registrazione** punti al pool di Lync Server 2010 per ogni utente elencato.
    
    ![Elenco utenti nel Pannello di controllo di Lync Server 2010](images/JJ205231.a9378c40-7a52-4c78-ad83-1463847c9edb(OCS.15).jpg "Elenco utenti nel Pannello di controllo di Lync Server 2010")

**Per verificare le impostazioni di Edge e federativo di Lync Server 2010**

1.  Avviare Generatore di topologie.

2.  Selezionare **Scarica topologia dalla distribuzione esistente**.

3.  Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.

4.  Espandere il nodo Lync Server 2010 per rivelare i vari ruoli del server nella distribuzione.

5.  Selezionare il nodo del sito e verificare se è impostato un valore di **assegnazione della route federativo del sito** .
    
    ![Generatore di topologie - Route federazione sito](images/JJ205231.87de3735-af7e-4280-8d72-c42cb0ea1c05(OCS.15).jpg "Generatore di topologie - Route federazione sito")

6.  Selezionare quindi il pool di front end del server Standard Edition o Enterprise Edition. Determinare se un pool di bordi è stato configurato per elementi multimediali al di sotto delle **associazioni**.
    
    ![Generatore di topologie con server e pool](images/JJ205231.5ad5ea3b-b122-44dd-8968-f1147d6d45f1(OCS.15).jpg "Generatore di topologie con server e pool")

7.  Infine, seleziona il pool di bordi e identifica se un pool di hop successivo è configurato sotto la **selezione dell'hop successivo**.
    
    ![Generatore di topologie - Selezione hop successivo](images/JJ205231.3121e723-fba7-498e-a786-bde7be1a55e2(OCS.15).jpg "Generatore di topologie - Selezione hop successivo")

**Verificare la configurazione legacy del partner federato XMPP**

1.  Dal server XMPP legacy, passare all'applet strumenti\\di amministrazione di servizi.

2.  Verificare che il servizio gateway XMPP di Office Communications Server sia stato avviato.
    
    ![Servizio gateway XMPP di Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servizio gateway XMPP di Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

