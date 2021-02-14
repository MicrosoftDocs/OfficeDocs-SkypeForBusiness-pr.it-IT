---
title: Eseguire la migrazione dei dispositivi di Lync Room System alle sale di Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Leggere questo argomento per informazioni su come eseguire la migrazione dei dispositivi di Lync Room System e usare il software Microsoft Teams Room.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662621"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="d77d7-103">Eseguire la migrazione dei dispositivi LRS (Lync Room System) alle sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d77d7-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="d77d7-104">I dispositivi Lync Room System (LRS) con software Skype Room System versione 1 (SRS v1) hanno raggiunto la fine del supporto il 9 ottobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="d77d7-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="d77d7-105">Questo vuol dire che il software Skype Room Systems v1 non otterrà più aggiornamenti di prodotto o correzioni.</span><span class="sxs-lookup"><span data-stu-id="d77d7-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="d77d7-106">I clienti con dispositivi Lync Room System che usano software Skype Room System v1 sono invitati ad aggiornare i dispositivi a Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d77d7-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="d77d7-107">Il software Microsoft Teams Rooms funziona con Microsoft Teams oltre ai servizi di Skype for Business Server e Online per le riunioni e le chiamate su tutte le sale di Microsoft Teams supportate.</span><span class="sxs-lookup"><span data-stu-id="d77d7-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="d77d7-108">I tuoi dispositivi **esistenti potrebbero** continuare a funzionare dopo la fine del supporto per il software Skype Room System v1.</span><span class="sxs-lookup"><span data-stu-id="d77d7-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="d77d7-109">Tuttavia, se si verifica un bug del software che richiede a Microsoft di rilasciare una correzione, non sarà supportato.</span><span class="sxs-lookup"><span data-stu-id="d77d7-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="d77d7-110">SRS v1 usa TLS 1.0/1.1, che sarà deprecato da Microsoft in futuro.</span><span class="sxs-lookup"><span data-stu-id="d77d7-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="d77d7-111">Altre informazioni sulla preparazione [per la deprecazione di TLS 1.0/1.1 sono ora più dettagliate.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="d77d7-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="d77d7-112">Quali dispositivi sono interessati?</span><span class="sxs-lookup"><span data-stu-id="d77d7-112">Which devices are affected?</span></span>

<span data-ttu-id="d77d7-113">Ecco l'elenco dei dispositivi interessati da questa modifica:</span><span class="sxs-lookup"><span data-stu-id="d77d7-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="d77d7-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="d77d7-114">Crestron RL</span></span>
- [<span data-ttu-id="d77d7-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="d77d7-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="d77d7-116">SMART Room systems</span><span class="sxs-lookup"><span data-stu-id="d77d7-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="d77d7-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="d77d7-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="d77d7-118">Opzioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d77d7-118">Upgrade options</span></span>

<span data-ttu-id="d77d7-119">Sono disponibili diverse opzioni per l'aggiornamento di Room Systems di Lync alla nuova generazione di sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d77d7-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="d77d7-120">Programma di trade-in hardware per Lo snodato</span><span class="sxs-lookup"><span data-stu-id="d77d7-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="d77d7-121">Crestron fornirà un aggiornamento al sistema [SR Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti Non-Crestron Lync Room System (ad esempio Smart o Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="d77d7-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="d77d7-122">Vedi i dettagli di questo programma [qui o](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="d77d7-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="d77d7-123">[e-mail](mailto:lrsupgrade@crestron.com) Supporto per Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="d77d7-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="d77d7-124">Aggiornamento di Crestron RL2 a Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="d77d7-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="d77d7-125">I clienti esistenti di Crestron RL2 (anche droni come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare l'attuale codice RL2 a RL3 utilizzando un costo minimo per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d77d7-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="d77d7-126">Vedi i dettagli di questo programma [qui.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="d77d7-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="d77d7-127">Aggiornamento di SMART Room Systems</span><span class="sxs-lookup"><span data-stu-id="d77d7-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="d77d7-128">Per i clienti SMART LRS, oltre al programma di scambio hardware Crestron, SMART sta lavorando anche a fornire una soluzione per l'aggiornamento a Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d77d7-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="d77d7-129">Questo aggiornamento verrà fornito da SMART Technologies Inc. al cliente in base al supporto tecnico del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d77d7-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="d77d7-130">Per altre informazioni, vedere [qui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="d77d7-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="d77d7-131">Cosa si deve fare?</span><span class="sxs-lookup"><span data-stu-id="d77d7-131">What should you do?</span></span>

<span data-ttu-id="d77d7-132">È consigliabile aggiornare i dispositivi di Lync Room System a Microsoft Teams Room prima della deprecazione di TLS 1.0/1.1 usando le opzioni di aggiornamento citate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d77d7-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="d77d7-133">Inoltre, è anche possibile sostituire i dispositivi esistenti con nuovi dispositivi certificati per sale di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d77d7-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="d77d7-134">Per [informazioni dettagliate,](https://aka.ms/roomdevices) vedere i dispositivi della sala e i requisiti [di Microsoft Teams Room.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="d77d7-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="d77d7-135">Il software Microsoft Teams Rooms supporta il protocollo TLS 1.2 a partire dal 14 dicembre 2018 con la versione dell'app 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="d77d7-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="d77d7-136">Per i clienti locali, l'abilitazione della comunicazione tramite TLS 1.2 per le sale di Microsoft Teams richiede l'aggiornamento cumulativo 9 (CU9) di Skype for Business Server 2015 o l'aggiornamento cumulativo 1 (CU1) di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d77d7-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="d77d7-137">Il cambiamento non dovrebbe interessare i clienti di Skype for Business online perché le modifiche apportate al client sono conformi alle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="d77d7-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
