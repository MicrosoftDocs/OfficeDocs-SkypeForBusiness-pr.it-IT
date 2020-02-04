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
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS e MTLS per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

I protocolli Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) garantiscono comunicazioni crittografate e autenticazione endpoint su Internet. Microsoft Lync Server 2013 usa questi due protocolli per creare la rete di server attendibili e per assicurarsi che tutte le comunicazioni tramite la rete siano crittografate. Tutte le comunicazioni SIP tra server si verificano su MTLS. Le comunicazioni SIP da client a server si verificano su TLS.

TLS consente agli utenti, tramite il loro software client, di autenticare i server di Lync Server 2013 a cui si connettono. Su una connessione TLS, il client richiede un certificato valido dal server. Per essere valido, il certificato deve essere stato emesso da una CA che sia anche considerata affidabile dal client e il nome DNS del server deve corrispondere al nome DNS sul certificato. Se il certificato è valido, il client utilizza la chiave pubblica nel certificato per crittografare le chiavi di crittografia simmetriche da utilizzare per la comunicazione, quindi solo il proprietario originale del certificato può utilizzare la propria chiave privata per decrittografare il contenuto della comunicazione. La connessione risultante è affidabile e da quel momento non viene contestata da altri server o client affidabili. In questo contesto, il Secure Sockets Layer (SSL) utilizzato con i servizi web può essere associato come basato su TLS.

Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca. Su una connessione MTLS, il server che genera un messaggio e il server che lo riceve si scambiano i certificati da una CA reciprocamente attendibile. I certificati dimostrano l'identità di ciascun server all'altro. Nelle distribuzioni di Lync Server 2013 i certificati emessi dalla CA dell'organizzazione che si trovano durante il periodo di validità e non revocati dalla CA emittente vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di un dominio Active Directory considerare attendibile la CA aziendale in tale dominio. Negli scenari federati la CA emittente deve essere considerata attendibile da entrambi i partner federati. Ogni partner può usare una CA diversa, se lo si desidera, purché tale CA sia attendibile anche per l'altro partner. Questo tipo di attendibilità è più semplice per gli Edge Server che hanno il certificato della CA radice del partner nelle rispettive autorità di certificazione radice attendibili oppure per l'uso di una CA di terze parti considerata attendibile da entrambe le entità.

TLS e MTLS contribuiscono a prevenire attacchi di intercettazione e attacchi man-in-the-middle. In un attacco man-in-the-middle, l'utente malintenzionato dirige le comunicazioni tra due entità di rete attraverso il computer dell'utente malintenzionato all'insaputa delle due parti. La specifica TLS e Lync Server 2013 dei server attendibili (solo quelli specificati in Generatore di topologia) mitiga il rischio di un attacco di tipo man-in-Middle parzialmente sul livello dell'applicazione usando la crittografia end-to-end coordinata tramite la crittografia a chiave pubblica tra i due endpoint e un utente malintenzionato dovrebbe avere un certificato valido e attendibile con la chiave privata corrispondente e rilasciato al nome del servizio a cui il client comunica per decrittografare la comunicazione. In definitiva, tuttavia, devi seguire le procedure di sicurezza ottimali con l'infrastruttura di rete (in questo caso il DNS aziendale). Lync Server 2013 presuppone che il server DNS sia attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono considerati attendibili, ma il DNS garantisce un livello di protezione dagli attacchi di hijack del DNS impedendo al server di un aggressore di rispondere correttamente a un richiedere il nome contraffatto.

La figura seguente mostra a livello elevato il modo in cui Lync Server 2013 USA MTLS per creare una rete di server attendibili.

**Connessioni attendibili in una rete Lync Server**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

