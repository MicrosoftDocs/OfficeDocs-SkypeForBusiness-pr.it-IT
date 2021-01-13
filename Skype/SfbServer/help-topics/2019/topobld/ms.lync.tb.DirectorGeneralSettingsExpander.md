---
title: Espansione delle impostazioni generali del Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un Director esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822626"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="6ab29-103">Espansione delle impostazioni generali di Director</span><span class="sxs-lookup"><span data-stu-id="6ab29-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="6ab29-104">Per modificare le impostazioni di un Director esistente, sono disponibili le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ab29-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="6ab29-105">Generale</span><span class="sxs-lookup"><span data-stu-id="6ab29-105">General settings</span></span>
    
- <span data-ttu-id="6ab29-106">Servizi Web</span><span class="sxs-lookup"><span data-stu-id="6ab29-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="6ab29-107">Generale</span><span class="sxs-lookup"><span data-stu-id="6ab29-107">General settings</span></span>

<span data-ttu-id="6ab29-p101">Nome di dominio completo (FQDN) del pool di server Director. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="6ab29-111">In **Associazioni** è possibile modificare o specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6ab29-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="6ab29-112">Condivisione file per il pool di server Director da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6ab29-112">File share for the Director pool to use.</span></span> <span data-ttu-id="6ab29-113">Selezionare una condivisione file esistente già definita in Generatore di topologie oppure fare clic su **nuovo** per creare una nuova definizione di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="6ab29-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="6ab29-114">Monitoraggio dell'archivio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6ab29-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6ab29-p103">Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio. Se è stata creata una nuova condivisione file, questa deve trovarsi nel server designato.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="6ab29-117">Servizi Web</span><span class="sxs-lookup"><span data-stu-id="6ab29-117">Web services</span></span>

<span data-ttu-id="6ab29-118">Per modificare o specificare ulteriori impostazioni per i servizi Web nel pool di server Director, modificare o specificare le impostazioni in Servizi Web interni e Servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="6ab29-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="6ab29-119">Per **Servizi Web interni** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6ab29-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6ab29-120">Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="6ab29-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="6ab29-121">Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile utilizzare **pool01.contoso.com** per un altro pool Front end o front end server.</span><span class="sxs-lookup"><span data-stu-id="6ab29-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="6ab29-122">Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end.</span><span class="sxs-lookup"><span data-stu-id="6ab29-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="6ab29-123">Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="6ab29-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="6ab29-p105">Se si seleziona Sostituisci FQDN, sarà possibile specificare un FQDN diverso per l'identità dei Servizi Web interni nel pool. Per impostazione predefinita, l'impostazione corrisponde al nome corrente definito per il pool di server Director.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="6ab29-p106">È possibile specificare le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. Le impostazioni predefinite, ovvero la porta 80 per HTTP e la porta 443 per HTTPS, sono le impostazioni più comuni e in genere non devono essere modificate, tranne nel caso di requisiti specifici per l'organizzazione e la progettazione dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="6ab29-128">Per **Servizi Web esterni** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6ab29-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="6ab29-p107">È possibile definire il nome di dominio completo dei servizi Web esterni. L'FQDN specificato qui in genere dipenderà dai requisiti della connessione esterna, ad esempio del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="6ab29-p108">È possibile specificare le porte di attesa e pubblicate per HTTP e HTTPS richieste dalla distribuzione. L'impostazione predefinita della porta 8080 per HTTP e della porta 4443 per HTTPS viene definita inizialmente. È possibile modificare queste impostazioni per le porte di attesa, in base ai requisiti previsti per il proxy inverso e la rete esterna. Le porte pubblicate vengono impostate sul valore predefinito corrispondente alla porta 80 per HTTP e alla porta 443 per HTTPS. Questi valori determinano le porte di attesa utilizzate dal pool Director o dal server Director per le richieste in arrivo. Questi valori devono essere in genere modificati solo in caso di conflitto tra i requisiti relativi alle porte nel pool. L'utilizzo degli stessi valore di porta da parte delle porte pubblicate interne ed esterne è previsto e non costituisce un conflitto.</span><span class="sxs-lookup"><span data-stu-id="6ab29-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

