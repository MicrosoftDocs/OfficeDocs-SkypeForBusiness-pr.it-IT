---
title: Unione legacy
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: L'FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.
ms.openlocfilehash: 87b70bc6d577f2752c00c7f7f73577eac7e759fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121064"
---
# <a name="legacy-merge"></a><span data-ttu-id="61cb0-104">Unione legacy</span><span class="sxs-lookup"><span data-stu-id="61cb0-104">Legacy Merge</span></span>

<span data-ttu-id="61cb0-105">**L'FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali.</span><span class="sxs-lookup"><span data-stu-id="61cb0-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="61cb0-106">Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna per conferenze Web del server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="61cb0-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="61cb0-107">Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Transmission Control Protocol) predefinita configurata per i client di conferenza.</span><span class="sxs-lookup"><span data-stu-id="61cb0-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="61cb0-108">Se il valore predefinito non è stato utilizzato, aggiornare il **valore della porta esterna di Conferenza Web** esterna.</span><span class="sxs-lookup"><span data-stu-id="61cb0-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="61cb0-109">Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per **la federazione** e la connettività di messaggistica istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione.</span><span class="sxs-lookup"><span data-stu-id="61cb0-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="61cb0-110">Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="61cb0-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="61cb0-111">Se non si seleziona questa casella e si decide in un secondo momento che si desidera abilitare la federazione, è necessario eseguire di nuovo l'Unione guidata generatore di topologie, nonché pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="61cb0-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="61cb0-112">Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).</span><span class="sxs-lookup"><span data-stu-id="61cb0-112">For details, see [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).</span></span>