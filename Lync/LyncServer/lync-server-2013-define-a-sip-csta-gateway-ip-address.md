---
title: "Lync Server 2013: Definire l'indirizzo IP di un gateway SIP/CSTA"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definire l'indirizzo IP di un gateway SIP/CSTA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Se Lync Server si connette al gateway SIP/CSTA distribuito per il controllo delle chiamate remote tramite una connessione TCP (Transmission Control Protocol), è necessario definire l'indirizzo IP del gateway in Generatore di topologia. Questo passaggio non è necessario per i gateway che supportano connessioni TLS (Transport Layer Security). Per qualsiasi gateway che supporta connessioni TLS, è possibile ignorare questa procedura e continuare la distribuzione del controllo delle chiamate remote seguendo la procedura descritta in [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Per definire l'indirizzo IP del gateway SIP/CSTA tramite Generatore di topologie

1.  Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

3.  Scegliere l'opzione per scaricare una topologia esistente.

4.  Espandere il nodo **Trusted Application Servers** .

5.  Fare clic con il pulsante destro del mouse sul pool di applicazioni attendibile creato, come descritto in [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)e quindi fare clic su **modifica proprietà**.

6.  Deselezionare la casella di controllo **Abilita replica dei dati di configurazione nel pool** .

7.  Fare clic su **limita l'utilizzo del servizio agli indirizzi IP selezionati**. L'impostazione predefinita è **usare tutti gli indirizzi IP configurati**.

8.  Nella casella di testo **indirizzo IP principale** immettere l'indirizzo IP del gateway SIP/CSTA.

9.  Per aggiornare la topologia in Central Management store, nell'albero della console fare clic su **Lync Server**e quindi, nel riquadro **azioni** , fare clic su **pubblica**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurare una voce applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

