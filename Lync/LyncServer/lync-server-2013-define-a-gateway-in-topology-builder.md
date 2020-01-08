---
title: 'Lync Server 2013: definire un gateway in Generatore di topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definire un gateway in Generatore di topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Seguire questa procedura per usare generatore di topologia per definire un *peer* con cui è possibile associare un Mediation Server per consentire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale. Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP) a cui ci si connette configurando un trunk SIP.

<div>


> [!NOTE]  
> Questo argomento presuppone che sia stato configurato almeno un pool Front-End interno o un server Standard Edition in almeno un sito centrale con un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front-end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione. Questo argomento presuppone inoltre che l'infrastruttura soddisfi i prerequisiti descritti in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">prerequisiti software per VoIP aziendale in Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Per definire un peer per il Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  In Lync Server 2013, il nome del sito, i componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.
    
    ![d898c3c1-8798-4b74-8F02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8F02-b994ef3db4c1")

3.  In **Definisci nuovo gateway IP/PSTN**Digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e fare clic su **Avanti**.
    
    ![8017ba5e-41bc-48D4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48D4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.

    
    </div>

4.  Definire la modalità di ascolto (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e fare clic su **Avanti**.
    
    ![c7fc0d12-adc8-45A7-ACA1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45A7-ACA1-b376e1d2fcec")

5.  Definire un *trunk radice* per il gateway PSTN. Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.
    
    {Nome completo di Mediation Server, porta di attesa di Mediation Server (TLS o TCP): IP gateway e FQDN, porta di ascolto del gateway}
    
      - Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.
    
      - Il trunk radice non può essere rimosso finché non viene rimosso il gateway PSTN associato.
    
    ![3b030757-EB35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-EB35-4616-bb6b-74ee67507e3d")

6.  In **porta di ascolto per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il PBX o il SBC utilizzerà per i messaggi SIP provenienti dal server di mediazione che verranno associati al trunk radice del gateway PSTN. Per impostazione predefinita, le porte sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS) in un gateway PSTN, un PBX o un SBC. In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.

7.  In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS.

    
    </div>

8.  In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.

9.  In **porta Mediation Server associata**Digitare la porta di ascolto che il server di mediazione userà per i messaggi SIP dal gateway.
    
    <div>
    

    > [!NOTE]  
    > Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP nel server Mediation da usare per la comunicazione con più gateway PSTN. Quando si definisce un trunk, la <STRONG>porta del server di mediazione associata</STRONG> deve essere compresa nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation. Questo intervallo di porte è definito in Lync Server 2013 e nei pool di mediazione. Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere <STRONG>modifica proprietà</STRONG>. Specificare l'intervallo di porte nel campo <STRONG>porte in attesa</STRONG> .

    
    </div>

10. Fare clic su **fine**.

<div>


> [!IMPORTANT]  
> Prima di completare questo passaggio, assicurarsi che il peer definito sia in uso e usare il nome di dominio completo o l'indirizzo IP specificato.



</div>

Per aggiungere quindi il peer alla topologia, seguire le procedure descritte in [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione. È necessario pubblicare la topologia ogni volta che si usa generatore di topologia per compilare o modificare la topologia, in modo che i dati possano essere usati per installare i file per i server che esegue Lync Server.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un trunk in Generatore di topologia in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

