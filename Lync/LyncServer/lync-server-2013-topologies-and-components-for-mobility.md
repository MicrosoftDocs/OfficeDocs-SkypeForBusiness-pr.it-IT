---
title: 'Lync Server 2013: topologie e componenti per dispositivi mobili'
description: 'Lync Server 2013: topologie e componenti per dispositivi mobili.'
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
ms.openlocfilehash: 731991c3395bd3014270430483c6047dd5487185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576022"
---
# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Topologie e componenti per dispositivi mobili in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Per supportare le applicazioni di Lync mobile nei dispositivi mobili, Lync Server 2013 offre tre servizi: Lync Server 2013 MCX Mobility Service, Lync Server 2013 Autodiscover Service e Lync Server 2013 Push Notification Service. Gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge un servizio gratuito, ma avanzato, per i client mobili di Lync 2013, ovvero il supporto per la mobilità tramite l'utilizzo di Unified Communications Web API o UCWA. In questa sezione vengono descritti brevemente i componenti e vengono identificate le topologie di Lync Server 2013 che supportano la mobilità.

<div>


> [!NOTE]  
> I servizi per dispositivi mobili sono disponibili anche nelle distribuzioni ibride. Non è necessario distribuire servizi per supportare i dispositivi mobili se gli utenti si trovano online. È necessario definire un'impostazione per il servizio di individuazione automatica per consentire agli utenti di dispositivi mobili di trovare la propria identità online.



</div>

<div>


> [!IMPORTANT]  
> Se si sta pianificando la connettività degli utenti esterni (ad esempio, Federazione, accesso utente esterno o funzionalità per dispositivi mobili), è necessario utilizzare server perimetrali con il server Standard Edition e il front end server o il pool Front end. Il server Standard Edition e il front end server o il pool Front end non dispongono dei componenti necessari per consentire agli utenti esterni di accedere alla distribuzione interna o per la distribuzione interna per comunicare con gli utenti esterni. Per tutti gli scenari che includono utenti esterni che collaborano o comunicano con utenti interni, tra cui la mobilità, è necessario distribuire almeno un server perimetrale e un proxy inverso.<BR><EM>Notifica push</EM> utilizza un tipo di federazione per i servizi Lync Online, che ospita la casa di compensazione notifiche push (centro PNCH). La notifica push si riferisce agli avvisi audio, agli avvisi su schermo (testo) e ai badge che vengono inseriti dalle applicazioni su Apple iPhone, iPad e Windows Phone, quando il dispositivo mobile è inattivo. CENTRO PNCH riceve notifiche push da Lync Server. Quando centro PNCH riceve una notifica di un messaggio, centro PNCH inoltra una notifica ai client mobili tramite Apple Push Notification Services o Lync Server 2013 Push Notification Service, in base al client per dispositivi mobili a cui è destinato il messaggio. PNCH è un servizio necessario per questi client mobili. Per la Federazione di Lync Online, centro PNCH utilizza i server perimetrali e i certificati per garantire la riservatezza e l'autenticazione, i criteri e i record DNS (Domain Name System) correttamente configurati. I client Nokia Symbian e Android basati su Lync non utilizzano centro PNCH. Per informazioni dettagliate sulla pianificazione e la distribuzione di server perimetrali, vedere <A href="lync-server-2013-planning-for-external-user-access.md">Planning for External User Access in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A>.<BR>I client Lync 2013 mobile per i dispositivi Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non utilizzano più la notifica push o la barra di compensazione notifiche push (centro PNCH). I client Lync 2013 per dispositivi mobili su Windows Phone utilizzano ancora notifiche push e (centro PNCH).



</div>

<div>

## <a name="mobility-components"></a>Componenti di mobilità

