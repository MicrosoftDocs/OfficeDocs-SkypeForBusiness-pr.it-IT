---
title: 'Lync Server 2013: Caratteristiche e funzionalità di Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a76dfed553e85838739c7c348e5bc53fc9943a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="5f722-102">Caratteristiche e funzionalità di Front End Server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f722-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f722-103">_**Argomento Ultima modifica:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="5f722-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="5f722-104">I server front-end garantiscono la maggior parte delle funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f722-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="5f722-105">Sono disponibili due edizioni: Lync Server Enterprise Edition, progettato principalmente per le organizzazioni di grandi dimensioni, e Lync Server Standard Edition, progettato principalmente per le organizzazioni più piccole che desiderano un Investment hardware più piccolo e non richiedono disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="5f722-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="5f722-106">Entrambe le edizioni supportano tutti i carichi di lavoro di Lync Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="5f722-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="5f722-107">La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo.</span><span class="sxs-lookup"><span data-stu-id="5f722-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="5f722-108">Sono supportate entrambe le sessioni di messaggistica istantanea a due parti e a più parti.</span><span class="sxs-lookup"><span data-stu-id="5f722-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="5f722-109">Un partecipante a una conversazione di messaggistica istantanea a due parti può aggiungere un terzo partecipante alla conversazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="5f722-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="5f722-110">In questo caso, la finestra di conversazione viene modificata per supportare le funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="5f722-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5f722-111">I client di Lync e Communicator quando sono coinvolti in una comunicazione uno-a-uno, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="5f722-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="5f722-112">Tecnicamente, i due client comunicano in una conversazione uno-a-uno, con l'unità di controllo multipunto di messaggistica istantanea (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="5f722-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="5f722-113">IMMCU è un componente del server front-end.</span><span class="sxs-lookup"><span data-stu-id="5f722-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="5f722-114">L'immissione di IMMCU nel flusso di lavoro di comunicazione richiesto consente la registrazione dei dettagli delle chiamate e altre caratteristiche abilitate dal server front-end.</span><span class="sxs-lookup"><span data-stu-id="5f722-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="5f722-115">La comunicazione è da una porta di origine dinamica nel client alla porta del server front-end TLS/TCP/5061 (presupponendo l'uso della sicurezza del livello di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="5f722-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="5f722-116">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU è attivo e disponibile.</span><span class="sxs-lookup"><span data-stu-id="5f722-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="5f722-117">La *presenza* fornisce informazioni agli utenti sullo stato di un altro utente nella rete.</span><span class="sxs-lookup"><span data-stu-id="5f722-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="5f722-118">Lo stato presenza di un utente fornisce informazioni utili per consentire agli altri utenti di decidere se provare a contattare l'utente e se usare la messaggistica istantanea, il telefono o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5f722-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="5f722-119">La presenza incoraggia le comunicazioni istantanee quando possibile, ma fornisce anche informazioni sul fatto che un utente si trovi in una riunione o fuori sede, indicando che la comunicazione immediata non è possibile.</span><span class="sxs-lookup"><span data-stu-id="5f722-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="5f722-120">Questo stato presenza viene visualizzato come icona presenza in Lync e in altre applicazioni che supportano la presenza, incluso il client di messaggistica e collaborazione di Microsoft Outlook, Microsoft SharePoint Technologies, Microsoft Word e il foglio di calcolo di Microsoft Excel software.</span><span class="sxs-lookup"><span data-stu-id="5f722-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="5f722-121">L'icona presenza rappresenta la disponibilità corrente dell'utente e la disponibilità a comunicare.</span><span class="sxs-lookup"><span data-stu-id="5f722-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

