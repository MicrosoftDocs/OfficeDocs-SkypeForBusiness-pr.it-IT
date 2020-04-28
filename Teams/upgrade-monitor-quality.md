---
title: Qualità dell'esperienza utente | Microsoft Teams | QoS | Qualità delle chiamate
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: L'amministratore può conoscere le attività e le attività necessarie per il monitoraggio della qualità e dell'uso di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9737834e38d87fbc5f925a5667d57ccd0a0aa626
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904341"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="f614a-103">Guida sul controllo della qualità dell'esperienza</span><span class="sxs-lookup"><span data-stu-id="f614a-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="f614a-104">![Diagramma che evidenzia la fase di eccellenza operativa del viaggio di aggiornamento](media/upgrade-banner-op-excellence.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di eccellenza operativa")</span><span class="sxs-lookup"><span data-stu-id="f614a-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="f614a-105">Questo articolo fa parte della fase di eccellenza operativa del viaggio di aggiornamento, che inizia non appena hai completato l'aggiornamento da Skype for business a teams.</span><span class="sxs-lookup"><span data-stu-id="f614a-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="f614a-106">La [Guida alla revisione della qualità della](https://aka.ms/qerguide) funzionalità include un set di attività che valutano e includono indicazioni per il risanamento in aree chiave che hanno un impatto maggiore sul miglioramento dell'esperienza utente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f614a-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="f614a-107">![Illustrazione delle aree chiave da esaminare durante una revisione.](media/plan-my-service-management-image2.png "Le aree principali da esaminare durante una revisione di qualità dell'esperienza: audio, affidabilità e risultati del sondaggio degli utenti.")</span><span class="sxs-lookup"><span data-stu-id="f614a-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="f614a-108">Valutando e rimediando continuamente le aree descritte nella Guida, è possibile ridurre le proprie potenzialità per influire negativamente sull'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="f614a-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="f614a-109">La maggior parte dei problemi di esperienza utente incontrati in una distribuzione può essere raggruppata nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f614a-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="f614a-110">Firewall o configurazione proxy incompleta</span><span class="sxs-lookup"><span data-stu-id="f614a-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="f614a-111">Scarsa copertura Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="f614a-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="f614a-112">Larghezza di banda insufficiente</span><span class="sxs-lookup"><span data-stu-id="f614a-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="f614a-113">VPN</span><span class="sxs-lookup"><span data-stu-id="f614a-113">VPN</span></span>

- <span data-ttu-id="f614a-114">Uso di dispositivi audio non ottimizzati o incorporati</span><span class="sxs-lookup"><span data-stu-id="f614a-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="f614a-115">Subnet problematiche o dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="f614a-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="f614a-116">Le indicazioni fornite nella Guida alla revisione della qualità dell'esperienza si basano sull'uso di Call Quality Dashboard (Call Quality Dashboard) online come strumento principale per segnalare e analizzare ogni area descritta, con un particolare interesse per l'audio per massimizzare l'adozione e l'impatto.</span><span class="sxs-lookup"><span data-stu-id="f614a-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="f614a-117">Le eventuali ottimizzazioni apportate alla rete per migliorare l'esperienza audio si traducono anche direttamente nei miglioramenti della condivisione di video e desktop.</span><span class="sxs-lookup"><span data-stu-id="f614a-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="f614a-118">Ti consigliamo vivamente di nominare il campione di qualità in anticipo.</span><span class="sxs-lookup"><span data-stu-id="f614a-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="f614a-119">Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con il contenuto della Guida alla [revisione della qualità dell'esperienza](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="f614a-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
