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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a>Informazioni sull'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-06-03_

Il servizio di individuazione automatica di Lync Server 2013 è una funzionalità introdotta in origine in Microsoft Lync Server 2010 come parte dell'aggiornamento cumulativo per Lync Server 2010: novembre 2011. Oltre alle correzioni, questo aggiornamento cumulativo ha fornito il supporto per i client Lync mobile e Lync 2013.

In Lync Server 2013 il servizio di individuazione automatica fa parte integrante del funzionamento dei client mobili esterni e interni e viene esteso anche ai nuovi client, ad esempio l'app Lync di Windows Store recentemente introdotta per Windows 8. L'individuazione automatica viene utilizzata anche dai client desktop di Lync 2013. L'individuazione automatica viene riconosciuta in Lync Server dai record DNS (Domain Name System) necessari **lyncdiscover.\< Domain\> ** e **LyncdiscoverInternal.\< Domain\>**. Inoltre, le versioni più recenti del client desktop Lync 2010 e Lync 2013 preferiscono l'individuazione automatica dei record SRV DNS (Domain Name System), usando i record SRV DNS solo se lyncdiscover. \<domain\> o LyncdiscoverInternal. \<il\> dominio non risponde o non si risolve. L'app Lync di Windows Store per Windows 8 e Lync Mobile USA l'individuazione automatica esclusivamente e non si riferisce ai record SRV DNS tradizionali.

In Lync Server 2013 l'individuazione automatica viene espansa per comunicare al client quali elementi, funzionalità e metodi di comunicazione sono disponibili per il client. Le informazioni vengono comunicate tramite una richiesta inviata dal client e i servizi Web di Lync Server rispondono con una risposta chiaramente definita che assegna un nome al client e come contattarle nel formato di individuazione automatica Documento di risposta.

Il modo migliore per comprendere il documento di risposta di individuazione automatica, tra cui i servizi Web che comunicano le caratteristiche ai client tramite questo documento, consiste nel sezionare e definire ogni riga in una risposta tipica dal documento di risposta di individuazione automatica del servizio Web di Lync.

<div class="">


> [!NOTE]  
> Nei dettagli che seguono l'utente ha già autenticato il server principale rispondendo a una richiesta di autenticazione.



</div>

<div class="">


> [!NOTE]  
> Il servizio Web di individuazione automatica di Lync è definito nei <STRONG>protocolli di Microsoft Office</STRONG> nella sezione <STRONG>specifiche aperte</STRONG> della raccolta MSDN ( <STRONG>Microsoft Developer Network</STRONG> ). Per informazioni dettagliate, vedere il documento di specifica completo "protocollo di servizio Web individuazione automatica Lync" in <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>:. Per informazioni dettagliate sull'autenticazione, vedere "protocollo di servizio Web di autenticazione <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>OC" all'indirizzo.



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a>Risposta di individuazione automatica del servizio Web di Lync Server

La risposta restituita quando viene inviata la richiesta di individuazione automatica è la stessa per un client interno o esterno. Alcuni parametri che hanno la posizione-Aware potrebbero cambiare. Se viene ricevuta una richiesta del client, ma il pool effettivo è diverso da quello che è stato contattato, il pool di Home dell'utente verrà impostato per l'utente. Un collega il cui account utente si trova in un pool diverso, ma accedendo dalla stessa sede riceverebbe una risposta leggermente diversa. La risposta indica il server front-end corretto o il pool Front-end per l'utente.

Esempio di documento di risposta di individuazione automatica:

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

Il documento di risposta di individuazione automatica può essere in uno dei due formati. Il formato predefinito è JSON (JavaScript Object Notation). L'altro formato è un documento XML (Extensible Markup Language). Per questo esempio viene usato il codice XML. La richiesta e la risposta sono prevedibili perché il documento ha uno schema definito che determina il formato. La riga del documento che descrive lo schema usato è la prima riga della richiesta o della risposta:

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

La definizione di **AccessLocation = "External"** indica che la richiesta è stata effettuata da un utente esterno.

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

SipServerInternalAccess e SipServerExternalAccess non sono attualmente usati. Queste voci sono riservate per un uso futuro.

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

SipClientInternalAccess e SipClientExternalAccess descrivono il nome di dominio completo e la porta che un client interno o esterno userà per accedere al server SIP definito. Il client desktop Lync e l'app Lync di Windows Store usano queste voci, in base alla loro posizione (interna o esterna) per trovare il Director o il server front-end.

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

I `Autodiscover` riferimenti contengono i punti di ingresso del servizio per il servizio di individuazione automatica. L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio. I `External/Autodiscover`client in una rete esterna usano. Il servizio di individuazione automatica viene installato come parte del processo di distribuzione. `Internal/Autodiscover`non è attualmente usato ed è riservato per un uso futuro.

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

I `AuthBroker` riferimenti contengono i punti di ingresso del servizio per il servizio di broker di autenticazione interni e esterni, in questo caso SIP. svc. L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio. Client della rete interna con l'utilizzo `Internal/AuthBroker`. I `External/AuthBroker`client in una rete esterna usano. Il servizio AuthBroker viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

Il `WebScheduler` token fa riferimento agli URL per l'accesso client alla programmazione basata sul Web per le conferenze di Lync Server. Attualmente viene usato solo `External/WebScheduler` il. Webscheduler viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

`Internal/Mcx`e `External/Mcx` sono le posizioni dei servizi per dispositivi mobili, introdotte in aggiornamento cumulativo per Lync Server 2010: novembre 2011. Questi riferimenti continueranno a essere usati da Lync 2010 mobile in tutti i dispositivi supportati. Il servizio MCX viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

**Internal/UCWA**, **External/UCWA** e **UCWA** offre ai client l'accesso all'interfaccia di programmazione delle applicazioni Web Unified Communications (UCWA API o semplicemente UCWA). `Internal/Ucwa`e `External/Ucwa` le directory virtuali sono punti di accesso riservati per il miglioramento delle caratteristiche future e non vengono usati. La `Ucwa` directory virtuale viene usata per Microsoft Lync mobile (introdotta con Lync Server 2013) in tutti i dispositivi supportati. Il servizio UCWA viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

`Internal/XFrame`, **External/Xframe** e **Xframe** consentono l'accesso per le applicazioni server basate su UCWA. XFrame viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

Il `Self` token fa riferimento a informazioni specifiche del client (tipo di risposta utente) che sta effettuando la richiesta. Il client che ha eseguito questa richiesta è stato esterno e questo riferimento per l'individuazione automatica si riferisce alla parte dell'utente del servizio di individuazione automatica.

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[Pianificazione per l'individuazione automatica in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

