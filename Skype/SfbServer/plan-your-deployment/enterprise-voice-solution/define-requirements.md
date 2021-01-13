---
title: Definire i requisiti per le chiamate di emergenza in Skype for Business Server
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: Vengono riepilogati i passaggi necessari per abilitare il servizio E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825816"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="dd6e6-103">Definire i requisiti per le chiamate di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="dd6e6-104">Vengono riepilogati i passaggi necessari per abilitare il servizio E9-1-1 in Skype for Business Server VoIP aziendale, a seconda che si disponga di un provider di servizi E9-1-1 trunk SIP o di un gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="dd6e6-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="dd6e6-105">Prima di iniziare la distribuzione di E9-1-1 di Skype for Business Server, è necessario essere in grado di rispondere alle domande descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd6e6-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="dd6e6-106">Gli elementi da pianificare dipendono dal tipo di soluzione E9-1-1 che si sceglie di distribuire, ovvero un provider di servizi E9-1-1 trunk SIP o un gateway ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="dd6e6-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="dd6e6-107">Nella tabella seguente vengono identificate le sezioni di questa cartella di lavoro di pianificazione che è necessario esaminare per ognuna di queste soluzioni.</span><span class="sxs-lookup"><span data-stu-id="dd6e6-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="dd6e6-108">**Passaggi per la pianificazione in base al tipo di soluzione E9-1-1**</span><span class="sxs-lookup"><span data-stu-id="dd6e6-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="dd6e6-109">**Provider di servizi trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="dd6e6-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="dd6e6-110">**Gateway ELIN**</span><span class="sxs-lookup"><span data-stu-id="dd6e6-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="dd6e6-111">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="dd6e6-112">Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="dd6e6-113">Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="dd6e6-114">Definire gli elementi di rete utilizzati per determinare la posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="dd6e6-115">Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="dd6e6-116">Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="dd6e6-117">Gestire le posizioni per i provider di servizi trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="dd6e6-118">Gestire le posizioni per i gateway ELIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="dd6e6-119">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="dd6e6-120">Definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="dd6e6-121">Progettare il trunk SIP per il servizio E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="dd6e6-122">Includere il desk di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="dd6e6-123">Includere il desk di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="dd6e6-124">Pianificare i criteri percorso per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="dd6e6-125">Scegliere un provider di servizi E9-1-1 per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="dd6e6-126">Assegnazione dell'ambito dei criteri percorso in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="dd6e6-127">Pianificare i criteri percorso per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="dd6e6-128">Assegnazione dell'ambito dei criteri percorso in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dd6e6-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

