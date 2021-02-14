---
title: Espansione delle impostazioni del server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:'
ms.openlocfilehash: cc8e0094a601faaf89c6a932172d5b6cb3522f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822436"
---
# <a name="edge-settings-expander"></a><span data-ttu-id="c7847-103">Espansione delle impostazioni del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="c7847-103">Edge Settings Expander</span></span>

<span data-ttu-id="c7847-104">Per modificare le impostazioni per un pool con un solo server perimetrale o di più server perimetrali, sono disponibili queste sezioni:</span><span class="sxs-lookup"><span data-stu-id="c7847-104">To edit the settings for an existing single or multiple server Edge pool, you are presented with the following sections:</span></span>

- <span data-ttu-id="c7847-105">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="c7847-105">General settings</span></span>

- <span data-ttu-id="c7847-106">Impostazioni per la selezione dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="c7847-106">Next hop selection settings</span></span>

- <span data-ttu-id="c7847-107">Configurazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c7847-107">Edge Server configuration</span></span>


## <a name="general-settings"></a><span data-ttu-id="c7847-108">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="c7847-108">General settings</span></span>

<span data-ttu-id="c7847-p101">Nome di dominio completo (FQDN) interno del pool di server perimetrali. Modificare l'FQDN del pool per cambiare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="c7847-p101">Internal pool fully qualified domain name (FQDN) of the Edge Server pool. Edit the FQDN of the pool to change this setting.</span></span>

<span data-ttu-id="c7847-111">Selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061)** se si configura la federazione con un server Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c7847-111">Select the check box **Enable federation for this Edge pool (Port 5061)** if you will set up federation with a Skype for Business Server 2015 server.</span></span>

<span data-ttu-id="c7847-112">Specificare il numero di porta per **Porta di replica configurazione interna (HTTPS)**.</span><span class="sxs-lookup"><span data-stu-id="c7847-112">Specify the port number for **Internal Configuration Replication Port (HTTPS)**.</span></span>

## <a name="next-hop-selection-settings"></a><span data-ttu-id="c7847-113">Impostazioni per la selezione dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="c7847-113">Next hop selection settings</span></span>

<span data-ttu-id="c7847-114">Per impostare o modificare il pool hop successivo che verrà utilizzato dai server perimetrali per comunicare con l'infrastruttura interna, selezionare un **director,** un pool di server Director, un Front End Server o un pool Front End Server dalla casella di riepilogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="c7847-114">To set or modify the **Next hop pool** that the Edge Servers will use to communicate to the internal infrastructure, select a Director, Director pool, Front End Server, or Front End Server pool from the drop-down list box.</span></span> <span data-ttu-id="c7847-115">Solo i Director o i Front End Server configurati in Generatore di topologie verranno visualizzati per la selezione.</span><span class="sxs-lookup"><span data-stu-id="c7847-115">Only Directors or Front Ends that have been configured in Topology Builder will appear for selection.</span></span>

## <a name="edge-server-configuration"></a><span data-ttu-id="c7847-116">Configurazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c7847-116">Edge Server configuration</span></span>

<span data-ttu-id="c7847-117">Per modificare o specificare le opzioni per **Impostazioni esterne** per i server perimetrali, è necessario prima di tutto determinare se verranno usati indirizzi IP separati per l'accesso SIP, il servizio Web Conferencing e il servizio Audio/Video.</span><span class="sxs-lookup"><span data-stu-id="c7847-117">To edit or specify settings for the **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for SIP access, web conferencing, and the Audio/Video service.</span></span>

<span data-ttu-id="c7847-p103">Se per ognuno si vuole usare indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c7847-p103">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding DNS host (A) record created for it.</span></span>

<span data-ttu-id="c7847-p104">Per ogni servizio con accesso all'esterno, specificare un FQDN e una porta associata. Ad esempio, per **Accesso SIP** è possibile usare sip.contoso.com con la porta 5061 associata.</span><span class="sxs-lookup"><span data-stu-id="c7847-p104">For each of the external-facing services, you specify a FQDN and an associated port. For example, the **SIP Access** would use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7847-122">Se si selezionano FQDN separati per ognuno dei servizi con accesso all'esterno, a ogni servizio deve essere associato un valore di porta univoco.</span><span class="sxs-lookup"><span data-stu-id="c7847-122">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="c7847-123">Per impostazione predefinita, sip è sulla porta 5061/TLS, il servizio Web Conferencing Edge si trova sulla porta 444/TLS e A/V Conferencing Server è sulla porta 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="c7847-123">By default, the SIP is on port 5061/TLS, the web conferencing edge service is on port 444/TLS, and the A/V Conferencing Server is on port 443/TLS.</span></span> <span data-ttu-id="c7847-124">Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di usare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="c7847-124">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all the other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="c7847-p106">Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c7847-p106">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7847-127">Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="c7847-127">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7847-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7847-128">See also</span></span>

<span data-ttu-id="c7847-129">Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Edge, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="c7847-129">For details about defining and configuring the settings for the Edge Services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


