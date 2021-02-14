---
title: Qualità dell'esperienza utente | Microsoft Teams | QoS | Qualità chiamata
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: L'amministratore può conoscere le attività e le attività necessarie per il monitoraggio della qualità e dell'utilizzo di Microsoft Teams.
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
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="f2ccf-103">Guida sul controllo della qualità dell'esperienza</span><span class="sxs-lookup"><span data-stu-id="f2ccf-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="f2ccf-104">![Diagramma che evidenzia la fase di preparazione operativa del percorso di aggiornamento](media/upgrade-banner-op-excellence.png "Fasi del percorso di aggiornamento, con enfasi sulla fase programmata operativa")</span><span class="sxs-lookup"><span data-stu-id="f2ccf-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="f2ccf-105">Questo articolo fa parte della fase di preparazione operativa del percorso di aggiornamento, che inizia non appena viene completato l'aggiornamento da Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="f2ccf-106">Migliorare e monitorare la qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="f2ccf-106">Improve and monitor call quality</span></span>

<span data-ttu-id="f2ccf-107">[Migliorare e monitorare la qualità delle](monitor-call-quality-qos.md) chiamate per Teams include un set di attività che valutano e forniscono indicazioni per la correzione nelle aree chiave che hanno il maggior impatto sul miglioramento dell'esperienza utente, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="f2ccf-108">![Illustrazione delle aree chiave da esaminare durante una revisione.](media/plan-my-service-management-image2.png "Aree chiave da esaminare durante una verifica della qualità: audio, affidabilità e risultati dei sondaggi degli utenti.")</span><span class="sxs-lookup"><span data-stu-id="f2ccf-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="f2ccf-109">Valutando e correndo continuamente le aree descritte nella guida, è possibile ridurre il rischio di influire negativamente sull'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="f2ccf-110">La maggior parte dei problemi di esperienza utente che si verificano in una distribuzione può essere raggruppata nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2ccf-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="f2ccf-111">Configurazione incompleta del firewall o del proxy</span><span class="sxs-lookup"><span data-stu-id="f2ccf-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="f2ccf-112">Copertura Wi-Fi scarsa</span><span class="sxs-lookup"><span data-stu-id="f2ccf-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="f2ccf-113">Larghezza di banda insufficiente</span><span class="sxs-lookup"><span data-stu-id="f2ccf-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="f2ccf-114">VPN</span><span class="sxs-lookup"><span data-stu-id="f2ccf-114">VPN</span></span>

- <span data-ttu-id="f2ccf-115">Uso di dispositivi audio non supportati o incorporati</span><span class="sxs-lookup"><span data-stu-id="f2ccf-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="f2ccf-116">Subnet o dispositivi di rete problematici</span><span class="sxs-lookup"><span data-stu-id="f2ccf-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="f2ccf-117">Le indicazioni fornite in Migliorare e monitorare la qualità delle chiamate per [Teams](monitor-call-quality-qos.md) riguardano l'uso di Call Quality Dashboard (CQD) Online come strumento principale per la segnalazione e l'analisi di ogni area descritta, concentrando l'attenzione sull'audio per ottimizzare l'adozione e l'impatto.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="f2ccf-118">Le ottimizzazioni apportate alla rete per migliorare l'esperienza audio verranno anche tradotte direttamente in miglioramenti nella condivisione di video e desktop.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="f2ccf-119">Consigliamo vivamente di nominare il campione della qualità fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="f2ccf-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="f2ccf-120">Dopo essere stati nominati, dovrebbero iniziare ad acquisire familiarità con i contenuti in Migliora e monitorare [la qualità delle chiamate per Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="f2ccf-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
