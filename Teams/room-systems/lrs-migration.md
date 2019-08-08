---
title: Eseguire la migrazione dei dispositivi di sistema room Lync a Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Leggere questo argomento per informazioni su come eseguire la migrazione dei dispositivi di Lync room System per l'uso del software Microsoft teams rooms.
ms.openlocfilehash: d07f214707253dc91495da1d219ed84dab2eec5d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243367"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Eseguire la migrazione dei dispositivi LRS (Lync room System) a Microsoft teams rooms

I dispositivi LRS (Lync room System) con il software Skype room System versione 1 (SRS V1) hanno raggiunto [la fine del supporto il 9 ottobre 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Questo significa che il software Skype room Systems V1 non otterrà più aggiornamenti o correzioni di prodotti. I clienti con i dispositivi di sistema room di Lync con il software Skype room System V1 si consiglia di aggiornare i propri dispositivi alle sale di Microsoft teams.

Il software Microsoft teams Rooms funziona con Microsoft teams oltre a Skype for Business Server e ai servizi online per riunioni e chiamate in tutti i dispositivi supportati da Microsoft teams rooms.

I dispositivi esistenti **possono** continuare a funzionare dopo la fine del supporto software Skype room System V1. Tuttavia, se il software colpisce un bug software che deve rilasciare una correzione per Microsoft, non sarà supportato. SRS V1 usa TLS 1.0/1,1 che sarà deprecato da Microsoft in futuro. Per ulteriori informazioni, vedere [preparazione per la deprecazione TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Microsoft teams Rooms aggiunge il supporto per TLS 1,2 e continuerà a funzionare oltre il 31 ottobre 2018. I clienti locali di Skype for business non devono disabilitare TLS 1.0/1.1 finché Microsoft teams Rooms non annuncia il supporto per TLS 1,2 indipendentemente dalle linee guida generali sulla deprecazione TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Quali dispositivi sono interessati?

Ecco l'elenco dei dispositivi interessati da questa modifica:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Sistemi per SMART room](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Opzioni di aggiornamento

Sono disponibili più opzioni per l'aggiornamento dei sistemi sala Lync alla nuova generazione di sale Microsoft teams.

### <a name="crestron-hardware-trade-in-program"></a>Programma di commercio hardware Crestron

Crestron fornirà un aggiornamento al [sistema Crestron Sr](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) o equivalente per tutti i clienti non Crestron di Lync room System (ad esempio Smart o Polycom LRS). Vedere i dettagli di questo programma [qui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) o <!-- For details, -->[posta elettronica](mailto:lrsupgrade@crestron.com) Supporto di Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 aggiornamento a Microsoft teams rooms

I clienti di Crestron RL2 (noto anche come Crestron RL200) possono acquisire un kit di aggiornamento per aggiornare RL2 corrente in RL3 usando un costo minimo per dispositivo. Vedere i dettagli di questo programma [qui](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Aggiornamento dei sistemi SMART room

Per i clienti SMART LRS, oltre al programma hardware di Crestron, SMART sta lavorando anche per fornire una soluzione per l'aggiornamento alle sale di Microsoft teams. Questo aggiornamento verrà fornito da SMART Technologies Inc al cliente in supporto tecnico. Per altre informazioni, vedere [qui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Cosa si deve fare?

È consigliabile pianificare l'aggiornamento di dispositivi di sistema room di Lync alle sale di Microsoft teams prima della deprecazione TLS 1.0/1.1 usando le opzioni di aggiornamento menzionate in precedenza. Inoltre, potresti anche sostituire i dispositivi esistenti con i nuovi dispositivi certificati per le sale di Microsoft teams. Vedere i dispositivi per la [sala](https://aka.ms/roomdevices) per i dettagli e anche dare un'occhiata ai [requisiti di Microsoft teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> La funzionalità tocco e lavagna non è ancora supportata nelle sale di Microsoft teams. Il supporto per il tocco e la lavagna è attualmente previsto per le sale di Microsoft teams e verrà aggiunto in 2019.

> [!NOTE]
> Il software Microsoft teams Rooms supporta il protocollo TLS 1,2 a partire dal 14 dicembre 2018 con la versione app 4.0.64.0. Per i clienti locali, l'abilitazione delle comunicazioni tramite TLS 1,2 per le sale di Microsoft teams richiede Skype for Business Server 2015 cumulativo Update 9 (CU9) o Skype for Business Server 2019 aggiornamento cumulativo 1 (CU1). La modifica non deve influire sui clienti di Skype for business online, in quanto le modifiche del client sono conformi a avanti e indietro.
