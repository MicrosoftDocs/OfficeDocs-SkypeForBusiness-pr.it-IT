---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-15_

Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete. Dopo la migrazione al pool di piloti di Lync Server 2013, è necessario eseguire la transizione dalla Route federativo di Lync Server 2010 Edge Server alla route federativo di Lync Server 2013 Edge Servers.

Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Lync Server 2010 Edge Server e Director a Lync Server 2013 Edge Server per una distribuzione a sito singolo.

<div>


> [!IMPORTANT]  
> Per modificare la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività della manutenzione per Lync Server 2013 e Lync Server 2010 Edge Server. L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione. È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima. Dovresti anche dare una notifica sufficiente agli utenti finali. Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione.



</div>

<div>


> [!IMPORTANT]  
> Se il server perimetrale di Lync Server 2010 è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge Services e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate. Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti da Lync Server 2010 a Lync Server 2013, quindi rimuovere la Commissione dal server Edge di Lync Server 2010 prima di abilitare la Federazione in Lync Server 2013 Edge Server.



</div>

<div>


> [!IMPORTANT]  
> Se la Federazione XMPP viene instradata tramite un server perimetrale di Lync Server 2013, gli utenti legacy di Lync Server 2010 non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Lync Server 2013, i criteri e i certificati XMPP sono stati configurato, il partner federato XMPP è stato configurato in Lync Server 2013 e infine le voci DNS sono state aggiornate.



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Per rimuovere l'associazione federativa Legacy dai siti di Lync Server 2013

1.  Nel server front-end di Lync Server 2013 aprire la topologia esistente in Generatore di topologia.

2.  Nel riquadro sinistro passare al nodo del sito, che si trova direttamente sotto **Lync Server**.

3.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.

4.  Nel riquadro sinistro selezionare **Route federativo**.

5.  In **assegnazione della route federativo di sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route federativo nell'ambiente legacy di Lync Server 2010.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Route di federazione](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Route di federazione")

6.  Fare clic su **OK** per chiudere la pagina Modifica proprietà.

7.  In **Generatore di topologie**selezionare il primo nodo **Lync Server**.

8.  Nel menu **azione** fare clic su **Pubblica topologia**.

9.  Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** quando il processo di pubblicazione è stato completato.

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federativo

1.  Nel riquadro sinistro passare al nodo **Lync Server 2010** e quindi al nodo **pool di bordi** .

2.  Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.

3.  Selezionare **generale** nel riquadro sinistro.

