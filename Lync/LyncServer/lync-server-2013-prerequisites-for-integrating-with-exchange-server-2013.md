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
ms.openlocfilehash: c92f88d35e573f0914698db28ddcf1fa54967f97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-22_

Prima di poter integrare Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è necessario assicurarsi che tutti i passaggi preliminari siano stati completati. Come si può immaginare, l'integrazione non può essere eseguita finché sia Exchange 2013 che Lync Server 2013 sono completamente installati e in esecuzione. Per informazioni dettagliate sull'installazione di Exchange, vedere la documentazione relativa alla pianificazione e [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)alla distribuzione di Exchange 2013 all'indirizzo. Per informazioni dettagliate sull'installazione di Lync Server 2013, vedere la documentazione relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)pianificazione e alla distribuzione all'indirizzo.

Dopo l'esecuzione dei server, è necessario assegnare certificati di autenticazione da server a server a Lync Server 2013 ed Exchange 2013; questi certificati consentono a Lync Server e Exchange di scambiare informazioni e comunicare tra loro. Quando si installa Exchange 2013, viene creato un certificato autofirmato con il nome del certificato di autenticazione di Microsoft Exchange Server. Questo certificato, che può essere trovato nell'archivio certificati del computer locale, deve essere utilizzato per l'autenticazione da server a server in Exchange 2013. Per informazioni dettagliate sull'assegnazione dei certificati in Exchange 2013, vedere la sezione "configurare il flusso di posta [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)e l'accesso client" all'indirizzo.

Per Lync Server 2013 è possibile utilizzare un certificato di Lync Server esistente come certificato di autenticazione da server a server. ad esempio, il certificato predefinito può essere utilizzato anche come certificato di OAuthTokenIssuer. Lync Server 2013 consente di utilizzare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:

  - Il certificato includa il nome del dominio SIP nel campo Oggetto.

  - Lo stesso certificato sia configurato come certificato OAuthTokenIssuer in tutti i Front End Server.

  - Il certificato abbia una lunghezza di almeno 2048 bit.

Per informazioni dettagliate sui certificati di autenticazione da server a server per Microsoft Lync Server 2013, vedere [assegnazione di un certificato di autenticazione da server a server a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica su Exchange 2013. In Exchange 2013, il servizio di individuazione automatica configura i profili utente e fornisce l'accesso ai servizi di Exchange quando gli utenti accedono al sistema. Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password. a sua incirca, i servizi forniscono all'utente informazioni quali:

  - Informazioni di connessione per la connettività sia interna che esterna a Exchange 2013.

  - Posizione del server della cassetta postale dell'utente.

  - URL per caratteristiche Outlook quali le informazioni di libero/occupato, la messaggistica unificata e la rubrica offline.

  - Impostazioni del server Outlook via Internet.

È necessario configurare il servizio di individuazione automatica prima di poter integrare Lync Server 2013 ed Exchange 2013. È possibile verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Se il valore è vuoto, è necessario assegnare un URI al servizio di individuazione automatica. Solitamente l'URI sarà simile a questo:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Per assegnare l'URI di individuazione automatica, è possibile eseguire un comando simile a questo:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Per informazioni dettagliate sul servizio di individuazione automatica, vedere la sezione "informazioni sul servizio di [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)individuazione automatica" all'indirizzo.

Dopo che il servizio di individuazione automatica è stato configurato, è necessario modificare le impostazioni di configurazione di Lync server OAuth. in questo modo, Lync Server è in grado di individuare il servizio di individuazione automatica. Per modificare le impostazioni di configurazione OAuth in Lync Server 2013, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell. Quando si esegue questo comando, accertarsi di specificare l'URI per il servizio di individuazione automatica in esecuzione nel server Exchange e di utilizzare **autodiscover. svc** in modo che punti alla posizione del servizio invece di **autodiscover. XML** (che punta al file XML utilizzato dal servizio):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> Il parametro Identity nel comando precedente è facoltativo. Ciò è dovuto al fatto che Lync Server consente solo di disporre di una singola raccolta globale di impostazioni di configurazione OAuth. Tra le altre cose, questo significa che è possibile configurare l'URL di individuazione automatica utilizzando questo comando leggermente più semplice:<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Per chi non avesse familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard utilizzato da numerosi siti Web di rilievo. Con OAuth, le credenziali e le password degli utenti non vengono passate da un computer all'altro. L'autenticazione e l'autorizzazione sono invece basate sullo scambio di token di sicurezza. Tali token consentono l'accesso a uno specifico set di risorse per un tempo specifico.



</div>

Oltre alla configurazione del servizio di individuazione automatica, è inoltre necessario creare un record DNS per il servizio che punta al server Exchange. Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, sarà necessario creare un record DNS per autodiscover.litwareinc.com che risolva il nome di dominio completo del server Exchange (ad esempio, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

