---
title: 'Lync Server 2013: TLS e MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e22fcf910062df155bb62a9da183bbe6ad73e0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503773"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS e MTLS per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

Transport Layer Security (TLS) e i protocolli MTLS (Mutual Transport Layer Security) forniscono comunicazioni crittografate e autenticazione endpoint su Internet. Microsoft Lync Server 2013 utilizza questi due protocolli per creare la rete di server attendibili e garantire che tutte le comunicazioni sulla rete siano crittografate. Tutte le comunicazioni SIP tra server avvengono tramite MTLS. Le comunicazioni SIP da client a server avvengono tramite TLS.

TLS consente agli utenti, tramite il software client, di autenticare i server Lync Server 2013 a cui si connettono. In una connessione TLS, il client richiede al server un certificato valido. Per essere valido, il certificato deve essere stato emesso da una CA considerata attendibile anche dal client e il nome DNS del server deve corrispondere al nome DNS nel certificato. Se il certificato è valido, il client utilizza la chiave pubblica del certificato per crittografare le chiavi di crittografia simmetrica da utilizzare nella comunicazione, in modo che solo il proprietario originale del certificato possa utilizzare la sua chiave privata per decrittografare il contenuto. La connessione risultante è considerata attendibile e, da questo punto di vista, non riceve richieste di autenticazione da altri client o server trusted. In questo contesto, SSL (Secure Sockets Layer), utilizzato con i servizi Web, può essere associato come basato su TLS.

Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca. In una connessione a MTLS, il server che ha creato un messaggio e il server che lo riceve ricevono i certificati di Exchange da una CA mutuamente attendibile. I certificati dimostrano l'identità di ogni server all'altro. Nelle distribuzioni di Lync Server 2013 i certificati emessi dall'autorità di certificazione dell'organizzazione che si trovano durante il periodo di validità e non revocati dall'autorità di certificazione di emissione vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di un dominio di Active Directory considerano attendibile l'autorità di certificazione aziendale del dominio. Negli scenari federati, è necessario che la CA di emissione sia considerata attendibile da entrambi i partner federati. Ogni partner può utilizzare una CA diversa, se lo si desidera, purché tale CA sia anche considerata attendibile dall'altro partner. Questa relazione di trust è più semplice per i server perimetrali che dispongono del certificato CA radice del partner nelle rispettive autorità di certificazione radice attendibili o per l'utilizzo di una CA di terze parti considerata attendibile da entrambi gli interlocutori.

TLS e MTLS aiutano a impedire sia gli attacchi di intercettazione che di tipo man-in-the-Middle. In un attacco man-in-the-Middle, l'utente malintenzionato reindirizza le comunicazioni tra due entità di rete nel computer dell'utente malintenzionato senza la conoscenza di entrambe le parti. Le specifiche di TLS e Lync Server 2013 dei server attendibili (solo quelle specificate in Generatore di topologie) attenuano il rischio di un attacco man-in-the Middle parzialmente sul livello dell'applicazione utilizzando la crittografia end-to-end coordinata utilizzando la crittografia a chiave pubblica tra i due endpoint. e un utente malintenzionato deve disporre di un certificato valido e attendibile con la chiave privata corrispondente e rilasciato al nome del servizio al quale il client comunica per decrittografare la comunicazione. In definitiva, tuttavia, è necessario attenersi alle migliori procedure di sicurezza con l'infrastruttura di rete (in questo caso DNS aziendale). Lync Server 2013 presuppone che il server DNS sia considerato attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono attendibili, ma il DNS fornisce un livello di protezione contro gli attacchi del dirottamento DNS impedendo al server di un utente malintenzionato di rispondere correttamente a una richiesta al nome falsificato.

Nella figura seguente viene illustrato un livello elevato di come Lync Server 2013 utilizza MTLS per creare una rete di server attendibili.

**Connessioni trusted in una rete di Lync Server**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

