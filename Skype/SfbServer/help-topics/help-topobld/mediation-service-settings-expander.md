---
title: Espansione delle impostazioni del servizio Mediation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Per il Mediation Server è possibile specificare quanto segue:'
ms.openlocfilehash: e6b89c61e84577af86576850f5c675861cfa3a80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819558"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="85dea-103">Espansione delle impostazioni del servizio Mediation</span><span class="sxs-lookup"><span data-stu-id="85dea-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="85dea-104">Per il **Mediation Server** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="85dea-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="85dea-105">Se si sta collocando il Mediation Server sul pool Front-end o sul server Standard Edition, selezionare la casella di controllo **Mediation Server collocato abilitato**.</span><span class="sxs-lookup"><span data-stu-id="85dea-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="85dea-106">Se si sceglie di non collocare il Mediation Server, in questa sezione non sono disponibili impostazioni definibili.</span><span class="sxs-lookup"><span data-stu-id="85dea-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="85dea-107">Se è stata abilitata la collocazione di Mediation Server, è necessario definire l'intervallo della porta in attesa nel server per Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="85dea-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="85dea-108">Per impostazione predefinita, questa porta è la 5067.</span><span class="sxs-lookup"><span data-stu-id="85dea-108">By default, this port is 5067.</span></span> <span data-ttu-id="85dea-109">Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato.</span><span class="sxs-lookup"><span data-stu-id="85dea-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="85dea-110">Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="85dea-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="85dea-111">Per impostazione predefinita, il valore della porta TCP è 5068.</span><span class="sxs-lookup"><span data-stu-id="85dea-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="85dea-112">Puoi definire i gateway PSTN associati al Mediation Server collocato.</span><span class="sxs-lookup"><span data-stu-id="85dea-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="85dea-113">Se sono già stati definiti gateway, saranno disponibili per l'associazione con il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="85dea-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="85dea-114">Se si ha più di un gateway associato a un Mediation Server, il primo gateway associato sarà il gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="85dea-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="85dea-115">Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="85dea-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="85dea-116">Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.</span><span class="sxs-lookup"><span data-stu-id="85dea-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="85dea-117">Per informazioni dettagliate su come definire e configurare le impostazioni per il pool di front end Enterprise Edition o per il server Standard Edition, vedere [definizione e configurazione della topologia](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) e [distribuzione di Mediation Server e definizione di peer](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="85dea-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


