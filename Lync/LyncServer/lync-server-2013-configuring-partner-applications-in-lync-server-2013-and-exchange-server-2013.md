---
title: Configurazione di applicazioni partner in Lync Server 2013 ed Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-12_

L'autenticazione da server a server in genere include tre entità: i due server che devono comunicare tra loro e un server token di sicurezza di terze parti. Se due server, ad esempio server A e server B, devono comunicare, questi vengono in genere avviati contattando un server token e ottenendo un token di sicurezza attendibile. Server A presentare quindi il token di sicurezza al server B (e viceversa) per garantirne l'autenticità e l'attendibilità.

Tuttavia, questa è una regola generale. Lync Server 2013, Microsoft Exchange Server 2013 e Microsoft SharePoint Server 2013 non devono usare un server di token di terze parti quando comunicano tra loro; Questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati uno dall'altro senza la necessità di un server token separato. Questa funzionalità è disponibile solo in Lync Server 2013, Exchange 2013 e SharePoint Server 2013. Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario farlo usando un server token di terze parti.

Per configurare l'autenticazione da server a server tra Lync Server e Exchange, è necessario eseguire due operazioni: 1) è necessario assegnare i certificati appropriati a ogni server. e 2) è necessario configurare ogni server come applicazione partner dell'altro server: ciò significa che è necessario configurare Lync Server 2013 come applicazione partner per Exchange 2013 ed è necessario configurare Exchange 2013 come applicazione partner per Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configurazione di Lync Server 2013 come applicazione partner per Exchange 2013

Il modo più semplice per configurare Lync Server 2013 come applicazione partner con Exchange 2013 consiste nell'eseguire lo script Configure-EnterprisePartnerApplication. ps1, uno script di Windows PowerShell fornito con Exchange 2013. Per eseguire questo script, è necessario specificare l'URL per il documento di metadati dell'autenticazione di Lync Server. in genere sarà il nome di dominio completo del pool di Lync Server 2013 seguito dal suffisso/Metadata/JSON/1. Ad esempio:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Per configurare Lync Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che usi il percorso della cartella predefinito):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) nella cassetta postale di Exchange e nei server Accesso client. È possibile riavviare IIS usando un comando simile a questo, che riavvia il servizio nel computer ATL-Exchange-001:

    iisreset atl-exchange-001

Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando eseguita in privilegi di amministratore.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configurazione di Exchange 2013 per un'applicazione partner per Lync Server 2013

Dopo aver configurato Lync Server 2013 come applicazione partner per Exchange 2013, è necessario configurare Exchange in un'applicazione partner per Lync Server. Questa operazione può essere eseguita tramite Lync Server Management Shell e specificando il documento di metadati di autenticazione per Exchange. si tratta in genere dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso/Metadata/JSON/1. Ad esempio:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

In Lync Server le applicazioni partner vengono configurate tramite il cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) . Oltre a specificare l'URI di metadati, devi anche impostare il livello di attendibilità dell'applicazione su completo. Ciò consentirà a Exchange di rappresentare se stesso e qualsiasi utente autorizzato nell'ambito. Ad esempio:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

In alternativa, è possibile creare un'applicazione partner copiando e modificando il codice di script trovato nella documentazione di autenticazione server-server di Lync Server 2013. Per altre informazioni, vedere l'articolo sulla [gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Se sono state configurate correttamente le applicazioni partner sia per Lync Server che per Exchange, ciò significa che è stata configurata anche l'autenticazione da server a server tra i due prodotti. Lync Server 2013 include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Lync Server possa connettersi a Exchange 2013. Il cmdlet esegue questa operazione connettendosi alla cassetta postale di un utente di Exchange 2013, scrivendo un elemento nella cartella Cronologia conversazioni per l'utente e quindi facoltativamente eliminando tale elemento.

Per testare l'integrazione di Lync Server 2013 ed Exchange 2013, eseguire un comando simile a questo da Lync Server Management Shell:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

Nel comando precedente, SipUri rappresenta l'indirizzo SIP di un utente con un account in Exchange 2013; il comando non riuscirà in questo caso non è un account utente valido.

Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

