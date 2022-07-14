---
title: Creare una mappa dell'edificio per Call Quality Dashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come creare una mappa dell'edificio che è possibile usare per caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD).
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789821"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Creare una mappa dell'edificio per Call Quality Dashboard (CQD)

In una distribuzione di Microsoft Teams o Skype for Business Online, tutti i client sono esterni. Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni in Call Quality Dashboard (CQD), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.

Quando si lavora con Call Quality Dashboard, è necessario conoscere la posizione di un endpoint e sapere se è stato connesso a una rete gestibile o non gestibile, presupponendo che sia possibile migliorare solo le reti che è possibile gestire. Caricando le informazioni su subnet e building in Call Quality Dashboard, si abilita Call Quality Dashboard per determinare se l'endpoint era connesso a una rete interna (gestita) o a una rete esterna (non gestita). Ecco perché è importante creare una mappa di creazione per l'organizzazione e [caricarla in Call Quality Dashboard](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Creazione di strumenti di mapping

Esistono molti modi per eseguire il mapping delle subnet dell'organizzazione. Se hai bisogno di aiuto, puoi usare il modulo powershell CQDTools descritto in questo [post di blog](https://aka.ms/cqdtools). Questi strumenti sono basati su PowerShell e usano siti e servizi di Active Directory (AD) e servizi DHCP Microsoft per pre-popolare il file di compilazione. Questi strumenti aiuteranno a eseguire le attività seguenti:

1. Eseguire query su siti e servizi active directory e creare un file di creazione basato sulle informazioni contenute in.
1. Eseguire una query su uno o più server DHCP Microsoft per estrarre le informazioni sulla subnet e creare automaticamente un file di edificio.
1. Convalidare un file di compilazione esistente, verificando la presenza di duplicati e sovrapposizioni.
1. Trovare subnet non mappate in Call Quality Dashboard.

## <a name="related-topics"></a>Argomenti correlati

[Caricare i dati del tenant e dell'edificio in Call Quality Dashboard](CQD-upload-tenant-building-data.md)