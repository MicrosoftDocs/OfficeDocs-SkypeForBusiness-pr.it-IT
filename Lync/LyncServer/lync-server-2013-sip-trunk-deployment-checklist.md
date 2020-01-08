---
title: 'Lync Server 2013: Elenco di controllo di distribuzione per i trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Elenco di controllo di distribuzione per i trunk SIP per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Prima di poter distribuire un trunk SIP, il provider di servizi deve scambiare alcune informazioni di base sui rispettivi endpoint del trunk SIP.

Ottenere le informazioni seguenti per ogni gateway di ITSP a cui ci si connette:

  - Indirizzo IP

  - Nome di dominio completo (FQDN)

<div>


> [!NOTE]  
> Il provider di servizi può richiedere di connettersi a più di un gateway ITSP. In questo caso, è necessario configurare una connessione tra ogni gateway ITSP e ogni Mediation Server nel pool.



</div>

Le informazioni fornite al provider di servizi variano a seconda del tipo di connessione trunk SIP:

  - Per le connessioni MPLS (Multiprotocol Label Switching) o private network, assegna al ITSP l'indirizzo IP instradabile pubblicamente del router nella rete perimetrale (nota anche come DMZ, zona demilitarizzata e subnet schermata). Verificare che il gateway o Session Border Controller (SBC) in ITSP possa raggiungere questo indirizzo. Assegna anche a ITSP il nome di dominio completo di Mediation Server.

  - Per le connessioni VPN (Virtual Private Network), assegnare all'ITSP l'indirizzo IP del server VPN.

<div>

## <a name="certificate-considerations"></a>Considerazioni sui certificati

Per determinare se è necessario un certificato per il trunking SIP, verificare con il proprio ITSP informazioni sul supporto del protocollo:

1.  Se il ITSP supporta solo TCP (Transmission Control Protocol), non è necessario un certificato.

2.  Se il ITSP supporta Transport Layer Security (TLS), ITSP deve specificare un certificato.

<div>


> [!NOTE]  
> SIP funziona in combinazione con RTP (Real-Time Transport Protocol) o SRTP (Secure Real-Time Transport Protocol), i protocolli che gestiscono i dati vocali effettivi nelle chiamate VoIP (Voice over Internet Protocol).



</div>

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

Per implementare il lato Lync Server della connessione trunk SIP, eseguire le operazioni seguenti:

1.  Usando il generatore di topologia di Lync Server, creare e configurare la topologia del dominio SIP. Per informazioni dettagliate, vedere [definire e configurare una topologia in Generatore di topologia per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) nella documentazione relativa alla distribuzione.

2.  Usando il pannello di controllo di Lync Server, configurare il routing vocale per il nuovo dominio SIP. Per informazioni dettagliate, vedere [configurazione di Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) nella documentazione relativa alla distribuzione.

3.  Testare la connettività usando il cmdlet **Test-CsPstnOutboundCall** . Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la Guida di Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

