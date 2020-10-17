---
title: "Lync Server 2013: nuove funzionalità per l'accesso degli utenti esterni"
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
ms.openlocfilehash: 43df9901b7bac37bb812eeb00c54537151496eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534313"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="bdd69-102">Nuove funzionalità per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd69-102">New features for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd69-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="bdd69-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="bdd69-104">Lync Server 2013 introduce nuove funzionalità che estendono le funzionalità e i metodi di comunicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bdd69-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="bdd69-105">Inoltre, Lync Server 2013 introduce modifiche ai servizi esistenti per migliorare l'integrazione e l'estensione dei servizi disponibili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bdd69-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="bdd69-106">Di seguito è riportato un riepilogo delle modifiche che possono influire sulla pianificazione e la distribuzione dei servizi server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdd69-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="bdd69-107">**Supporto per l'indirizzamento IPv6**     Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="bdd69-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="bdd69-108">Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile utilizzare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="bdd69-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bdd69-109">L'utilizzo degli indirizzi IPv6 in Lync Server 2013 dipende dal supporto di IPv6 nei router e nei firewall distribuiti dall'organizzazione, nonché dal supporto tramite il provider di servizi Internet.</span><span class="sxs-lookup"><span data-stu-id="bdd69-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="bdd69-110">**Protocollo XMPP (Extensible Messaging and Presence Protocol)**     Lync Server 2013 introduce un proxy XMPP completamente integrato (distribuito sui server perimetrali) e un gateway XMPP distribuito nei server front end.</span><span class="sxs-lookup"><span data-stu-id="bdd69-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="bdd69-111">È possibile distribuire la federazione XMPP come componente facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bdd69-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="bdd69-112">L'aggiunta e la configurazione del proxy XMPP e del gateway XMPP consentiranno agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="bdd69-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdd69-113">Attualmente, i servizi XMPP in Lync Server 2013 forniscono solo la messaggistica istantanea e la presenza tra i client Lync e i contatti basati su XMPP.</span><span class="sxs-lookup"><span data-stu-id="bdd69-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="bdd69-114">**Servizi di mobilità per i client mobili**     Introdotti in un aggiornamento dei clienti per Lync Server 2010, i servizi per dispositivi mobili in Lync Server 2013 consentono ai client Microsoft Lync Mobile sui telefoni cellulari e sui tablet che utilizzano i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="bdd69-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="bdd69-115">Inoltre, i dispositivi mobili supportano alcune funzionalità di VoIP aziendale, ad esempio la partecipazione con un clic, Chiamata tramite ufficio, numero unico, segreteria telefonica e notifica delle chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="bdd69-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdd69-116">I servizi di mobilità utilizzano il proxy inverso e i servizi pubblicati distribuiti nel Front End Server.</span><span class="sxs-lookup"><span data-stu-id="bdd69-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="bdd69-117">Non sono necessarie modifiche per i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="bdd69-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="bdd69-118">**I direttori sono un ruolo facoltativo**     Il ruolo del server Director nella topologia di Lync Server 2013 non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="bdd69-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="bdd69-119">Continua a ospitare i servizi Web, esegue la preautenticazione delle richieste utente in arrivo e indirizza gli utenti esterni al pool principale.</span><span class="sxs-lookup"><span data-stu-id="bdd69-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="bdd69-120">La modifica del Director da un ruolo consigliato a un ruolo facoltativo non diminuisce il valore del Director, ma enfatizza la riduzione del numero di server e di altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bdd69-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="bdd69-121">Poiché i Front End Server possono eseguire lo stesso processo del Director senza alcun impatto sui servizi forniti, è possibile distribuire direttori se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="bdd69-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="bdd69-122">È possibile escludere in modo sicuro il Director con la sicurezza che i Front End Server forniranno gli stessi servizi al proprio posto.</span><span class="sxs-lookup"><span data-stu-id="bdd69-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bdd69-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdd69-123">See Also</span></span>


[<span data-ttu-id="bdd69-124">Pianificazione e configurazione di IPv6 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd69-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="bdd69-125">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd69-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="bdd69-126">Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd69-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

