---
title: Usare NDI in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 86c0908b04b2eece835a747d9f57625878c15a99
ms.sourcegitcommit: 95989f1a93524a2025feeb50b8635da332961ea3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588290"
---
# <a name="use-ndi-in-microsoft-teams"></a>Usare NDI in Microsoft Teams

[!INCLUDE [template](includes/preview-feature.md)]

Network Device Interface (NDI) è una soluzione moderna per connettere dispositivi multimediali, ad esempio una videocamera e un mixer di studio. Invece di usare le connessioni fisiche, NDI consente la connettività su una Intranet locale, anche in un computer locale.

NewTek NDI® è diventata una soluzione industriale standard per la produzione di contenuti dinamici per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.

Skype ha aggiunto in precedenza la funzionalità NDI in Skype alla fine di 2018. Microsoft teams sfrutta questa funzionalità per migliorare l'esperienza di riunione.

NDI è limitato a una rete locale e deve essere considerato solo una parte del flusso di lavoro di produzione, non una soluzione broadcast.

## <a name="turn-on-ndi"></a>Attivare NDI

NDI richiede che vengano attivati due passaggi per un utente.

1. L'amministratore del tenant deve abilitare la proprietà "AllowNDIStreaming" in CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Dopo aver popolato questa modifica, l'utente finale deve attivare NDI per il proprio client specifico dalle autorizzazioni per **le impostazioni**  >  **Permissions**.

Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione viene trasmessa. Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere abbandonati alla riunione.

L'immagine seguente mostra il messaggio di banner visualizzato da un utente in una riunione di teams.

![Immagine del banner di NDI visualizzato in una riunione di teams.](media/NDI-disclosure.png)

Il banner contiene un collegamento ai [criteri di privacy Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Impostazioni locali e tipi di utente supportati

NDI è supportato in tutte le impostazioni locali. Gli utenti seguenti sono supportati in una riunione di NDI:

- In-tenant-supporto completo, distribuito in base a Ring/ID tenant/userId (controllato da criteri riunioni)
- Federati-No (anche quando hanno NDI)<sup>1</sup>
- Freemium-No (valore predefinito)
- Anonimo-No (valore predefinito)
- Guest-No (valore predefinito)

<sup>1</sup> i dispositivi hanno un'impostazione NDI attiva per impostazione predefinita. Se un partecipante alla riunione usa un dispositivo con NDI disattivato, dovrà attivare NDI.
