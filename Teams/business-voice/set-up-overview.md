---
title: Configurare Microsoft 365 Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Informazioni su come configurare le Microsoft 365 Business Voice nell'organizzazione o nelle piccole e medie imprese.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 892b093003accf782b7fb6c0a6234bf1f8beb952
ms.sourcegitcommit: 592e5a0638c7739dfaa3565b67d4edc621eebc9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2021
ms.locfileid: "52656039"
---
# <a name="set-up-microsoft-365-business-voice"></a><span data-ttu-id="f1cf9-103">Configurare Microsoft 365 Business Voice</span><span class="sxs-lookup"><span data-stu-id="f1cf9-103">Set up Microsoft 365 Business Voice</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEu8R]  

</br>

<span data-ttu-id="f1cf9-104">Business Voice è un sistema telefonico completo in grado di sostituire il provider di telefonia esistente.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-104">Business Voice is a complete phone system that can replace your existing telephony provider.</span></span> <span data-ttu-id="f1cf9-105">Che si sia una nuova azienda che configura i numeri di telefono per la prima volta o un'azienda consolidata che si sposta da un provider di telefonia locale legacy, i passaggi descritti in questi articoli possono essere utili per iniziare a usare Business Voice.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-105">Whether you're a new business setting up phone numbers for the first time, or an established business moving from a legacy on-premises telephony provider, the steps in these articles can help you get up and running with Business Voice.</span></span> <span data-ttu-id="f1cf9-106">Al termine della configurazione di VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="f1cf9-106">When you're finished setting up Business Voice:</span></span>

* <span data-ttu-id="f1cf9-107">Potrai ricevere chiamate a numero verde o a numero verde su una linea telefonica aziendale principale.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-107">You'll be able to receive toll or toll-free phone calls on a main company phone line.</span></span> <span data-ttu-id="f1cf9-108">Se si vuole, è anche possibile configurare un menu di chiamata.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-108">You can even set up a call menu if you want.</span></span>
* <span data-ttu-id="f1cf9-109">Gli utenti impostati con Business Voice avranno i propri numeri di telefono con chiamata diretta che possono usare per effettuare e ricevere chiamate telefoniche da qualsiasi dispositivo Teams installato.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-109">Users set up with Business Voice will have their own direct-dial phone numbers that they can use to make and receive phone calls from any device with Teams installed.</span></span>
* <span data-ttu-id="f1cf9-110">I partecipanti alla riunione potranno accedere alle riunioni usando un normale telefono se non riescono a partecipare da un Teams clienti.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-110">Meeting participants will be able to call in to meetings using a regular phone if they're unable to join from a Teams client.</span></span>
* <span data-ttu-id="f1cf9-111">Se hai numeri di telefono esistenti, potrai continuare a usarli dopo che saranno stati spostati in VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-111">If you have existing phone numbers, you'll be able to continue using them after they're moved to Business Voice.</span></span>

