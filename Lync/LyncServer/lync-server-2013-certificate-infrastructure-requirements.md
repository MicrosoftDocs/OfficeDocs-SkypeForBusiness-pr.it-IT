---
title: "Lync Server 2013: Requisiti dell'infrastruttura dei certificati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Requisiti dell'infrastruttura dei certificati per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-06-23_

Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per il supporto delle connessioni TLS e Mutual TLS (MTLS).

Lync Server usa i certificati per i seguenti scopi:

  - Connessioni TLS tra client e server

  - Connessioni MTLS tra server

  - Federazione che usa l'individuazione automatica del DNS dei partner

  - Accesso remoto agli utenti per la messaggistica istantanea (IM)

  - Accesso degli utenti esterni a sessioni audio/video (A/V), condivisione applicazioni e conferenze

  - Richieste per dispositivi mobili che usano l'individuazione automatica dei servizi Web

Per Lync Server, si applicano i requisiti comuni seguenti:

  - Tutti i certificati server devono supportare l'autorizzazione del server (server EKU).

  - Tutti i certificati server devono contenere un punto di distribuzione CRL (CDP).

  - Tutti i certificati devono essere firmati usando un algoritmo di firma supportato dal sistema operativo. Lync Server 2013 supporta la famiglia di dimensioni digest SHA-1 e SHA-2 (224, 256, 384 e 512 bit) e soddisfa o supera i requisiti del sistema operativo. Per il supporto del sistema operativo [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002), vedere.
    
    <div>
    

    > [!NOTE]  
    > L'uso dell'algoritmo di firma RSASSA-PSS non è supportato e può comportare errori per i problemi di accesso e inoltro di chiamata, tra gli altri.

    
    </div>

  - La registrazione automatica è supportata per i server interni che gestiscono Lync Server.

  - La registrazione automatica non è supportata per Lync Server Edge Servers.

  - Quando si invia una richiesta di certificato basata sul Web a una CA di Windows Server 2003, è necessario inviarla da un computer che utilizza Windows Server 2003 con SP2 o Windows XP.
    
    Tieni presente che anche se KB922706 offre il supporto per la risoluzione dei problemi di registrazione di certificati Web su una registrazione Web di Servizi certificati di Windows Server 2003, non consente di usare Windows Server 2008, Windows Vista o Windows 7 per richiedere un certificato da una CA di Windows Server 2003.

  - Sono supportate le lunghezze della chiave di crittografia di 1024, 2048 e 4096. Sono consigliate le lunghezze delle chiavi di 2048 e superiori.

  - L'algoritmo digest predefinito o la firma hash è RSA. Sono supportati\_anche gli algoritmi\_ECDH P256, ECDH\_p384 e ECDH P521. 

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Requisiti dei certificati per il server Chat persistente in Lync Server 2013](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Requisiti dei certificati per i dispositivi mobili in Lync Server 2013](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

