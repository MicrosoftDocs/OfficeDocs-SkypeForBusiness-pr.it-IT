---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc9f88d731873a16535e80eb0726aec8335e447b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Distribuire Edge Server pilota

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima della distribuzione del server Edge di Lync Server 2013. I processi di distribuzione e configurazione per Lync Server 2013 sono molto simili a Lync Server 2010. Questa sezione evidenzia solo i punti chiave da tenere in considerazione nell'ambito della distribuzione del pool pilota. Per la procedura dettagliata, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, che descrive il processo di distribuzione e fornisce anche informazioni sulla configurazione per l'accesso degli utenti esterni.

Mentre ci si sposta nella procedura guidata **Definisci nuovo pool Edge** , rivedere le impostazioni di configurazione chiave illustrate nella procedura seguente. Tieni presente che vengono visualizzate solo alcune pagine della procedura guidata **Definisci nuovo pool di Edge** .

**Definire un pool di bordi**

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Passare al nodo Lync Server 2013. Fare clic con il pulsante destro del mouse su pool **Edge**e scegliere **nuovo pool di bordi**.
    
    ![Finestra di dialogo Definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo Definire il nuovo pool di server perimetrali")

3.  Un pool di Edge può essere un pool di **computer multipli** o un pool di **computer singolo**.
    
    ![Finestra di dialogo Definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo Definire l'FQDN del pool di server perimetrali")

4.  Nella pagina **Seleziona funzionalità** non abilitare la Federazione o la Federazione XMPP. Federazione e Federazione XMPP sono entrambi attualmente instradati attraverso il server perimetrale Lync Server 2010 legacy. Queste caratteristiche verranno configurate in una fase successiva della migrazione.
    
    ![Finestra di dialogo Selezionare funzionalità](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Selezionare funzionalità")

5.  Continuare quindi a completare le pagine della procedura guidata seguenti: **FQDN esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.

6.  Nella pagina **Definisci l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2010.
    
    ![Finestra di dialogo Definire l'hop successivo](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Finestra di dialogo Definire l'hop successivo")

7.  Nella pagina **Associa pool di mediazione o front-end** non associare un pool a questo pool di Edge in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale Lync Server 2010 legacy. Questa impostazione verrà configurata in una fase successiva della migrazione.
    
    ![Finestra di dialogo Associare pool Front End](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Finestra di dialogo Associare pool Front End")

8.  Fare clic su **fine** e quindi **pubblicare** la topologia.

9.  Seguire la procedura descritta in [installare Edge Server per Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Edge Server, configurare i certificati e avviare i servizi.

È molto importante seguire le linee guida degli argomenti relativi alla [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. Questa sezione ha semplicemente fornito alcune indicazioni sulle impostazioni di configurazione durante l'installazione di questi ruoli del server.

Ora dovresti avere un server perimetrale Lync Server 2010 distribuito in parallelo con una distribuzione di Lync Server 2013 Edge Server. Verificare che entrambe le distribuzioni vengano eseguite correttamente, i servizi vengano avviati ed è possibile amministrare ogni distribuzione prima di passare alla fase successiva.

</div>

<span> </span>

</div>

</div>

</div>

