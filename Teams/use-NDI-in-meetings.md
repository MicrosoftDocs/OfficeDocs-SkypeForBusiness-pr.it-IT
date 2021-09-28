---
title: Trasmettere il contenuto della riunione
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI e SDI per trasmettere il contenuto delle riunioni in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941881"
---
# <a name="broadcast-meeting-content"></a>Trasmettere il contenuto della riunione 



Teams offre due opzioni per la trasmissione Teams contenuto della riunione: Network Device Interface (NewTek NDI®) e Serial Digital Interface (SDI):

- La tecnologia NewTek NDI® è una soluzione moderna per la connessione di dispositivi multimediali , ad esempio una fotocamera da studio e un mixer. Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.

  La tecnologia NDI® è diventata una soluzione standard di settore per la produzione di contenuti live per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.

- SDI è stato usato nelle produzioni broadcast dal 1989 ed è supportato nella maggior parte dei dispositivi hardware legacy dello studio. I dispositivi hardware di AJA Video Systems e Blackmagic Design forniscono connettività ai dispositivi broadcast legacy che usano SDI.

> [!NOTE]
> La funzionalità Uscita hardware video del supporto SDI è attualmente in versione preview.

La tecnologia NDI® e SDI è supportata in tutte le impostazioni locali.

L'accesso all'uso di NDI e SDI è determinato dai criteri di riunione per l'utente che tenta di attivare la caratteristica. Per la soluzione più sicura, non attivare il parametro di streaming locale come impostazione globale.


## <a name="enable-broadcast-features"></a>Abilitare le funzionalità di trasmissione

Per abilitare le funzionalità di ® broadcast NDI e SDI per un utente:

1. L'amministratore tenant deve consentire all'utente finale di attivare lo streaming locale per i criteri di riunione. 

2. L'utente finale deve attivare lo streaming locale per il proprio client specifico.


Per abilitare l'utente finale, è possibile usare l'interfaccia Teams di amministrazione o Teams PowerShell come indicato di seguito.

Nell'Teams di amministrazione passare a Criteri **riunione > audio & video** e selezionare Consenti streaming **NDI.**

Per usare PowerShell, usare il cmdlet Set-CsTeamsMeetingPolicy seguente:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Dopo aver popolato questa modifica, l'utente finale deve attivare lo streaming locale per il proprio client specifico da Impostazioni  >  **autorizzazioni**. Per altre informazioni, vedere [Trasmissione di audio](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)e video da Teams .





