---
title: Requisiti dell'infrastruttura dei certificati di Lync Server 2013
description: Requisiti dell'infrastruttura dei certificati di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c7e69f272c29f0ba9386f403db326b4d39bbff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544292"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Requisiti dell'infrastruttura dei certificati per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-06-23_

Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per il supporto delle connessioni TLS e Mutual TLS (MTLS).

Lync Server utilizza i certificati per gli scopi seguenti:

  - Connessioni TLS tra client e server

  - Connessioni MTLS tra server

  - Federazione con individuazione DNS automatica dei partner

  - Accesso utente remoto per la messaggistica istantanea

  - Accesso utente esterno a sessioni audio/video (A/V), condivisione applicazioni e conferenze

  - Richieste mobili con individuazione automatica dei servizi Web

Per Lync Server, si applicano i requisiti comuni seguenti:

  - Tutti i certificati del server devono supportare l'autorizzazione server (utilizzo chiavi avanzato del server).

  - Tutti i certificati del server devono contenere un punto di distribuzione CRL (CDP).

  - Tutti i certificati devono essere firmati utilizzando un algoritmo di firma supportato dal sistema operativo. Lync Server 2013 supporta la famiglia di dimensioni del digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo. Per il supporto del sistema operativo, vedere [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .
    
    <div>
    

    > [!NOTE]  
    > L'utilizzo dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori relativi ai problemi di accesso e di inoltro di chiamata, tra gli altri.

    
    </div>

  - La registrazione automatica è supportata per i server interni che eseguono Lync Server.

  - La registrazione automatica non è supportata per i server perimetrali di Lync Server.

  - Quando si invia una richiesta di certificato Web a un'autorità di certificazione (CA) di Windows Server 2003, è necessario inviarla da un computer che esegue Windows Server 2003 con SP2 oppure Windows XP.
    
    Benché nell'articolo KB922706 venga fornito il supporto per risolvere i problemi di registrazione dei certificati Web con la funzionalità di registrazione Web dei Servizi certificati di Windows Server 2003, non è possibile utilizzare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato a una CA di Windows Server 2003.

  - Sono supportate le lunghezze delle chiavi di crittografia pari a 1024, 2048 e 4096. È consigliabile utilizzare la lunghezza della chiave di 2048 e una maggiore.

  - L'algoritmo digest o hash predefinito è RSA. \_Sono supportati anche gli algoritmi di ECDH P256, ECDH \_ p384 e ECDH P521 \_ . 

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisiti dei certificati per il server Chat persistente in Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisiti dei certificati per i dispositivi mobili in Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

