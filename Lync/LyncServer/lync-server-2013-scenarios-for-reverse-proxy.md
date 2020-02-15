---
title: 'Lync Server 2013: scenari per il proxy inverso'
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
ms.openlocfilehash: be05e3b63b73daeecbd4c0b34d9a893a8e27fa83
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Scenari per il proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-21_

I proxy inversi sono necessari in Lync Server 2013 per fornire l'accesso ai servizi e alle risorse, come gli URL semplici della riunione e delle chiamate in ingresso, la Rubrica, il contenuto delle riunioni, l'espansione della lista di distribuzione, i servizi per dispositivi mobili e altro. Lo scenario tipico del proxy inverso in Lync Server 2013 è consentire ai client esterni (ad esempio, client desktop o client di Lync Web App) l'accesso ai servizi Web esterni del server Director o front end.

**Proxy inverso e servizi Web esterni**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

Durante la fase di pianificazione, è possibile definire i requisiti per il proxy inverso in una distribuzione di Lync Server 2013. Il proxy inverso consente di accedere alle funzionalità per i client esterni seguenti:

  - Client desktop Microsoft Lync 2013

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - App Lync Windows Store

Quando si pianifica la distribuzione di Lync Server 2013, è necessario eseguire il mapping dei requisiti effettivi per Lync Server 2013 alle funzionalità del proxy inverso.

1.  I client esterni si connetteranno al proxy inverso sulla porta TCP 443 e utilizzeranno Secure Socket Layer (SSL) o Transport Layer Security (TLS). I client Microsoft Lync mobile possono connettersi sulla porta TCP 80, ma solo quando eseguono la connessione iniziale ai servizi di individuazione di Lync e l'amministratore ha configurato i record CNAME (o alias) di DNS (Domain Name System) appropriati e accetta che questo la comunicazione non verrà crittografata.

2.  I servizi Web esterni di Lync Server 2013 (distribuiti nel front end server e/o nel Director) prevedono una connessione da un proxy inverso sulla porta TCP 4443 e si prevede che la connessione sia SSL/TLS.
    
    <div>
    

    > [!IMPORTANT]  
    > Le porte di attesa predefinite consigliate per i servizi Web esterni sono TCP 8080 per il traffico HTTP e TCP 4443 per il traffico HTTPS. Generatore di topologie consente di ignorare le impostazioni predefinite e di definire le proprie porte di attesa per i servizi Web esterni. È importante tenere presente che il proxy inverso comunica con i servizi Web esterni e i client esterni comunicano con il proxy inverso. Il client esterno comunica con il proxy inverso sulla porta TCP 443, ma è possibile ridefinire la porta in cui il proxy inverso comunica con i servizi Web esterni. Le opzioni in Generatore di topologie per l'override delle porte di attesa predefinite per i servizi Web consentono di risolvere i conflitti delle porte di attesa che possono verificarsi nell'infrastruttura.

    
    </div>

3.  I servizi Web esterni di Lync Server 2013 prevedono un'intestazione host non modificata dal client per identificare il servizio e la directory del server Web che il client sta tentando di utilizzare. Le richieste devono essere visualizzate come provenivano dal proxy inverso

4.  I servizi Web esterni utilizzano directory virtuali (vDir) del server Web definite che forniscono i servizi offerti ai client. I servizi Web specifici esternamente identificabili sono i seguenti:
    
      - VDir "Meet" per riunioni di conferenze Web
    
      - VDir "dialin" per l'accesso telefonico e le conferenze telefoniche
    
      - L'vDir "individuazione automatica" per l'app Lync Windows Store, Lync mobile e il client desktop Lync 2013. Il servizio di individuazione automatica in Lync Server 2013 è noto con il nome DNS "Lyncdiscover"
    
      - I servizi non definiti sono accessibili dal client esterno tramite chiamate dirette ai servizi Web esterni. Ad esempio, il gruppo di distribuzione Expansion (DLX) e il servizio Rubrica (ABS) sono accessibili tramite chiamate dirette ai servizi Web esterni e ai vDirs associati. Il client conosce il percorso effettivo di vDir e costruisce un URL (Uniform record Locator) basato su queste informazioni. Il client accede al servizio Rubrica utilizzando un URL simile a`https://externalweb.contoso.com/abs/handler`
    
      - Il server Office Web Apps quando le conferenze vengono definite e configurate come parte della topologia di Lync Server
        
        <div>
        

        > [!NOTE]  
        > Il server Office Web Apps è un server di ruoli separato e non è configurato come parte dei servizi Web esterni. Questo server viene pubblicato separatamente per l'accesso client.

        
        </div>

5.  Definire il bridging SSL per ogni servizio. La porta esterna TCP 443 è mappata alla porta dei servizi Web esterni di TCP 4443. Per HTTP non crittografato, la porta TCP 80 è mappata alla porta dei servizi Web esterni TCP 8080

6.  Pianificare la pubblicazione delle risorse del server Web per i listener proxy inversi

7.  Richiedere e configurare il certificato per il proxy inverso in base ai servizi che verranno offerti. Se configurato con i nomi alternativi del soggetto corretti, questo certificato può essere condiviso da tutti i listener configurati nel server proxy inverso

Risorse disponibili per la pianificazione della distribuzione del proxy inverso:

  - [Raccolta dati in Lync Server 2013](lync-server-2013-data-collection.md)

  - [Riepilogo del certificato-proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Riepilogo delle porte-proxy inverso in Lync Server 2013](lync-server-2013-port-summary-reverse-proxy.md)

  - [Riepilogo DNS-proxy inverso in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

