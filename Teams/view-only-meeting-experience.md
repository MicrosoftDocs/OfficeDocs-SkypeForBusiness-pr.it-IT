---
title: Esperienza di riunione di sola visualizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di riunione in sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875056"
---
# <a name="teams-view-only-meeting-experience"></a>Esperienza di riunione in sola visualizzazione di Teams

> [!Note]
> Le trasmissioni di sola visualizzazione sono disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5. Questa caratteristica verrà abilitata l'1 marzo 2021 come impostazione predefinita. La funzionalità di Microsoft 365 Government Community Cloud (GCC) inizierà a essere disponibile alla fine di marzo 2021. Government Community Cloud High (GCCH) e Department of Defense (DoD) verranno implementazioni in un secondo momento. È necessario modificare il criterio predefinito dopo tale data se si vuole che la caratteristica sia attivata per impostazione predefinita. Usare PowerShell per abilitare il `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` criterio.

> [!Note]
> Se la riunione o il webinar raggiunge la capacità, Teams si adatta perfettamente a un'esperienza di trasmissione solo visualizzazione di 10.000 persone. Inoltre, durante questo periodo di maggiore attività remota, sfruttare le trasmissioni di 20.000 persone ancora più grandi fino alla fine di quest'anno.

Microsoft Teams consente a un massimo di 10.000 partecipanti di partecipare a una riunione di Teams. Dopo aver raggiunto la capacità della riunione principale, altri partecipanti si uniranno con un'esperienza di sola visualizzazione.

I partecipanti che aderiscono per primi alla riunione, fino alla capacità della riunione, otterrà l'esperienza completa della riunione di Teams. Possono condividere audio e video, vedere i video condivisi e partecipare alla chat delle riunioni.

I partecipanti che aderiscono dopo aver raggiunto la capacità della riunione principale avranno un'esperienza di sola visualizzazione.

Abbiamo il supporto completo per Android e iOS per dispositivi mobili a cui un partecipante può partecipare.

> [!Note]
> Il limite corrente per il numero di persone che possono chattare e chiamare a una riunione è 300 in WW e 250 in GCC, GCC High e DoD.

L'esperienza di sola visualizzazione è disabilitata per impostazione predefinita per qualsiasi organizzatore con SKU E3/E5/A3/A5. Non sono necessarie altre configurazioni o configurazioni.

## <a name="disable-teams-view-only-experience"></a>Disabilitare l'esperienza di sola visualizzazione di Teams

Gli amministratori possono disabilitare l'esperienza di sola visualizzazione usando PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.

## <a name="impact-to-users"></a>Impatto sugli utenti

L'esperienza di un utente varia a seconda di diversi fattori.

Una volta raggiunta la capacità della riunione principale, un partecipante non sarà in grado di partecipare alla riunione se una delle condizioni seguenti è vera:

- Un amministratore ha disabilitato l'esperienza di sola visualizzazione di Teams.
- Il partecipante non ha l'autorizzazione per ignorare la sala d'attesa.

Una volta raggiunta la capacità della riunione principale, l'organizzatore della riunione e i relatori vedranno uno striscione che informa che la capacità della riunione è stata raggiunta e che i nuovi partecipanti si uniranno a un partecipante di sola visualizzazione.

  ![il client Teams e il messaggio banner per organizzatori e relatori](media/chat-and-banner-message.png)

Una volta raggiunta la capacità della riunione principale, i partecipanti alla riunione verranno informati nella schermata di pre-partecipazione che stanno partecipando in modalità di sola visualizzazione.

  ![la schermata di pre-partecipazione di Teams e il messaggio per i partecipanti che informano che si uniranno in modalità di sola visualizzazione](media/view-only-pre-join-screen.png)

Se c'è spazio, un utente partecipa sempre alla riunione principale. Se la riunione principale raggiunge la capacità e uno o più partecipanti lasciano la riunione principale, la riunione principale ha la capacità disponibile. I partecipanti che aderiscono alla riunione (o a cui si partecipa di nuovo) aderiscono alla riunione principale finché non raggiunge di nuovo la capacità. I partecipanti all'esperienza di sola visualizzazione non verranno alzati di livello automaticamente alla riunione principale e non potranno essere alzati di livello manualmente alla riunione principale.

Se i ruoli relatore/partecipante non sono stati impostati, gli spazi nella riunione principale vengono riempiti in base al primo arrivato e al primo servizio. Una volta raggiunta la capacità della riunione, tutti gli altri utenti potranno partecipare con un'esperienza di sola visualizzazione.

## <a name="impact-to-meeting-presenters"></a>Impatto sui relatori della riunione

Le limitazioni per i relatori della riunione includono:

- Non si hanno informazioni sul partecipante di sola visualizzazione. L'individuazione elettronica non è disponibile per i partecipanti di sola visualizzazione.
- Gli utenti non possono vedere i partecipanti di sola visualizzazione.
- Non è possibile rimuovere un partecipante di sola visualizzazione dalla riunione.

> [!Note]
> Il conteggio dei partecipanti rifletterà solo le persone nella riunione e non le persone nella sala di sola visualizzazione. Di conseguenza, i relatori non possono ottenere un conteggio esatto degli utenti nell'esperienza di sola visualizzazione.

## <a name="experience-for-view-only-attendees"></a>Esperienza per i partecipanti di sola visualizzazione

L'esperienza di sola visualizzazione di Teams consente ai partecipanti di:

- Ascoltare i partecipanti alla riunione principale di Teams.
- Vedere il feed video per l'altoparlante attivo (se l'altoparlante attivo sta condividendo il video).
- Visualizzare il contenuto condiviso con la funzionalità condividi desktop.

Il partecipante di sola visualizzazione non sarà in grado di visualizzare le opzioni seguenti nelle riunioni:

- Partecipare alla riunione se il partecipante non ha l'autorizzazione per ignorare la sala d'attesa in base alle opzioni o ai criteri di sala d'attesa impostati.
- Partecipare alla sala di sola visualizzazione usando le audioconferenze.
- Partecipare alla sala di sola visualizzazione usando il sistema Room di Microsoft Teams o i servizi CVI (Cloud Video Interop).
- Condividere l'audio o il video.
- Visualizzare o partecipare alla chat della riunione.
- Vedere il feed video dei partecipanti alla riunione, a meno che il partecipante non sia il relatore attivo.
- Vedere File di PowerPoint condivisi con la funzionalità di Condivisione nativa di PowerPoint o singole condivisioni di applicazioni (diverse dalla condivisione desktop).

## <a name="view-only-feature-limitations"></a>Limitazioni delle funzionalità di sola visualizzazione

- I partecipanti di sola visualizzazione visualizzano sempre i sottotitoli in tempo reale, indipendentemente dall'impostazione dei sottotitoli in tempo reale per la riunione. Al momento sono supportate solo le didascalie in inglese.
- I partecipanti di sola visualizzazione saranno supportati dalla tecnologia di streaming.
- I partecipanti di sola visualizzazione non verranno inclusi nel report di partecipazione.
- I partecipanti di sola visualizzazione avranno una singola esperienza video. Possono vedere il relatore attivo o il contenuto condiviso, ma non entrambi.
- Attualmente non sono supportati i **layout** della **modalità Raccolta,** Raccolta grande o Insieme per i partecipanti di sola visualizzazione.  
- I partecipanti di sola visualizzazione non hanno la stessa latenza di un partecipante normale. <sup>1</sup>

  <sup>1</sup> I partecipanti di sola visualizzazione avranno un ritardo audio e video di 30 secondi nella riunione.  
