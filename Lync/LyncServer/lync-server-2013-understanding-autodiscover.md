---
title: "Lync Server 2013: informazioni sull'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e29608dd8c3a0187b17c03e6ba9373b31f08f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527763"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a>Informazioni su individuazione automatica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-06-03_

Il servizio di individuazione automatica di Lync Server 2013 è una funzionalità originariamente introdotta in Microsoft Lync Server 2010 come parte dell'aggiornamento cumulativo per Lync Server 2010: novembre 2011. Oltre alle correzioni, questo aggiornamento cumulativo ha fornito il supporto per i client Lync mobile e Lync 2013.

In Lync Server 2013, il servizio di individuazione automatica è parte integrante del funzionamento dei client mobili esterni e interni e viene esteso anche ai nuovi client, ad esempio l'app Lync Windows Store recentemente introdotta per Windows 8. L'individuazione automatica viene utilizzata anche dai client desktop Lync 2013. Il servizio di individuazione automatica è riconosciuto in Lync Server dai record DNS (Domain Name System) necessari **lyncdiscover. \<domain\> ** e **LyncdiscoverInternal. \<domain\> **. Inoltre, le versioni più recenti di Lync 2010 e Lync 2013 desktop client preferiscono l'individuazione automatica sui record SRV DNS (Domain Name System), utilizzando i record DNS SRV solo se lyncdiscover.\<domain\> o LyncdiscoverInternal.\<domain\> non risponde o non si risolve. L'app Lync Windows Store per Windows 8 e Lync mobile utilizza l'individuazione automatica esclusivamente e non si riferisce ai record DNS SRV tradizionali.

In Lync Server 2013, l'individuazione automatica viene espansa per comunicare al client quali elementi, caratteristiche e metodi di comunicazione sono disponibili per il client. Le informazioni vengono comunicate tramite una richiesta inviata dal client e i servizi Web di Lync Server rispondono con una risposta chiaramente definita che consente di assegnare un nome a ciò che è disponibile per il client e come contattare tali funzionalità nel formato del documento di risposta di individuazione automatica.

Il modo migliore per comprendere il documento di risposta di individuazione automatica, compreso il modo in cui i servizi Web comunicano le caratteristiche ai client tramite questo documento, consiste nel sezionare e definire ogni riga in una risposta tipica del documento di risposta di individuazione automatica del servizio Web Lync.

<div class="">


> [!NOTE]  
> Nei dettagli seguenti, l'utente ha già autenticato il server principale rispondendo a una richiesta di autenticazione.



</div>

<div class="">


> [!NOTE]  
> Il servizio Web di individuazione automatica di Lync è definito nei <STRONG>protocolli di Microsoft Office</STRONG> nella sezione <STRONG>Open specifiche</STRONG> della raccolta MSDN ( <STRONG>Microsoft Developer Network</STRONG> ). Per informazioni dettagliate, vedere il documento delle specifiche complete, "Lync Autodiscover Web Service Protocol" all'indirizzo: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> . Per informazioni dettagliate sull'autenticazione, vedere "OC Authentication Web Service Protocol" all'indirizzo <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> .



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Risposta di individuazione automatica del servizio Web di Lync Server

La risposta restituita quando viene inviata la richiesta di individuazione automatica è la stessa per un client interno o esterno. Alcuni parametri che possono essere modificati per la posizione potrebbero variare. Se viene ricevuta una richiesta del client, ma il pool effettivo è diverso da quello che è stato contattato, il pool di casa dell'utente verrà impostato per tale utente. Un collega il cui account utente si trova in un pool diverso, ma accedendo dallo stesso ufficio, riceverà una risposta leggermente diversa. La risposta indica il front end server o il pool Front end corretto per tale utente.

Un esempio di un documento di risposta di individuazione automatica:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a>Dettagli del documento di risposta di individuazione automatica

Il documento di risposta di individuazione automatica può essere in uno dei due formati. Il formato predefinito è una notazione JSON (JavaScript Object Notation). L'altro formato è un documento XML (Extensible Markup Language). Il codice XML viene utilizzato per questo esempio. La richiesta e la risposta sono prevedibili perché il documento ha uno schema definito che determina il formato. La riga del documento in cui viene descritto lo schema utilizzato è la prima riga della richiesta o della risposta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La definizione di **AccessLocation = "External"** indica che la richiesta è stata effettuata da un utente esterno.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess e SipServerExternalAccess non sono attualmente utilizzati. Tali voci sono riservate per un utilizzo futuro.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess e SipClientExternalAccess descrivono il nome di dominio completo e la porta che un client interno o esterno utilizzerà per accedere al server SIP definito. Il client Lync desktop e l'app Lync Windows Store utilizzano queste voci, in base alla posizione (interna o esterna) per individuare il server Director o front end.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

I `Autodiscover` riferimenti contengono i punti di ingresso del servizio per il servizio di individuazione automatica. L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio. I client di una rete esterna utilizzano `External/Autodiscover` . Il servizio di individuazione automatica viene installato come parte del processo di distribuzione. `Internal/Autodiscover` non è attualmente utilizzato ed è riservato per utilizzi futuri.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

I `AuthBroker` riferimenti contengono i punti di ingresso del servizio per il servizio Broker di autenticazione interno e esterno, in questo caso SIP. svc. L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio. Client sulla rete interna con utilizzo `Internal/AuthBroker` . I client di una rete esterna utilizzano `External/AuthBroker` . Il servizio AuthBroker viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Il `WebScheduler` token fa riferimento agli URL per l'accesso client alla programmazione basata sul Web per le conferenze di Lync Server. Attualmente, `External/WebScheduler` viene utilizzato solo il. L'utilità Webscheduler è installata come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx` e `External/Mcx` sono i percorsi dei servizi per dispositivi mobili, introdotti in aggiornamento cumulativo per Lync Server 2010: novembre 2011. Tali riferimenti continueranno a essere utilizzati da Lync 2010 Mobile su tutti i dispositivi supportati. Il servizio MCX viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/UCWA**, **External/UCWA** e **UCWA** forniscono un mezzo per consentire ai client di accedere all'interfaccia di programmazione delle applicazioni Web Unified Communications (UCWA API o Simply UCWA). `Internal/Ucwa` e le `External/Ucwa` directory virtuali sono punti di accesso riservati per il futuro miglioramento delle funzionalità e non vengono utilizzati. La `Ucwa` directory virtuale viene utilizzata per Microsoft Lync mobile (introdotta con Lync Server 2013) in tutti i dispositivi supportati. Il servizio UCWA viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** e **Xframe** forniscono l'accesso per le applicazioni server basate su UCWA. XFrame viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Il `Self` token si riferisce alle informazioni specifiche del client (tipo di risposta dell'utente) che effettua la richiesta. Il client che ha effettuato questa richiesta è stato esterno e questo riferimento per l'individuazione automatica si riferisce alla parte relativa all'utente del servizio di individuazione automatica.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Pianificazione dell'individuazione automatica in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

