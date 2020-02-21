---
title: 'Lync Server 2013: elenco di controllo di distribuzione trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08beaff401b8f261d311ad0d05a07f5221131864
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Elenco di controllo per la distribuzione del trunk SIP per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Prima di distribuire un trunk SIP, è necessario scambiare con il provider del servizio alcune informazioni di connessione di base sui rispettivi endpoint di trunk SIP.

Ottenere le informazioni seguenti per ogni gateway ITSP (Internet Telephony Service Provider, provider di servizi di telefonia Internet) al quale si eseguirà la connessione:

  - Indirizzo IP

  - Nome di dominio completo (FQDN)

<div>


> [!NOTE]  
> Il provider di servizi potrebbe chiedere di eseguire la connessione a più gateway ITSP. In tal caso, è necessario configurare una connessione tra ogni gateway di ITSP e ogni Mediation Server nel pool.



</div>

Le informazioni fornite al provider di servizi variano in base al tipo di connessione trunk SIP:

  - Per le connessioni MPLS (Multiprotocol Label Switching) o a reti private, fornire all'ITSP l'indirizzo IP instradabile pubblicamente del router nella rete perimetrale, denominata anche DMZ o subnet schermata. Verificare che il gateway o il Session Border Controller dell'ITSP sia in grado di raggiungere tale indirizzo. Assegnare anche all'ITSP il nome di dominio completo del Mediation Server.

  - Per le connessioni VPN, fornire all'ITSP l'indirizzo IP del server VPN.

<div>

## <a name="certificate-considerations"></a>Considerazioni sui certificati

Per determinare se è necessario un certificato per il trunking SIP, verificare i protocolli supportati con l'ITSP:

1.  Se l'ITSP supporta solo TCP, non è necessario un certificato.

2.  Se supporta TLS, l'ITSP dovrà fornire un certificato.

<div>


> [!NOTE]  
> Il protocollo SIP funziona in combinazione con RTP o SRTP, i protocolli che gestiscono gli effettivi dati vocali nelle chiamate VoIP.



</div>

</div>

<div>

## <a name="deployment-process"></a>Processo di distribuzione

Per implementare il margine Lync Server della connessione trunk SIP, eseguire la procedura seguente:

1.  Se si utilizza il generatore di topologie di Lync Server, creare e configurare la topologia di dominio SIP. Per informazioni dettagliate, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) nella documentazione relativa alla distribuzione.

2.  Se si utilizza il pannello di controllo di Lync Server, configurare il routing vocale per il nuovo dominio SIP. Per informazioni dettagliate, vedere [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) nella documentazione relativa alla distribuzione.

3.  Testare la connettività utilizzando il cmdlet  **Test-CsPstnOutboundCall**. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell o la guida per Lync Server Management Shell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

