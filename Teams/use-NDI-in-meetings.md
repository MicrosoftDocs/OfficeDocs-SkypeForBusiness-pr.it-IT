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
description: Informazioni su come usare NDI in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1ad11000de2ae0dac7563d785dfaea8c34978ed
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337015"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usare la tecnologia NDI® in Microsoft Teams

 La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per la connessione di dispositivi multimediali (ad esempio una fotocamera da studio e un mixer). Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche su un computer locale.

La tecnologia NDI® è diventata una soluzione di settore standard per la produzione di contenuti in tempo reale per i flussi e ha guadagnato una significativa consapevolezza e adozione nel mondo delle trasmissioni professionali.

Skype ha aggiunto in ® funzionalità di out-out NDI a Skype negli ultimi mesi del 2018. Microsoft Teams usa questa funzionalità per migliorare l'esperienza delle riunioni.

La tecnologia NDI ® è limitata a una rete locale e deve essere considerata solo parte del flusso di lavoro di produzione, non una soluzione di trasmissione.

## <a name="turn-on-ndi-technology"></a>Attivare la tecnologia NDI®

La tecnologia NDI® richiede due passaggi per essere attivata per un utente.

1. L'amministratore del tenant deve abilitare la proprietà "AllowNDIStreaming" in CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Dopo aver popolato la modifica, l'utente finale deve attivare la tecnologia NDI® per il client specifico da  >  **Autorizzazioni impostazioni.**

Quando un utente partecipa a una riunione, visualizza un messaggio che lo informa che la riunione è in corso di trasmissione. Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno essere presenti nella riunione.

L'immagine seguente mostra il messaggio del banner che un utente vede in una riunione di Teams.

![He NDI® technology banner that displays in a Teams meeting.](media/NDI-disclosure.png)

Il banner include un collegamento [all'informativa sulla privacy di Microsoft.](https://aka.ms/teamsprivacy)

## <a name="supported-locales-and-user-types"></a>Impostazioni locali e tipi di utente supportati

La tecnologia NDI® è supportata in tutte le impostazioni locali. Gli utenti seguenti sono inclusi in un flusso ® tecnologia NDI®, ma non tutti gli utenti possono accedervi:

- Supporto completo all'interno del tenant, recapitato in base a ring/tenantId/userId (controllato dai criteri di riunione)
- Federato : nessun accesso al flusso (anche se la tecnologia NDI® è on)<sup>1</sup>
- Premium - nessun accesso in streaming
- Anonimo: nessun accesso al flusso
- Guest : nessun accesso in flusso  

<sup>1</sup> I dispositivi dispongono di ® tecnologia NDI attivata per impostazione predefinita. Se un partecipante alla riunione usa un dispositivo con la tecnologia NDI®, dovrà attivare la tecnologia NDI®>
