---
title: Distribuire Edge Server pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b7cf106cb8c65f01a1c1935ff98a8f9d428b27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502933"
---
# <a name="deploy-pilot-edge-server"></a>Distribuire Edge Server pilota

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

In questo argomento vengono evidenziate le impostazioni di configurazione di cui tenere conto prima di distribuire il server perimetrale di Lync Server 2013. In questa sezione vengono evidenziati solo i punti chiave di cui è consigliabile tenere conto nell'ambito della distribuzione del pool di server perimetrali pilota. Per la procedura dettagliata, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione, in cui viene descritto il processo di distribuzione e vengono fornite anche informazioni di configurazione per l'accesso degli utenti esterni.

Man mano che si va avanti nella procedura guidata **Definisci pool di server perimetrali**, esaminare le impostazioni di configurazione chiave illustrate nei passaggi seguenti. Si noti che sono visualizzate solo alcune pagine della procedura guidata **Definisci pool di server perimetrali**.

**Definire un pool di server perimetrali**

1.  Aprire la topologia pool pilota utilizzando Generatore di topologie.

2.  Passare al nodo Lync Server 2013. Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e scegliere **Nuovo pool di server perimetrali**.
    
    ![Finestra di dialogo definire il nuovo pool di server perimetrali](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Finestra di dialogo definire il nuovo pool di server perimetrali")

3.  Un pool di server perimetrali può essere un **Pool di più computer** o un **Pool computer singolo**.
    
    ![Finestra di dialogo definire l'FQDN del pool di server perimetrali](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Finestra di dialogo definire l'FQDN del pool di server perimetrali")

4.  Nella pagina **Selezionare funzionalità** non abilitare la federazione o la federazione XMPP. La Federazione e la Federazione XMPP sono attualmente instradate attraverso il server perimetrale Office Communications Server 2007 R2 legacy. Queste funzionalità verranno configurate in una fase successiva della migrazione.
    
    ![Finestra di dialogo Seleziona funzionalità.](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Finestra di dialogo Seleziona funzionalità.")

5.  Successivamente, completare le pagine seguenti della procedura guidata: **Selezionare le opzioni IP**, **FQDN esterni**, **Definire l'indirizzo IP interno** e **Definire l'indirizzo IP esterno**.

6.  Nella pagina **definire l'hop successivo** selezionare il Director per l'hop successivo del pool di Edge di Lync Server 2013.
    
    ![Finestra di dialogo Definisci nuovo pool di server perimetrali, elenco pool hop successivo](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool di server perimetrali, elenco pool hop successivo")

7.  Nella pagina **Associa pool Front End** non associare un pool al pool di server perimetrali in questo momento. Il traffico multimediale esterno è attualmente instradato attraverso il server perimetrale Office Communications Server 2007 R2 legacy. Questa impostazione verrà configurata in una fase successiva della migrazione.
    
    ![Finestra di dialogo Definisci nuovo pool di server perimetrali](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Finestra di dialogo Definisci nuovo pool di server perimetrali")

8.  Fare clic su **Fine** e quindi su **Pubblica** per pubblicare la topologia.

9.  Seguire la procedura descritta in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo server perimetrale, configurare i certificati e avviare i servizi.

È molto importante seguire le linee guida illustrate negli argomenti relativi alla [distribuzione di accesso utente esterno in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) nella documentazione relativa alla distribuzione. In questa sezione vengono fornite solo indicazioni sulle impostazioni di configurazione durante la fase di installazione di questi ruoli server.

È ora necessario disporre di una distribuzione di Office Communications Server 2007 R2 server perimetrale legacy, indicata dalla presenza di BackCompatSite, in parallelo con una distribuzione di Lync Server 2013 Edge Server. La Federazione è configurata per l'utilizzo del Director di Office Communications Server 2007 R2. Prima di passare alla fase successiva, verificare che entrambe le distribuzioni funzionino correttamente, che i servizi siano stati avviati e che sia possibile amministrare ogni distribuzione.

![Generatore di topologie che mostra il server perimetrale OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generatore di topologie che mostra il server perimetrale OCS")

</div>

<span> </span>

</div>

</div>

</div>

