---
title: Creare una mappa di edificio per Call Quality Dashboard (CQD)
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Scopri come creare una cartina da utilizzare per caricare dati di tenant e edificio in Call Quality Dashboard (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584035"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Creare una mappa di edificio per Call Quality Dashboard (CQD)

In una distribuzione di Microsoft Teams o Skype for Business online, tutti i client sono esterni. Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni al Call Quality Dashboard (CQD), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.

Quando si lavora con CQD, è necessario conoscere la posizione di un endpoint e se era connesso a una rete che è possibile gestire o una rete che non è possibile gestire, presupponendo che sia possibile solo migliorare le reti che è possibile gestire. Caricando le informazioni sulla subnet e l'edificio in CQD, si abilita CQD per determinare se l'endpoint era connesso a una rete interna (gestita) o a una rete esterna (non gestita). Ecco perché è importante creare una mappa di edificio per l'organizzazione e [caricarla in CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Strumenti di mapping di compilazione

Esistono diversi modi per mappare le subnet dell'organizzazione. Se serve aiuto, è possibile usare il modulo di PowerShell CQDTools descritto in questo [post di blog.](https://aka.ms/cqdtools) Questi strumenti sono basati su PowerShell e usano i siti e i servizi di Active Directory (AD) e Microsoft per pre-popolare il file di edificio. Questi strumenti sono utili per le attività seguenti:

1. Eseguire query su siti e servizi Active Directory e creare un file di tipo building in base alle informazioni contenute al suo interno.
1. Eseguire una query su uno o più server Microsoft AND PER estrarre le informazioni sulla subnet e creare automaticamente un file di edificio.
1. Convalidare un file di edificio esistente, verificando la presenza di duplicati e sovrapposizioni.
1. Trovare subnet non mappate in CQD.

## <a name="related-topics"></a>Argomenti correlati

[Caricare i dati del tenant e dell'edificio in CQD](CQD-upload-tenant-building-data.md)