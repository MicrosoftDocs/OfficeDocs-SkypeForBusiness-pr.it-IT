---
title: Aggiungere associazioni di Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:'
ms.openlocfilehash: 8ff7d11a40f7eccfda78643fd8b3a17146c014d7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103252"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="30c3e-105">Aggiungere associazioni di Front End Server</span><span class="sxs-lookup"><span data-stu-id="30c3e-105">Add Front End Associations</span></span>

<span data-ttu-id="30c3e-p102">È ora possibile abilitare il supporto di funzionalità specifiche che richiedono la distribuzione di altri server associando ruoli del server al pool Front End. È inoltre possibile associare ruoli del server con il pool Front End in un secondo momento. I ruoli del server che possono essere associati a un pool Front End includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="30c3e-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="30c3e-109">A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="30c3e-109">A/V Edge Server.</span></span> <span data-ttu-id="30c3e-110">Per informazioni dettagliate sull'implementazione di un A/V Edge Server, vedere [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="30c3e-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30c3e-111">Se si abilita ora il supporto per una di queste funzionalità, la progettazione della topologia pubblicata includerà i componenti server necessari per implementare ogni funzionalità selezionata.</span><span class="sxs-lookup"><span data-stu-id="30c3e-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="30c3e-112">Per pubblicare una topologia senza che vengano generati errori, è necessario che i computer fisici siano aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="30c3e-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="30c3e-113">Ad esempio, se si abilita ora il supporto per l'archiviazione, è necessario distribuire un server di archiviazione e configurare le opzioni di archiviazione appropriate prima di avviare l'archiviazione delle comunicazioni per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30c3e-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>