I servizi che supportano i dispositivi mobili sono i seguenti:

  - **Lync Server 2013 Unified Communications Web API (UCWA)**     Fornisce servizi per le comunicazioni in tempo reale con i client mobili e Web in Lync Server 2013. Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: February 2013 to the front end server e Director, l'installazione crea una directory virtuale nei servizi Web interni ed esterni (UCWA). Un componente Web che fa parte della directory virtuale di UCWA accetta le chiamate provenienti da client abilitati a UCWA. Le app client comunicano su un'interfaccia REST per presenza, contatti, messaggistica istantanea, VoIP, video conferenza e collaborazione. UCWA utilizza un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, un messaggio istantaneo in arrivo o un messaggio all'app client.
    
    <div>
    

    > [!NOTE]  
    > <EM>Rest</EM> or Representational State Transfer, è uno stile di architettura software per sistemi distribuiti ampiamente adottati in molte forme ed è adatto ai requisiti dei servizi Web in generale.

    
    </div>

  - **Lync Server 2013 Mobility Service (MCX)**     Questo servizio supporta le funzionalità di Lync, quali messaggistica istantanea, presenza e contatti, su dispositivi mobili. Il servizio per dispositivi mobili è installato in tutti i front end server in ogni pool che supporta la funzionalità di Lync su un dispositivo mobile. Quando si installa Lync Server 2013, viene creata una nuova directory virtuale (MCX) sia nel sito Web interno che nel sito Web esterno nei server front end.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta sia il servizio per dispositivi mobili introdotto nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, comunemente noto come MCX, sia il componente Web UCWA. La combinazione di questi due servizi per dispositivi mobili fornisce l'interoperabilità e l'utilizzo da parte degli utenti con Lync 2010 mobile e i client mobili Lync 2013 su Lync Server 2013.

    
    </div>

  - Servizio di individuazione **automatica di Lync Server 2013**     Questo servizio identifica la posizione dell'utente e consente ai dispositivi mobili e ad altri client Lync di individuare risorse, ad esempio gli URL interni ed esterni per i servizi Web di Lync Server 2013 e l'URL per MCX o UCWA, indipendentemente dal percorso di rete. Individuazione automatica utilizza nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete; lyncdiscover per gli utenti all'esterno della rete) e il dominio SIP dell'utente. Supporta le connessioni client che utilizzano HTTP o HTTPS.
    
    Il servizio di individuazione automatica viene installato in tutti i Front End Server e in tutti i Director di ogni pool che supporta le funzionalità di Lync nei dispositivi mobili. Quando si installa il servizio di individuazione automatica, viene creata una nuova directory virtuale (individuazione automatica) sia nel sito Web interno che nel sito Web esterno, sia nei front end server che nei direttori.
    
    <div>
    

    > [!NOTE]  
    > Il servizio di individuazione automatica è elencato in questo articolo perché rimane un componente critico quando fornisce servizi client per dispositivi mobili. Il ruolo dell'individuazione automatica in Lync Server 2013 è stato esteso in modo da fornire servizi per tutti i client. Per informazioni dettagliate sulla pianificazione del servizio di individuazione automatica, vedere <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.

    
    </div>

  - Servizio di notifica **push**     Questo servizio è un servizio basato sul cloud che si trova nel Data Center di Lync Online. Quando l'applicazione Lync Mobile su un dispositivo Apple iOS supportato o Windows Phone è inattiva, non è in grado di rispondere a nuovi eventi, ad esempio un nuovo invito di messaggistica istantanea, un messaggio istantaneo senza risposta, una chiamata non conforme o una segreteria telefonica, perché questi dispositivi non supportano le applicazioni mobili in esecuzione in background. In questi casi, una notifica del nuovo evento, denominata *notifica push*, viene inviata al dispositivo mobile. Il servizio per dispositivi mobili Invia la notifica al servizio di notifica push basato sul cloud, che invia la notifica al servizio di notifica push di Apple (APNS) (per gli strumenti Apple iOS supportati) o al servizio di notifica push di Microsoft (MPNS) (per Windows Phone), che lo invia al dispositivo mobile. L'utente può quindi rispondere alla notifica sul dispositivo mobile per attivare l'applicazione.
    
    I dispositivi Lync 2010 Mobile su Apple e Windows Phone utilizzano le notifiche push. Il client Lync 2013 mobile per i dispositivi Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non utilizza più la notifica push o la barra di compensazione notifiche push (centro PNCH).

Nel diagramma seguente viene illustrato il modo in cui il servizio di notifica push rientra in una topologia di Lync Server 2013 che utilizza i client mobili di UCWA e Lync 2013.

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Introdotta in aggiornamento cumulativo per Lync Server 2010: novembre 2011, il servizio MCX fornisce servizi ai client mobili Lync 2010. Nel diagramma seguente viene illustrato il servizio di notifica push applicato a una topologia utilizzando MCX e i client mobili Lync 2010.

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>Topologie supportate

Applicazione degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge i componenti Web di UCWA per supportare la mobilità per le funzionalità dei client mobili di Lync 2013 nelle topologie seguenti:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

Il server perimetrale può essere un server perimetrale di Lync Server 2010.

Una distribuzione di Lync Server 2013 senza gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 utilizzerà il servizio per dispositivi mobili di MCX e potrà fornire servizi solo per Lync 2010 mobile.

<div>


> [!IMPORTANT]  
> Il servizio per dispositivi mobili è supportato nei front end server collocati con il ruolo Mediation Server con due interfacce di rete, ma è necessario eseguire le procedure appropriate per configurare le interfacce. È necessario assegnare gli indirizzi IP all'interfaccia specifica che comunicherà come Mediation Server e l'IP dell'interfaccia di rete che comunicherà come server front-end. È possibile eseguire questa operazione in Generatore di topologie selezionando l'indirizzo IP corretto per ogni servizio, invece di utilizzare l'impostazione predefinita <STRONG>tutti gli indirizzi IP configurati</STRONG>.



</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)  
[Pianificazione dell'individuazione automatica in Lync Server 2013](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

