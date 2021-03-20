---
title: Esperienza di solo visualizzazione nelle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875056"
---
# <a name="teams-view-only-meeting-experience"></a>Esperienza di sola visualizzazione nelle riunioni di Teams

> [!Note]
> Le trasmissioni nella modalità di sola visualizzazione sono disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5. Questa caratteristica sarà abilitata come predefinita l'1 marzo 2021. La distribuzione di questa funzionalità in Microsoft 365 Government Community Cloud (GCC) inizierà alla fine di marzo 2021. Government Community Cloud High (GCCH) e Department of Defense (DoD) saranno distribuiti in seguito. È necessario modificare i criteri predefiniti dopo tale data se si attivare la funzionalità. Usare PowerShell per abilitare i criteri `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Se la riunione o il webinar supera la capacità, Teams si adatterà rapidamente per offrire un'esperienza di trasmissione in modalità solo visualizzazione per 10.000 persone.  Inoltre, durate questo periodo di maggiore telelavoro, si possono organizzare trasmissioni ancora più grandi, per 20.000 persone, fino alla fine di quest'anno.

Microsoft Teams consente fino a 10.000 partecipanti alle riunioni. Una volta raggiunta la capacità della riunione principale, gli altri partecipanti accederanno un'esperienza di sola visualizzazione.

Gli utenti che accedono alla riunione per primi vivranno l'esperienza di riunione completa, fino al raggiungimento del limite della riunione. Possono condividere audio e video, visualizzare i video condivisi e partecipare alla chat delle riunioni.

Gli utenti che accedono dopo il superamento della capacità della riunione accederanno a un'esperienza di sola visualizzazione.  

La partecipazione alle riunioni supporta pienamente i dispositivi mobili Android e iOS.

> [!Note]
> Il limite attuale del numero di persone che possono chattare e chiamare durante le riunioni è 300 per WW, 250 per GCC, GCC High e DoD.

L'esperienza di sola visualizzazione è disabilitata per impostazione predefinita per tutti gli organizzatori dotati con SKU E3/E5/A3/A5. Non sono necessarie altre operazioni di configurazione o impostazione.

## <a name="disable-teams-view-only-experience"></a>Disabilitare l'esperienza di solo visualizzazione di Teams

Gli amministratori possono disabilitare l'esperienza di sola visualizzazione con PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.

## <a name="impact-to-users"></a>Impatto sugli utenti

L'esperienza d'uso varia a seconda di numerosi fattori.

Quando il limite di partecipati della riunione principale viene raggiunto, i partecipanti non possono accedere alla riunione se una qualsiasi delle seguenti condizioni è vera: 

- L'esperienza di sola visualizzazione di Teams è stata disabilitata da un amministratore.
- Il partecipante non è autorizzato a ignorare la sala di attesa.

Quando viene raggiunto il limite di partecipanti della riunione principale, l'organizzatore della riunione e i presentatori vedranno un banner, che notifica che il limite è stato raggiunto e i nuovi partecipanti accederanno solo a un'esperienza di sola visualizzazione.

  ![il cient di Teams e il banner di notifica per organizzatori e relatori](media/chat-and-banner-message.png)

Quando viene raggiunto il limite di partecipanti della riunione principale, i partecipanti vengono informati nella schermata preliminare di accesso che stanno accedendo a un'esperienza di sola visualizzazione. 

  ![la schermata preliminare di accesso e il messaggio per i partecipanti che notifica  che si sta accedendo a un'esperienza di sola visualizzazione](media/view-only-pre-join-screen.png)

Se lo spazio è sufficiente, i nuovi utenti accedono sempre alla riunione principale. Se il limite della riunione principale viene raggiunto e uno o più utenti abbandonano la riunione, la riunione principale ha una capacità sufficiente. I partecipanti che accedono (o riaccedono) alla riunione entreranno nella sala principale fino al raggiungimento del limite di utenti. I partecipanti che hanno avviato l'esperienza di sola visualizzazione non saranno promossi automaticamente alla riunione principale, e al momento non possono esservi promossi.

Se i ruoli relatore/partecipante non sono stati configurati, i posti disponibili nella sala vengono assegnati in base all'ordine di accesso. Una volta raggiunto il limite della riunione, tutti gli altri utenti potranno accedere a un'esperienza di sola visualizzazione.

## <a name="impact-to-meeting-presenters"></a>Impatto per i relatori della riunione

Le limitazioni dei relatori delle riunioni includono:

- Non sono disponibili informazioi sui partecipanti in modalità di sola visualizzazione. I processi e-discovery non sono supportati per i partecipanti in modalità di sola visualizzazione.
- Gli utenti non possono vedere gli utenti in modalità di sola visualizzazione.
- Non è possibile rimuovere i partecipanti in modalità di sola visualizzazione dalle riunioni.

> [!Note]
> Il numero di partecipanti indicato riflette solo gli utenti della riunione, non le persone che si trovano nella sala di sola visualizzazione. Pertanto, i presentatori non possono conoscere esattamente il numero degli utenti nella sala di sola visualizzazione.

## <a name="experience-for-view-only-attendees"></a>Esperienza per gli in modalità nella sala di sola visualizzazione

L'esperienza di sola visualizzazione consente ai partecipanti di:

- Ascoltare i partecipanti alla riunione principale di Teams.
- Vedere il feed video del relatore attivo (se il relatore sta condividendo il video).
- Visualizzare i contenuti condivisi con la funzionalità di condivisione del desktop.

I partecipanti nella sala di sola visualizzazione non potranno usare le seguenti opzioni delle riunioni:

- Partecipare alle riunioni se il partecipante non è autorizzato a ignorare la sala di attesa in base ai criteri o alle opzioni configurati della sala di attesa.
- Accedere alla sala di solo visualizzazione usando la funzionalità di audioconferenza.
- Partecipare alla sala di sola visualizzazione usando il sistema della Sala riunioni di Teams o usando i servizi Cloud Video Interop (CVI).
- Condividere l'audio o il video.
- Leggere o partecipare alla chat della riunione.
- Visualizzare il video trasmesso dai partecipanti alla riunione, se non sono i relatori attivi.
- Vedere i file di PowerPoint condivisi usando la funzionalità di condivisione nativa di PowerPoint o specifiche applicazioni di condivisione (diverse dalla condivisione desktop).

## <a name="view-only-feature-limitations"></a>Limitazioni della funzionalità di sola visualizzazione

- I partecipanti nella sala di sola visualizzazione vedranno sempre i sottotitoli, indipendentemente dalle impostazioni dei sottotitoli della riunione. Al momento sono supportati solo i sottotitoli in inglese.
- I partecipanti nella sala di sola visualizzazione saranno supportati dalla tecnologia di streaming.
- I partecipanti nella sala di sola visualizzazione non vengono inclusi nel report sui partecipanti.
- I partecipanti nella sala di sola visualizzazione hanno un'esperienza video singola. Possono accedere l'altoparlante attivo o i contenuti che vengono condivisi, ma non entrambi.
- Al momento non supportiamo i layout **Galleria**, **Galleria estesa**, o **Modalità Insieme** per gli utenti nella sala di sola visualizzazione.  
- Gli utenti nella sala di sola visualizzazione non avranno la stessa latenza degli utenti regolari. <sup>1</sup>

  <sup>1</sup> I partecipanti nella sala di sola visualizzazione avrannno un ritardo audio e video di 30 secondi durante la riunione.  
