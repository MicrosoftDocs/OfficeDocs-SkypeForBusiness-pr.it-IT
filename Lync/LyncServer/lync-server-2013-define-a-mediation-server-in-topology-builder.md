---
title: 'Lync Server 2013: definire un Mediation Server in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definire un Mediation Server in Generatore di topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-25_

Seguire la procedura descritta in questo argomento per usare generatore di topologia per definire un Mediation Server autonomo o un pool collocato con un pool Front-end in un sito per il quale non è stato distribuito in precedenza Enterprise Voice.

Puoi definire una topologia usando un account che è un membro del gruppo Administrators.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definire Mediation Server collocato in un pool Front-End

Seguire la procedura descritta in questo argomento per usare generatore di topologia per definire un Mediation Server collocato in un pool Front-end in un sito in cui Enterprise Voice non è stato distribuito in precedenza.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Per aggiungere un Mediation Server a un pool Front-End

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un pool Front-end.

3.  Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front-end desiderato e quindi scegliere **nuovo pool Front-end.**..

4.  Spostarsi tra la procedura guidata **Definisci nuovo pool di front end** fino a raggiungere la pagina **Selezione ruoli server collocati** .

5.  In **Seleziona ruoli server collocati selezionare**l'opzione **collocazione Mediation Server**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Se il tipo di pool Front-End selezionato è Enterprise Edition, il componente Mediation Server verrà installato in tutti i server front-end del pool Front-end.</P>
    > <LI>
    > <P>Il <STRONG>pool di hop successivo</STRONG> usato dal Mediation Server sarà il pool Front-end in cui è installato il Mediation Server.</P>
    > <LI>
    > <P>Il <STRONG>pool di Edge</STRONG> usato da Mediation Server sarà lo stesso pool di Edge associato al pool Front-end in cui è installato il Mediation Server.</P></LI></UL>

    
    </div>

6.  Fare clic su **Imposta predefinito** per usare questo pool Front-end per instradare le chiamate da Microsoft Office Communications Server 2007 R2 alla rete PSTN.

7.  Al termine, fare clic su **fine** per associare uno o più peer al pool Front-end.
    
    <div>
    

    > [!NOTE]  
    > Prima di procedere con il passaggio successivo nel processo di distribuzione di VoIP aziendale, verificare che il pool di Mediation Server (ad esempio il pool Front end con il componente Mediation Server) usi i nomi di dominio completi specificati.

    
    </div>

8.  Seguire quindi le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione della Guida alla distribuzione per aggiungere il Mediation Server alla topologia prima di procedere con il passaggio successivo della modifica delle porte di ascolto del server di mediazione, se necessario. È necessario pubblicare la topologia ogni volta che si usa generatore di topologie per definire o modificare la topologia.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definire Mediation Server autonomo

Seguire i passaggi descritti in questo argomento per usare generatore di topologia per definire un server di mediazione autonomo o un pool in un sito in cui Enterprise Voice non è stato distribuito in precedenza.

Se sono già stati distribuiti server di mediazione collocati in pool Front-end in questo sito, è possibile ignorare questa sezione e [installare i file per Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) prima di procedere alla [configurazione dei trunk in Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> In questa sezione si presuppone che sia già stato configurato almeno un pool Front-End, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione della Guida alla distribuzione.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Per aggiungere un Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un Mediation Server.

3.  Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **pool di mediazione** e quindi scegliere **pool di Mediation Server**.

4.  In **Definisci nuovo pool di mediazione**Digitare il nome di dominio completo (FQDN) del pool di Mediation Server.

5.  Eseguire quindi una delle operazioni seguenti:
    
      - Se si vuole distribuire più server di mediazione nel pool per ottenere una disponibilità elevata, selezionare **più pool di computer**.
        
        <div>
        

        > [!NOTE]  
        > È necessario distribuire il bilanciamento del carico DNS per supportare i pool di Mediation Server con più server di mediazione. Per informazioni dettagliate, vedere la sezione Utilizzo di bilanciamento del carico DNS nei pool di Mediation Server del <A href="lync-server-2013-dns-load-balancing.md">bilanciamento del carico DNS in Lync Server 2013</A> nella documentazione relativa alla pianificazione.

        
        </div>
    
      - Se si vuole distribuire un solo Mediation Server nel pool perché non è necessaria una disponibilità elevata, selezionare **Single computer pool**. Ignorare il passaggio seguente.

6.  Se nel passaggio precedente è stato selezionato **più pool di computer** , nell' **elemento Definisci i computer in questo pool** fare clic su **FQDN computer**, digitare il nome di dominio completo di ogni server nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti gli altri Mediation Server che si vuole aggiungere al pool. Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.

7.  Nella pagina **selezionare l'hop successivo** fare clic su **pool hop successivo**, fare clic sul nome di dominio completo del pool Front-end che utilizzerà questo pool di Mediation Server e quindi fare clic su **Avanti**.

8.  Nella pagina **selezionare un server perimetrale** eseguire una delle operazioni seguenti:
    
      - Se si vuole consentire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in **selezionare pool Edge usato da questo Mediation Server**fare clic sul nome di dominio completo del pool di Edge Server che utilizzerà questo pool di Mediation Server per consentire la connettività PSTN a tali utenti esterni e quindi fare clic su **Avanti**.
    
      - Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si vuole concedere connettività PSTN agli utenti quando si trovano all'esterno della rete interna, fare clic su **Avanti**.

9.  Seguire quindi le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione per aggiungere il Mediation Server alla topologia. È necessario pubblicare la topologia ogni volta che si usa generatore di topologie per creare o modificare la topologia in modo che i dati possano essere usati per installare i file per i server che esegue Lync Server. Continuare con i passaggi successivi per modificare le porte di ascolto nel server Mediation, se necessario.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definire le porte di ascolto di Mediation Server

Seguire i passaggi descritti in questo argomento per usare generatore di topologie per definire le porte in attesa un server di mediazione o un pool accetteranno le connessioni in ingresso da un peer del gateway.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Per modificare le porte di ascolto di Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console di generatore di topologia espandere il nodo **pool di mediazione** e fare clic con il pulsante destro del mouse sul server di mediazione creato in precedenza.

3.  Per impostazione predefinita, le porte di ascolto SIP sul Mediation Server sono 5070 per il traffico TLS da Lync Server, 5067 per il traffico TLS da peer (gateway, sistemi PBX o SBCs). La porta TCP è disabilitata per impostazione predefinita. È necessario abilitare la porta TCP se sono presenti gateway che non supportano TLS.

4.  Specificare l'intervallo di porte di ascolto TLS o TCP desiderato il server di mediazione accetterà le connessioni in ingresso dai gateway PSTN.
    
    <div>
    

    > [!NOTE]  
    > L'immissione di un intervallo di porte TCP non è necessaria se l' <STRONG>Abilitazione della porta TCP</STRONG> non è selezionata. Questa impostazione è facoltativa.

    
    </div>

Definire quindi [un gateway in Generatore di topologia in Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e installare i file in ogni Mediation Server nel pool seguendo le procedure descritte in [installare i file per Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

