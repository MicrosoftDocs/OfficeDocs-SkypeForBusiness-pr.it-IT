---
title: 'Lync Server 2013: Componenti e topologie per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Componenti e topologie per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Per supportare le applicazioni mobili Lync nei dispositivi mobili, Lync Server 2013 offre tre servizi: Lync Server 2013 MCX Mobility Service, Lync Server 2013 servizio di individuazione automatica e il servizio di notifica push di Lync Server 2013. Gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge un servizio gratuito, ma avanzato, per i client mobili Lync 2013, il supporto per la mobilità attraverso l'uso di Unified Communications Web API o UCWA. Questa sezione descrive brevemente questi componenti e identifica le topologie di Lync Server 2013 che supportano la mobilità.

<div>


> [!NOTE]  
> I servizi mobili sono disponibili anche in distribuzioni ibride. Non è necessario distribuire i servizi per supportare la mobilità se gli utenti sono ospitati online. È necessario definire un'impostazione per il servizio di individuazione automatica per consentire agli utenti mobili di trovare l'identità online.



</div>

<div>


> [!IMPORTANT]  
> Se si sta pianificando la connettività degli utenti esterni, ad esempio la Federazione, l'accesso degli utenti esterni o le caratteristiche di mobilità, è necessario usare Edge Servers con il server Standard Edition e il front end server o il pool Front-end. Il server Standard Edition e il front end server o il pool Front end non dispongono dei componenti necessari per consentire agli utenti esterni di accedere alla distribuzione interna o alla distribuzione interna per comunicare con gli utenti esterni. Per tutti gli scenari che includono utenti esterni che collaborano o comunicano con utenti interni, inclusa la mobilità, è necessario distribuire almeno un server perimetrale e un proxy inverso.<BR><EM>Notifica push</EM> usa un tipo di federazione per i servizi Lync Online, che ospita la camera di clearing delle notifiche push (centro PNCH). Notifica push fa riferimento agli avvisi audio, agli avvisi sullo schermo (testo) e ai badge che vengono inseriti dalle applicazioni in Apple iPhone, iPad e Windows Phone, quando il dispositivo mobile non è attivo. CENTRO PNCH riceve le notifiche push da Lync Server. Quando centro PNCH riceve una notifica di un messaggio, centro PNCH inoltra una notifica ai client mobili tramite Apple Push Notification Services o il servizio di notifica push di Lync Server 2013, in base al client mobile per cui è destinato il messaggio. CENTRO PNCH è un servizio obbligatorio per i client mobili. Per la Federazione a Lync Online, centro PNCH USA Edge Server e certificati per garantire la riservatezza e l'autenticazione, i criteri e i record DNS (Domain Name System) correttamente configurati. I client di Lync mobile di Nokia Symbian e Android non usano centro PNCH. Per informazioni dettagliate sulla pianificazione e la distribuzione di Edge Server, vedere <A href="lync-server-2013-planning-for-external-user-access.md">pianificazione per l'accesso degli utenti esterni in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">distribuzione dell'accesso degli utenti esterni in Lync Server 2013</A>.<BR>I client di Lync 2013 per dispositivi mobili Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non usano più la notifica push o la camera di compensazione delle notifiche push (centro PNCH). I client mobili di Lync 2013 in Windows Phone usano ancora la notifica push e la (centro PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componenti per la mobilità

I servizi che supportano la mobilità sono i seguenti:

  - **Lync Server 2013 Unified Communications Web API (UCWA)**   offre servizi per le comunicazioni in tempo reale con i client mobili e Web in Lync Server 2013. Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 per il server front-end e il direttore, l'installazione crea una directory virtuale nei servizi Web interni ed esterni (UCWA). Un componente Web che fa parte della directory virtuale UCWA accetta chiamate da client abilitati per UCWA. Le app client comunicano tramite un'interfaccia REST per la presenza, i contatti, la messaggistica istantanea, il VoIP, la videoconferenza e la collaborazione. UCWA usa un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, un messaggio istantaneo in arrivo o un messaggio all'app client.
    
    <div>
    

    > [!NOTE]  
    > Il trasferimento di stato <EM>Rest</EM> o Representational è uno stile architetturale software per sistemi distribuiti ampiamente adottato in molte forme ed è particolarmente adatto alle esigenze dei servizi Web in generale.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**   questo servizio supporta le funzionalità di Lync, ad esempio messaggistica istantanea, presenza e contatti nei dispositivi mobili. Il servizio di mobilità viene installato in ogni server front-end in ogni pool che supporta la funzionalità Lync nei dispositivi mobili. Quando si installa Lync Server 2013, viene creata una nuova directory virtuale (MCX) sia nel sito Web interno che nel sito Web esterno nei server front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013:2013 febbraio supporta sia il servizio di mobilità introdotto nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, comunemente noto come MCX, che il componente Web UCWA. La combinazione di questi due servizi di mobilità consente l'interoperabilità e l'uso degli utenti con i client mobili Lync 2010 per dispositivi mobili e Lync 2013 in Lync Server 2013.

    
    </div>

  - **Servizio di individuazione automatica di Lync Server 2013**   questo servizio identifica la posizione dell'utente e consente ai dispositivi mobili e ad altri client Lync di individuare risorse, ad esempio gli URL interni ed esterni per i servizi Web di Lync Server 2013 e l'URL per MCX o UCWA, indipendentemente dal percorso di rete. L'individuazione automatica usa nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete; lyncdiscover per gli utenti esterni alla rete) e il dominio SIP dell'utente. Supporta le connessioni client che usano HTTP o HTTPS.
    
    Il servizio di individuazione automatica viene installato in ogni server front-end e in ogni Director in ogni pool che supporta la funzionalità Lync nei dispositivi mobili. Quando si installa il servizio di individuazione automatica, viene creata una nuova directory virtuale (individuazione automatica) sia nel sito Web interno che nel sito Web esterno, sia nei server front-end che nei direttori.
    
    <div>
    

    > [!NOTE]  
    > Il servizio di individuazione automatica è elencato qui perché rimane un componente critico quando fornisce servizi client per dispositivi mobili. Il ruolo di individuazione automatica in Lync Server 2013 è stato ampliato per consentire servizi per tutti i client. Per informazioni dettagliate sulla pianificazione per il servizio di individuazione automatica, vedere <A href="lync-server-2013-planning-for-autodiscover.md">pianificazione per l'individuazione automatica in Lync Server 2013</A>.

    
    </div>

  - **Servizio notifica push**   questo servizio è un servizio basato su cloud che si trova nel centro dati di Lync Online. Quando l'applicazione Lync mobile in un dispositivo iOS o un Windows Phone supportato è inattiva, non può rispondere a nuovi eventi, ad esempio un nuovo invito alla messaggistica istantanea, un messaggio istantaneo non superato, una chiamata senza risposta o una segreteria telefonica, perché questi dispositivi non supportano applicazioni mobili in uso in background. In questi casi, una notifica del nuovo evento, denominata *notifica push*, viene inviata al dispositivo mobile. Il servizio di mobilità Invia la notifica al servizio di notifica push basata su cloud, che invia la notifica al servizio di notifica push Apple (APN) (per i dispositivi iOS supportati) o al servizio di notifica push Microsoft (MPNS ) (per Windows Phone), che viene quindi inviato al dispositivo mobile. L'utente può quindi rispondere alla notifica sul dispositivo mobile per attivare l'applicazione.
    
    I dispositivi Lync 2010 Mobile su Apple e Windows Phone usano le notifiche push. Il client mobile Lync 2013 per i dispositivi Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non usa più la notifica push o la camera di compensazione delle notifiche push (centro PNCH).

Il diagramma seguente illustra il modo in cui il servizio di notifica push rientra in una topologia di Lync Server 2013 che usa client mobili di UCWA e Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introdotta in aggiornamento cumulativo per Lync Server 2010: novembre 2011, il servizio MCX offre servizi ai client mobili Lync 2010. Il diagramma seguente illustra il servizio di notifica push applicato a una topologia usando i client mobili di MCX e Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

Applicazione degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge i componenti Web UCWA per supportare la mobilità per le caratteristiche dei client mobili Lync 2013 nelle topologie seguenti:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Il server perimetrale può essere un server perimetrale di Lync Server 2010.

Una distribuzione di Lync Server 2013 senza gli aggiornamenti cumulativi per Lync Server 2013: il 2013 febbraio utilizzerà il servizio di mobilità MCX e può erogare servizi solo per Lync 2010 mobile.

<div>


> [!IMPORTANT]  
> Il servizio mobilità è supportato nei server front-end collocati con il ruolo Mediation Server con due interfacce di rete, ma è necessario eseguire le operazioni appropriate per configurare le interfacce. È necessario assegnare gli indirizzi IP all'interfaccia specifica che verrà comunicata come server Mediation e l'IP dell'interfaccia di rete che comunicherà come server front-end. Puoi eseguire questa operazione in Generatore di topologia selezionando l'indirizzo IP corretto per ogni servizio, invece di usare l'impostazione predefinita <STRONG>Usa tutti gli indirizzi IP configurati</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Pianificazione per l'individuazione automatica in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

