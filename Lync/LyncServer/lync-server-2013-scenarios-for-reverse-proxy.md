---
title: 'Lync Server 2013: Scenari per i proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Scenari per i proxy inversi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-21_

I proxy inversi sono necessari in Lync Server 2013 per consentire l'accesso a servizi e risorse, come gli URL semplici della riunione e della chiamata in ingresso, la Rubrica, il contenuto della riunione, l'espansione della lista di distribuzione, i servizi di mobilità e altri. Lo scenario di proxy inverso tipico in Lync Server 2013 consente ai client esterni, ad esempio client desktop o client Lync Web App, di accedere ai servizi Web esterni di Director o front end server.

**Proxy inverso e servizi Web esterni**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

Durante la fase di pianificazione, è possibile definire i requisiti per il proxy inverso in una distribuzione di Lync Server 2013. Il proxy inverso consente l'accesso alle funzionalità per i client esterni seguenti:

  - Client desktop di Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync mobile

  - App Lync di Windows Store

Quando si pianifica la distribuzione di Lync Server 2013, è possibile eseguire il mapping dei requisiti effettivi per Lync Server 2013 alle funzionalità proxy inverso.

1.  I client esterni si connetteranno al proxy inverso sulla porta TCP 443 e useranno Secure Socket Layer (SSL) o Transport Layer Security (TLS). I client di Microsoft Lync mobile possono connettersi alla porta TCP 80, ma solo quando si esegue la connessione iniziale ai servizi di individuazione Lync e l'amministratore ha configurato i record CNAME (o alias) DNS (Domain Name System) appropriati e accetta che questo le comunicazioni non verranno crittografate.

2.  I servizi Web esterni di Lync Server 2013 (distribuiti nel server front-end e/o nel Director) prevedono una connessione da un proxy inverso sulla porta TCP 4443 e prevede che la connessione sarà SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Le porte di ascolto predefinite suggerite per i servizi Web esterni sono TCP 8080 per il traffico HTTP e TCP 4443 per il traffico HTTPS. Generatore di topologia offre l'opportunità di ignorare le impostazioni predefinite e definire le proprie porte di ascolto per i servizi Web esterni. È importante notare che il proxy inverso comunica con i servizi Web esterni e i client esterni comunicano con il proxy inverso. Il client esterno comunica con il proxy inverso sulla porta TCP 443, ma è possibile ridefinire la porta con cui il proxy inverso comunica con i servizi Web esterni. Le opzioni in Generatore di topologie per ignorare le porte di ascolto predefinite per i servizi Web consentono di risolvere i conflitti di porta di ascolto che potrebbero verificarsi nell'infrastruttura.

    
    </div>

3.  I servizi Web esterni di Lync Server 2013 si aspettano un'intestazione host non modificata dal client per identificare il servizio e la directory del server Web che il client sta provando a usare. Le richieste devono essere visualizzate come provenivano dal proxy inverso

4.  I servizi Web esterni usano le directory virtuali server Web definite (vDir) che offrono i servizi offerti ai client. I servizi Web specifici esternamente identificabili sono:
    
      - VDir "riunione" per le riunioni di conferenza Web
    
      - VDir "chiamata" per l'accesso telefonico e le conferenze telefoniche
    
      - Il vDir "individuazione automatica" per l'app Lync di Windows Store, Lync mobile e il client desktop Lync 2013. L'individuazione automatica in Lync Server 2013 è nota con il nome DNS "Lyncdiscover"
    
      - I servizi non definiti sono accessibili dal client esterno tramite chiamate dirette ai servizi Web esterni. Ad esempio, l'espansione del gruppo di distribuzione (DLX) e il servizio Rubrica (ABS) sono accessibili tramite chiamate dirette ai servizi Web esterni e ai vDirs associati. Il client conosce il percorso effettivo di vDir e costruisce un URL (Uniform record Locator) in base a queste informazioni. Il client accede al servizio Rubrica usando un URL simile a`https://externalweb.contoso.com/abs/handler`
    
      - Il server Office Web Apps quando la conferenza viene definita e configurata come parte della topologia di Lync Server
        
        <div>
        

        > [!NOTE]  
        > Il server Office Web Apps è un server di ruoli distinto e non è configurato come parte dei servizi Web esterni. Questo server viene pubblicato separatamente per l'accesso client.

        
        </div>

5.  Definire il bridging SSL per ogni servizio. La porta esterna TCP 443 viene mappata alla porta dei servizi Web esterni di TCP 4443. Per HTTP non crittografato, la porta TCP 80 viene mappata alla porta dei servizi Web esterni TCP 8080

6.  Pianificare l'inversione dei listener proxy per pubblicare le risorse del server Web

7.  Richiedere e configurare il certificato per il proxy inverso in base ai servizi che verranno offerti. Se configurato con i nomi alternativi del soggetto corretti, questo certificato può essere condiviso da tutti i listener configurati nel server proxy inverso

Risorse disponibili per pianificare la distribuzione del proxy inverso:

  - [Raccolta dati in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Riepilogo dei certificati - proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Riepilogo delle porte - proxy inverso in Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Riepilogo di DNS - proxy inverso in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

