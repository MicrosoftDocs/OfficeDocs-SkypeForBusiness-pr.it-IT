---
title: 'Lync Server 2013: definire un indirizzo IP del gateway SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Se Lync Server si connetterà al gateway SIP/CSTA distribuito per il controllo delle chiamate remote tramite una connessione TCP (Transmission Control Protocol), sarà necessario definire l'indirizzo IP del gateway in Generatore di topologie. Questa operazione non è necessaria per i gateway che supportano le connessioni TLS (Transport Layer Security). Per tutti i gateway che supportano le connessioni TLS, è possibile ignorare questa procedura e continuare la distribuzione del controllo delle chiamate remote attenendosi alla procedura descritta in [Enable Lync users for Remote Call Control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Per definire l'indirizzo IP di un gateway SIP/CSTA mediante Generatore di topologie

1.  Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.

2.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

3.  Scegliere l'opzione per scaricare una topologia esistente.

4.  Espandere il nodo **Server applicazioni attendibili**.

5.  Fare clic con il pulsante destro del mouse sul pool di applicazioni attendibili creato, come descritto in [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), quindi fare clic su **modifica proprietà**.

6.  Deselezionare la casella di controllo **Abilita la replica dei dati di configurazione nel pool**.

7.  Fare clic su **Limita utilizzo servizio a indirizzi IP selezionati**. L'impostazione predefinita è **Usa tutti gli indirizzi IP configurati**.

8.  Nella casella di testo **Indirizzo IP primario** immettere l'indirizzo IP del gateway SIP/CSTA.

9.  Per aggiornare la topologia nell'archivio di gestione centrale, fare clic su **Lync Server** nell'albero della console e quindi su **Pubblica** nel riquadro **Azioni**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

