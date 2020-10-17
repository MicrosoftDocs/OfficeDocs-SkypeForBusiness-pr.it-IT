---
title: 'Lync Server 2013: requisiti di configurazione per il proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555169f6de67ae23bc63d81aad549b0033a6696c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507743"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisiti di configurazione per il proxy inverso in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-05_

Lync Server 2013 impone alcuni requisiti per le comunicazioni provenienti dal client esterno, che vengono quindi passate ai servizi Web esterni ospitati nel server Director, nel pool di Director, nel front-end o nel pool Front end. Il proxy inverso è anche responsabile della pubblicazione del server Office Web Apps, se si offrono servizi di audioconferenza agli utenti.

<div>


> [!NOTE]  
> Lync Server 2013 non specifica un particolare proxy inverso che è necessario utilizzare. Lync Server 2013 definisce solo i requisiti operativi che il proxy inverso deve essere in grado di eseguire. In genere, il proxy inverso già distribuito nell'infrastruttura potrebbe essere in grado di soddisfare i requisiti.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisiti relativi al proxy inverso

Le operazioni funzionali che Lync Server 2013 prevede che un proxy inverso venga eseguito sono le seguenti:

  - Utilizzare Secure Socket Layer (SSL) e Transport Layer Security (TLS) implementato utilizzando i certificati acquisiti da un'autorità di certificazione pubblica per la connessione ai servizi Web esterni pubblicati del server Director, del pool di Director, del front-end o del pool Front end. Il server Director e front end può essere in un pool con bilanciamento del carico tramite i dispositivi di compensazione del carico hardware.

  - In grado di pubblicare siti Web interni utilizzando i certificati per la crittografia oppure pubblicarli in modo non crittografato, se necessario.

  - In grado di pubblicare un sito Web ospitato internamente tramite un nome di dominio completo (FQDN, Fully Qualified Domain Name).

  - In grado di pubblicare tutto il contenuto del sito Web ospitato. Per impostazione predefinita, è possibile utilizzare la **/\*** direttiva, riconosciuta dalla maggior parte dei server Web per indicare "pubblicare tutto il contenuto sul server Web". È inoltre possibile modificare la direttiva, ad esempio **/Uwca/ \* **, che significa "pubblicare tutto il contenuto nella directory virtuale UCWA".

  - Deve essere configurabile per richiedere connessioni Secure Sockets Layer (SSL) e/o Transport Layer Security (TLS) con client che richiedono contenuti da un sito Web pubblicato.

  - Deve accettare i certificati con le voci del nome alternativo soggetto (SAN).

  - Deve essere in grado di consentire l'associazione di un certificato a un listener o a un'interfaccia tramite la quale verrà risolto il nome di dominio completo dei servizi Web esterni. Le configurazioni dei listener sono preferibili alle interfacce. Molti listener possono essere configurati in una singola interfaccia.

  - Deve consentire la configurazione della gestione delle intestazioni host. Spesso, l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, anziché essere modificata dal proxy inverso.

  - Bridging del traffico SSL e TLS da una porta definita esternamente (ad esempio, TCP 443) a un'altra porta definita (ad esempio, TCP 4443). Il proxy inverso può decrittografare il pacchetto al ricevimento e quindi rieseguire la crittografia del pacchetto all'invio.

  - Bridging del traffico TCP non crittografato da una porta (ad esempio, TCP 80) a un altro (ad esempio, TCP 8080).

  - Consenti configurazione o accettazione dell'autenticazione NTLM, nessuna autenticazione e autenticazione pass-through.

</div>

</div>

<span> </span>

</div>

</div>

</div>

