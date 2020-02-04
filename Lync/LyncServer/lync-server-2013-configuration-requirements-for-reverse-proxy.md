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
ms.openlocfilehash: 37a2a535ddaa90efa2f4140236b52788fa58e41a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Requisiti di configurazione per il proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-05_

Lync Server 2013 impone alcuni requisiti per le comunicazioni dal client esterno che vengono quindi passate ai servizi Web esterni ospitati nel pool Director, Director, server front end o front end. Il proxy inverso è anche responsabile della pubblicazione del server Office Web Apps, se si offrono servizi di conferenza agli utenti.

<div>


> [!NOTE]  
> Lync Server 2013 non specifica un particolare proxy inverso che deve essere usato. Lync Server 2013 definisce solo i requisiti operativi che devono essere in grado di eseguire il proxy inverso. In genere, il proxy inverso già distribuito nell'infrastruttura può essere in grado di soddisfare i requisiti.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>Requisiti del proxy inverso

Le operazioni funzionali che Lync Server 2013 prevede che un proxy inverso eseguano siano:

  - Usare Secure Socket Layer (SSL) e Transport Layer Security (TLS) implementati usando i certificati acquisiti da un'autorità di certificazione pubblica per connettersi ai servizi Web esterni pubblicati del Director, del pool di Director, del front end server o del pool Front-end. Il Director e il server front-end possono essere in un pool di bilanciamento del carico usando i bilanciatori di carico hardware.

  - In grado di pubblicare siti Web interni usando i certificati per la crittografia oppure pubblicarli su un mezzo non crittografato, se necessario.

  - In grado di pubblicare un sito Web ospitato internamente esternamente usando un nome di dominio completo (FQDN).

  - In grado di pubblicare tutti i contenuti del sito Web ospitata. Per impostazione predefinita, è possibile usare ** / ** la direttiva, riconosciuta dalla maggior parte dei server Web per indicare "pubblica tutto il contenuto sul server Web". È anche possibile modificare la direttiva, ad esempio **/Uwca/\***, che significa "pubblica tutto il contenuto nella directory virtuale UCWA".

  - Devono essere configurabili per richiedere connessioni SSL (Secure Sockets Layer) e/o TLS (Transport Layer Security) con i client che richiedono contenuto da un sito Web pubblicato.

  - Deve accettare i certificati con le voci di nome alternativo soggetto (SAN).

  - Deve essere in grado di consentire l'associazione di un certificato a un listener o un'interfaccia tramite cui verrà risolto l'FQDN dei servizi Web esterni. Le configurazioni dei listener sono preferibili alle interfacce. Molti listener possono essere configurati in una singola interfaccia.

  - Deve consentire la configurazione della gestione delle intestazioni host. Spesso l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, invece di essere modificata dal proxy inverso.

  - Bridging del traffico SSL e TLS da una porta definita esternamente, ad esempio TCP 443, a un'altra porta definita, ad esempio TCP 4443. Il proxy inverso può decrittografare il pacchetto alla ricezione e quindi ricrittografare il pacchetto all'invio.

  - Bridging del traffico TCP non crittografato da una porta, ad esempio TCP 80, a un altro (ad esempio, TCP 8080).

  - Consentire la configurazione di, o accettare, l'autenticazione NTLM, nessuna autenticazione e l'autenticazione pass-through.

</div>

</div>

<span> </span>

</div>

</div>

</div>

