---
title: Rimuovi le autorizzazioni dell'ambiente locale Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Istruzioni su come rimuovere le autorizzazioni dell'ambiente Skype for Business locale.
ms.openlocfilehash: 420ca75e12737ce85c2fd03031f3e1b8fd9ca625
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510797"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Rimuovi le autorizzazioni dell'ambiente locale Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Se l'organizzazione usa Teams o Skype for Business Online con una distribuzione locale di Skype for Business Server, è possibile eseguire la migrazione completa di questi ambienti nel cloud e quindi ritirare la distribuzione locale di Skype for Business Server. 

> [!NOTE]
> Prima di rimuovere le autorizzazioni dell'ambiente [](configure-hybrid-connectivity.md) locale, è necessario configurare la connettività ibrida tra la distribuzione locale e Microsoft 365. Dopo aver configurato la connettività ibrida, è possibile eseguire la migrazione degli utenti nel cloud, durante la migrazione delle riunioni da locale e la migrazione di qualsiasi contatto da Skype for Business Server a Teams. La configurazione della connettività ibrida è un passaggio necessario per eseguire la migrazione degli utenti da locale al cloud e per garantire la funzionalità Teams completa.

Per completare lo spostamento dall'ambiente locale al cloud e rimuovere le autorizzazioni dell'ambiente Skype for Business Server locale, è necessario completare i passaggi seguenti nell'ordine seguente:

- **Passaggio 1.** [Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)

- **Passaggio 2.** [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- **Passaggio 3.** [Spostare gli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)

- **Passaggio 4.** [Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)

