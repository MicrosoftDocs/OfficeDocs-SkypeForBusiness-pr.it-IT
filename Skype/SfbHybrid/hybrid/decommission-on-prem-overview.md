---
title: Rimuovere le autorizzazioni dell'ambiente Skype for Business locale
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
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593899"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Rimuovere le autorizzazioni dell'ambiente Skype for Business locale

Se l'organizzazione usa Teams o Skype for Business online con una distribuzione locale di Skype for Business Server, è possibile eseguire la migrazione completa di questi ambienti nel cloud e quindi ritirare la distribuzione locale di Skype for Business Server. 

> [!NOTE]
> Prima di rimuovere le autorizzazioni dell'ambiente [](configure-hybrid-connectivity.md) locale, è necessario configurare la connettività ibrida tra la distribuzione locale e Microsoft 365. Dopo aver configurato la connettività ibrida, è possibile eseguire la migrazione degli utenti nel cloud, durante la migrazione delle riunioni da locale e la migrazione di qualsiasi contatto da Skype for Business Server a Teams. La configurazione della connettività ibrida è un passaggio necessario per eseguire la migrazione degli utenti da locale al cloud e per garantire la funzionalità completa di Teams.

Per completare lo spostamento dall'ambiente locale al cloud e rimuovere le autorizzazioni dell'ambiente Skype for Business Server locale, è necessario completare i passaggi seguenti nell'ordine seguente:

- **Passaggio 1.** [Spostare tutti gli utenti e gli endpoint dell'applicazione necessari da](decommission-move-on-prem-users.md)locale a online.

- **Passaggio 2.** [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- **Passaggio 3.** Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)

