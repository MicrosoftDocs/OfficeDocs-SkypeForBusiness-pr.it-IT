---
title: Lync Server 2013 messaggistica istantanea e presenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1c612102cb34113c96d02e9e408563a16bfb3bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="1fd1c-102">Messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd1c-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd1c-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="1fd1c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="1fd1c-104">La messaggistica istantanea e la presenza vengono installate automaticamente in qualsiasi distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="1fd1c-105">Le informazioni sulla *presenza* consentono agli utenti di contattare i colleghi nel momento più appropriato con la corretta forma di comunicazione, per garantire un ambiente di lavoro più produttivo.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="1fd1c-106">La presenza di un utente è una raccolta di informazioni che includono la disponibilità, la disposizione a comunicare, note aggiuntive (come posizione e stato) e le modalità in cui può essere contattato un utente.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="1fd1c-107">La presenza è migliorata in Lync Server con immagini, informazioni sulla posizione e un insieme avanzato di Stati di presenza che includono "off work", "not disturbe" e "right back", oltre agli Stati di base, ad esempio "available", "Busy" e "in a Conference".</span><span class="sxs-lookup"><span data-stu-id="1fd1c-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="1fd1c-108">Gli amministratori possono inoltre definire stati presenza specifici dell'organizzazione e personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="1fd1c-p102">Opzioni di gestione dei contatti e di accesso utente consentono agli utenti di controllare le informazioni visualizzate dagli altri. Gli utenti possono impostare livelli diversi di contatti, ciascuno dei quali può visualizzare livelli diversi di informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-p102">Contact management and user access options enable users to control what information others can see. Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="1fd1c-p103">Semplicemente osservando un elenco di contatti, gli utenti possono trovare immediatamente tutte le informazioni necessarie. Icone colorate intuitive indicano lo stato di presenza di altri utenti. Vengono visualizzate anche un'immagine e la posizione.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-p103">By simply looking at a Contacts list, users can find everything they need to know at a glance. Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="1fd1c-113">Con l'integrazione tra Lync Server e altri prodotti come Outlook e SharePoint, ogni volta che viene visualizzato il nome di un contatto, ad esempio in un messaggio di posta elettronica o in un sito Web del team, vengono visualizzati anche lo stato e le informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="1fd1c-114">Inoltre, se si distribuisce Exchange 2013, Lync Server e Exchange 2013 possono condividere un archivio contatti unificato, a cui è possibile accedere dai client di entrambi i prodotti.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="1fd1c-115">Con la messaggistica istantanea in Lync Server, gli utenti possono rapidamente inviarsi un messaggio con informazioni tempestive.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="1fd1c-116">Se si preferisce, gli utenti possono anche comunicare con gli utenti di reti di messaggistica istantanea pubblica, ad esempio MSN/\!Windows Live, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="1fd1c-117">Si noti che potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con Windows Live, AOL e Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="1fd1c-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="1fd1c-118">Lync Server include anche la compatibilità con il protocollo XMPP (Extensible Messaging and Presence Protocol), in modo che gli utenti possano scambiare messaggi di messaggistica istantanea e informazioni sulla presenza con utenti di servizi XMPP come Google Talk.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1fd1c-119">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="1fd1c-120">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1fd1c-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1fd1c-121">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="1fd1c-122">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1fd1c-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1fd1c-123">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-123">has been announced.</span></span> <span data-ttu-id="1fd1c-124">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="1fd1c-125">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1fd1c-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1fd1c-126">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-126">Messenger.</span></span> <span data-ttu-id="1fd1c-127">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="1fd1c-128">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1fd1c-129">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1fd1c-130">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1fd1c-131">La cronologia conversazioni consente agli utenti di tenere traccia di vecchie conversazioni di messaggistica istantanea e di recuperare informazioni che potrebbero essere state comunicate di messaggistica istantanea anche diversi mesi prima.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="1fd1c-132">La funzionalità Persistent Chat consente agli utenti di partecipare a conversazioni a più parti, basate su argomenti che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="1fd1c-133">I messaggi inseriti nelle chat room (forum di discussione) possono essere permanenti, ovvero possono rimanere disponibili nel tempo, in modo da consentire la partecipazione di persone dislocate in sedi e reparti diversi, anche quando non sono tutte online contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="1fd1c-134">Se l'organizzazione è soggetta a regolamentazioni di conformità, è possibile distribuire una caratteristica di archiviazione dei messaggi che consente di archiviare il contenuto dei messaggi istantanei per tutti gli utenti dell'organizzazione o solo per alcuni utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="1fd1c-135">Se si distribuisce anche Exchange 2013, l'archivio di messaggistica istantanea può essere integrato con la funzionalità di archiviazione sul posto di Exchange, per fornire una singola esperienza di amministrazione per la conformità.</span><span class="sxs-lookup"><span data-stu-id="1fd1c-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

