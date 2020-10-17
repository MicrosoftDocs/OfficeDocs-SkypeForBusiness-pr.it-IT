---
title: "Lync Server 2013: componenti necessari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a97635c66d66703fc2e9879024004a95c2c09eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502453"
---
# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componenti necessari per l'accesso degli utenti esterni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-29_

La maggior parte dei componenti perimetrali viene distribuita in una rete perimetrale. I componenti riportati di seguito costituiscono la topologia perimetrale della rete perimetrale. Eccetto dove indicato, i componenti fanno parte degli [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e si trovano nella rete perimetrale. I componenti perimetrali includono quanto segue:

  - server perimetrali

  - Proxy inversi

  - Firewall

  - Direttori (facoltativi e logicamente presenti nella rete interna)

  - Bilanciamento del carico di tipo per topologie perimetrali con scalabilità implementata (bilanciamento del carico DNS o dispositivo di bilanciamento del carico hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > Non è possibile usare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware in un'altra. È necessario usare lo stesso tipo di bilanciamento del carico per entrambe le interfacce, in quanto non è supportata una combinazione dei due tipi.

    
    </div>

<div>

## <a name="edge-servers"></a>server perimetrali

I server perimetrali inviano e ricevono il traffico di rete per i servizi offerti dalla distribuzione interna da parte di utenti esterni. Nel server perimetrale vengono eseguiti i servizi seguenti:

  - **Servizio**     Access Edge Il servizio Access Edge fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.

  - Servizio Web Conferencing **Edge**     Il servizio Web Conferencing Edge consente agli utenti esterni di partecipare alle riunioni ospitate nella distribuzione interna di Lync Server 2013.

  - Servizio A/ **V Edge**     Il servizio A/V Edge rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni. Gli utenti possono aggiungere audio e video alle riunioni che includono partecipanti esterni e possono comunicare utilizzando audio e/o video direttamente con un utente esterno nelle sessioni punto-punto. Il servizio A/V Edge offre inoltre il supporto per la condivisione desktop e il trasferimento di file.

  - **Servizio**     proxy XMPP Il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.

Gli utenti esterni autorizzati possono accedere ai server perimetrali per la connessione alla distribuzione interna di Lync Server 2013, ma i server perimetrali non forniscono un mezzo per qualsiasi altro accesso alla rete interna.

<div>


> [!NOTE]  
> I server perimetrali vengono distribuiti per fornire connessioni per i client Lync abilitati e altri server perimetrali Microsoft (come negli scenari di federazione). Non sono progettate per consentire connessioni da altri tipi di server o client di endpoint. Il server gateway XMPP può essere distribuito per consentire le connessioni con i partner XMPP configurati. Il server perimetrale e il gateway XMPP sono in grado di supportare solo le connessioni a endpoint da questi tipi di client e di Federazione.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverso

Questo proxy è necessario per eseguire le operazioni seguenti:

  - Consentire agli utenti di connettersi alle riunioni o alle conferenze telefoniche con accesso esterno utilizzando URL semplici

  - Consentire agli utenti esterni di scaricare il contenuto delle riunioni

  - Consentire agli utenti esterni di espandere i gruppi di distribuzione

  - Consentire all'utente di ottenere un certificato basato sugli utenti per l'autenticazione basata sui certificati client

  - Consentire agli utenti remoti di scaricare file dal server della Rubrica o inviare query al servizio Address Book Web Query

  - Consentire agli utenti remoti di ottenere aggiornamenti per il software client e dei dispositivi

  - Consentire ai dispositivi mobili di individuare automaticamente i Front End Server che offrono servizi per dispositivi mobili

  - Per abilitare le notifiche push ai dispositivi mobili da Microsoft 365, Office 365 o Apple Push Notification Services

Per ulteriori informazioni relative ai proxy inversi e ai requisiti che devono soddisfare i proxy inversi, vedere i dettagli nei [requisiti di configurazione per il proxy inverso in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Gli utenti esterni non necessitano di una connessione VPN (Virtual Private Network) alla propria organizzazione per partecipare alle comunicazioni tramite Lync Server 2013. Se la tecnologia VPN è stata implementata nell'organizzazione e gli utenti utilizzano la VPN per Lync, è possibile che il traffico multimediale, ad esempio le conferenze video, sia influenzato negativamente. È consigliabile fornire un mezzo per il traffico multimediale per la connessione al servizio di AV Edge direttamente e ignorare la VPN. Per informazioni dettagliate, vedere l'articolo del Blog di NextHop "Abilitazione di Lync media per ignorare un tunnel VPN" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

È possibile distribuire la topologia perimetrale solo con un firewall esterno oppure con un firewall esterno e uno interno. Le architetture degli scenari includono due firewall. L'utilizzo di due firewall è il metodo consigliato poiché garantisce un routing rigoroso da un perimetro all'altro della rete e protegge la distribuzione interna con due livelli di firewall.

</div>

<div>

## <a name="director"></a>Director

Un Director è un ruolo del server facoltativo separato in Lync Server 2013 che non ospita account utente o che fornisce servizi di conferenza o presenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director preautentica le richieste in ingresso e le reindirizza al pool o al server Home dell'utente. Eseguendo la preautenticazione presso il server Director, è possibile eliminare le richieste dagli account utente sconosciute alla distribuzione.

Un amministratore consente di isolare i server Standard Edition e front end server in pool Enterprise Edition front end da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director. Per informazioni dettagliate sull'utilizzo dei direttori, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti per il bilanciamento del carico hardware per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

