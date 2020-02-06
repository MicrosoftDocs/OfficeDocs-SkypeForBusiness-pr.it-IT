---
title: Novità di Skype for Business Server 2019 | Caratteristiche
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: queste funzionalità sono nuove in Skype for Business Server 2019.'
ms.openlocfilehash: 6db5ea6589a56f696f233854372fc95d6064fed7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799416"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="26ab2-103">Novità di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="26ab2-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="26ab2-104">**Riepilogo:** Leggere questo argomento per informazioni sulle nuove funzionalità di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="26ab2-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="26ab2-105">Le nuove funzionalità di Skype for Business Server 2019 includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="26ab2-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="26ab2-106">Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="26ab2-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="26ab2-107">Connettore dati chiamate</span><span class="sxs-lookup"><span data-stu-id="26ab2-107">Call Data Connector</span></span>
- <span data-ttu-id="26ab2-108">Migrazione affiancata</span><span class="sxs-lookup"><span data-stu-id="26ab2-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="26ab2-109">Servizi di messaggistica unificata: cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="26ab2-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="26ab2-110">La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for business 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="26ab2-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="26ab2-111">A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene sottolineata a favore delle caratteristiche del cloud voicemail e dell'operatore automatico cloud.</span><span class="sxs-lookup"><span data-stu-id="26ab2-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="26ab2-112">Cloud Voicemail consente a tutti gli utenti di Skype for business 2019&#x2014;se si trovano in locale o in&#x2014;online per avere accesso allo stesso servizio di segreteria telefonica nel cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26ab2-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="26ab2-113">Cloud Voicemail offre i vantaggi seguenti per gli utenti locali e online:</span><span class="sxs-lookup"><span data-stu-id="26ab2-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="26ab2-114">Accedere alla segreteria telefonica nella propria cassetta postale di Exchange usando i client Skype for business online, teams o Outlook</span><span class="sxs-lookup"><span data-stu-id="26ab2-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="26ab2-115">Possibilità di usare il portale basato sul Web per gestire le opzioni della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="26ab2-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="26ab2-116">Per altre informazioni, Vedi pianificare il servizio per la [segreteria cloud](../sfbhybrid/hybrid/plan-cloud-voicemail.md) e [pianificare Skype for Business Server e Exchange Server Migration](../sfbhybrid/hybrid/plan-um-migration.md) .</span><span class="sxs-lookup"><span data-stu-id="26ab2-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="26ab2-117">Chiamata di monitoraggio: connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="26ab2-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="26ab2-118">Chiamata Data Connector semplifica notevolmente il monitoraggio delle chiamate in un ambiente ibrido perché non è più necessario usare set diversi di strumenti locali e online per monitorare tutta la qualità delle chiamate degli utenti.</span><span class="sxs-lookup"><span data-stu-id="26ab2-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="26ab2-119">Indipendentemente dal fatto che gli utenti siano ospitati in locale o online, è possibile scegliere di visualizzare la qualità delle chiamate per l'intera organizzazione online.</span><span class="sxs-lookup"><span data-stu-id="26ab2-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="26ab2-120">Con il connettore dati chiamata, è possibile eseguire le attività seguenti usando un set di strumenti singoli:</span><span class="sxs-lookup"><span data-stu-id="26ab2-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="26ab2-121">Monitorare l'esperienza utente in Microsoft teams, Skype for business online e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="26ab2-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="26ab2-122">Visualizzare e risolvere i problemi in tutta la rete</span><span class="sxs-lookup"><span data-stu-id="26ab2-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="26ab2-123">Assegnare i ruoli di helpdesk e amministratore per l'analisi delle chiamate, in modo da consentire ai dipendenti dell'helpdesk di visualizzare e risolvere i problemi relativi alle aree di responsabilità.</span><span class="sxs-lookup"><span data-stu-id="26ab2-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="26ab2-124">Per altre informazioni, vedere [pianificare il connettore dati](../sfbhybrid/hybrid/plan-call-data-connector.md) per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="26ab2-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="26ab2-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26ab2-125">See also</span></span>

[<span data-ttu-id="26ab2-126">Cosa è deprecato da Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="26ab2-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
