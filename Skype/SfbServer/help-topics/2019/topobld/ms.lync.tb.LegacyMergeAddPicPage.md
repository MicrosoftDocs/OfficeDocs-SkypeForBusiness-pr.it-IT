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
description: L'FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare alle riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805706"
---
# <a name="legacy-merge"></a><span data-ttu-id="2f281-104">Unione legacy</span><span class="sxs-lookup"><span data-stu-id="2f281-104">Legacy Merge</span></span>

<span data-ttu-id="2f281-105">**L'FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare alle riunioni locali.</span><span class="sxs-lookup"><span data-stu-id="2f281-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="2f281-106">Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="2f281-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="2f281-107">Il valore della porta esterna **443** per le conferenze **Web** esterne è la porta SIP (Session Initiation Protocol) TCP (Transmission Control Protocol) predefinita configurata per i client di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2f281-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="2f281-108">Se non è stato utilizzato il valore predefinito, aggiornare il valore della porta **esterna di Web Conferencing** esterna.</span><span class="sxs-lookup"><span data-stu-id="2f281-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="2f281-109">Selezionare la casella di controllo Questo pool di server perimetrali viene utilizzato per la federazione e la connettività **per messaggistica** istantanea pubblica se si prevede di utilizzare questo server perimetrale per la federazione.</span><span class="sxs-lookup"><span data-stu-id="2f281-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="2f281-110">Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="2f281-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="2f281-111">Se non si seleziona questa casella e in seguito si decide di abilitare la federazione, sarà necessario eseguire di nuovo l'unione guidata di Generatore di topologie e pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="2f281-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="2f281-112">Per informazioni dettagliate, vedere [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f281-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


