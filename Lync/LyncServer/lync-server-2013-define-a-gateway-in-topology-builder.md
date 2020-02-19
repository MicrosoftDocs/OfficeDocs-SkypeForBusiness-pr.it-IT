---
title: 'Lync Server 2013: definire un gateway in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definire un gateway in Generatore di topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Eseguire la procedura seguente per utilizzare il generatore di topologie per definire un *peer* con cui è possibile associare un Mediation Server per fornire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale. Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un session border controller (SBC) per un provider di servizi di telefonia Internet (ITSP) a cui si effettua la connessione configurando un trunk SIP.

<div>


> [!NOTE]  
> In questo argomento si presuppone che sia stato configurato almeno un pool Front End interno o un server Standard Edition in almeno un sito centrale con un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione. In questo argomento si presuppone inoltre che sia stata verificata la conformità dell'infrastruttura ai prerequisiti descritti nei prerequisiti <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">software per VoIP aziendale in Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">ai prerequisiti di configurazione e sicurezza per VoIP aziendale in Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Per definire un peer per il Mediation Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Lync Server 2013, nome del sito, componenti condivisi fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Nella finestra **Definisci nuovo gateway IP/PSTN** digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e quindi fare clic su **Avanti**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.

    
    </div>

4.  Definire la modalità di attesa (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e quindi fare clic su **Avanti**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Definire un *trunk radice* per il gateway PSTN. Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.
    
    {FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP e FQDN del gateway, porta di attesa del gateway}
    
      - Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.
    
      - Il trunk radice non può essere rimosso se non si rimuove prima il gateway PSTN associato.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  In **porta di attesa per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il sistema PBX o l'SBC utilizzerà per i messaggi SIP provenienti dal Mediation Server che verranno associati al trunk radice del gateway PSTN. Per impostazione predefinita, vengono utilizzate la porta 5066 per TCP (Transmission Control Protocol) e la porta 5067 per TLS (Transport Layer Security) in un gateway PSTN, un PBX o un sistema SBC. In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.

7.  In **Protocollo trasporto SIP** fare clic sul tipo di trasporto utilizzato dal peer e quindi su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS.

    
    </div>

8.  In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.

9.  In **porta Mediation Server associato**Digitare la porta di attesa che verrà utilizzata dal Mediation Server per i messaggi SIP provenienti dal gateway.
    
    <div>
    

    > [!NOTE]  
    > Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP sul Mediation Server da utilizzare per la comunicazione con più gateway PSTN. Quando si definisce un trunk, la <STRONG>porta del Mediation Server associata</STRONG> deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server. Questo intervallo di porte è definito in Lync Server 2013 e Mediation pool. Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere <STRONG>modifica proprietà</STRONG>. Specificare l'intervallo di porte nel campo <STRONG>Porte di attesa</STRONG>.

    
    </div>

10. Fare clic su **Fine**.

<div>


> [!IMPORTANT]  
> Prima di completare questo passaggio, verificare che il peer definito sia in esecuzione e utilizzi l'FQDN o l'indirizzo IP specificato.



</div>

Successivamente, per aggiungere il peer alla topologia, seguire le procedure illustrate in [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md) nella documentazione relativa alla distribuzione. È necessario pubblicare la topologia ogni volta che si utilizza Generatore di topologie per creare o modificare la topologia, in modo che i dati possano essere utilizzati per installare i file per i server che eseguono Lync Server.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

