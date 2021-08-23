---
title: Usare la funzionalità delle unità amministrative in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare le funzionalità delle unità amministrative in Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93add1771e76f6640b6f1fde3ee6e732499aa329
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2021
ms.locfileid: "58399362"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>Funzionalità delle unità amministrative per la gestione dei dispositivi in Teams

Avere un accesso più granulare basato sui ruoli per la gestione dei dispositivi usando l'Microsoft Teams di amministrazione. Il concetto di unità amministrativa per la gestione dei dispositivi è stato implementato tramite l'Teams di amministrazione.

Con il concetto di unità amministrativa, si garantirà l'accesso a un set specifico di risorse a un amministratore dedicato. L'unità amministrativa limita l'accesso a tutte le risorse. È possibile estendere la stessa funzionalità per la gestione Teams dispositivi mobili.

> [!NOTE]
> Il concetto di unità amministrativa è attualmente disponibile solo per il Teams amministratore del dispositivo.

Ad esempio, Contoso ha operazioni in aree geografiche diverse. Alice è un amministratore IT globale di Londra, mentre Prashant è un amministratore IT per l'India. Oggi, quando Prashant accede all'Teams di amministrazione con il ruolo di amministratore del dispositivo, può vedere i dispositivi in tutto il mondo. Alice vuole limitare l'accesso di Prashant solo ai dispositivi presenti in India. Il concetto di unità amministrative consente di risolvere il problema. Altre informazioni sul [concetto di unità amministrativa.](/azure/active-directory/roles/administrative-units)

![un diagramma che mostra gli scenari](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>Creazione di unità amministrative

Creare unità amministrative nel portale di Azure e assegnare amministratori per le rispettive unità amministrative. Per altre informazioni sull'assegnazione di unità amministrative, vedere [Gestire le unità di amministrazione.](/azure/active-directory/roles/admin-units-manage)

![un esempio di unità amministrative aziendali](media/au-example.png)

Una volta creato, l'amministratore IT globale può quindi aggiungere utenti di dispositivi che corrispondono a tale unità amministrativa.

![una società di esempio con l'anteprima degli utenti](media/au-example2.png)

L'assegnazione del ruolo può essere eseguita tramite PowerShell usando il cmdlet [Add-AzureADMSScopedRoleMembership.](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0)

Dopo aver assegnato i ruoli agli utenti per le unità amministrative, gli utenti devono accedere all'Teams di amministrazione per iniziare a gestire i dispositivi con ambito.

## <a name="experience-for-administrative-unit-admin"></a>Esperienza per l'amministratore delle unità amministrative

Se agli stessi amministratori è assegnata la responsabilità di più unità amministrative, è possibile passare da un'unità amministrativa all'altro senza uscire dal portale. Nella visualizzazione dell'unità amministrativa modificata verranno visualizzati solo i set di dispositivi associati alla nuova unità amministrativa.
