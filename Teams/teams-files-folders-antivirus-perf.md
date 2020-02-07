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
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dbb4b31fc3cddd8c434eb5c94e4f8801ff0633b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837676"
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

### <a name="folders"></a>Cartelle

Aggiungere le cartelle teams seguenti all'elenco di indirizzi attendibili antivirus.

|Categoria  |Posizione  |
|---------|---------|
|File di programma  |%localappdata%\Microsoft\Teams|
|File di dati     |%appdata%\Microsoft\Teams\|