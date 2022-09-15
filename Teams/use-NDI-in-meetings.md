---
title: Trasmettere contenuto della riunione
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI e SDI per trasmettere contenuti delle riunioni in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc185a22c7ea4d849008989da29f50a8f98ebb9d
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706813"
---
# <a name="broadcast-meeting-content"></a>Trasmettere contenuto della riunione 



Teams offre due opzioni per la trasmissione del contenuto delle riunioni di Teams: Network Device Interface (NewTek NDI®) e Serial Digital Interface (SDI):

- La tecnologia NewTek NDI® è una soluzione moderna per la connessione di dispositivi multimediali, ad esempio una fotocamera in studio e un mixer. Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività tramite una intranet locale, anche su un computer locale.

  La tecnologia NDI® è diventata una soluzione standard del settore per la produzione di contenuti live per i flussi e ha acquisito una significativa consapevolezza e adozione nel mondo della trasmissione professionale.

- SDI è stato utilizzato nelle produzioni di trasmissione dal 1989 ed è supportato nella maggior parte dei dispositivi hardware di studio legacy. I dispositivi hardware di AJA Video Systems e Blackmagic Design forniscono connettività ai dispositivi di trasmissione legacy che usano SDI.

> [!NOTE]
> La funzionalità Uscita hardware video che supporta SDI è attualmente nella versione Preview.

La tecnologia NDI® e SDI è supportata in tutte le impostazioni locali.

L'accesso all'uso di NDI e SDI è determinato dai criteri della riunione per l'utente che tenta di attivare la funzionalità. Per la soluzione più sicura, non attivare il parametro di streaming locale come impostazione globale.


## <a name="enable-broadcast-features"></a>Abilitare le funzionalità di trasmissione

Per abilitare le funzionalità di trasmissione NDI® e SDI per un utente:

1. L'amministratore del tenant deve consentire all'utente finale di attivare lo streaming locale per i criteri delle riunioni. 

2. L'utente finale deve attivare lo streaming locale per il proprio client specifico.


Per abilitare l'utente finale, è possibile usare il centro Amministrazione teams o PowerShell di Teams come indicato di seguito.

Nell'interfaccia di amministrazione di Teams, vai a **Criteri riunione > Audio & video** e seleziona **Trasmissione locale**.

Per usare PowerShell, usare il cmdlet Set-CsTeamsMeetingPolicy come segue:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Dopo che questa modifica è stata popolata, l'utente finale deve attivare la riproduzione in streaming locale per il client specifico da **Autorizzazioni impostazioni** > . Per altre informazioni, vedere [Trasmettere audio e video da Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





