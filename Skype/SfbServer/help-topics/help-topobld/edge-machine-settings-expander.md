---
title: Espansione delle impostazioni del computer perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Per modificare le proprietà di un server di un pool di server perimetrali, eseguire le operazioni seguenti:'
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807126"
---
# <a name="edge-machine-settings-expander"></a><span data-ttu-id="17895-103">Espansione delle impostazioni del computer perimetrale</span><span class="sxs-lookup"><span data-stu-id="17895-103">Edge Machine Settings Expander</span></span>
 
<span data-ttu-id="17895-104">Per modificare le proprietà di un server di un pool di server perimetrali, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="17895-104">To edit the properties for a server in a pool of Edge Servers, do the following:</span></span>
  
<span data-ttu-id="17895-p101">Il valore del campo **Nome o FQDN interno** può essere cambiato modificando il nome di dominio completo (FQDN). L'FQDN deve corrispondere al record host (A) DNS (Domain Name System) e al nome soggetto del certificato assegnato al server per l'interfaccia di rete perimetrale interna. Il valore del campo **Indirizzo IP interno** definisce l'indirizzo IP assegnato all'interfaccia di rete definita come rete interna rispetto alla struttura della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="17895-p101">The **Internal name or FQDN** can be changed by editing the fully qualified domain name (FQDN). The FQDN must match the Domain Name System (DNS) host (A) record, and the subject name of the certificate assigned to the server for the internal Edge network interface. The value of **Internal IP address** defines the IP address that is assigned the network interface that is defined as an internal network, relative to the perimeter network design.</span></span>
  
<span data-ttu-id="17895-p102">Nelle tre sezioni successive della finestra di dialogo vengono definiti gli indirizzi IP per la configurazione esterna del server perimetrale. La possibilità di modificare gli indirizzi IP dipende dall'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** nelle proprietà a livello di pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="17895-p102">The next three sections of the dialog define the IP addresses for the external configuration of this Edge Server. The ability to change the IP addresses is affected by the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the Properties settings at the Edge Server pool level.</span></span>
  
## <a name="sip-access"></a><span data-ttu-id="17895-110">Accesso SIP</span><span class="sxs-lookup"><span data-stu-id="17895-110">SIP Access</span></span>

<span data-ttu-id="17895-p103">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per l'accesso SIP (Session Initiation Protocol). Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="17895-p103">Edit the external IP address that is assigned to the network interface for Session Initiation Protocol (SIP) access. This IP address can either be a public IP address or an address in the private IP address range.</span></span>
  
> [!NOTE]
> <span data-ttu-id="17895-113">Se l'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** è abilitata nella pagina delle impostazioni del pool, sarà disponibile per la modifica solo l'indirizzo IP per l'accesso SIP.</span><span class="sxs-lookup"><span data-stu-id="17895-113">If the setting **Enable separate FQDN and IP address for web conferencing and A/V** on the pool settings page is enabled, only the IP address for SIP access will be available for editing.</span></span>
  
## <a name="web-conferencing"></a><span data-ttu-id="17895-114">Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="17895-114">Web Conferencing</span></span>

<span data-ttu-id="17895-p104">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per le conferenze Web. Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="17895-p104">Edit the external IP address that is assigned to the network interface for web conferencing. This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
## <a name="audiovideo"></a><span data-ttu-id="17895-117">Audio/video</span><span class="sxs-lookup"><span data-stu-id="17895-117">Audio/Video</span></span>

<span data-ttu-id="17895-p105">Modificare l'indirizzo IP esterno assegnato all'interfaccia di rete per audio/video (A/V). Tale indirizzo IP può essere un indirizzo IP pubblico o un indirizzo dell'intervallo di indirizzi IP privati.</span><span class="sxs-lookup"><span data-stu-id="17895-p105">Edit the external IP address that is assigned to the network interface for audio/video (A/V). This IP address can be either a public IP address or an address in the private IP address range.</span></span>
  
<span data-ttu-id="17895-p106">L'impostazione di **Indirizzo IP pubblico abilitato NAT utilizzato** rappresenta l'indirizzo pubblico usato dall'interfaccia esterna per l'interfaccia di rete A/V o il server perimetrale in generale. Se l'impostazione **Abilita FQDN e indirizzo IP distinti per Web Conferencing e A/V** è abilitata, questo indirizzo IP pubblico viene usato per tutte e tre le interfacce esterne.</span><span class="sxs-lookup"><span data-stu-id="17895-p106">The setting for **NAT enabled public IP address used** is the public address used by the external interface for either the A/V network interface or the Edge Server in general. If the setting **Enable separate FQDN and IP address for web conferencing and A/V** is enabled, this public IP address is used for all three external interfaces.</span></span>
  

