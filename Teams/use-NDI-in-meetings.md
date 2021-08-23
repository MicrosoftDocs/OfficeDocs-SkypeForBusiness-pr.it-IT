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
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359183"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usare la tecnologia NDI® in Microsoft Teams

 La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per la connessione di dispositivi multimediali , ad esempio una fotocamera da studio e un mixer. Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.

La tecnologia NDI® è diventata una soluzione di settore standard per la produzione di contenuti live per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.

Skype aggiunto in precedenza ® funzionalità di Skype NDI alla fine del 2018. Microsoft Teams questa funzionalità per migliorare l'esperienza della riunione.

La tecnologia NDI® è limitata a una rete locale e deve essere considerata solo una parte del flusso di lavoro di produzione, non una soluzione broadcast.

## <a name="turn-on-ndi-technology"></a>Attivare la tecnologia NDI®

La tecnologia NDI® richiede due passaggi per essere attivata per un utente.

1. L'amministratore tenant deve consentire all'utente finale di attivare NDI per i criteri di riunione. Questa operazione può essere eseguita singolarmente nel portale di amministrazione di Teams o tramite powershell di Teams dalla proprietà _AllowNDIStreaming_ in CsTeamsMeetingPolicy.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Dopo aver popolato questa modifica, l'utente finale deve attivare la tecnologia NDI® per il proprio client specifico da  >  **Impostazioni Autorizzazioni**.

Dopo essere stato attivato per un utente e il suo client specifico, l'utente può attivare NDI tramite il menu di overflow e selezionare "Broadcast su NDI".

Dopo l'avvio dell'NDI e la sottoscrizione di un endpoint a un feed NDI, verrà visualizzato un messaggio che informa che la riunione è in fase di trasmissione. Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno rilasciare dalla riunione.

L'immagine seguente mostra il messaggio banner visualizzato da un utente in una riunione Teams riunione.

![striscione ® tecnologia NDI che viene visualizzato in una Teams riunione.](media/NDI-disclosure.png)

Il banner contiene un collegamento [all'informativa sulla privacy Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® viene attivato solo per sessione. Nella riunione successiva, l'utente deve attivarla prima di usare NDI®.

## <a name="supported-locales-and-user-types"></a>Impostazioni locali e tipi di utente supportati

La ® NDI è supportata in tutte le impostazioni locali.

L'accesso all'uso di NDI è determinato dai criteri di riunione per l'utente che tenta di attivare la caratteristica. Per la soluzione più sicura, non attivare i criteri NDI come impostazione globale.
