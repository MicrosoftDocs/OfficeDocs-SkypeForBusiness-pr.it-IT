---
title: Espansione delle impostazioni generali delle applicazioni esterne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un server delle applicazioni attendibile già definito, seguire queste istruzioni.
ms.openlocfilehash: dffeb52ab1633a936a73cb2270a204d26ccf1056
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702171"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="b6da2-103">Espansione delle impostazioni generali delle applicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="b6da2-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="b6da2-104">Per modificare le proprietà di un server delle applicazioni attendibile già definito, seguire queste istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b6da2-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="b6da2-105">È possibile modificare due sezioni:</span><span class="sxs-lookup"><span data-stu-id="b6da2-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="b6da2-106">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6da2-106">General settings</span></span>
> 
> <span data-ttu-id="b6da2-107">Impostazioni dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="b6da2-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="b6da2-108">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="b6da2-108">General Settings</span></span>

<span data-ttu-id="b6da2-109">È possibile modificare il nome di dominio completo corrente per il pool di server applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="b6da2-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="b6da2-110">Modificare il nome dell'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="b6da2-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="b6da2-111">È necessario che i record DNS (Domain Name System) host (A) siano presenti per la nuova voce prima che i client o i server possano connettersi al nuovo nome del pool.</span><span class="sxs-lookup"><span data-stu-id="b6da2-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="b6da2-112">Selezionare **Abilita la replica dei dati di configurazione nel pool** se è necessario avere la replica dei dati di configurazione nel pool.</span><span class="sxs-lookup"><span data-stu-id="b6da2-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="b6da2-113">Deselezionare il segno di spunta se non si vogliono replicare i dati di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b6da2-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="b6da2-114">Impostazioni hop successivo</span><span class="sxs-lookup"><span data-stu-id="b6da2-114">Next Hop Settings</span></span>

<span data-ttu-id="b6da2-115">È possibile specificare il server dell'hop successivo del pool di server delle applicazioni attendibili selezionando il pool di front end di Enterprise Edition definito o il server front-end Standard Edition nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="b6da2-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="b6da2-116">Un pool di Director o Director non è una selezione valida per un server applicazioni attendibile hop successivo e non verrà visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b6da2-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="b6da2-117">Fare clic su **OK** per accettare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b6da2-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="b6da2-118">Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b6da2-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

