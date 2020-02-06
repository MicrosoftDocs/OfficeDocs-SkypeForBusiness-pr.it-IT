---
title: Unione legacy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Il nome FQDN esterno di Web Conferencing consente agli utenti esterni di partecipare a riunioni locali. Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.
ms.openlocfilehash: 8572436ac1f72b5aed611dbaee53e93b68e98e81
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795367"
---
# <a name="legacy-merge"></a><span data-ttu-id="2ca03-104">Unione legacy</span><span class="sxs-lookup"><span data-stu-id="2ca03-104">Legacy Merge</span></span>

<span data-ttu-id="2ca03-105">Il **nome FQDN esterno di Web Conferencing** consente agli utenti esterni di partecipare a riunioni locali.</span><span class="sxs-lookup"><span data-stu-id="2ca03-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="2ca03-106">Immettere il nome di dominio completo (FQDN) dell'interfaccia esterna di Web Conferencing del server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="2ca03-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="2ca03-107">Il valore della **porta esterna Web** per la conferenza esterna di **443** è la porta SIP (default Transmission Control Protocol) predefinita configurata per i client di conferenza.</span><span class="sxs-lookup"><span data-stu-id="2ca03-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="2ca03-108">Se il valore predefinito non è stato usato, aggiornare il valore della **porta esterna di Web Conferencing esterno** .</span><span class="sxs-lookup"><span data-stu-id="2ca03-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="2ca03-109">Selezionare la casella di controllo **questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** se si prevede di usare questo Edge Server per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="2ca03-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="2ca03-110">Se sono distribuiti più server perimetrali, solo uno di essi verrà abilitato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="2ca03-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="2ca03-111">Se non si seleziona questa casella e si decide in seguito che si vuole abilitare la Federazione, è necessario eseguire di nuovo la procedura guidata di Unione di generatore di topologia, nonché pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="2ca03-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="2ca03-112">Per informazioni dettagliate, vedere la [fase 4: unire le topologie](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ca03-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


