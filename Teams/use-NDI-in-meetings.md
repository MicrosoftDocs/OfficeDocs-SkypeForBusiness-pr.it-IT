---
title: Usare NDI in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522916"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="f8554-103">Usare NDI in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8554-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="f8554-104">Network Device Interface (NDI) è una soluzione moderna per connettere dispositivi multimediali, ad esempio una videocamera e un mixer di studio.</span><span class="sxs-lookup"><span data-stu-id="f8554-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="f8554-105">Invece di usare le connessioni fisiche, NDI consente la connettività su una Intranet locale, anche in un computer locale.</span><span class="sxs-lookup"><span data-stu-id="f8554-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="f8554-106">NewTek NDI® è diventata una soluzione industriale standard per la produzione di contenuti dinamici per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.</span><span class="sxs-lookup"><span data-stu-id="f8554-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="f8554-107">Skype ha aggiunto in precedenza la funzionalità NDI in Skype alla fine di 2018.</span><span class="sxs-lookup"><span data-stu-id="f8554-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="f8554-108">Microsoft teams sfrutta questa funzionalità per migliorare l'esperienza di riunione.</span><span class="sxs-lookup"><span data-stu-id="f8554-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="f8554-109">NDI è limitato a una rete locale e deve essere considerato solo una parte del flusso di lavoro di produzione, non una soluzione broadcast.</span><span class="sxs-lookup"><span data-stu-id="f8554-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="f8554-110">Attivare NDI</span><span class="sxs-lookup"><span data-stu-id="f8554-110">Turn on NDI</span></span>

<span data-ttu-id="f8554-111">NDI richiede che vengano attivati due passaggi per un utente.</span><span class="sxs-lookup"><span data-stu-id="f8554-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="f8554-112">L'amministratore del tenant deve abilitare il flag di funzionalità enableStreamingCallsOverNdi.</span><span class="sxs-lookup"><span data-stu-id="f8554-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="f8554-113">Dopo aver popolato questa modifica, l'utente finale deve attivare NDI per il proprio client specifico dalle autorizzazioni per **le impostazioni**  >  **Permissions**.</span><span class="sxs-lookup"><span data-stu-id="f8554-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="f8554-114">Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione viene trasmessa.</span><span class="sxs-lookup"><span data-stu-id="f8554-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="f8554-115">Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere abbandonati alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f8554-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="f8554-116">L'immagine seguente mostra il messaggio di banner visualizzato da un utente in una riunione di teams.</span><span class="sxs-lookup"><span data-stu-id="f8554-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![Immagine del banner di NDI visualizzato in una riunione di teams.](media/NDI-disclosure.png)

<span data-ttu-id="f8554-118">Il banner contiene un collegamento ai [criteri di privacy Microsoft](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span><span class="sxs-lookup"><span data-stu-id="f8554-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="f8554-119">Impostazioni locali e tipi di utente supportati</span><span class="sxs-lookup"><span data-stu-id="f8554-119">Supported locales and user types</span></span>

<span data-ttu-id="f8554-120">NDI è supportato in tutte le impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="f8554-120">NDI is supported in all locales.</span></span> <span data-ttu-id="f8554-121">Gli utenti seguenti sono supportati in una riunione di NDI:</span><span class="sxs-lookup"><span data-stu-id="f8554-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="f8554-122">In-tenant-supporto completo, distribuito in base a Ring/ID tenant/userId (controllato da criteri riunione + contrassegno funzionalità)</span><span class="sxs-lookup"><span data-stu-id="f8554-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="f8554-123">Federati-No (anche quando hanno NDI)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f8554-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="f8554-124">Freemium-No (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="f8554-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="f8554-125">Anonimo-No (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="f8554-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="f8554-126">Guest-No (valore predefinito)</span><span class="sxs-lookup"><span data-stu-id="f8554-126">Guest – no  (default value)</span></span>

<span data-ttu-id="f8554-127"><sup>1</sup> i dispositivi hanno un'impostazione NDI attiva per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f8554-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="f8554-128">Se un partecipante alla riunione usa un dispositivo con NDI disattivato, dovrà attivare NDI.</span><span class="sxs-lookup"><span data-stu-id="f8554-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
