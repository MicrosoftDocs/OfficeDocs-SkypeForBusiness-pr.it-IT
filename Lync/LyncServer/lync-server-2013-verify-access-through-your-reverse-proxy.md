---
title: "Lync Server 2013: Verificare l'accesso tramite il proxy inverso"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Verificare l'accesso tramite il proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-29_

Usare la procedura seguente per verificare che gli utenti possano accedere alle informazioni sul proxy inverso. Può essere necessario completare la configurazione del firewall e la configurazione DNS (Domain Name System) prima che Access funzioni correttamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Per verificare che sia possibile accedere al sito Web tramite Internet

  - Aprire un Web browser, digitare gli URL nella barra degli **indirizzi** che i client usano per accedere ai file della Rubrica e al sito Web per i servizi di conferenza come segue:
    
      - Per server rubrica, digitare un URL simile al seguente: **https://externalwebfarmFQDN/abs** dove FQDNWebfarmesterna è il nome di dominio completo esterno dei servizi Web esterni che ospitano i servizi Rubrica. L'utente dovrebbe ricevere una sfida HTTP, perché la sicurezza della directory nella cartella del server rubrica è configurata per impostazione predefinita in autenticazione di Windows.
    
      - Per i servizi di conferenza, digitare un URL simile al **https://externalwebfarmFQDN/meet** seguente: dove FQDNWebfarmesterna è il nome di dominio completo esterno della Web farm che ospita il contenuto della riunione. Questo URL dovrebbe visualizzare la pagina di risoluzione dei problemi per i servizi di conferenza. In alternativa, verificare che l'URL semplice per le funzioni di conferenza sia corretto. Un esempio di URL semplice per il join di conferenza potrebbe esserehttps://meet.contoso.com
    
      - Per l'espansione del gruppo di distribuzione, digitare un URL simile al **https://externalwebfarmFQDN/GroupExpansion/service.svc**seguente:. L'utente dovrebbe ricevere una sfida HTTP, perché la sicurezza della directory nel servizio di espansione del gruppo di distribuzione è configurata per impostazione predefinita per l'autenticazione di Windows.
    
      - Per l'accesso esterno, digitare l'URL semplice in modo simile al **https://externalwebfarmFQDN/dialin** seguente, dove FQDNWebfarmesterna è il nome di dominio completo esterni della Web farm che ospita la pagina per la telefonia esterna con accesso esterno. L'utente deve essere indirizzato alla pagina di accesso esterno. In alternativa, verificare che le funzioni di accesso semplice per gli URL siano corrette. Un esempio di URL semplice per l'accesso esterno potrebbe esserehttps://dialin.contoso.com
    
      - Per verificare che l'URL di individuazione automatica funzioni, digitare https://lyncdiscover. externaldomainFQDN. Il browser dovrebbe richiedere l'apertura di un file. Selezionare Blocco note per aprirlo. Una risposta tipica sarebbe simile alla seguente:
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

