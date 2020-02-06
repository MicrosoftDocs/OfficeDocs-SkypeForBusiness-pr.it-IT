---
title: Espansione delle impostazioni generali di Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Per modificare le impostazioni di un amministratore esistente, è possibile presentarle con le sezioni seguenti:'
ms.openlocfilehash: e6fb587484cd4024e69c8630e49f95a978ec747a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820128"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="99e1d-103">Espansione delle impostazioni generali di Director</span><span class="sxs-lookup"><span data-stu-id="99e1d-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="99e1d-104">Per modificare le impostazioni di un amministratore esistente, è possibile presentarle con le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99e1d-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="99e1d-105">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="99e1d-105">General settings</span></span>
    
- <span data-ttu-id="99e1d-106">Servizi Web</span><span class="sxs-lookup"><span data-stu-id="99e1d-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="99e1d-107">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="99e1d-107">General settings</span></span>

<span data-ttu-id="99e1d-108">Nome di dominio completo (FQDN) del pool di Director.</span><span class="sxs-lookup"><span data-stu-id="99e1d-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="99e1d-109">Modificare l'FQDN del server per cambiarne il valore.</span><span class="sxs-lookup"><span data-stu-id="99e1d-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="99e1d-110">È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="99e1d-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="99e1d-111">In **Associazioni** è possibile modificare o specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="99e1d-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="99e1d-112">Condivisione file per il pool di Director da usare.</span><span class="sxs-lookup"><span data-stu-id="99e1d-112">File share for the Director pool to use.</span></span> <span data-ttu-id="99e1d-113">Selezionare una condivisione file esistente già definita in Generatore di topologia oppure fare clic su **nuovo** per creare una nuova definizione di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="99e1d-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="99e1d-114">Monitoraggio di SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="99e1d-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="99e1d-115">Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.</span><span class="sxs-lookup"><span data-stu-id="99e1d-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="99e1d-116">Se è stata creata una nuova condivisione file, la condivisione file deve essere creata nel server che si vuole designare.</span><span class="sxs-lookup"><span data-stu-id="99e1d-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="99e1d-117">Servizi Web</span><span class="sxs-lookup"><span data-stu-id="99e1d-117">Web services</span></span>

<span data-ttu-id="99e1d-118">Per modificare o specificare altre impostazioni per i servizi Web nel pool di Director, è possibile modificare o specificare le impostazioni nei servizi Web interni e nei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="99e1d-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="99e1d-119">Per i **servizi Web interni** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="99e1d-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="99e1d-120">Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="99e1d-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="99e1d-121">Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile usare **pool01.contoso.com** per un altro pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="99e1d-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="99e1d-122">Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server.</span><span class="sxs-lookup"><span data-stu-id="99e1d-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="99e1d-123">Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director.</span><span class="sxs-lookup"><span data-stu-id="99e1d-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="99e1d-124">Se si seleziona Sostituisci FQDN, sarà possibile specificare un FQDN diverso per l'identità dei Servizi Web interni nel pool.</span><span class="sxs-lookup"><span data-stu-id="99e1d-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="99e1d-125">Per impostazione predefinita, l'impostazione è il nome del pool corrente definito per il pool di Director.</span><span class="sxs-lookup"><span data-stu-id="99e1d-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="99e1d-126">È possibile specificare le porte di ascolto e pubblicazione per HTTP e HTTPS necessarie per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="99e1d-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="99e1d-127">L'impostazione predefinita della porta 80 per HTTP e della porta 443 per HTTPS sono le impostazioni più comuni e in genere non è necessario modificarle, a meno che non si disponga di requisiti specifici all'interno dell'organizzazione e della struttura dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="99e1d-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="99e1d-128">Per i **servizi Web esterni**, è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="99e1d-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="99e1d-129">Puoi definire il nome di dominio completo dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="99e1d-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="99e1d-130">L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="99e1d-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="99e1d-131">È possibile specificare le porte di ascolto e pubblicazione per HTTP e HTTPS necessarie per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="99e1d-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="99e1d-132">Le impostazioni predefinite della porta 8080 per HTTP e della porta 4443 per HTTPS sono definite inizialmente.</span><span class="sxs-lookup"><span data-stu-id="99e1d-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="99e1d-133">Queste impostazioni vengono modificate per le porte in ascolto in base a quali sono i requisiti per il proxy inverso e per i requisiti di rete esterna.</span><span class="sxs-lookup"><span data-stu-id="99e1d-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="99e1d-134">Le porte pubblicate sono impostate su default della porta 80 per HTTP e della porta 443 per HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99e1d-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="99e1d-135">Questi valori determinano quali porte verrà ascoltata dal pool di Director o dal server Director per le richieste in arrivo.</span><span class="sxs-lookup"><span data-stu-id="99e1d-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="99e1d-136">In genere, non è necessario modificarlo, a meno che non ci sia un conflitto di requisiti di porta nel pool.</span><span class="sxs-lookup"><span data-stu-id="99e1d-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="99e1d-137">Le porte pubblicate interne ed esterne che usano gli stessi valori di porta sono previste.</span><span class="sxs-lookup"><span data-stu-id="99e1d-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="99e1d-138">Non si tratta di un conflitto.</span><span class="sxs-lookup"><span data-stu-id="99e1d-138">This is not a conflict.</span></span>
  

