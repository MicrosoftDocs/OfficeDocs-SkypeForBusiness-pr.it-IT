---
title: 'Lync Server 2013: funzionalità di resilienza dei siti di succursale'
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
ms.openlocfilehash: b8f141b592fb5a89941d5b6e2b3e1e5c9d770fdc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513013"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="e7b3a-102">Funzionalità di resilienza dei siti di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7b3a-102">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b3a-103">_**Ultimo argomento modificato:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="e7b3a-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="e7b3a-104">Se si fornisce la resilienza dei siti derivati, in caso di errore della connessione WAN di un sito derivato con un sito centrale o qualora il sito centrale non sia raggiungibile, le funzionalità vocali seguenti devono continuare a essere disponibili:</span><span class="sxs-lookup"><span data-stu-id="e7b3a-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="e7b3a-105">Chiamate PSTN in entrata e in uscita</span><span class="sxs-lookup"><span data-stu-id="e7b3a-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="e7b3a-106">Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi</span><span class="sxs-lookup"><span data-stu-id="e7b3a-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="e7b3a-107">Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento</span><span class="sxs-lookup"><span data-stu-id="e7b3a-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="e7b3a-108">Messaggistica istantanea tra due parti</span><span class="sxs-lookup"><span data-stu-id="e7b3a-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="e7b3a-109">Inoltro di chiamata, squillo simultaneo degli endpoint, delega delle chiamate e servizi di intercettazione team, ma solo se delegante e delegato (ad esempio un capo e l'amministratore del capo), oppure tutti i membri del team, sono configurati nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="e7b3a-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="e7b3a-110">Registrazione dettagli chiamata (CDR)</span><span class="sxs-lookup"><span data-stu-id="e7b3a-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="e7b3a-111">Conferenze telefoniche con accesso esterno PSTN con Operatore automatico conferenza</span><span class="sxs-lookup"><span data-stu-id="e7b3a-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="e7b3a-112">Funzionalità di segreteria telefonica, se si configurano le impostazioni di rerouting della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="e7b3a-113">Per informazioni dettagliate, vedere [requisiti di resilienza dei siti di succursale per Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7b3a-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="e7b3a-114">Autenticazione e autorizzazione utente</span><span class="sxs-lookup"><span data-stu-id="e7b3a-114">User authentication and authorization</span></span>

<span data-ttu-id="e7b3a-115">Le funzionalità seguenti saranno disponibili solo se la soluzione di resilienza è una distribuzione di Lync Server su vasta scala nel sito di succursale:</span><span class="sxs-lookup"><span data-stu-id="e7b3a-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="e7b3a-116">Conferenze di messaggistica istantanea, Web e audio/video</span><span class="sxs-lookup"><span data-stu-id="e7b3a-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="e7b3a-117">Routing in base a presenza e Non disturbare (le chiamate non squillano agli interni che hanno il Non disturbare attivato)</span><span class="sxs-lookup"><span data-stu-id="e7b3a-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="e7b3a-118">Aggiornamento delle impostazioni di inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="e7b3a-119">Applicazione Response Group e applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="e7b3a-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="e7b3a-120">Provisioning di nuovi telefoni e client, ma solo se i servizi di dominio Active Directory sono presenti nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="e7b3a-121">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="e7b3a-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="e7b3a-122">Se si distribuisce il servizio E9-1-1 e il trunk SIP nel sito centrale non è disponibile perché il collegamento WAN è inattivo, il Survivable Branch Appliance instraderà le chiamate di E9-1-1 al gateway di succursale locale.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="e7b3a-123">Per abilitare questa funzionalità, i criteri vocali degli utenti del sito di succursale devono eseguire il routing delle chiamate al gateway locale in caso di errore della WAN.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7b3a-124">SBA (Survivable Branch Office) non è supportato per XMPP.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="e7b3a-125">Gli utenti ospitati in una configurazione SBA non saranno in grado di inviare messaggi istantanei o vedere presenza con contatti XMPP.</span><span class="sxs-lookup"><span data-stu-id="e7b3a-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

