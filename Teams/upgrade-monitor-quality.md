---
title: Qualità dell'esperienza utente | Microsoft Teams | QoS | Qualità chiamata
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: L'amministratore può conoscere le attività e le attività necessarie per monitorare la qualità e l'uso Microsoft Teams.
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
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808996"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="c9996-103">Guida sul controllo della qualità dell'esperienza</span><span class="sxs-lookup"><span data-stu-id="c9996-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="c9996-104">![Diagramma che evidenzia la fase di eccellenza operativa del percorso di aggiornamento](media/upgrade-banner-op-excellence.png "Fasi del percorso di aggiornamento, con enfasi sulla fase Di eccellenza operativa")</span><span class="sxs-lookup"><span data-stu-id="c9996-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="c9996-105">Questo articolo fa parte della fase operational excellence del percorso di aggiornamento, che inizia non appena l'aggiornamento è stato completato da Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="c9996-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="c9996-106">Migliorare e monitorare la qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="c9996-106">Improve and monitor call quality</span></span>

<span data-ttu-id="c9996-107">[Migliorare e monitorare la](monitor-call-quality-qos.md) qualità delle chiamate per Teams include una serie di attività che valutano e forniscono indicazioni per la correzione nelle aree chiave che hanno l'impatto maggiore sul miglioramento dell'esperienza utente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c9996-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="c9996-108">![Illustrazione delle aree chiave da esaminare durante una revisione.](media/plan-my-service-management-image2.png "Aree chiave da esaminare durante una verifica della qualità dell'esperienza: audio, affidabilità e risultati dei sondaggi degli utenti.")</span><span class="sxs-lookup"><span data-stu-id="c9996-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="c9996-109">Valutando e correndo continuamente le aree descritte nella guida, è possibile ridurne il potenziale per influire negativamente sull'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="c9996-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="c9996-110">La maggior parte dei problemi di esperienza utente riscontrati in una distribuzione può essere raggruppata nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9996-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="c9996-111">Configurazione incompleta del firewall o del proxy</span><span class="sxs-lookup"><span data-stu-id="c9996-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="c9996-112">Copertura Wi-Fi scarsa</span><span class="sxs-lookup"><span data-stu-id="c9996-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="c9996-113">Larghezza di banda insufficiente</span><span class="sxs-lookup"><span data-stu-id="c9996-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="c9996-114">VPN</span><span class="sxs-lookup"><span data-stu-id="c9996-114">VPN</span></span>

- <span data-ttu-id="c9996-115">Uso di dispositivi audio non supportati o incorporati</span><span class="sxs-lookup"><span data-stu-id="c9996-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="c9996-116">Subnet o dispositivi di rete problematici</span><span class="sxs-lookup"><span data-stu-id="c9996-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="c9996-117">Le indicazioni fornite in Migliorare e monitorare la qualità delle chiamate per [Teams](monitor-call-quality-qos.md) sono incentrate sull'uso di Call Quality Dashboard (CQD) Online come strumento principale per segnalare e analizzare ogni area descritta, concentrando l'attenzione sull'audio per massimizzare l'adozione e l'impatto.</span><span class="sxs-lookup"><span data-stu-id="c9996-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="c9996-118">Tutte le ottimizzazioni apportate alla rete per migliorare l'esperienza audio si tradurranno anche direttamente in miglioramenti nella condivisione di video e desktop.</span><span class="sxs-lookup"><span data-stu-id="c9996-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="c9996-119">È consigliabile nominare il campione di qualità in anticipo.</span><span class="sxs-lookup"><span data-stu-id="c9996-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="c9996-120">Dopo essere stati nominati, dovrebbero iniziare a familiarizzare con il contenuto in Migliorare e monitorare [la](monitor-call-quality-qos.md)qualità delle chiamate per Teams .</span><span class="sxs-lookup"><span data-stu-id="c9996-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
