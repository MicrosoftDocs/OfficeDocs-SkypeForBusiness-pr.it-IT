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
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Eseguire la migrazione dei dispositivi LRS (Lync Room System) alle sale di Microsoft Teams

I dispositivi Lync Room System (LRS) con software Skype Room System versione 1 (SRS v1) hanno raggiunto la fine del supporto il 9 ottobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Questo vuol dire che il software Skype Room Systems v1 non otterrà più aggiornamenti di prodotto o correzioni. I clienti con dispositivi Lync Room System che usano software Skype Room System v1 sono invitati ad aggiornare i dispositivi a Microsoft Teams Rooms.

Il software Microsoft Teams Rooms funziona con Microsoft Teams oltre ai servizi di Skype for Business Server e Online per le riunioni e le chiamate su tutte le sale di Microsoft Teams supportate.

I tuoi dispositivi **esistenti potrebbero** continuare a funzionare dopo la fine del supporto per il software Skype Room System v1. Tuttavia, se si verifica un bug del software che richiede a Microsoft di rilasciare una correzione, non sarà supportato. SRS v1 usa TLS 1.0/1.1, che sarà deprecato da Microsoft in futuro. Altre informazioni sulla preparazione [per la deprecazione di TLS 1.0/1.1 sono ora più dettagliate.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Quali dispositivi sono interessati?

Ecco l'elenco dei dispositivi interessati da questa modifica:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room systems](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Sono disponibili diverse opzioni per l'aggiornamento di Room Systems di Lync alla nuova generazione di sale di Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programma di trade-in hardware per Lo snodato

Crestron fornirà un aggiornamento al sistema [SR Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti Non-Crestron Lync Room System (ad esempio Smart o Polycom LRS). Vedi i dettagli di questo programma [qui o](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[e-mail](mailto:lrsupgrade@crestron.com) Supporto per Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Aggiornamento di Crestron RL2 a Microsoft Teams Rooms

I clienti esistenti di Crestron RL2 (anche droni come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare l'attuale codice RL2 a RL3 utilizzando un costo minimo per dispositivo. Vedi i dettagli di questo programma [qui.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Aggiornamento di SMART Room Systems

Per i clienti SMART LRS, oltre al programma di scambio hardware Crestron, SMART sta lavorando anche a fornire una soluzione per l'aggiornamento a Microsoft Teams Rooms. Questo aggiornamento verrà fornito da SMART Technologies Inc. al cliente in base al supporto tecnico del prodotto. Per altre informazioni, vedere [qui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Cosa si deve fare?

È consigliabile aggiornare i dispositivi di Lync Room System a Microsoft Teams Room prima della deprecazione di TLS 1.0/1.1 usando le opzioni di aggiornamento citate in precedenza. Inoltre, è anche possibile sostituire i dispositivi esistenti con nuovi dispositivi certificati per sale di Microsoft Teams. Per [informazioni dettagliate,](https://aka.ms/roomdevices) vedere i dispositivi della sala e i requisiti [di Microsoft Teams Room.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Il software Microsoft Teams Rooms supporta il protocollo TLS 1.2 a partire dal 14 dicembre 2018 con la versione dell'app 4.0.64.0. Per i clienti locali, l'abilitazione della comunicazione tramite TLS 1.2 per le sale di Microsoft Teams richiede l'aggiornamento cumulativo 9 (CU9) di Skype for Business Server 2015 o l'aggiornamento cumulativo 1 (CU1) di Skype for Business Server 2019. Il cambiamento non dovrebbe interessare i clienti di Skype for Business online perché le modifiche apportate al client sono conformi alle versioni precedenti.