<span data-ttu-id="f1cf9-112">Per altre informazioni su Business Voice, vedere Che cos'è [Microsoft 365 Business Voice?](whats-business-voice.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf9-112">If you want to learn more about Business Voice, check out [What is Microsoft 365 Business Voice?](whats-business-voice.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1cf9-113">Le informazioni contenute in questi articoli sono applicabili solo a Business Voice **with** Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-113">The information in these articles is applicable to Business Voice **with** Calling Plan only.</span></span> <span data-ttu-id="f1cf9-114">Business Voice con Piano per chiamate è disponibile solo in determinati paesi e regioni.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-114">Business Voice with Calling Plan is available only in select countries and regions.</span></span> <span data-ttu-id="f1cf9-115">Prima di iniziare a configurare VoIP aziendale, controllare la disponibilità di Paese e area geografica per [Business Voice](country-region-availability.md) per verificare se il paese o l'area geografica supporta Voce aziendale con piano chiamate.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-115">Before you start setting up Business Voice, check [Country and region availability for Business Voice](country-region-availability.md) to see whether your country or region supports Business Voice with Calling Plan.</span></span>
>
> <span data-ttu-id="f1cf9-116">Se il tenant si trova in un paese o un'area geografica che non supporta Business Voice con Piano per chiamate, vedere [Ottenere assistenza da parte di un rivenditore o un partner Microsoft](reseller-partner-support.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf9-116">If your tenant is located in a country or region that doesn't support Business Voice with Calling Plan, check out [Get help from a Microsoft reseller or partner](reseller-partner-support.md).</span></span>
>
> <span data-ttu-id="f1cf9-117">Microsoft Teams e Business Voice funzionano solo quando le cassette postali degli utenti si trovano in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-117">Microsoft Teams and Business Voice only work when your users' mailboxes are located in Microsoft 365.</span></span>  <span data-ttu-id="f1cf9-118">Le cassette postali in Exchange Server locale non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-118">They don't support mailboxes on on-premises Exchange Server.</span></span>
>
> <span data-ttu-id="f1cf9-119">Questo processo di configurazione non supporta le Skype for Business ibride.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-119">This setup process doesn't support Skype for Business hybrid deployments.</span></span> <span data-ttu-id="f1cf9-120">Se si usa una distribuzione ibrida di Skype for Business e si vuole configurare VoIP aziendale, vedere [Configurare il Sistema telefonico nell'organizzazione](../setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf9-120">If you have a Skype for Business hybrid deployment and want to set up Business Voice, check out [Set up Phone System in your organization](../setting-up-your-phone-system.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f1cf9-121">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f1cf9-121">Before you begin</span></span>

<span data-ttu-id="f1cf9-122">Prima di configurare VoIP aziendale, è necessario eseguire alcune operazioni.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-122">Before you set up Business Voice, there are a few things you need to do.</span></span> <span data-ttu-id="f1cf9-123">Le attività seguenti assicurano che l'organizzazione sia pronta per Business Voice.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-123">The following tasks will make sure your organization is ready for Business Voice.</span></span>

* <span data-ttu-id="f1cf9-124">**Acquista le licenze Business Voice** e, se vuoi ottenere un numero verde o effettuare chiamate interurbane, Crediti comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-124">**Buy Business Voice licenses** and, if you want to get a toll-free number or make long-distance phone calls, Communication Credits.</span></span> <span data-ttu-id="f1cf9-125">Per altre informazioni, vedere Cosa è necessario acquistare per usare [Microsoft 365 Business Voice?](what-to-buy.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf9-125">For more information, see [What do I need to buy to use Microsoft 365 Business Voice?](what-to-buy.md).</span></span>
* <span data-ttu-id="f1cf9-126">**Verificare che la connessione Internet sia in grado di supportare Business Voice.**</span><span class="sxs-lookup"><span data-stu-id="f1cf9-126">**Make sure your Internet connection can support Business Voice**.</span></span> <span data-ttu-id="f1cf9-127">Per altre informazioni, vedere [Controllare la connessione Internet per VoIP aziendale.](get-ready-internet.md)</span><span class="sxs-lookup"><span data-stu-id="f1cf9-127">For more information, see [Check your Internet connection for Business Voice](get-ready-internet.md).</span></span>
* <span data-ttu-id="f1cf9-128">**Configurare le Teams nei dispositivi** degli utenti, configurare i messaggi di saluto della segreteria telefonica e aiutare gli utenti a conoscere Teams.</span><span class="sxs-lookup"><span data-stu-id="f1cf9-128">**Set up Teams on your users' devices**, set up voicemail greetings, and help your users learn about Teams.</span></span> <span data-ttu-id="f1cf9-129">Per altre informazioni, vedere [Come si preparano](prepare-users.md)gli utenti per Microsoft 365 Business Voice? .</span><span class="sxs-lookup"><span data-stu-id="f1cf9-129">For more information, see [How do I get my users ready for Microsoft 365 Business Voice?](prepare-users.md).</span></span>

<span data-ttu-id="f1cf9-130">Dopo aver preparato l'organizzazione per Business Voice, selezionare **Passaggio successivo: Avviare la configurazione di VoIP aziendale.**</span><span class="sxs-lookup"><span data-stu-id="f1cf9-130">After you've prepare your organization for Business Voice, select **Next step: Start setting up Business Voice**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f1cf9-131">Passaggio successivo: Avviare la configurazione di Business Voice</span><span class="sxs-lookup"><span data-stu-id="f1cf9-131">Next step: Start setting up Business Voice</span></span>](set-up-emergency-locations.md)
