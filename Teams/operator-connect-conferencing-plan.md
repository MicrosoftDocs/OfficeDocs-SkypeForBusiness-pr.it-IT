---
title: Pianificare Conferenze con connessione tramite operatore
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sui Conferenze con connessione tramite operatore, ad esempio i requisiti e la pianificazione della distribuzione.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e1c363c66028a9e8611fa38179585e1e073c54b
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583981"
---
# <a name="plan-for-operator-connect-conferencing"></a>Pianificare Conferenze con connessione tramite operatore

I servizi di audioconferenza Microsoft offrono la possibilità di accedere a una conferenza e di effettuare chiamate in uscita da una conferenza utilizzando numeri di telefono PSTN (Public Switched Telephone Network).  I partecipanti accedono alle riunioni di Microsoft Teams utilizzando un bridge di conferenza solo audio.

Con le funzionalità Conferenze con connessione tramite operatore, le organizzazioni possono usare i numeri di telefono di un operatore di terze parti per partecipare alle riunioni di Microsoft Teams. Se l'operatore corrente fa parte del programma Microsoft Operator Connect, puoi aggiungere i numeri di telefono del tuo operatore al bridge di audioconferenza e usarli per partecipare alle riunioni.

Senza Conferenze con connessione tramite operatore funzionalità, le organizzazioni possono utilizzare solo i numeri di telefono forniti da Microsoft per il bridge di audioconferenza.

>[!NOTE]
>Un provider di numeri di telefono che fa parte del programma Microsoft Operator Connect viene indicato in questo articolo come "operatore".
>
>Per vedere se il tuo operatore partecipa al programma Microsoft Operator Connect, vedi la [directory Microsoft 365 Operator Connect](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

Questo articolo descrive Conferenze con connessione tramite operatore:

- [Vantaggi](#benefits)
- [Requisiti di licenza e fatturazione](#licensing-requirements-and-billing)
- [Ulteriori informazioni sui servizi di audioconferenza Microsoft](#additional-information-on-microsoft-audio-conferencing)

Per informazioni sulla configurazione di Conferenze con connessione tramite operatore, vedere [Configurare Conferenze con connessione tramite operatore](operator-connect-conferencing-configure.md).

Se alcuni utenti dell'organizzazione devono effettuare chiamate esterne ai numeri di telefono PSTN, è comunque necessario un piano per le chiamate. Per informazioni sull'uso di un operatore di terze parti per la connettività PSTN esterna, vedere [Plan for Operator Connect](operator-connect-plan.md).

## <a name="benefits"></a>Vantaggi

Conferenze con connessione tramite operatore offre i seguenti vantaggi:

- **Allocazione flessibile dei numeri di telefono tra l'operatore e Microsoft.** Usa i numeri di telefono di Microsoft e del tuo operatore (solo con un abbonamento Microsoft Audio Conferencing Standard) o usa solo i numeri di telefono del tuo operatore (solo con una licenza di Conferenze con connessione tramite operatore).

- **Infrastruttura gestita dall'operatore.** L'operatore gestisce i controller dei confini di sessione e l'interconnettività con Microsoft, risparmiandoti da acquisti e gestione hardware aggiuntivi.

- **Distribuzione più rapida e semplice.** Connettersi rapidamente all'operatore e assegnare numeri di telefono al bridge di audioconferenza dall'interfaccia di amministrazione di Teams.

- **Supporto e affidabilità migliorati.** Gli operatori forniscono supporto tecnico e contratti a livello di servizio condiviso per migliorare il supporto del servizio e il peering diretto con tecnologia Azure crea una connessione di rete uno-a-uno per un'affidabilità avanzata.

Conferenze con connessione tramite operatore potrebbe essere la soluzione giusta per l'organizzazione se:

- Si desidera **mantenere i contratti** con il provider di numeri di telefono esistente

- Espandere **la copertura globale** del bridge di Audioconferenza Microsoft esistente

- Vuoi ottenere **i numeri di telefono per i servizi di audioconferenza** da un nuovo provider di numeri di telefono

- **I servizi di audioconferenza Microsoft non sono disponibili nella tua posizione geografica**

- Si desidera **sfruttare un operatore per i servizi di audioconferenza con un modello di pagamento al minuto**, ad esempio utilizzare numeri verdi e effettuare chiamate in uscita dalle riunioni di Teams ai numeri di telefono in paesi non inclusi nell'abbonamento

## <a name="licensing-requirements-and-billing"></a>Requisiti di licenza e fatturazione

Gli utenti che hanno bisogno di Conferenze con connessione tramite operatore numeri per partecipare alle riunioni che organizzano devono disporre di un abbonamento Microsoft Audio Conferencing Standard o di una licenza microsoft Conferenze con connessione tramite operatore assegnata.

### <a name="audio-conferencing-standard-subscription"></a>Abbonamento a Audioconferenza Standard

Un abbonamento Microsoft Audio Conferencing Standard può essere acquistato come componente aggiuntivo di una licenza di Microsoft Teams ed è incluso anche negli abbonamenti a Microsoft 365 E5 e Office 365 E5.

L'abbonamento a Audioconferenza Standard consente agli abbonati di utilizzare i numeri di telefono di Microsoft ed espandere il bridge dei servizi di audioconferenza con i numeri di un operatore. Gli abbonati possono anche decidere quali chiamate in uscita dalle riunioni di Teams instradare tramite Microsoft e quali chiamate instradare tramite un operatore.

Per altre informazioni, vedere [**Configurare Conferenze con connessione tramite operatore**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Conferenze con connessione tramite operatore licenza

Una licenza di Microsoft Conferenze con connessione tramite operatore può essere acquisita come componente aggiuntivo di una licenza di Microsoft Teams.

La licenza Conferenze con connessione tramite operatore consente agli abbonati di usare i numeri di telefono di un operatore, ma non include i numeri di telefono di Microsoft. Tutte le chiamate in uscita dalle riunioni di Teams devono essere instradate tramite un operatore.

Per altre informazioni, vedere [**Configurare Conferenze con connessione tramite operatore**](operator-connect-conferencing-configure.md).

>[!Note]
>Per partecipare a una riunione organizzata da un utente con funzionalità di Conferenze con connessione tramite operatore, i partecipanti alla riunione non richiedono una licenza per l'abbonamento standard ai servizi di audioconferenza o una licenza di Conferenze con connessione tramite operatore.

Con Conferenze con connessione tramite operatore, Microsoft fattura l'organizzazione in base al tipo di licenza per i servizi di audioconferenza utilizzato dall'organizzazione, ai servizi di audioconferenza o Conferenze con connessione tramite operatore Microsoft e all'uso di qualsiasi numero di telefono fornito da Microsoft.

L'operatore fattura all'organizzazione l'uso dei numeri di Conferenze con connessione tramite operatore forniti.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Ulteriori informazioni sui servizi di audioconferenza Microsoft

Microsoft Audioconferenza consente ai partecipanti di partecipare alle riunioni di Microsoft Teams effettuando l'accesso con un numero di telefono PSTN o chiamando un numero di telefono PSTN. Per altre informazioni sulle funzionalità di Audioconferenza Microsoft disponibili per l'organizzazione, vedere [Audioconferenza in Microsoft 365](audio-conferencing-in-office-365.md).
