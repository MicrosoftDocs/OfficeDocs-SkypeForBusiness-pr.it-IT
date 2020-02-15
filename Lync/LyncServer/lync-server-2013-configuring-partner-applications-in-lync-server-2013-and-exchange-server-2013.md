---
title: Configurazione delle applicazioni partner in Lync Server 2013 e Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d6eb00b5efcd811d0fbf1397bce5f8b965c9110
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-12_

L'autenticazione da server a server in genere implica tre entità: i due server che devono comunicare tra loro e un server di token di sicurezza di terze parti. Se due server (ad esempio, il server A e il server B) devono comunicare, in genere entrambi i server cominciano a contattare un server di token e a ottenere un token di sicurezza attendibile. Server A quindi presentare il token di sicurezza al server B (e viceversa) per garantire l'autenticità e la sua attendibilità.

Tuttavia, questa è una regola generale. Lync Server 2013, Microsoft Exchange Server 2013 e Microsoft SharePoint Server 2013 non è necessario utilizzare un server di token di terze parti per comunicare tra loro; Questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati l'uno dall'altro senza la necessità di un server di token separato. Questa funzionalità è disponibile solo in Lync Server 2013, Exchange 2013 e SharePoint Server 2013. Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario eseguire questa operazione utilizzando un server di token di terze parti.

Per configurare l'autenticazione da server a server tra Lync Server e Exchange, è necessario eseguire due operazioni: 1) è necessario assegnare i certificati adeguati a ogni server; e 2) è necessario configurare ogni server come applicazione partner dell'altro server: questo significa che è necessario configurare Lync Server 2013 come applicazione partner per Exchange 2013 ed è necessario configurare Exchange 2013 come applicazione partner per Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configurazione di Lync Server 2013 come applicazione partner per Exchange 2013

Il modo più semplice per configurare Lync Server 2013 come applicazione partner con Exchange 2013 consiste nell'eseguire lo script Configure-EnterprisePartnerApplication. ps1, uno script di Windows PowerShell fornito con Exchange 2013. Per eseguire questo script, è necessario fornire l'URL per il documento dei metadati di autenticazione di Lync Server. si tratta in genere del nome di dominio completo del pool di Lync Server 2013 seguito dal suffisso/Metadata/JSON/1. Ad esempio:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Per configurare Lync Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso della cartella predefinito):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) nei server cassette postali e accesso client di Exchange. Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:

    iisreset atl-exchange-001

Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando eseguita con privilegi di amministratore.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configurazione di Exchange 2013 come applicazione partner per Lync Server 2013

Dopo aver configurato Lync Server 2013 come applicazione partner per Exchange 2013, è necessario configurare Exchange in modo che sia un'applicazione partner per Lync Server. È possibile eseguire questa operazione utilizzando Lync Server Management Shell e specificando il documento dei metadati di autenticazione per Exchange. si tratta in genere dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso/Metadata/JSON/1. Ad esempio:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

In Lync Server, le applicazioni partner vengono configurate utilizzando il cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) . Oltre a specificare l'URI dei metadati, è inoltre necessario impostare il livello di attendibilità dell'applicazione su Full. Ciò consentirà a Exchange di rappresentare se stesso e tutti gli utenti autorizzati nell'area di autenticazione. Ad esempio:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

In alternativa, è possibile creare un'applicazione partner copiando e modificando il codice di script trovato nella documentazione relativa all'autenticazione da server a server di Lync Server 2013. Per ulteriori informazioni, vedere l'articolo [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Se le applicazioni partner sono state configurate correttamente sia per Lync Server che per Exchange, ciò significa che è stata configurata correttamente anche l'autenticazione da server a server tra i due prodotti. Lync Server 2013 include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Lync Server sia in grado di connettersi a Exchange 2013. Il cmdlet esegue la connessione alla cassetta postale di un utente di Exchange 2013, scrivendo un elemento nella cartella Cronologia conversazioni per l'utente e quindi facoltativamente eliminando tale elemento.

Per testare l'integrazione di Lync Server 2013 ed Exchange 2013, eseguire un comando simile al seguente dall'interno di Lync Server Management Shell:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Nel comando precedente, SipUri rappresenta l'indirizzo SIP di un utente con un account su Exchange 2013; il comando avrà esito negativo in questo non è un account utente valido.

Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

