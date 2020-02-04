---
title: 'Lync Server 2013: Funzionalità di resilienza dei siti di succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="2d5c2-102">Funzionalità di resilienza dei siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d5c2-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d5c2-103">_**Argomento Ultima modifica:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="2d5c2-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="2d5c2-104">Se si specifica la resilienza del sito di succursale, se la connessione WAN di un sito di succursale a un sito centrale non riesce o se il sito centrale non è raggiungibile, è necessario che le caratteristiche vocali seguenti continuino a essere disponibili:</span><span class="sxs-lookup"><span data-stu-id="2d5c2-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="2d5c2-105">Chiamate PSTN (Public Switched Telephone Network) in ingresso e in uscita</span><span class="sxs-lookup"><span data-stu-id="2d5c2-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="2d5c2-106">Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi</span><span class="sxs-lookup"><span data-stu-id="2d5c2-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="2d5c2-107">Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento</span><span class="sxs-lookup"><span data-stu-id="2d5c2-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="2d5c2-108">Messaggistica istantanea a due parti</span><span class="sxs-lookup"><span data-stu-id="2d5c2-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="2d5c2-109">Inoltro di chiamata, squillo simultaneo di endpoint, delega delle chiamate e servizi di chiamata del team, ma solo se il delegante e il delegato, ad esempio un Manager e l'amministratore del responsabile, o tutti i membri del team, sono configurati nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="2d5c2-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="2d5c2-110">Record dettagli chiamata (CDRs)</span><span class="sxs-lookup"><span data-stu-id="2d5c2-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="2d5c2-111">Servizi di conferenza telefonica con accesso esterno PSTN con l'operatore automatico di conferenza</span><span class="sxs-lookup"><span data-stu-id="2d5c2-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="2d5c2-112">Funzionalità della segreteria telefonica se si configurano le impostazioni di reinstradamento della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="2d5c2-113">Per informazioni dettagliate, vedere [requisiti di resilienza dei siti secondari per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d5c2-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="2d5c2-114">Autenticazione e autorizzazione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2d5c2-114">User authentication and authorization</span></span>

<span data-ttu-id="2d5c2-115">Le caratteristiche seguenti saranno disponibili solo se la soluzione di resilienza è una distribuzione su vasta scala di Lync Server presso il sito della filiale:</span><span class="sxs-lookup"><span data-stu-id="2d5c2-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="2d5c2-116">Servizi di conferenza di messaggistica istantanea, Web e A/V</span><span class="sxs-lookup"><span data-stu-id="2d5c2-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="2d5c2-117">Routing basato su presenza e non disturbare (DND) (dove le chiamate non squillano in estensioni con DND attivato)</span><span class="sxs-lookup"><span data-stu-id="2d5c2-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="2d5c2-118">Aggiornamento delle impostazioni di inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="2d5c2-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="2d5c2-119">Applicazione Response Group Application e Call Park</span><span class="sxs-lookup"><span data-stu-id="2d5c2-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="2d5c2-120">Provisioning di nuovi telefoni e client, ma solo se i servizi di dominio Active Directory sono presenti nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="2d5c2-121">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="2d5c2-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="2d5c2-122">Se E9-1-1 è distribuito e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è in calo, il Survivable Branch Appliance instraderà le chiamate E9-1-1 al gateway della filiale locale.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="2d5c2-123">Per abilitare questa funzionalità, i criteri vocali degli utenti del sito della filiale devono instradare le chiamate al gateway locale in caso di errore WAN.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d5c2-124">SBA (Survivable Branch Office) non è supportato per XMPP.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="2d5c2-125">Gli utenti ospitati in una configurazione SBA non saranno in grado di inviare messaggi istantanei o vedere la presenza con contatti XMPP.</span><span class="sxs-lookup"><span data-stu-id="2d5c2-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

