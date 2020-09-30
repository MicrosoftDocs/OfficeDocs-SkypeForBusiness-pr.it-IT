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
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308169"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usare la tecnologia® NDI in Microsoft Teams

 La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per connettere dispositivi multimediali, ad esempio una videocamera e un mixer di studio. Invece di usare le connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.

La tecnologia NDI® è diventata una soluzione industriale standard per la produzione di contenuti dinamici per flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.

Skype ha aggiunto in precedenza la funzionalità®-out di NDI a Skype alla fine di 2018. Microsoft teams USA questa funzionalità per migliorare l'esperienza di riunione.

La tecnologia NDI® è limitata a una rete locale e deve essere considerata solo una parte del flusso di lavoro di produzione e non una soluzione broadcast.

## <a name="turn-on-ndi-technology"></a>Attivare la tecnologia® NDI

La tecnologia NDI® richiede che vengano attivati due passaggi per un utente.

1. L'amministratore del tenant deve abilitare la proprietà "AllowNDIStreaming" in CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Dopo aver popolato questa modifica, l'utente finale deve attivare la tecnologia NDI® per il suo specifico client dalle autorizzazioni per **le impostazioni**  >  **Permissions**.

Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione viene trasmessa. Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere abbandonati alla riunione.

L'immagine seguente mostra il messaggio di banner visualizzato da un utente in una riunione di teams.

![Immagine del banner della tecnologia® NDI che viene visualizzato in una riunione teams.](media/NDI-disclosure.png)

Il banner contiene un collegamento ai [criteri di privacy Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Impostazioni locali e tipi di utente supportati

La tecnologia NDI® è supportata in tutte le impostazioni locali. Gli utenti seguenti sono inclusi in un flusso di tecnologia® NDI, ma non tutti gli utenti possono accedere al flusso di tecnologia NDI®:

- In-tenant-supporto completo, distribuito in base a Ring/ID tenant/userId (controllato da criteri riunioni)
- Federati: nessun accesso allo stream (anche se hanno la tecnologia NDI®)<sup>1</sup>
- Freemium-nessun accesso allo stream
- Anonimo-Nessun accesso allo stream
- Guest: nessun accesso allo stream  

<sup>1</sup> i dispositivi hanno un'impostazione di tecnologia NDI® attivata per impostazione predefinita. Se un partecipante alla riunione usa un dispositivo con NDI® Technology off, dovrà attivare NDI® tecnologia.
