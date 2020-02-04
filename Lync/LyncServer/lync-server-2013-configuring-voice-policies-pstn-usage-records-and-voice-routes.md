---
title: Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali
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
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="8c528-102">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c528-103">_**Argomento Ultima modifica:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="8c528-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="8c528-104">I criteri vocali, i record di utilizzo PSTN e le route vocali sono correlati integralmente.</span><span class="sxs-lookup"><span data-stu-id="8c528-104">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="8c528-105">Si configurano i criteri vocali selezionando un set di funzionalità di chiamata e quindi assegnando al criterio un set di record di utilizzo PSTN, che specificano i diritti autorizzati per gli utenti o i gruppi a cui è assegnato il criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="8c528-105">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="8c528-106">Alle route vocali vengono assegnati anche record di utilizzo PSTN, che servono per abbinare le route con gli utenti autorizzati ad usarli.</span><span class="sxs-lookup"><span data-stu-id="8c528-106">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="8c528-107">Gli utenti possono quindi inserire solo chiamate che usano le route per cui hanno un record di utilizzo PSTN corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8c528-107">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="8c528-108">Il flusso di lavoro consigliato per una nuova distribuzione di VoIP aziendale consiste nell'iniziare la configurazione di un criterio vocale che include i record di utilizzo PSTN appropriati e quindi associare le route appropriate a ogni record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="8c528-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8c528-109">È anche possibile creare criteri vocali con l'ambito <EM>degli</EM> utenti e assegnarli a singoli utenti o gruppi.</span><span class="sxs-lookup"><span data-stu-id="8c528-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="8c528-110">Per la procedura dettagliata per eseguire ognuna di queste attività, vedere le procedure descritte in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="8c528-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c528-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8c528-111">In This Section</span></span>

  - [<span data-ttu-id="8c528-112">Configurazione di criteri vocali e record utilizzo PSTN per autorizzare privilegi e funzionalità di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="8c528-113">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="8c528-114">Configurazione di route vocali per le chiamate in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="8c528-115">Esportazione e importazione della configurazione di route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="8c528-116">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="8c528-117">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c528-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

