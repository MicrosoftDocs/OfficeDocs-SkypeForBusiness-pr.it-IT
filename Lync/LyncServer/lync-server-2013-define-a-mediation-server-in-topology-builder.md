---
title: 'Lync Server 2013: definire un Mediation Server in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0109a7091870b7409fd9bc20b9de3abd3b2f3a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definire un Mediation Server in Generatore di topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-25_

Attenersi alla procedura descritta in questo argomento per utilizzare il generatore di topologie per definire un Mediation Server autonomo o un pool collocato con un pool Front end in un sito per il quale non è stata distribuita in precedenza Enterprise Voice.

È possibile definire una topologia utilizzando un account membro del gruppo Administrators.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definire Mediation Server collocato in un pool Front End

Attenersi alla procedura descritta in questo argomento per utilizzare il generatore di topologie per definire un Mediation Server collocato in un pool Front end in un sito in cui Enterprise Voice non è stata distribuita in precedenza.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Per aggiungere un Mediation Server a un pool Front End

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie, nell'albero della console, espandere il nome del sito per il quale si desidera definire un pool Front end.

3.  Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front end desiderato e quindi scegliere **nuovo pool Front end.**..

4.  Scorrere i vari passaggi della procedura guidata **Definisci nuovo pool Front End** fino a raggiungere la pagina **Selezionare ruoli server collocati**.

5.  In **Seleziona ruoli server collocati, selezionare**l'opzione **colloca Mediation Server**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Se il tipo di pool Front End selezionato è Enterprise Edition, il componente Mediation Server verrà installato in tutti i front end server del pool Front end.</P>
    > <LI>
    > <P>Il <STRONG>pool di hop successivo</STRONG> utilizzato dal Mediation Server sarà il pool Front end in cui è collocato il Mediation Server.</P>
    > <LI>
    > <P>Il <STRONG>pool Edge</STRONG> utilizzato dal Mediation Server sarà lo stesso pool di server perimetrali associato al pool Front end in cui è collocato il Mediation.</P></LI></UL>

    
    </div>

6.  Fare clic su **Rendi predefinito** per utilizzare questo pool Front end per instradare le chiamate da Microsoft Office Communications Server 2007 R2 alla rete PSTN.

7.  Dopo aver completato l'associazione di uno o più peer al pool Front End, fare clic **su fine.**
    
    <div>
    

    > [!NOTE]  
    > Prima di procedere con il passaggio successivo del processo di distribuzione di VoIP aziendale, verificare che il pool di Mediation Server (ovvero il pool Front end con il componente Mediation Server collocato) utilizzi gli FQDN specificati.

    
    </div>

8.  Successivamente, seguire le procedure illustrate in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione della Guida alla distribuzione per aggiungere il Mediation Server alla topologia prima di procedere con il passaggio successivo della modifica delle porte di attesa del Mediation Server, se necessario. Per definire o modificare la topologia, è necessario pubblicare la topologia ogni volta che si utilizza Generatore di topologie.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definire Mediation Server autonomo

Attenersi alla procedura descritta in questo argomento per utilizzare il generatore di topologie per definire un Mediation Server autonomo o un pool in un sito in cui Enterprise Voice non è stata distribuita in precedenza.

Se è già stato distribuito Mediation Server collocato in pool Front end in questo sito, è possibile ignorare questa sezione e [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) prima di procedere alla [configurazione dei trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> In questa sezione si presuppone che sia già stato configurato almeno un pool Front End, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione della Guida alla distribuzione.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Per aggiungere un Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie, nell'albero della console, espandere il nome del sito per il quale si desidera definire un Mediation Server.

3.  Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **pool Mediation** e quindi scegliere **pool di Mediation Server**.

4.  In **Definisci nuovo pool Mediation**, digitare il nome di dominio completo (FQDN) del pool di Mediation Server.

5.  Eseguire quindi una delle operazioni seguenti:
    
      - Se si desidera distribuire più Mediation Server nel pool per fornire disponibilità elevata, selezionare pool di **più computer**.
        
        <div>
        

        > [!NOTE]  
        > È necessario distribuire il bilanciamento del carico DNS per supportare i pool di Mediation Server che dispongono di più Mediation Server. Per informazioni dettagliate, vedere la sezione Utilizzo del bilanciamento del carico DNS su pool di Mediation Server per il <A href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync server 2013</A> nella documentazione relativa alla pianificazione.

        
        </div>
    
      - Se si desidera distribuire un solo Mediation Server nel pool perché non è necessario disporre di disponibilità elevata, selezionare **pool di computer singolo**. Ignorare il passaggio seguente.

6.  Se si seleziona **Pool di più computer** nel passaggio precedente , in **Definire i computer nel pool corrente** fare clic su **FQDN computer**, digitare l'FQDN di ogni server nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti gli altri Mediation Server che si desidera aggiungere al pool. Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.

7.  Nella pagina **selezionare l'hop successivo** fare clic su **pool hop successivo**, fare clic sul nome di dominio completo del pool Front end che utilizzerà questo pool di Mediation Server e quindi fare clic su **Avanti**.

8.  Nella pagina **Selezionare un server perimetrale** eseguire una delle operazioni seguenti:
    
      - Se si desidera garantire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in **Seleziona pool di server perimetrali utilizzato da questo Mediation Server**, fare clic sul nome di dominio completo del pool di servizi perimetrali che utilizzerà questo pool di Mediation Server per fornire la connettività PSTN agli utenti esterni e quindi fare clic su **Avanti**.
    
      - Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si desidera fornire connettività PSTN agli utenti quando si trovano al di fuori della rete interna, fare clic su **Avanti**.

9.  Successivamente, seguire le procedure illustrate in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione per aggiungere il Mediation Server alla topologia. È necessario pubblicare la topologia ogni volta che si utilizza il generatore di topologie per creare o modificare la topologia in modo che i dati possano essere utilizzati per installare i file per i server che eseguono Lync Server. Continuare quindi con i passaggi successivi per modificare le porte di attesa nel Mediation Server, se necessario.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definire le porte di attesa del Mediation Server

Attenersi alla procedura descritta in questo argomento per utilizzare il generatore di topologie per definire le porte di attesa un Mediation Server o un pool accetterà le connessioni in ingresso da un peer gateway.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Per modificare le porte di attesa di Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie, nell'albero della console, espandere il nodo **pool Mediation** e fare clic con il pulsante destro del mouse sul Mediation Server creato in precedenza.

3.  Per impostazione predefinita, le porte di ascolto SIP sul Mediation Server sono 5070 per il traffico TLS da Lync Server, 5067 per il traffico TLS da peer (gateway, sistemi PBX o SBCs). La porta TCP è disabilitata per impostazione predefinita. È necessario abilitare la porta TCP in presenza di gateway che non supportano TLS.

4.  Specificare l'intervallo di porte di attesa TLS o TCP desiderato il Mediation Server accetterà le connessioni in ingresso dai gateway PSTN.
    
    <div>
    

    > [!NOTE]  
    > Non è necessario immettere un intervallo di porte TCP se l'opzione <STRONG>Abilita la porta TCP</STRONG> non è selezionata. Questa impostazione è facoltativa.

    
    </div>

Successivamente, [definire un gateway in Generatore di topologie in Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e installare i file su ogni Mediation Server nel pool attenendosi alle procedure descritte in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

