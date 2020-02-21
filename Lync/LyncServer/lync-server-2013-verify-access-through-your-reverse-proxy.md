---
title: "Lync Server 2013: verificare l'accesso tramite il proxy inverso"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d061daedcdfabf4636c78a3a6a8bbe601903a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>Verificare l'accesso tramite il proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-29_

Eseguire la procedura seguente per verificare che gli utenti possano accedere alle informazioni nel proxy inverso. Potrebbe essere necessario completare la configurazione del firewall e la configurazione di DNS (Domain Name System) prima che l'accesso funzioni correttamente.

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>Per verificare che sia possibile accedere al sito Web tramite Internet

  - Aprire un Web browser, digitare nella barra**** degli indirizzi gli URL utilizzati dai client per accedere ai file della Rubrica e al sito Web per le conferenze, come indicato di seguito:
    
      - Per il server della Rubrica, digitare un URL analogo al seguente **https://externalwebfarmFQDN/abs** : dove FQDNWebfarmesterna è il nome di dominio completo esterno dei servizi Web esterni che ospita i servizi Rubrica. L'utente deve ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nella cartella del server della Rubrica è configurata per l'uso dell'autenticazione di Windows per impostazione predefinita.
    
      - Per le conferenze, digitare un URL analogo al seguente **https://externalwebfarmFQDN/meet** : dove FQDNWebfarmesterna è il nome di dominio completo esterno della Web farm che ospita il contenuto della riunione. Questo URL dovrebbe visualizzare la pagina di risoluzione dei problemi per le conferenze. In alternativa, confermare che l'URL semplice per le funzioni di conferenza funzioni correttamente. Un esempio di URL semplice per la conferenza join potrebbe esserehttps://meet.contoso.com
    
      - Per l'espansione del gruppo di distribuzione, digitare un URL simile al **https://externalwebfarmFQDN/GroupExpansion/service.svc**seguente:. L'utente dovrebbe ricevere una richiesta di verifica HTTP, poiché la sicurezza delle directory nel servizio di espansione dei gruppi di distribuzione è configurata per l'utilizzo dell'autenticazione di Windows per impostazione predefinita.
    
      - Per l'accesso esterno, digitare l'URL semplice, analogo al **https://externalwebfarmFQDN/dialin** seguente, in cui FQDNWebfarmesterna è il nome di dominio completo esterni della Web farm in cui è ospitata la pagina di chiamata in accesso esterno per le conferenze telefoniche con accesso interno. L'utente deve essere indirizzato alla pagina di accesso remoto. In alternativa, confermare che l'URL semplice per l'accesso remoto funzioni correttamente. Un esempio di URL semplice per l'accesso esterno può esserehttps://dialin.contoso.com
    
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

