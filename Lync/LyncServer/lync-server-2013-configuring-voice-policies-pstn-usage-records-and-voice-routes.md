---
title: Configurazione di criteri vocali, record di utilizzo PSTN e route vocali
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e749419cf84303cfef9d4718488a4483adecb97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537003"
---
# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="f0651-102">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0651-103">_**Ultimo argomento modificato:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f0651-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f0651-p101">I criteri vocali, i record di utilizzo PSTN e le route vocali sono strettamente correlati. È infatti possibile configurare i criteri vocali selezionando un insieme di funzionalità di chiamata e quindi assegnando al criterio un insieme di record di utilizzo PSTN, che specificano quali diritti sono autorizzati per gli utenti o i gruppi a cui viene assegnato il criterio. Anche alle route vocali vengono assegnati record di utilizzo PSTN, allo scopo di trovare una corrispondenza tra le route e gli utenti che sono autorizzati a utilizzarle. In altri termini, gli utenti possono effettuare esclusivamente chiamate che utilizzino le route per cui dispongono di un record di utilizzo PSTN corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f0651-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="f0651-108">Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nel configurare innanzitutto un criterio vocale contenente i record di utilizzo PSTN appropriati e quindi nell'associare le route appropriate a ogni record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="f0651-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f0651-109">È inoltre possibile creare criteri vocali con ambito <EM>utente </EM> e assegnarli a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="f0651-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="f0651-110">Per i passaggi dettagliati per l'esecuzione di ognuna di queste attività, vedere le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f0651-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0651-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f0651-111">In This Section</span></span>

  - [<span data-ttu-id="f0651-112">Configurazione di criteri vocali e record utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="f0651-113">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="f0651-114">Configurazione di route vocali per le chiamate in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="f0651-115">Esportazione e importazione della configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="f0651-116">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="f0651-117">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0651-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

