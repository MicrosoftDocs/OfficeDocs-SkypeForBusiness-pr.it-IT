---
title: Definire i requisiti per le chiamate di emergenza in Skype for Business Server
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Riepiloga i passaggi necessari per abilitare E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.
ms.openlocfilehash: 9e6ccd4b93416d49993dbc24ee0592d130e25de8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187736"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="879ed-103">Definire i requisiti per le chiamate di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="879ed-104">Riepiloga i passaggi necessari per abilitare E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="879ed-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="879ed-105">Prima di iniziare una distribuzione di E9-1-1 di Skype for Business Server, è necessario prima di tutto rispondere alle domande descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="879ed-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="879ed-106">La pianificazione che devi eseguire dipende dal tipo di soluzione E9-1-1 che scegli di distribuire: un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="879ed-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="879ed-107">La tabella seguente identifica le sezioni della cartella di lavoro per la pianificazione che è necessario rivedere per ognuna di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="879ed-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="879ed-108">**Passaggi per la pianificazione per tipo di soluzione E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="879ed-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="879ed-109">**Provider di servizi trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="879ed-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="879ed-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="879ed-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="879ed-111">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="879ed-112">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="879ed-113">Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="879ed-114">Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="879ed-115">Abilitare gli utenti per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="879ed-116">Abilitare gli utenti per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="879ed-117">Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="879ed-118">Gestire le posizioni per i gateway ELIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="879ed-119">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="879ed-120">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="879ed-121">Progettare il trunk SIP per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="879ed-122">Includere lo sportello di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="879ed-123">Includere lo sportello di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="879ed-124">Pianificare i criteri di posizione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="879ed-125">Scegliere un provider di servizi E9-1-1 per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="879ed-126">Assegnare l'ambito dei criteri di posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="879ed-127">Pianificare i criteri di posizione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="879ed-128">Assegnare l'ambito dei criteri di posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="879ed-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

