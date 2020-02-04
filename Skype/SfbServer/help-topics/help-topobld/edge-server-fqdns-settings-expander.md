---
title: Espansione delle impostazioni degli FQDN dei server perimetrali
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Per modificare o specificare le opzioni in Impostazioni esterne per i server perimetrali, è necessario prima di tutto determinare se verranno usati indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.
ms.openlocfilehash: 2559c1487077465e656ecdfd00ad74002c87a832
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697407"
---
# <a name="edge-server-fqdns-settings-expander"></a><span data-ttu-id="c83eb-103">Espansione delle impostazioni degli FQDN dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="c83eb-103">Edge Server FQDNs Settings Expander</span></span>

<span data-ttu-id="c83eb-104">Per modificare o specificare le opzioni in **Impostazioni esterne** per i server perimetrali, è necessario prima di tutto determinare se verranno usati indirizzi IP separati per l'accesso SIP (Session Initiation Protocol), il servizio Web Conferencing Edge e il servizio Audio/Video Edge.</span><span class="sxs-lookup"><span data-stu-id="c83eb-104">To edit or specify **External Settings** for the Edge Servers, you first must determine if you will use separate IP addresses for Session Initiation Protocol (SIP) access, the Web Conferencing Edge service, and the Audio/Video Edge service.</span></span>

<span data-ttu-id="c83eb-p101">Se per ognuno si vogliono usare indirizzi IP separati, selezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. Per ogni servizio deve essere creato un record host (A) DNS (Domain Name System) corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c83eb-p101">If you intend to use separate IP addresses for each, select the check box **Enable separate FQDN and IP address for Web conferencing and A/V**. Each service must have a corresponding Domain Name System (DNS) host (A) record created for it.</span></span>

<span data-ttu-id="c83eb-p102">Per ogni servizio con accesso all'esterno, specificare un nome di dominio completo (FQDN) e una porta associata. Ad esempio, per **Accesso SIP** è possibile usare sip.contoso.com con la porta 5061 associata.</span><span class="sxs-lookup"><span data-stu-id="c83eb-p102">For each of the external-facing services, specify a fully qualified domain name (FQDN) and an associated port. For example, for **SIP Access**, you might use sip.contoso.com with an associated port of 5061.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c83eb-p103">Se si selezionano FQDN separati per ognuno dei servizi con accesso all'esterno, a ogni servizio deve essere associato un valore di porta univoco. Per impostazione predefinita, SIP è sulla porta 5061/TLS, il servizio Web Conferencing Edge è sulla porta 444/TLS e il servizio A/V Conferencing Edge è sulla porta 443/TLS. Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="c83eb-p103">If you select separate FQDNs for each of the external-facing services, each service must have a unique port value associated with it. By default, SIP is on port 5061/TLS, the Web Conferencing Edge service is on port 444/TLS, and the A/V Conferencing Edge service is on port 443/TLS. If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="c83eb-p104">Se si stabilisce che nell'organizzazione verranno usati un solo FQDN e un solo indirizzo IP per i servizi con accesso all'esterno, deselezionare la casella di controllo **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V**. È quindi possibile modificare i valori per la porta e l'FQDN del pool per **Accesso SIP**, se necessario.</span><span class="sxs-lookup"><span data-stu-id="c83eb-p104">If you determine that your organization will use a single FQDN and IP address for the external-facing services, clear the **Enable separate FQDN and IP address for Web conferencing and A/V** check box. You can then edit the **SIP Access** pool FQDN and port values, if necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c83eb-114">Se si modifica una qualsiasi di queste impostazioni, compresa la decisione di utilizzare FQDN e indirizzi IP separati o porte separate, è necessario aggiornare tutti gli altri servizi che usano i valori configurati all'inizio.</span><span class="sxs-lookup"><span data-stu-id="c83eb-114">If you make changes to any of these settings, including using separate FQDN and IP addresses or ports, you must update all other services that will rely on the initially configured values.</span></span>

<span data-ttu-id="c83eb-115">Per informazioni dettagliate sulla definizione e la configurazione delle impostazioni per i servizi Edge, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="c83eb-115">For details about defining and configuring the settings for the Edge services, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).</span></span>


