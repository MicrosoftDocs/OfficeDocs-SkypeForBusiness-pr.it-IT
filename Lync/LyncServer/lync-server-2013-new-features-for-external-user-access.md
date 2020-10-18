---
title: "Lync Server 2013: nuove funzionalità per l'accesso degli utenti esterni"
description: "Lync Server 2013: nuove funzionalità per l'accesso degli utenti esterni."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d960a469334a836c453e8ae3bbf51f1b66bb93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578842"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Nuove funzionalità per l'accesso degli utenti esterni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-17_

Lync Server 2013 introduce nuove funzionalità che estendono le funzionalità e i metodi di comunicazione per gli utenti. Inoltre, Lync Server 2013 introduce modifiche ai servizi esistenti per migliorare l'integrazione e l'estensione dei servizi disponibili per l'organizzazione. Di seguito è riportato un riepilogo delle modifiche che possono influire sulla pianificazione e la distribuzione dei servizi server perimetrali di Lync Server 2013.

  - **Supporto per l'indirizzamento IPv6**     Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi server perimetrali. Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile utilizzare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie.
    
    <div>
    

    > [!IMPORTANT]  
    > L'utilizzo degli indirizzi IPv6 in Lync Server 2013 dipende dal supporto di IPv6 nei router e nei firewall distribuiti dall'organizzazione, nonché dal supporto tramite il provider di servizi Internet.

    
    </div>

  - **Protocollo XMPP (Extensible Messaging and Presence Protocol)**     Lync Server 2013 introduce un proxy XMPP completamente integrato (distribuito sui server perimetrali) e un gateway XMPP distribuito nei server front end. È possibile distribuire la federazione XMPP come componente facoltativo. L'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentiranno agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.
    
    <div>
    

    > [!NOTE]  
    > Attualmente, i servizi XMPP in Lync Server 2013 forniscono solo la messaggistica istantanea e la presenza tra i client Lync e i contatti basati su XMPP.

    
    </div>

  - **Servizi di mobilità per i client mobili**     Introdotti in un aggiornamento dei clienti per Lync Server 2010, i servizi per dispositivi mobili in Lync Server 2013 consentono ai client Microsoft Lync Mobile sui telefoni cellulari e sui tablet che utilizzano i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. Inoltre, i dispositivi mobili supportano alcune funzionalità di VoIP aziendale, ad esempio la partecipazione con un clic, Chiamata tramite ufficio, numero unico, segreteria telefonica e notifica delle chiamate senza risposta.
    
    <div>
    

    > [!NOTE]  
    > I servizi di mobilità utilizzano il proxy inverso e i servizi pubblicati distribuiti nel Front End Server. Non sono necessarie modifiche per i server perimetrali.

    
    </div>

  - **I direttori sono un ruolo facoltativo**     Il ruolo del server Director nella topologia di Lync Server 2013 non è stato modificato. Continua a ospitare i servizi Web, esegue la preautenticazione delle richieste utente in arrivo e indirizza gli utenti esterni al pool principale. La modifica del Director da un ruolo consigliato a un ruolo facoltativo non diminuisce il valore del Director, ma enfatizza la riduzione del numero di server e di altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità. Poiché i Front End Server possono eseguire lo stesso processo del Director senza alcun impatto sui servizi forniti, è possibile distribuire direttori se lo si sceglie. È possibile escludere in modo sicuro il Director con la sicurezza che i Front End Server forniranno gli stessi servizi al proprio posto.

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

