---
title: Espansione delle impostazioni dei nomi di dominio completi (FQDN) per il server perimetrale
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
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Per modificare o specificare le impostazioni esterne per i server perimetrali, è innanzitutto necessario determinare se si utilizzeranno indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095561"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="9497e-103">Espansione delle impostazioni dei nomi di dominio completi (FQDN) per il server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9497e-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="9497e-104">Per modificare  o specificare le impostazioni esterne per i server perimetrali, è innanzitutto necessario determinare se si utilizzeranno indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.</span><span class="sxs-lookup"><span data-stu-id="9497e-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="9497e-p101">Se si intende utilizzare per ognuno indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS (Domain Name System) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9497e-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="9497e-p102">Per ogni servizio con accesso all'esterno, specificare un nome di dominio completo (FQDN) e una porta associata. Ad esempio, per **Accesso SIP** è possibile utilizzare sip.contoso.com con la porta 5061 associata.</span><span class="sxs-lookup"><span data-stu-id="9497e-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9497e-109">Se si selezionano FQDN distinti per ognuno dei servizi con accesso all'esterno, a ciascun servizio deve essere associato un valore di porta univoco.</span><span class="sxs-lookup"><span data-stu-id="9497e-109">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it.</span></span> <span data-ttu-id="9497e-110">Per impostazione predefinita, SIP è sulla porta 5061/TLS, il servizio Web Conferencing Edge è sulla porta 444/TLS e il servizio A/V Conferencing Edge è sulla porta 443/TLS.</span><span class="sxs-lookup"><span data-stu-id="9497e-110">By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS.</span></span> <span data-ttu-id="9497e-111">Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="9497e-111">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="9497e-p104">Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="9497e-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9497e-114">Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="9497e-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="9497e-115">Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Perimetrali, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span><span class="sxs-lookup"><span data-stu-id="9497e-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).</span></span>