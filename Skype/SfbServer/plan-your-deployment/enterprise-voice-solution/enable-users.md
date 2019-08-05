---
title: Abilitare gli utenti per E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisioni necessarie per i criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.
ms.openlocfilehash: 1e714e5296e8176c9052b50a5d4ce4f2c0d6184b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187706"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="bbadd-103">Abilitare gli utenti per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbadd-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="bbadd-104">Decisioni necessarie per i criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.</span><span class="sxs-lookup"><span data-stu-id="bbadd-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="bbadd-105">Durante la registrazione del client, Skype for Business Server usa un criterio di posizione per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bbadd-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="bbadd-106">Questo criterio contiene le impostazioni che definiscono la modalità di implementazione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="bbadd-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="bbadd-107">Ad esempio, il criterio di posizione contiene informazioni come la stringa di chiamata di emergenza e se un utente deve immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente uno.</span><span class="sxs-lookup"><span data-stu-id="bbadd-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="bbadd-108">Per una definizione completa dei criteri di posizione, vedere [pianificare i criteri di posizione per Skype for Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bbadd-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="bbadd-109">Skype for Business Server può assegnare un criterio di posizione ai client in base alla subnet o agli utenti in base a un criterio globale, per sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="bbadd-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="bbadd-110">Per decidere come abilitare gli utenti, è necessario prima rispondere alle domande seguenti.</span><span class="sxs-lookup"><span data-stu-id="bbadd-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="bbadd-111">**Si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione?**</span><span class="sxs-lookup"><span data-stu-id="bbadd-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="bbadd-112">È possibile assegnare una posizione a tutti gli utenti dell'organizzazione usando un criterio di posizione globale.</span><span class="sxs-lookup"><span data-stu-id="bbadd-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="bbadd-113">Tuttavia, assegnando un criterio di posizione a un sito di rete di Skype for Business Server e aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing del servizio E9-1-1 per ogni singolo sito.</span><span class="sxs-lookup"><span data-stu-id="bbadd-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="bbadd-114">**Si prevede di abilitare singoli utenti tramite un criterio utente?**</span><span class="sxs-lookup"><span data-stu-id="bbadd-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="bbadd-115">Per personalizzare il supporto di E9-1-1, è possibile assegnare i criteri di posizione direttamente a utenti specifici o oggetti contatto telefonico di area comune.</span><span class="sxs-lookup"><span data-stu-id="bbadd-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="bbadd-116">**Quando i client vagano all'esterno della rete o si connettono da una subnet non definita, i client devono essere ancora abilitati per E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="bbadd-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="bbadd-117">Se agli utenti viene assegnato un criterio di posizione globale, sito o per utente, è possibile che sia necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni sulla posizione non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="bbadd-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="bbadd-118">Per informazioni dettagliate, vedere [definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="bbadd-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

