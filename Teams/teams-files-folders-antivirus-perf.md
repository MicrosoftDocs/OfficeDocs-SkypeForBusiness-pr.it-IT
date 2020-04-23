---
title: File e cartelle di Teams da escludere dall'analisi antivirus
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Migliorare le prestazioni dei team escludendo determinati file e cartelle dalla normale analisi antivirus.
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1e890509428b3bfba19f6bfb01916e8ea837147
ms.sourcegitcommit: 0fa50d1cf354d79fbaf16b6aaec60e8d3ab852e8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43579592"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>File e cartelle di Teams da escludere dall'analisi antivirus
=================================

Puoi migliorare le prestazioni complessive della distribuzione dei team impedendo ai programmi antivirus di analizzare file e cartelle di determinati team. In questo modo, eviterai le spese delle risorse di sistema per la digitalizzazione di file e cartelle che non devono essere analizzati.

> [!NOTE]
> Quando gli utenti scaricano file o condividono file tra loro, questi file non passano attraverso i percorsi elencati nella sezione seguente. Le posizioni in cui gli utenti caricano, scaricano o condividono file verranno ancora regolarmente analizzate dal programma antivirus.

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>File e cartelle da aggiungere agli elenchi di sicurezza antivirus

Usare le procedure supportate dal programma antivirus per aggiungere i file e le cartelle seguenti agli elenchi attendibili. In questo modo le risorse di sistema verranno conservate evitando scansioni antivirus di queste posizioni.

### <a name="programs"></a>Programmi

Aggiungere i seguenti programmi teams all'elenco di indirizzi attendibili antivirus.

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

