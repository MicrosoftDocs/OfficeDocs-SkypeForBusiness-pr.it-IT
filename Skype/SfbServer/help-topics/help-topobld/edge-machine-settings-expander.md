---
title: Espansione delle impostazioni per il computer perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Per modificare le proprietà di un server in un pool di Edge Server, eseguire le operazioni seguenti:'
ms.openlocfilehash: aeb9c48968b7b5223ac33fc3419d630229724a09
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697481"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="1536f-103">Espansione delle impostazioni per il computer perimetrale</span><span class="sxs-lookup"><span data-stu-id="1536f-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="1536f-104">Per modificare le proprietà di un server in un pool di Edge Server, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1536f-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="1536f-105">Il **nome interno o l'FQDN** può essere modificato modificando il nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="1536f-105">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN).</span></span> <span data-ttu-id="1536f-106">L'FQDN deve corrispondere al record host DNS (Domain Name System) (A) e al nome dell'oggetto del certificato assegnato al server per l'interfaccia di rete perimetrale interna.</span><span class="sxs-lookup"><span data-stu-id="1536f-106">The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface.</span></span> <span data-ttu-id="1536f-107">Il valore dell' **indirizzo IP interno** definisce l'indirizzo IP a cui viene assegnata l'interfaccia di rete definita come rete interna, rispetto alla struttura della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1536f-107">The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="1536f-108">Le tre sezioni successive della finestra di dialogo definiscono gli indirizzi IP per la configurazione esterna di questo Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1536f-108">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server.</span></span> <span data-ttu-id="1536f-109">La possibilità di modificare gli indirizzi IP viene influenzata dall'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separati per le conferenze Web e a/V** nelle impostazioni delle proprietà a livello di pool di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1536f-109">The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="1536f-110">Accesso SIP</span><span class="sxs-lookup"><span data-stu-id="1536f-110">SIP Access</span></span>

<span data-ttu-id="1536f-111">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'accesso SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="1536f-111">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access.</span></span> <span data-ttu-id="1536f-112">Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="1536f-112">This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1536f-113">Se l'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separato per le conferenze Web e a/V** nella pagina Impostazioni pool è abilitato, solo l'indirizzo IP per l'accesso SIP sarà disponibile per la modifica.</span><span class="sxs-lookup"><span data-stu-id="1536f-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="1536f-114">Conferenze Web</span><span class="sxs-lookup"><span data-stu-id="1536f-114">Web Conferencing</span></span>

<span data-ttu-id="1536f-115">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per i servizi di conferenza Web.</span><span class="sxs-lookup"><span data-stu-id="1536f-115">Edit the external IP address that is assigned to the network interface for web conferencing.</span></span> <span data-ttu-id="1536f-116">Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="1536f-116">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="1536f-117">Audio/video</span><span class="sxs-lookup"><span data-stu-id="1536f-117">Audio/Video</span></span>

<span data-ttu-id="1536f-118">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'audio/video (A/V).</span><span class="sxs-lookup"><span data-stu-id="1536f-118">Edit the external IP address that is assigned to the network interface for audio/video (A/V).</span></span> <span data-ttu-id="1536f-119">Questo indirizzo IP può essere un indirizzo IP pubblico o un indirizzo nell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="1536f-119">This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="1536f-120">L'impostazione per l' **indirizzo IP pubblico abilitato per NAT usato** è l'indirizzo pubblico usato dall'interfaccia esterna per l'interfaccia di rete a/V o per il server perimetrale in generale.</span><span class="sxs-lookup"><span data-stu-id="1536f-120">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general.</span></span> <span data-ttu-id="1536f-121">Se l'impostazione **Abilita il nome di dominio completo e l'indirizzo IP separati per i servizi di conferenza Web e l'opzione A/V** è abilitata, questo indirizzo IP pubblico viene usato per tutte e tre le interfacce esterne.</span><span class="sxs-lookup"><span data-stu-id="1536f-121">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

