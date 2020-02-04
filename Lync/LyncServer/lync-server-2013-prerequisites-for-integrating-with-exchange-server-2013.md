---
title: "Lync Server 2013: prerequisiti per l'integrazione con Exchange Server 2013"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-22_

Prima di poter integrare Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è necessario assicurarsi che tutte le operazioni preliminari siano state completate. Come ci si potrebbe aspettare, l'integrazione non può essere eseguita fino a quando Exchange 2013 e Lync Server 2013 sono completamente installati e operativi. Per informazioni dettagliate sull'installazione di Exchange, vedere la documentazione relativa alla pianificazione e [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)distribuzione di Exchange 2013. Per informazioni dettagliate sull'installazione di Lync Server 2013, vedere la documentazione relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)pianificazione e alla distribuzione.

Una volta eseguiti i server, è necessario assegnare certificati di autenticazione da server a server a Lync Server 2013 ed Exchange 2013; questi certificati consentono a Lync Server e Exchange di scambiare informazioni e comunicare tra loro. Quando si installa Exchange 2013, viene creato un certificato autofirmato con il nome certificato di autenticazione di Microsoft Exchange Server. Questo certificato, disponibile nell'archivio certificati del computer locale, deve essere usato per l'autenticazione da server a server in Exchange 2013. Per informazioni dettagliate sull'assegnazione di certificati in Exchange 2013, vedere "configurare il flusso di posta e l' [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)accesso client".

Per Lync Server 2013 è possibile usare un certificato di Lync Server esistente come certificato di autenticazione da server a server. ad esempio, il certificato predefinito può essere usato anche come certificato OAuthTokenIssuer. Lync Server 2013 consente di usare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:

  - Il certificato include il nome del dominio SIP nel campo oggetto.

  - Lo stesso certificato è configurato come certificato OAuthTokenIssuer in tutti i server front-end.

  - Il certificato ha una lunghezza di almeno 2048 bit.

Per informazioni dettagliate sui certificati di autenticazione da server a server per Microsoft Lync Server 2013, vedere [assegnazione di un certificato di autenticazione server-server a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica in Exchange 2013. In Exchange 2013 il servizio di individuazione automatica configura i profili utente e consente l'accesso ai servizi di Exchange quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password; a sua volta, i servizi conferiscono all'utente informazioni come:

  - Informazioni sulla connessione per la connettività interna ed esterna a Exchange 2013.

  - Posizione del server delle cassette postali dell'utente.

  - URL per le funzionalità di Outlook, ad esempio informazioni sulla disponibilità, messaggistica unificata e Rubrica fuori rete.

  - Impostazioni del server Outlook Anywhere.

Il servizio di individuazione automatica deve essere configurato prima di poter integrare Lync Server 2013 ed Exchange 2013. Puoi verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Se questo valore è vuoto, devi assegnare un URI al servizio di individuazione automatica. In genere questo URI avrà un aspetto simile al seguente:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Puoi assegnare l'URI di individuazione automatica eseguendo un comando simile al seguente:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Per informazioni dettagliate sul servizio di individuazione automatica, vedere "informazioni sul servizio di [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)individuazione automatica".

Dopo aver configurato il servizio di individuazione automatica, è necessario modificare le impostazioni di configurazione di Lync server OAuth. Questo assicura che Lync Server sappia dove trovare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione OAuth in Lync Server 2013, eseguire il comando seguente dall'interno di Lync Server Management Shell. Quando esegui questo comando, assicurati di specificare l'URI per il servizio di individuazione automatica in uso nel server Exchange e usi **autodiscover. svc** per puntare alla posizione del servizio invece di **autodiscover. XML** (che punta al file XML usato dal servizio):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Il parametro Identity nel comando precedente è facoltativo. Questo perché Lync Server consente solo di avere una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che puoi configurare l'URL di individuazione automatica usando questo comando leggermente più semplice:<BR>Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Se non si ha familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard usato da numerosi siti Web principali. Con OAuth, le credenziali utente e le password non vengono passate da un computer a un altro. L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo.



</div>

Oltre a configurare il servizio di individuazione automatica, è necessario creare anche un record DNS per il servizio che punta al server Exchange. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, è necessario creare un record DNS per autodiscover.litwareinc.com che venga risolto nel nome di dominio completo del server di Exchange, ad esempio atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

