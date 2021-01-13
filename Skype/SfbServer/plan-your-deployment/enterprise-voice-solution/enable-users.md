---
title: Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Le decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, compresi gli utenti che consentono di abilitare e come supportare gli utenti di roaming.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825746"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="a6d59-103">Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a6d59-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="a6d59-104">Le decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, compresi gli utenti che consentono di abilitare e come supportare gli utenti di roaming.</span><span class="sxs-lookup"><span data-stu-id="a6d59-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="a6d59-105">Durante la registrazione dei client, in Skype for Business Server viene utilizzato un criterio percorso per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="a6d59-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="a6d59-106">In un criterio percorso sono contenute tutte le impostazioni che definiscono come verrà implementata la funzionalità E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a6d59-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="a6d59-107">Ad esempio, il criterio percorso contiene informazioni quali la stringa di chiamata di emergenza e se un utente è tenuto a immettere manualmente una posizione se il servizio informazioni percorso non ne fornisce automaticamente una.</span><span class="sxs-lookup"><span data-stu-id="a6d59-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="a6d59-108">Per una definizione completa dei criteri percorso, vedere [Plan location Policies for Skype for Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a6d59-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="a6d59-109">Skype for Business Server è in grado di assegnare un criterio percorso ai client in base alla subnet o agli utenti in base a criteri globali, per sito o per utente.</span><span class="sxs-lookup"><span data-stu-id="a6d59-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="a6d59-110">Per decidere come abilitare gli utenti, è consigliabile innanzitutto tenere conto degli aspetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="a6d59-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="a6d59-111">**Valutare se si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="a6d59-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="a6d59-112">È possibile assegnare una posizione a tutti gli utenti dell'organizzazione utilizzando un criterio percorso globale.</span><span class="sxs-lookup"><span data-stu-id="a6d59-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="a6d59-113">Tuttavia, assegnando un criterio percorso a un sito di rete di Skype for Business Server e quindi aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing di E9-1-1 per ogni singolo sito.</span><span class="sxs-lookup"><span data-stu-id="a6d59-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="a6d59-114">**Valutare se si prevede di abilitare singoli utenti mediante un criterio utente**</span><span class="sxs-lookup"><span data-stu-id="a6d59-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="a6d59-115">È possibile assegnare criteri percorso direttamente a utenti specifici o a oggetti contatto di telefoni di area comune se si desidera personalizzare il relativo supporto E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="a6d59-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="a6d59-116">**Valutare se abilitare per E9-1-1 i client che effettuano il roaming all'esterno della rete o si connettono da una subnet non definita**</span><span class="sxs-lookup"><span data-stu-id="a6d59-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="a6d59-117">Se agli utenti viene assegnato un criterio percorso globale, sito o per utente, è possibile che venga richiesto di immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni percorso non è stato trovato.</span><span class="sxs-lookup"><span data-stu-id="a6d59-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="a6d59-118">Per ulteriori informazioni, vedere [definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="a6d59-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

