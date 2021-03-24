---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per Mediation Server è possibile specificare quanto segue:'
ms.openlocfilehash: e3593fd98c9207b6dd7033e5aac26170988ae956
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096902"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="9ec95-103">Espansione delle impostazioni del servizio Mediation</span><span class="sxs-lookup"><span data-stu-id="9ec95-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="9ec95-104">Per **Mediation Server** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ec95-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="9ec95-105">Se si colloca il Mediation Server nel pool Front End o nel server Standard Edition, selezionare la casella di controllo **Mediation Server collocato abilitato.**</span><span class="sxs-lookup"><span data-stu-id="9ec95-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="9ec95-106">Se si sceglie di non collocare il Mediation Server, non vi sono impostazioni che è possibile definire in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9ec95-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="9ec95-p102">Se il collocamento di Mediation Server è stato abilitato, sarà necessario definire l'intervallo delle porte di attesa sul server per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network). Per impostazione predefinita, il valore della porta TCP è 5068.</span><span class="sxs-lookup"><span data-stu-id="9ec95-p102">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="9ec95-p103">Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9ec95-p103">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="9ec95-p104">Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.</span><span class="sxs-lookup"><span data-stu-id="9ec95-p104">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**. To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="9ec95-117">Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per il pool Enterprise Edition Front End o il server Standard Edition, vedere [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) e [Deploying Mediation Server e Defining Peers.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)</span><span class="sxs-lookup"><span data-stu-id="9ec95-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>