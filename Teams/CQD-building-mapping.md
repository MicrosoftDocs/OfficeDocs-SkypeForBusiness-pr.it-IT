---
title: Creare una mappa dell'edificio per il dashboard di qualità delle chiamate (Call Quality Dashboard)
ms.author: lolaj
author: LolaJacobsen
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
description: Informazioni su come creare una mappa dell'edificio che è possibile usare per caricare i dati del tenant e della creazione in dashboard qualità chiamata (Call Quality Dashboard).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086102"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Creare una mappa dell'edificio per il dashboard di qualità delle chiamate (Call Quality Dashboard)

In una distribuzione di Microsoft teams o Skype for business online tutti i client sono esterni. Di conseguenza, per impostazione predefinita, tutti i client vengono segnalati come esterni in Call Quality Dashboard (Call Quality Dashboard), indipendentemente dal fatto che il client sia connesso a una rete aziendale interna.

Quando si usa call Quality dashboard, è necessario conoscere la posizione di un endpoint e stabilire se si è connessi a una rete che si riesce a gestire o a una rete che non si riesce a gestire, perché è possibile migliorare solo le reti che è possibile gestire. Caricando subnet e costruendo informazioni in Call Quality dashboard, puoi abilitare Call Quality dashboard per determinare se l'endpoint è connesso a una rete interna (gestita) o a una rete esterna (non gestita). Ecco perché è importante creare una mappa dell'edificio per l'organizzazione e [caricarla in Call Quality dashboard](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Strumenti di mapping della creazione

Esistono diversi modi per eseguire il mapping delle subnet dell'organizzazione. Se hai bisogno di assistenza, puoi usare il modulo di PowerShell CQDTools descritto in questo [post di Blog](https://aka.ms/cqdtools). Questi strumenti sono basati su PowerShell e usano i siti e i servizi Active Directory (AD) e i servizi DHCP Microsoft per aiutare a precompilare il file di costruzione. Questi strumenti saranno utili per le attività seguenti:

1. Eseguire query su siti e servizi di annunci e creare un file di costruzione basato sulle informazioni contenute in.
1. Eseguire una query su un server DHCP o server Microsoft per estrarre le informazioni sulla subnet e creare automaticamente un file di costruzione.
1. Convalidare un file di costruzione esistente, verificando i duplicati e le sovrapposizioni.
1. Trovare subnet non mappate in Call Quality dashboard.

## <a name="related-topics"></a>Argomenti correlati

[Caricare i dati del tenant e della creazione in Call Quality dashboard](CQD-upload-tenant-building-data.md)