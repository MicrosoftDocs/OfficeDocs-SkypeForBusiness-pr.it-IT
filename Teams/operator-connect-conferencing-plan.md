---
title: Pianificare le conferenze Connessione con operatore conferenza
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
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sulle conferenze Connessione con operatore, ad esempio i requisiti e la pianificazione della distribuzione.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257539"
---
# <a name="plan-for-operator-connect-conferencing"></a>Pianificare le conferenze Connessione con operatore conferenza

Le audioconferenze Microsoft forniscono la possibilità di accedere a una conferenza telefonica ed effettuare chiamate in uscita da una conferenza usando numeri di telefono PSTN (Public Switched Telephone Network).  I partecipanti a Microsoft Teams riunioni con un bridge di audioconferenza.

Con Connessione con operatore conferencing, le organizzazioni possono usare i numeri di telefono di un operatore di terze parti per partecipare a Microsoft Teams riunioni. Se l'attuale operatore fa parte del programma Microsoft Connessione con operatore, è possibile aggiungere i numeri di telefono dell'operatore al bridge di audioconferenza e usarli per partecipare alle riunioni.

Senza Connessione con operatore di conferenza telefonica, le organizzazioni possono usare solo i numeri di telefono forniti da Microsoft per il bridge di audioconferenza.

>[!NOTE]
>Un provider di numeri di telefono che fa parte del programma Microsoft Connessione con operatore viene indicato in questo articolo come "operatore".
>
>Per vedere se l'operatore partecipa al programma Microsoft Connessione con operatore, vedere la [directory Microsoft 365 Connessione con operatore.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)

Questo articolo descrive le conferenze Connessione con operatore conferenza:

- [Vantaggi](#benefits)
- [Requisiti di licenza e fatturazione](#licensing-requirements-and-billing)
- [Altre informazioni sui servizi di audioconferenza Microsoft](#additional-information-on-microsoft-audio-conferencing)

Per informazioni sulla configurazione delle conferenze Connessione con operatore, vedere [Configurare Connessione con operatore conferenza](operator-connect-conferencing-configure.md)telefonica.

Se alcuni utenti dell'organizzazione devono effettuare chiamate esterne ai numeri di telefono PSTN, è comunque necessario un piano per le chiamate. Per informazioni sull'uso di un operatore di terze parti per la connettività PSTN [esterna,](operator-connect-plan.md)vedere Pianificare Connessione con operatore .

## <a name="benefits"></a>Vantaggi

Connessione con operatore Conferencing offre i vantaggi seguenti:

- **Assegnazione flessibile dei numeri di telefono tra l'operatore e Microsoft.** Usare i numeri di telefono di Microsoft e dell'operatore (solo con un abbonamento a Microsoft Audio Conferencing Standard) oppure usare solo i numeri di telefono dell'operatore (solo con una licenza di conferenza Connessione con operatore).

- **Infrastruttura gestita dall'operatore.**   Il tuo operatore gestisce i Session Border Controller (SBC) e l'interconnessione con Microsoft, risparmiandoti dagli acquisti e dalla gestione aggiuntivi dell'hardware.

- **Distribuzione più rapida e semplice.**   Connettersi rapidamente all'operatore e assegnare numeri di telefono al bridge di audioconferenza dall'Teams di amministrazione.

- **Supporto e affidabilità migliorati.**   Gli operatori forniscono supporto tecnico e contratti di servizio condivisi per migliorare il supporto dei servizi e il peering diretto basato su Azure crea una connessione di rete uno-a-uno per migliorare l'affidabilità.

Connessione con operatore conferencing potrebbe essere la soluzione giusta per l'organizzazione se:

- Si vogliono mantenere **i contratti con** il provider di numeri di telefono esistente

- Si vuole espandere **la copertura globale del** bridge di audioconferenza Microsoft esistente

- Si vogliono ottenere **numeri di telefono per le audioconferenze** da un nuovo provider di numeri di telefono

- **I servizi di audioconferenza Microsoft non sono disponibili nella posizione geografica dell'utente**

- Si vuole sfruttare un **operatore** per i servizi di audioconferenza con un modello di pagamento al minuto, ad esempio usare numeri verde ed effettuare chiamate in uscita da riunioni Teams a numeri di telefono in paesi non inclusi nell'abbonamento

## <a name="licensing-requirements-and-billing"></a>Requisiti di licenza e fatturazione

Gli utenti che devono Connessione con operatore i numeri di conferenza per partecipare alle riunioni che organizzano devono avere un abbonamento a Microsoft Audio Conferencing Standard o una licenza Di conferenza di Microsoft Connessione con operatore assegnata.

### <a name="audio-conferencing-standard-subscription"></a>Abbonamento a Audio Conferencing Standard

Un abbonamento a Microsoft Audio Conferencing Standard può essere acquistato come componente aggiuntivo per una licenza di Microsoft Teams ed è incluso anche negli abbonamenti Microsoft 365 E5 e Office 365 E5 audio.

L'abbonamento a Audio Conferencing Standard consente agli abbonati di usare i numeri di telefono di Microsoft ed espandere i bridge di audioconferenza con i numeri di un operatore. Gli abbonati possono anche decidere quali chiamate in uscita Teams riunioni da instradare tramite Microsoft e quali chiamate instradare tramite un operatore.

Per altre informazioni, vedere [**Configurare Connessione con operatore conferenza**](operator-connect-conferencing-configure.md).

### <a name="operator-connect-conferencing-license"></a>Connessione con operatore conferenza telefonica

Una licenza di Connessione con operatore Conferencing di Microsoft può essere acquistata come componente aggiuntivo per una licenza Microsoft Teams conferenza.

La Connessione con operatore conferencing consente agli abbonati di usare i numeri di telefono di un operatore, ma non include i numeri di telefono di Microsoft. Tutte le chiamate in uscita Teams riunioni devono essere instradati tramite un operatore.

Per altre informazioni, vedere [**Configurare Connessione con operatore conferenza**](operator-connect-conferencing-configure.md).

>[!Note]
>Per partecipare a una riunione organizzata da un utente con funzionalità di Connessione con operatore Conferencing, i partecipanti alla riunione non richiedono una licenza di audioconferenza Standard Subscription o una licenza Connessione con operatore Conferencing.

Con Connessione con operatore Conferencing, Microsoft fattura l'organizzazione in base al tipo di licenza di audioconferenza usata dall'organizzazione, ai servizi di audioconferenza Microsoft o alle conferenze Connessione con operatore e all'uso di qualsiasi numero di telefono fornito da Microsoft.

L'operatore addebita all'organizzazione l'uso Connessione con operatore numeri di conferenza che forniscono.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Altre informazioni sui servizi di audioconferenza Microsoft

I servizi di audioconferenza Microsoft consentono ai partecipanti di partecipare a Microsoft Teams riunioni tramite accesso esterno con un numero di telefono PSTN o tramite chiamata in uscita a un numero di telefono PSTN. Per altre informazioni sulle funzionalità di audioconferenza Microsoft disponibili per l'organizzazione, vedere [Audioconferenza in Microsoft 365](audio-conferencing-in-office-365.md).
