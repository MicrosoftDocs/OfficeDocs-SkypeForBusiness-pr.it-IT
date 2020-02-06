---
title: Definire i requisiti per le chiamate di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Riepiloga i passaggi necessari per abilitare E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.
ms.openlocfilehash: ffda7796390fea6c44d943770c9b4af6d299549a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803086"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="7027e-103">Definire i requisiti per le chiamate di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="7027e-104">Riepiloga i passaggi necessari per abilitare E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="7027e-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="7027e-105">Prima di iniziare una distribuzione di E9-1-1 di Skype for Business Server, è necessario prima di tutto rispondere alle domande descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7027e-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="7027e-106">La pianificazione che devi eseguire dipende dal tipo di soluzione E9-1-1 che scegli di distribuire: un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="7027e-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="7027e-107">La tabella seguente identifica le sezioni della cartella di lavoro per la pianificazione che è necessario rivedere per ognuna di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="7027e-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="7027e-108">**Passaggi per la pianificazione per tipo di soluzione E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="7027e-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="7027e-109">**Provider di servizi trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="7027e-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="7027e-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="7027e-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7027e-111">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="7027e-112">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="7027e-113">Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="7027e-114">Definire gli elementi di rete usati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="7027e-115">Abilitare gli utenti per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="7027e-116">Abilitare gli utenti per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="7027e-117">Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="7027e-118">Gestire le posizioni per i gateway ELIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="7027e-119">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="7027e-120">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="7027e-121">Progettare il trunk SIP per E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="7027e-122">Includere lo sportello di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="7027e-123">Includere lo sportello di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="7027e-124">Pianificare i criteri di posizione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="7027e-125">Scegliere un provider di servizi E9-1-1 per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="7027e-126">Assegnare l'ambito dei criteri di posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="7027e-127">Pianificare i criteri di posizione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="7027e-128">Assegnare l'ambito dei criteri di posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7027e-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

