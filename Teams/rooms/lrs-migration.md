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
ms.openlocfilehash: a700e66a966035b52a3036210e39c09612ed18b5df34430545987c51c40575f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301072"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Eseguire la migrazione di dispositivi Lync Room System (LRS) a Microsoft Teams Rooms

I dispositivi Lync Room System (LRS) con Skype Room System versione 1 (SRS v1) hanno raggiunto la fine del supporto il 9 ottobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Questo vuol dire che il software Skype Room Systems v1 non otterrà più aggiornamenti di prodotto o correzioni. I clienti con dispositivi Lync Room System che usano software Skype Room System v1 sono invitati ad aggiornare i dispositivi a Microsoft Teams Rooms.

Microsoft Teams Rooms software funziona con Microsoft Teams oltre ai Skype for Business Server e ai servizi online per riunioni e chiamate su Microsoft Teams Rooms dispositivi supportati.

I dispositivi esistenti **potrebbero** continuare a funzionare dopo la fine del Skype del software Room System v1. Tuttavia, se questo software colpisce un bug software che richiede a Microsoft di rilasciare una correzione, non sarà supportato. SRS v1 usa TLS 1.0/ 1.1 che verrà deprecato da Microsoft in futuro. Altre informazioni sulla preparazione [per la deprecazione di TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Quali dispositivi sono interessati?

Ecco l'elenco dei dispositivi interessati da questa modifica:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemi smart room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Sono disponibili diverse opzioni per l'aggiornamento di Lync Room Systems alla nuova generazione di Microsoft Teams Rooms.

### <a name="crestron-hardware-trade-in-program"></a>Programma di scambio hardware Crestron

Crestron fornirà un aggiornamento al sistema [SR Crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti non-Crestron Lync Room System (ad esempio Smart o Polycom LRS). Vedi i dettagli di questo [programma qui o](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[posta elettronica](mailto:lrsupgrade@crestron.com) Supporto per Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Aggiornamento di Crestron RL2 a Microsoft Teams Rooms

I clienti esistenti di Crestron RL2 (noto anche come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare l'attuale RL2 a RL3 usando un costo minimo per dispositivo. Vedere i dettagli di questo [programma qui](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Aggiornamento di SMART Room Systems

Per i clienti SMART LRS, oltre al programma di scambio hardware Crestron, SMART sta lavorando anche alla fornitura di una soluzione per l'aggiornamento a Microsoft Teams Rooms. Questo aggiornamento verrà fornito da SMART Technologies Inc. al cliente in base al supporto del prodotto. Per saperne di più, [consulta qui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Cosa si deve fare?

È consigliabile pianificare l'aggiornamento dei dispositivi lync room system Microsoft Teams Rooms prima della deprecazione di TLS 1.0/1.1 usando le opzioni di aggiornamento menzionate in precedenza. È anche possibile sostituire i dispositivi esistenti con nuovi dispositivi certificati per Microsoft Teams Rooms. Per [informazioni dettagliate](https://aka.ms/roomdevices) sui dispositivi della sala, vedere Requisiti Microsoft Teams Rooms [sala](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> Microsoft Teams Rooms software supporta il protocollo TLS 1.2 a partire dal 14 dicembre 2018 con la versione 4.0.64.0 dell'app. Per i clienti locali, l'abilitazione delle comunicazioni tramite TLS 1.2 per Microsoft Teams Rooms richiede Skype for Business Server 2015 l'aggiornamento cumulativo 9 (CU9) o Skype for Business Server 2019 aggiornamento cumulativo 1 (CU1). La modifica non dovrebbe influire sui clienti Skype for Business online, in quanto le modifiche dei clienti sono conformi alle versioni precedenti e in avanti.