4.  Deselezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e scegliere **OK** per chiudere la pagina.
    
    ![Modifica proprietà, Generale, deselezione di Abilita federazione](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Modifica proprietà, Generale, deselezione di Abilita federazione")

5.  Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.

6.  Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.

7.  Verificare che la Federazione per il server perimetrale legacy sia disabilitata.
    
    ![Generatore di topologie, pool di server perimetrali, federazione disabilitata](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, federazione disabilitata")

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a>Per configurare i certificati nel server perimetrale di Lync Server 2010

1.  Esportare il certificato proxy di accesso esterno, con la chiave privata, dal server perimetrale Lync Server 2010 legacy.

2.  Nel server Edge di Lync Server 2013 importare il certificato esterno del proxy di accesso dal passaggio precedente.

3.  Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Lync Server 2013 dell'Edge Server.

4.  Il certificato di interfaccia interno del server Edge di Lync Server 2013 deve essere richiesto da una CA attendibile e assegnato.

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a>Per modificare la route federativo di Lync Server 2010 per l'uso di Lync Server 2013 Edge Server

1.  Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .

2.  Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.

3.  Selezionare **generale** nel riquadro sinistro.

4.  Selezionare la voce della casella di controllo per **abilitare la Federazione per questo pool di bordi (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Generale")

5.  Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.

6.  Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata.

7.  Verifica **Federazione (la porta 5061)** è impostata su **Enabled**.
    
    ![Generatore di topologie, pool di server perimetrali, federazione abilitata](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generatore di topologie, pool di server perimetrali, federazione abilitata")

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a>Per aggiornare Lync Server 2013 Edge Server Federation next hop

1.  Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.

3.  Nella pagina **generale** , in **selezione hop successivo**, selezionare nell'elenco a discesa il pool di Lync Server 2013.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Hop successivo](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Hop successivo")

4.  Fare clic su **OK** per chiudere la pagina Modifica proprietà.

5.  In **Generatore di topologie**selezionare il primo nodo **Lync Server** .

6.  Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata.

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Per configurare il percorso multimediale in uscita di Lync Server 2013 Edge Server

1.  In Generatore di topologie, nel riquadro sinistro, passare al nodo **Lync Server 2013** e quindi al pool sotto i **server front end Standard Edition** o i **pool Front End di Enterprise Edition**.

2.  Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.

3.  Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** .
    
    ![Modifica proprietà, Generale - Associa pool di server perimetrali](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Modifica proprietà, Generale - Associa pool di server perimetrali")

4.  Nella casella a discesa selezionare il server Edge di Lync Server 2013.

5.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Per attivare Lync Server 2013 Edge Server Federation

1.  Nel riquadro sinistro di generatore di topologia passare al nodo **Lync Server 2013** e quindi al nodo Pool di **bordi** .

2.  Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**.
    
    <div>
    

    > [!NOTE]  
    > La Federazione può essere abilitata solo per un singolo pool di Edge. Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi.

    
    </div>

3.  Nella pagina **generale** verificare che l'impostazione **Abilita federazione per questo pool di Edge (porta 5061)** sia selezionata.
    
    ![Finestra di dialogo Modifica proprietà - Pagina Generale](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Finestra di dialogo Modifica proprietà - Pagina Generale")

4.  Fare clic su **OK** per chiudere la pagina Modifica proprietà.

5.  Passare quindi al nodo del sito.

6.  Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.

7.  Nel riquadro sinistro fare clic su **Route federativo**.

8.  In **assegnazione percorso federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Lync Server 2013 elencato.
    
    ![Modifica proprietà - Pagina Route di federazione](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Modifica proprietà - Pagina Route di federazione")

9.  Fare clic su **OK** per chiudere la pagina **modifica proprietà** .
    
    Per le distribuzioni multisito, completare questa procedura in ogni sito.

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche alla configurazione di Edge Server

1.  In **Generatore di topologie**selezionare il primo nodo **Lync Server** .

2.  Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata.

3.  Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.
    
    <div>
    

    > [!NOTE]  
    > Potrebbe essere visualizzato il messaggio seguente:<BR><STRONG>Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Lync Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.</STRONG><BR>Questo avviso è previsto e può essere ignorato in modo sicuro.

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a>Per configurare Lync Server 2013 Edge Server

1.  Riunire tutti i server Edge di Lync Server 2013 online.

2.  Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) nel server perimetrale di Lync Server 2013, invece che nel server perimetrale legacy.
    
    <div>
    

    > [!NOTE]  
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolverlo nel nuovo server di Access Edge di Lync Server. Per eseguire questa operazione con un minimo di interruzioni, ridurre il valore di TLL per l'FQDN di Access Edge di Lync Server esterno, in modo che quando il DNS viene aggiornato per posizionare il puntatore sul nuovo bordo di accesso di Lync Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente.

    
    </div>

3.  Arrestare quindi il **bordo di accesso di Lync Server** da ogni computer Edge Server.

4.  Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.

5.  Nell'elenco servizi individuare **Edge Access di Lync Server**.

6.  Fare clic con il pulsante destro del mouse sul nome dei servizi e quindi scegliere **Interrompi** per arrestare il servizio.

7.  Impostare il tipo di avvio su **disabled**.

8.  Fare clic su **OK** per chiudere la finestra **Proprietà** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

