---
title: Creare una mappa dell'edificio per Call Quality Dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Informazioni su come creare una mappa dell'edificio che è possibile usare per caricare i dati del tenant e della creazione in Call Quality Dashboard (CQD).
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634100"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Creare una mappa dell'edificio per Call Quality Dashboard (CQD)

In una Microsoft Teams o Skype for Business online, tutti i client sono esterni. Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni in Call Quality Dashboard (CQD), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.

Quando si lavora con CQD, è necessario conoscere la posizione di un endpoint e se è stato connesso a una rete che è possibile gestire o a una rete che non è possibile gestire, presupponendo che sia possibile migliorare solo le reti che è possibile gestire. Caricando le informazioni sulla subnet e l'edificio in CQD, si abilita CQD per determinare se l'endpoint era connesso a una rete interna (gestita) o a una rete esterna (non gestita). Ecco perché è importante creare una mappa dell'edificio per l'organizzazione e [caricarla in CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Strumenti di mappatura dell'edificio

Esistono molti modi per mappare le subnet dell'organizzazione. Se serve assistenza, è possibile usare il modulo di PowerShell CQDTools descritto in questo [post di blog.](https://aka.ms/cqdtools) Questi strumenti si basano su PowerShell e usano Siti e servizi di Active Directory (AD) e i servizi MICROSOFT DHCP per precompilare il file di edificio. Questi strumenti consentono di eseguire le attività seguenti:

1. Eseguire query su Siti e servizi di Active Directory e creare un file di edificio in base alle informazioni contenute all'interno.
1. Eseguire una query su uno o più server MICROSOFT DHCP per estrarre le informazioni sulla subnet e creare automaticamente un file di edificio.
1. Convalidare un file di edificio esistente, verificando la presenza di duplicati e sovrapposizioni.
1. Trovare subnet non mappate in CQD.

## <a name="related-topics"></a>Argomenti correlati

[Upload tenant e di creazione dati in CQD](CQD-upload-tenant-building-data.md)