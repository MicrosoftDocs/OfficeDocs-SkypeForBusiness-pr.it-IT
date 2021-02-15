---
title: Esperienza di riunione in sola visualizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di riunione di sola visualizzazione di Teams per amministratori, relatori e partecipanti
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237456"
---
# <a name="teams-view-only-meeting-experience"></a>Esperienza di riunione in sola visualizzazione di Teams

> [!Note]
> L'esperienza di sola visualizzazione per le riunioni sarà disponibile all'inizio di marzo 2021.

> [!Note]
> L'esperienza di sola visualizzazione è stata temporaneamente aumentata per 20.000 partecipanti, ma il supporto verrà ripristinato a 10.000 partecipanti il 30 giugno 2021.

Microsoft Teams consente a un massimo di 10.000 partecipanti di partecipare a una riunione di Teams. Una volta raggiunta la capacità della riunione principale, altri partecipanti potranno partecipare con un'esperienza di sola visualizzazione.

I partecipanti che aderiscono per primi alla riunione, fino alla capacità della riunione, otterrà l'esperienza completa della riunione di Teams. Possono condividere audio e video, vedere i video condivisi e partecipare alla chat della riunione.

I partecipanti che aderiscono dopo aver raggiunto la capacità principale della riunione avranno un'esperienza di sola visualizzazione.

Per un partecipante è disponibile il supporto completo per dispositivi mobili Android e iOS.

> [!Note]
> Il limite corrente per il numero di persone che possono chattare e chiamare per una riunione è 300 in WW e 250 in GCC, GCC High e DoD.

L'esperienza di sola visualizzazione è abilitata per impostazione predefinita per tutti gli organizzatori che hanno SKU E3/E5/A3/A5. Non sono necessarie altre configurazioni o configurazioni.

### <a name="disable-teams-view-only-experience"></a>Disabilitare l'esperienza di sola visualizzazione di Teams

Gli amministratori possono disabilitare l'esperienza di sola visualizzazione con PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In futuro, gli amministratori potranno anche disabilitare l'esperienza di sola visualizzazione nell'interfaccia di amministrazione di Teams.

## <a name="impact-to-users"></a>Impatto sugli utenti

L'esperienza di un utente varia in base a diversi fattori.

Una volta raggiunta la capacità della riunione principale, un partecipante non sarà in grado di partecipare se si verifica una delle condizioni seguenti:

- Un amministratore ha disabilitato l'esperienza di sola visualizzazione di Teams.
- Il partecipante non è autorizzato a ignorare la sala di attesa.

Una volta raggiunta la capacità della riunione principale, l'organizzatore e i relatori della riunione vedranno un banner che li informa che è stata raggiunta la capacità della riunione e che i nuovi partecipanti potranno partecipare a un partecipante di sola visualizzazione.

  ![The Teams client and banner messsage for organizers and presenters](media/chat-and-banner-message.png)

Quando viene raggiunta la capacità della riunione principale, i partecipanti alla riunione vengono informati nella schermata di pre-accesso che stanno partecipando in modalità di sola visualizzazione.

  ![schermata di pre-partecipazione di Teams e messaggio per i partecipanti che li informa che potranno partecipare in modalità di sola visualizzazione](media/view-only-pre-join-screen.png)

Se c'è spazio, un utente partecipa sempre alla riunione principale. Se la riunione principale raggiunge la capacità e uno o più partecipanti lasciano la riunione principale, la riunione principale ha la capacità disponibile. I partecipanti che a partecipare (o a rientrare) alla riunione principale non raggiungeranno nuovamente la capacità. I partecipanti che hanno esperienza di sola visualizzazione non verranno automaticamente alzati di livello alla riunione principale e al momento non possono essere alzati manualmente alla riunione principale.

Se i ruoli di relatore/partecipante non sono stati impostati, gli spazi nella riunione principale vengono compilati in base al primo utente. Una volta raggiunta la capacità della riunione, tutti gli altri utenti potranno partecipare con un'esperienza di sola visualizzazione.

## <a name="impact-to-meeting-presenters"></a>Impatto sui relatori della riunione

Nella riunione normale verrà prenotato uno spazio per gli utenti esplicitamente indicati come relatori nelle opzioni della riunione. Se un relatore lascia la riunione e in seguito rientra nella riunione, il relatore passerà alla riunione come relatore.

Le limitazioni per i relatori della riunione includono:

- Non si hanno informazioni sul partecipante di sola visualizzazione. L'e-discovery non è disponibile per i partecipanti di sola visualizzazione.
- Gli utenti non possono vedere i partecipanti di sola visualizzazione.
- Non è possibile rimuovere un partecipante di sola visualizzazione dalla riunione.

> [!Note]
> Il numero di partecipanti rifletterà solo le persone presenti alla riunione e non le persone nella sala di riversamento. Di conseguenza, i relatori non possono ottenere il conteggio esatto degli utenti nell'esperienza di sola visualizzazione.

## <a name="experience-for-view-only-attendees"></a>Esperienza per i partecipanti di sola visualizzazione

L'esperienza di sola visualizzazione di Teams consente ai partecipanti di:

- Ascoltare i partecipanti alla riunione di Teams principale.
- Vedere il feed video dell'altoparlante attivo (se il relatore attivo sta condividendo il video).
- Visualizzare il contenuto condiviso usando la funzionalità Condividi desktop.

Il partecipante di sola visualizzazione non sarà in grado di visualizzare le opzioni seguenti nelle riunioni:

- Partecipare alla riunione se il partecipante non è autorizzato a evitare la sala di attesa in base alle opzioni o ai criteri di attesa impostati.
- Partecipare alla sala di riversamento tramite audioconferenza.
- Entra nella sala riversamento tramite il sistema Room system di Microsoft Teams o tramite i servizi Cloud Video Interoperabilità (CVI).
- Entra nella sala riversamento tramite l'app Teams per dispositivi mobili Android.
- Condividere l'audio o il video.
- Visualizzare o partecipare alla chat della riunione.
- Visualizzare il feed video dei partecipanti alla riunione a meno che il partecipante non sia il relatore attivo.
- Visualizzare i file di PowerPoint condivisi usando la funzionalità nativa di PowerPoint condivisa o le singole condivisioni applicazioni (diversa dalla condivisione desktop).

## <a name="view-only-feature-limitations"></a>Limitazioni delle caratteristiche di sola visualizzazione

- I partecipanti in sola visualizzazione visualizzano sempre i sottotitoli in tempo reale, indipendentemente dall'impostazione dei sottotitoli in tempo reale per la riunione. Al momento sono supportati solo i sottotitoli in inglese.
- I partecipanti in sola visualizzazione saranno supportati dalla tecnologia di streaming.
- I partecipanti di sola visualizzazione non verranno inclusi nel report sulle presenze.
- I partecipanti in sola visualizzazione avranno un'unica esperienza video. Possono vedere il relatore attivo o il contenuto condiviso, ma non entrambi.
- Al momento, i **layout** della **raccolta,** della raccolta **grande** o della modalità Insieme non sono supportati per i partecipanti in sola visualizzazione.  
- I partecipanti di sola visualizzazione non hanno la stessa latenza di un normale partecipante. <sup>1</sup>

  <sup>1</sup> I partecipanti in sola visualizzazione avranno un ritardo audio e video di 30 secondi nella riunione.  

## <a name="related-topics"></a>Argomenti correlati

- [Componente aggiuntivo per le comunicazioni avanzate per Teams](teams-add-on-licensing/advanced-communications.md)
- [Limiti e specifiche per Teams](limits-specifications-teams.md)
