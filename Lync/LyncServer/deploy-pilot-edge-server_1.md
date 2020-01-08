---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975204"
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

Questo argomento evidenzia le impostazioni di configurazione da tenere presenti prima della distribuzione del server Edge di Lync Server 2013. Questa sezione evidenzia solo i punti chiave da considerare come parte della distribuzione del pool di Edge pilota. Per la procedura dettagliata, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, che descrive il processo di distribuzione e fornisce anche informazioni sulla configurazione per l'accesso degli utenti esterni.

Mentre ci si sposta nella procedura guidata **Definisci nuovo pool Edge** , rivedere le impostazioni di configurazione chiave illustrate nella procedura seguente. Tieni presente che vengono visualizzate solo alcune pagine della procedura guidata **Definisci nuovo pool di Edge** .

**Definire un pool di bordi**

1.  Aprire la topologia del pool di Pilot usando generatore di topologia.

2.  Passare al nodo Lync Server 2013. Fare clic con il pulsante destro del mouse su pool **Edge**e scegliere **nuovo pool di bordi**.
    
    ![Definire la finestra di dialogo nuovo pool di bordi](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "definire la finestra di dialogo nuovo pool di bordi")

3.  Un pool di Edge può essere un pool di **computer multipli** o un pool di **computer singolo**.
    
    ![Definire la finestra di dialogo FQDN pool Edge](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definisci la finestra di dialogo FQDN pool di Edge")

4.  Nella pagina **Seleziona funzionalità** non abilitare la Federazione o la Federazione XMPP. Federazione e Federazione XMPP sono attualmente instradati attraverso il server perimetrale legacy di Office Communications Server 2007 R2. Queste caratteristiche verranno configurate in una fase successiva della migrazione.
    
    Finestra di dialogo ![Seleziona caratteristiche]selezionare la finestra di(images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "dialogo caratteristiche")

5.  Continuare quindi a completare le pagine della procedura guidata seguenti: **selezionare opzioni IP**, nomi di **dominio completi esterni**, **definire l'indirizzo IP interno**e **definire l'indirizzo IP esterno**.

6.  Nella pagina **Definisci l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2013.
    
    ![Finestra di dialogo Definisci nuovo pool di bordi, elenco pool hop successivo](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Definisci nuova finestra di dialogo bordo piscina, elenco pool hop successivo")

7.  Nella pagina **Associa pool Front-End** non associare un pool a questo pool di Edge in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale legacy di Office Communications Server 2007 R2. Questa impostazione verrà configurata in una fase successiva della migrazione.
    
    (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Finestra di") ![dialogo Definisci nuovo pool di bordi]

8.  Fare clic su **fine** e quindi **pubblicare** la topologia.

9.  Seguire la procedura descritta in [installare Edge Server per Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Edge Server, configurare i certificati e avviare i servizi.

È molto importante seguire le linee guida degli argomenti relativi alla [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. Questa sezione ha semplicemente fornito alcune indicazioni sulle impostazioni di configurazione durante l'installazione di questi ruoli del server.

Ora dovresti avere una distribuzione legacy di Office Communications Server 2007 R2 Edge Server, indicata dalla presenza di BackCompatSite, in parallelo con una distribuzione di Lync Server 2013 Edge Server. La Federazione è configurata per l'uso di Office Communications Server 2007 R2 Director. Verificare che entrambe le distribuzioni vengano eseguite correttamente, i servizi vengano avviati ed è possibile amministrare ogni distribuzione prima di passare alla fase successiva.

![Generatore di topologia che mostra]generatore di topologia OCS Edge Server con(images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "OCS Edge Server")

</div>

<span> </span>

</div>

</div>

</div>

