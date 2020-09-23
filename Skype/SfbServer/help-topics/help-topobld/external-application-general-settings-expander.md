---
title: Espansione delle impostazioni generali dell'applicazione esterna
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Per modificare le proprietà per un server applicazioni attendibili che è già stato definito, seguire queste istruzioni.
ms.openlocfilehash: 9a9ed62040724d08ebcd711551cd1ce6e831d683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218137"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="a08d0-103">Espansione delle impostazioni generali dell'applicazione esterna</span><span class="sxs-lookup"><span data-stu-id="a08d0-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="a08d0-104">Per modificare le proprietà per un server applicazioni attendibili che è già stato definito, seguire queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="a08d0-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="a08d0-105">È possibile modificare due sezioni:</span><span class="sxs-lookup"><span data-stu-id="a08d0-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="a08d0-106">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="a08d0-106">General settings</span></span>
> 
> <span data-ttu-id="a08d0-107">Impostazioni dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="a08d0-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="a08d0-108">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="a08d0-108">General Settings</span></span>

<span data-ttu-id="a08d0-p101">È possibile modificare l'attuale nome di dominio completo (FQDN) del pool di server applicazioni attendibili. Modificare il nome di questo FQDN. I record host (A) DNS (Domain Name System) per la nuova voce devono esistere prima che i client o i server possano connettersi al nuovo nome del pool.</span><span class="sxs-lookup"><span data-stu-id="a08d0-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="a08d0-p102">Selezionare **Abilita la replica dei dati di configurazione nel pool** se è necessaria la replica dei dati di configurazione in questo pool. Deselezionare la casella di controllo se non si vuole replicare i dati di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a08d0-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="a08d0-114">Impostazioni dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="a08d0-114">Next Hop Settings</span></span>

<span data-ttu-id="a08d0-115">È possibile specificare il server dell'hop successivo del pool di server applicazioni attendibili selezionando il pool Enterprise Edition front end o il server Standard Edition front end dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a08d0-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="a08d0-116">Un Director o un pool di server Director non costituisce una selezione valida per l'hop successivo di un server applicazioni attendibili e non risulterà visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a08d0-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="a08d0-117">Fare clic su **OK** per accettare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="a08d0-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="a08d0-118">Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a08d0-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

