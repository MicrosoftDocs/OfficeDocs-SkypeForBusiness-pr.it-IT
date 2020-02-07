---
title: Eseguire la migrazione dei dispositivi di sistema room Lync a Microsoft teams rooms
ms.author: v-lanac
author: lanachin
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
description: Leggere questo argomento per informazioni su come eseguire la migrazione dei dispositivi di Lync room System per l'uso del software Microsoft teams rooms.
ms.openlocfilehash: 4aad70c0a91824f0b1eff892aa1940760fc39d39
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826004"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Eseguire la migrazione dei dispositivi LRS (Lync room System) a Microsoft teams rooms

I dispositivi LRS (Lync room System) con il software Skype room System versione 1 (SRS V1) hanno raggiunto [la fine del supporto il 9 ottobre 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018). Questo vuol dire che il software Skype Room Systems v1 non otterrà più aggiornamenti di prodotto o correzioni. I clienti con dispositivi Lync Room System che usano software Skype Room System v1 sono invitati ad aggiornare i dispositivi a Microsoft Teams Rooms.

Il software Microsoft teams Rooms funziona con Microsoft teams oltre a Skype for Business Server e ai servizi online per riunioni e chiamate in tutti i dispositivi supportati da Microsoft teams rooms.

I dispositivi esistenti **possono** continuare a funzionare dopo la fine del supporto software Skype room System V1. Tuttavia, se il software colpisce un bug software che deve rilasciare una correzione per Microsoft, non sarà supportato. SRS V1 usa TLS 1.0/1,1 che sarà deprecato da Microsoft in futuro. Per ulteriori informazioni, vedere [preparazione per la deprecazione TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). 

## <a name="which-devices-are-affected"></a>Quali dispositivi sono interessati?

Ecco l'elenco dei dispositivi interessati da questa modifica:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemi per SMART room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Sono disponibili più opzioni per l'aggiornamento dei sistemi sala Lync alla nuova generazione di sale Microsoft teams.

### <a name="crestron-hardware-trade-in-program"></a>Programma di commercio hardware Crestron

Crestron fornirà un aggiornamento al [sistema Crestron Sr](https://www.crestron.com/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti non Crestron di Lync room System (ad esempio Smart o Polycom LRS). Vedere i dettagli di questo programma [qui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, -->[posta elettronica](mailto:lrsupgrade@crestron.com) Supporto di Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 aggiornamento a Microsoft teams rooms

I clienti di Crestron RL2 (noto anche come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare RL2 corrente in RL3 usando un costo minimo per dispositivo. Vedere i dettagli di questo programma [qui](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Aggiornamento dei sistemi SMART room

Per i clienti SMART LRS, oltre al programma hardware di Crestron, SMART sta lavorando anche per fornire una soluzione per l'aggiornamento alle sale di Microsoft teams. Questo aggiornamento verrà fornito da SMART Technologies Inc al cliente in supporto tecnico. Per altre informazioni, vedere [qui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Cosa si deve fare?

È consigliabile pianificare l'aggiornamento di dispositivi di sistema room di Lync alle sale di Microsoft teams prima della deprecazione TLS 1.0/1.1 usando le opzioni di aggiornamento menzionate in precedenza. Inoltre, potresti anche sostituire i dispositivi esistenti con i nuovi dispositivi certificati per le sale di Microsoft teams. Vedere i dispositivi per la [sala](https://aka.ms/roomdevices) per i dettagli e anche dare un'occhiata ai [requisiti di Microsoft teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> Il software Microsoft teams Rooms supporta il protocollo TLS 1,2 a partire dal 14 dicembre 2018 con la versione app 4.0.64.0. Per i clienti locali, l'abilitazione delle comunicazioni tramite TLS 1,2 per le sale di Microsoft teams richiede Skype for Business Server 2015 cumulativo Update 9 (CU9) o Skype for Business Server 2019 aggiornamento cumulativo 1 (CU1). La modifica non deve influire sui clienti di Skype for business online, in quanto le modifiche del client sono conformi a avanti e indietro.
