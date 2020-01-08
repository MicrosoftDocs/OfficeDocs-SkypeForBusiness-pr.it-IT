---
title: "Lync Server 2013: Nuove funzionalità per l'accesso utente esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nuove funzionalità per l'accesso utente esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-17_

Lync Server 2013 introduce nuove funzionalità che estendono le caratteristiche e i metodi di comunicazione per gli utenti. Inoltre, Lync Server 2013 introduce le modifiche ai servizi esistenti per integrare meglio ed estendere i servizi disponibili per l'organizzazione. Di seguito è riportato un riepilogo delle modifiche che possono influenzare la pianificazione e la distribuzione dei servizi di Lync Server 2013 Edge Server.

  - **Supporto per l'indirizzamento**   IPv6 Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi Edge Server. Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile usare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie.
    
    <div>
    

    > [!IMPORTANT]  
    > L'uso degli indirizzi IPv6 in Lync Server 2013 dipende dal supporto di IPv6 nei router e nei firewall distribuiti dall'organizzazione, oltre che dal supporto per il provider di servizi Internet.

    
    </div>

  - **Il protocollo XMPP (Extensible Messaging and Presence Protocol)**   Lync Server 2013 introduce un proxy XMPP completamente integrato (distribuito sugli Edge Server) e un gateway XMPP distribuito nei server front-end. Puoi distribuire la Federazione XMPP come componente facoltativo. L'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentirà agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.
    
    <div>
    

    > [!NOTE]  
    > Attualmente, i servizi XMPP in Lync Server 2013 consentono solo la messaggistica istantanea e la presenza tra i client Lync e i contatti basati su XMPP.

    
    </div>

  - **Servizi di mobilità per i client**   mobili introdotti in un aggiornamento del cliente per Lync Server 2010, i servizi di mobilità in Lync Server 2013 consentono ai client di Microsoft Lync Mobile su telefoni cellulari e tablet che usano i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione di contatti e la presenza della visualizzazione. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e la notifica delle chiamate perse.
    
    <div>
    

    > [!NOTE]  
    > I servizi di mobilità usano il proxy inverso e i servizi pubblicati distribuiti nei server front-end. Per Edge Server non sono necessarie modifiche.

    
    </div>

  - **Gli amministratori sono un ruolo**   facoltativo il ruolo del server Director nella topologia di Lync Server 2013 non è cambiato. Ospita ancora servizi Web, pre-autentica le richieste degli utenti in arrivo e indirizza gli utenti esterni al proprio pool Home. La modifica del Director da un ruolo consigliato a un ruolo facoltativo non diminuisce il valore del Director, ma enfatizza la riduzione del numero di server e di altri requisiti hardware, ad esempio i requisiti di bilanciamento del carico hardware per il Director, senza caratteristiche e funzionalità compromesse. Poiché i server front-end possono eseguire lo stesso processo del Director senza alcun impatto sui servizi forniti, è possibile facoltativamente distribuire direttori se si sceglie di. È possibile escludere in modo sicuro il Director con la certezza che i server front-end forniranno gli stessi servizi nella propria posizione.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione e configurazione di IPv6 in Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Pianificazione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

