---
title: 'Lync Server 2013: contratti a livello di servizio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f902a946d272ce3a16db5f032b74ec031c7e3a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="13f3d-102">Contratti a livello di servizio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13f3d-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13f3d-103">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="13f3d-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="13f3d-104">Il contratto di servizio è un documento che definisce i servizi che il cliente si aspetta da un utente.</span><span class="sxs-lookup"><span data-stu-id="13f3d-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="13f3d-105">La complessità e il contenuto di questo documento dipendono in gran parte dal fatto che i clienti siano interni (all'interno dell'ambiente) o esterni.</span><span class="sxs-lookup"><span data-stu-id="13f3d-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="13f3d-106">Clienti esterni</span><span class="sxs-lookup"><span data-stu-id="13f3d-106">External Customers</span></span>

<span data-ttu-id="13f3d-107">Se il cliente è esterno, l'SLA può essere incluso in un contratto legale con incentivi finanziari e penalità per le prestazioni che cadono all'interno o all'esterno di livelli di servizio definiti.</span><span class="sxs-lookup"><span data-stu-id="13f3d-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="13f3d-108">La definizione di questi livelli di servizio deve essere inclusa nella negoziazione generale del contratto.</span><span class="sxs-lookup"><span data-stu-id="13f3d-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="13f3d-109">Come per tutti i contratti, è importante che entrambe le parti comprendano le aspettative.</span><span class="sxs-lookup"><span data-stu-id="13f3d-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="13f3d-110">Il contratto di servizio di SLA definisce queste aspettative.</span><span class="sxs-lookup"><span data-stu-id="13f3d-110">The SLA defines these expectations.</span></span> <span data-ttu-id="13f3d-111">Il contenuto del documento deve essere modificato raramente e solo a causa di trattative con il cliente.</span><span class="sxs-lookup"><span data-stu-id="13f3d-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="13f3d-112">Clienti interni</span><span class="sxs-lookup"><span data-stu-id="13f3d-112">Internal Customers</span></span>

<span data-ttu-id="13f3d-113">Se il cliente è interno, è possibile che si desideri ancora definire i servizi previsti per i team operativi e i sistemi IT.</span><span class="sxs-lookup"><span data-stu-id="13f3d-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="13f3d-114">Il servizio SLA può essere creato dal personale operativo e intesa come un insieme di obiettivi per la disponibilità dei servizi IT all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="13f3d-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="13f3d-115">In alternativa, i livelli di prestazioni possono essere impostati dalla gestione e utilizzati come benchmark quando si valutano le prestazioni del personale.</span><span class="sxs-lookup"><span data-stu-id="13f3d-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="13f3d-116">Criteri tipici</span><span class="sxs-lookup"><span data-stu-id="13f3d-116">Typical Criteria</span></span>

<span data-ttu-id="13f3d-117">Gli SLA includono sezioni che definiscono i criteri di livelli minimi di disponibilità, supporto e capacità.</span><span class="sxs-lookup"><span data-stu-id="13f3d-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="13f3d-118">**Disponibilità**   definire le ore e i sistemi operativi in cui saranno disponibili i siti e gli altri servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="13f3d-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="13f3d-119">Qualsiasi manutenzione di routine che influisce sulla disponibilità del servizio deve essere definita.</span><span class="sxs-lookup"><span data-stu-id="13f3d-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="13f3d-120">Definire fattori esterni che influiscono sul servizio, ad esempio la perdita di connettività Internet.</span><span class="sxs-lookup"><span data-stu-id="13f3d-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="13f3d-121">**Supporto**   definire le ore in cui il supporto di un sistema sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="13f3d-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="13f3d-122">Specificare i metodi per i clienti per contattare il personale di supporto, la modalità di raggruppamento degli incidenti e il tempo di destinazione per la risposta e la risoluzione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="13f3d-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="13f3d-123">Definire la frequenza e il contenuto dei commenti e suggerimenti per il cliente.</span><span class="sxs-lookup"><span data-stu-id="13f3d-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="13f3d-124">**Capacità**   definire le dimensioni massime abilitate dei siti di Lync e i passaggi da eseguire se viene superato il limite.</span><span class="sxs-lookup"><span data-stu-id="13f3d-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="13f3d-125">Definire il tempo massimo consentito per eseguire attività standard, ad esempio il tempo necessario per recuperare un documento da una raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="13f3d-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="13f3d-126">Definire il numero massimo di utenti per pool Lync e accettare un processo per aumentare la capacità se sono stati aggiunti più utenti.</span><span class="sxs-lookup"><span data-stu-id="13f3d-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

