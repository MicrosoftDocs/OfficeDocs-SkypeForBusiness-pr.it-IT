---
title: Eseguire la migrazione dei dispositivi di sistema della chat room Lync Microsoft Teams Rooms
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
description: Leggere questo argomento per informazioni su come eseguire la migrazione dei dispositivi di Lync Room System per usare Microsoft Teams Rooms software.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117524"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="e79ec-103">Eseguire la migrazione di dispositivi Lync Room System (LRS) a Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e79ec-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="e79ec-104">I dispositivi Lync Room System (LRS) con Skype Room System versione 1 (SRS v1) hanno raggiunto la fine del supporto il 9 ottobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="e79ec-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="e79ec-105">Questo vuol dire che il software Skype Room Systems v1 non otterrà più aggiornamenti di prodotto o correzioni.</span><span class="sxs-lookup"><span data-stu-id="e79ec-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="e79ec-106">I clienti con dispositivi Lync Room System che usano software Skype Room System v1 sono invitati ad aggiornare i dispositivi a Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e79ec-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="e79ec-107">Microsoft Teams Rooms software funziona con Microsoft Teams oltre ai Skype for Business Server e ai servizi online per riunioni e chiamate su Microsoft Teams Rooms dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="e79ec-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="e79ec-108">I dispositivi esistenti **potrebbero** continuare a funzionare dopo la fine del Skype del software Room System v1.</span><span class="sxs-lookup"><span data-stu-id="e79ec-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="e79ec-109">Tuttavia, se questo software colpisce un bug software che richiede a Microsoft di rilasciare una correzione, non sarà supportato.</span><span class="sxs-lookup"><span data-stu-id="e79ec-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="e79ec-110">SRS v1 usa TLS 1.0/ 1.1 che verrà deprecato da Microsoft in futuro.</span><span class="sxs-lookup"><span data-stu-id="e79ec-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="e79ec-111">Altre informazioni sulla preparazione [per la deprecazione di TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="e79ec-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="e79ec-112">Quali dispositivi sono interessati?</span><span class="sxs-lookup"><span data-stu-id="e79ec-112">Which devices are affected?</span></span>

<span data-ttu-id="e79ec-113">Ecco l'elenco dei dispositivi interessati da questa modifica:</span><span class="sxs-lookup"><span data-stu-id="e79ec-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="e79ec-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="e79ec-114">Crestron RL</span></span>
- [<span data-ttu-id="e79ec-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="e79ec-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="e79ec-116">Sistemi smart room</span><span class="sxs-lookup"><span data-stu-id="e79ec-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="e79ec-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="e79ec-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="e79ec-118">Opzioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e79ec-118">Upgrade options</span></span>

<span data-ttu-id="e79ec-119">Sono disponibili diverse opzioni per l'aggiornamento di Lync Room Systems alla nuova generazione di Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e79ec-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="e79ec-120">Programma di scambio hardware Crestron</span><span class="sxs-lookup"><span data-stu-id="e79ec-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="e79ec-121">Crestron fornirà un aggiornamento al sistema [SR Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti non-Crestron Lync Room System (ad esempio Smart o Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="e79ec-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="e79ec-122">Vedi i dettagli di questo [programma qui o](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="e79ec-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="e79ec-123">[posta elettronica](mailto:lrsupgrade@crestron.com) Supporto per Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="e79ec-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="e79ec-124">Aggiornamento di Crestron RL2 a Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="e79ec-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="e79ec-125">I clienti esistenti di Crestron RL2 (noto anche come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare l'attuale RL2 a RL3 usando un costo minimo per dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e79ec-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="e79ec-126">Vedere i dettagli di questo [programma qui](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span><span class="sxs-lookup"><span data-stu-id="e79ec-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="e79ec-127">Aggiornamento di SMART Room Systems</span><span class="sxs-lookup"><span data-stu-id="e79ec-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="e79ec-128">Per i clienti SMART LRS, oltre al programma di scambio hardware Crestron, SMART sta lavorando anche alla fornitura di una soluzione per l'aggiornamento a Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e79ec-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="e79ec-129">Questo aggiornamento verrà fornito da SMART Technologies Inc. al cliente in base al supporto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="e79ec-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="e79ec-130">Per saperne di più, [consulta qui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="e79ec-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="e79ec-131">Cosa si deve fare?</span><span class="sxs-lookup"><span data-stu-id="e79ec-131">What should you do?</span></span>

<span data-ttu-id="e79ec-132">È consigliabile pianificare l'aggiornamento dei dispositivi lync room system Microsoft Teams Rooms prima della deprecazione di TLS 1.0/1.1 usando le opzioni di aggiornamento menzionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e79ec-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="e79ec-133">È anche possibile sostituire i dispositivi esistenti con nuovi dispositivi certificati per Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e79ec-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="e79ec-134">Per [informazioni dettagliate](https://aka.ms/roomdevices) sui dispositivi della sala, vedere Requisiti Microsoft Teams Rooms [sala](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="e79ec-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="e79ec-135">Microsoft Teams Rooms software supporta il protocollo TLS 1.2 a partire dal 14 dicembre 2018 con la versione 4.0.64.0 dell'app.</span><span class="sxs-lookup"><span data-stu-id="e79ec-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="e79ec-136">Per i clienti locali, l'abilitazione delle comunicazioni tramite TLS 1.2 per Microsoft Teams Rooms richiede Skype for Business Server 2015 l'aggiornamento cumulativo 9 (CU9) o Skype for Business Server 2019 aggiornamento cumulativo 1 (CU1).</span><span class="sxs-lookup"><span data-stu-id="e79ec-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="e79ec-137">La modifica non dovrebbe influire sui clienti Skype for Business online, in quanto le modifiche dei clienti sono conformi alle versioni precedenti e in avanti.</span><span class="sxs-lookup"><span data-stu-id="e79ec-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>