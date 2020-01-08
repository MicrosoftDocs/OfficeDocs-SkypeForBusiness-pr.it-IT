---
title: "Lync Server 2013: Componenti necessari per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895f2d4837eb465f0eead2b70cf1d603504699ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Componenti necessari per l'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-29_

La maggior parte dei componenti Edge viene distribuita in una rete perimetrale. I componenti seguenti costituiscono la topologia di Edge della rete perimetrale. Eccetto dove indicato, i componenti fanno parte degli [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e si trovano nella rete perimetrale. I componenti Edge includono i seguenti:

  - Edge Server

  - Reverse proxy

  - Firewall

  - Amministratori (facoltativi e logicamente presenti nella rete interna)

  - Bilanciamento del carico per le topologie di Edge in scala (bilanciamento del carico DNS o un servizio di bilanciamento del carico hardware)
    
    <div>
    

    > [!IMPORTANT]  
    > L'uso del bilanciamento del carico DNS su un'interfaccia e il bilanciamento del carico hardware dall'altro non è supportato. È necessario usare il bilanciamento del carico hardware per entrambe le interfacce o il bilanciamento del carico DNS per entrambi.

    
    </div>

<div>

## <a name="edge-servers"></a>Edge Server

Gli Edge Server inviano e ricevono il traffico di rete per i servizi offerti dalla distribuzione interna da parte di utenti esterni. Il server perimetrale esegue i servizi seguenti:

  - **Access Edge Services**   il servizio Access Edge offre un unico punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.

  - **Web Conferencing Edge service**   il Web Conferencing Edge service consente agli utenti esterni di partecipare a riunioni ospitate nella distribuzione interna di Lync Server 2013.

  - **A/v Edge service**   l'a/v Edge Services rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni. Gli utenti possono aggiungere audio e video alle riunioni che includono partecipanti esterni e possono comunicare usando audio e/o video direttamente con un utente esterno nelle sessioni Point-to-Point. Il servizio A/V Edge offre anche il supporto per la condivisione desktop e il trasferimento di file.

  - **Servizio proxy XMPP**   il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federativi XMPP configurati.

Gli utenti esterni autorizzati possono accedere agli Edge Server per connettersi alla distribuzione interna di Lync Server 2013, ma gli Edge Server non consentono di accedere alla rete interna.

<div>


> [!NOTE]  
> I server perimetrali vengono distribuiti per consentire connessioni per i client Lync abilitati e altri server Microsoft Edge (come in scenari federativi). Non sono progettate per consentire connessioni da altri tipi di client o server di fine Point. Il server gateway XMPP può essere distribuito per consentire connessioni con partner XMPP configurati. Il gateway Edge Server e XMPP può supportare solo le connessioni di fine punto da questi tipi di client e federazioni.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>Proxy inverso

Il proxy inverso è necessario per gli elementi seguenti:

  - Per consentire agli utenti di connettersi a riunioni o conferenze telefoniche con accesso esterno usando URL semplici

  - Per consentire agli utenti esterni di scaricare il contenuto della riunione

  - Per consentire agli utenti esterni di espandere i gruppi di distribuzione

  - Per consentire all'utente di ottenere un certificato basato sull'utente per l'autenticazione basata su certificato client

  - Per consentire agli utenti remoti di scaricare i file dal server della Rubrica o di inviare query al servizio query Web Rubrica

  - Per consentire agli utenti remoti di ottenere gli aggiornamenti al software client e dispositivi

  - Per consentire ai dispositivi mobili di individuare automaticamente i server front-end che offrono servizi di mobilità

  - Per abilitare le notifiche push ai dispositivi mobili da Office 365 o Apple Push Notification Services

Per altre informazioni relative ai proxy inversi e ai requisiti che devono essere conformi ai proxy inversi, vedere i dettagli dei [requisiti di configurazione per il proxy inverso in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).

<div>


> [!NOTE]  
> Gli utenti esterni non hanno bisogno di una connessione VPN (Virtual Private Network) alla propria organizzazione per partecipare alle comunicazioni tramite Lync Server 2013. Se è stata implementata la tecnologia VPN nell'organizzazione e gli utenti usano la VPN per Lync, il traffico multimediale (ad esempio videoconferenza) può essere influenzato negativamente. È consigliabile fornire un mezzo per il traffico multimediale per connettersi direttamente al servizio Edge AV e ignorare la VPN. Per informazioni dettagliate, vedere l'articolo su Blog di NextHop "Abilitazione di Lync media per ignorare un tunnel <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>VPN".



</div>

</div>

<div>

## <a name="firewall"></a>Firewall

È possibile distribuire la topologia di Edge con solo un firewall esterno o sia firewall esterni che interni. Le architetture di scenario includono due firewall. L'uso di due firewall è l'approccio consigliato perché garantisce un routing rigoroso da un bordo di rete all'altro e protegge la distribuzione interna dietro due livelli di firewall.

</div>

<div>

## <a name="director"></a>Director

Un amministratore è un ruolo del server facoltativo separato in Lync Server 2013 che non ospita gli account utente o offre servizi di conferenza o presenza. Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni. Il Director effettua la preautenticazione delle richieste in ingresso e le reindirizza al server o al pool di utenti. Eseguendo la preautenticazione presso il Director, è possibile eliminare le richieste da un account utente sconosciuto alla distribuzione.

Un amministratore consente di isolare i server standard e i server front-end nei pool Front End di Enterprise Edition da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore. Per informazioni dettagliate sull'uso dei direttori, vedere [scenari per il Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti relativi al servizio di bilanciamento del carico hardware per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

