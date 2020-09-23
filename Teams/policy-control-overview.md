---
title: Panoramica sui controlli dei criteri di Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Panoramica dei controlli dei criteri per Microsoft teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136044"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Panoramica sui controlli dei criteri di Microsoft Teams

Microsoft si impegna a fornire le informazioni e i controlli necessari per scegliere le modalità di raccolta e utilizzo dei dati quando si usa Microsoft Teams, incluso in Microsoft 365.

Questo articolo ha lo scopo di fornire informazioni sui controlli per la privacy per le aree seguenti:

- **Dati di diagnostica** che vengono raccolti e inviati a Microsoft sul software client di Office in uso nei computer che eseguono Teams e Office all'interno della propria organizzazione.
- **Esperienze connesse** che usano funzionalità basate sul cloud per offrire funzionalità avanzate di Teams e Office agli utenti.

Nell'ambito di queste modifiche, nell'interfaccia utente vengono introdotti nuovi elementi e nuove impostazioni dei criteri.

> [!IMPORTANT]
> Per altre informazioni, vedere la sezione della [Panoramica sui controlli dei criteri](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls) relativa a M365.

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Dati di diagnostica inviati da Microsoft 365 Apps for enterprise a Microsoft

I dati di diagnostica sono usati per:

- Mantenere Teams sicuro e aggiornato.
- Individuare, diagnosticare e risolvere i problemi.
- Migliorare il prodotto.

Alcuni esempi dei dati raccolti includono:

- Lingua dell'applicazione
- Tipo di utente
- Versione del sistema operativo

## <a name="clients-that-adhere-to-diagnostic-controls"></a>Client che aderiscono ai controlli diagnostici

I client seguenti sono sottoposti ai controlli diagnostici e inviano dati:

- iOS
- Android
- Desktop (solo il componente che usa l'API win32)

Per i dati diagnostica per dispositivi mobili necessari, vedere [Controlli dei criteri dei dati di diagnostica per dispositivi mobili](policy-control-diagnostic-data-mobile.md).

Per i dati diagnostica desktop necessari, vedere [Controlli dei criteri dei dati di diagnostica desktop](policy-control-diagnostic-data-desktop.md).

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Dati di diagnostica inviati da Teams a Microsoft

Questi dati di diagnostica raccolti e inviati a Microsoft riguardano il software Teams in uso su computer che eseguono Windows all'interno della propria organizzazione.

Esistono tre livelli di dati di diagnostica per il software Teams tra cui è possibile scegliere:

- **Obbligatorio** I dati minimi necessari per mantenere Office sicuro, aggiornato e correttamente funzionante nel dispositivo sono installati. 
- **Facoltativo** Dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.
- **Nessuno** Nessun dato diagnostico sul software Teams in esecuzione nel dispositivo dell’utente viene raccolto o inviato a Microsoft. Questa opzione, tuttavia, limita in modo significativo la possibilità di rilevare, diagnosticare e risolvere i problemi che gli utenti potrebbero riscontrare durante l’uso di Teams.

I dati di diagnostici necessari possono includere, ad esempio, informazioni sulla versione del client di Teams installata nel dispositivo, o informazioni che indicano che Teams si arresta in modo anomalo quando si prova a partecipare alle riunioni. I dati di diagnostica facoltativi possono includere informazioni sul tempo necessario per avviare una telefonata, che potrebbero indicare un problema relativo alla connettività o alle prestazioni della rete.

Se si sceglie di inviare i dati di diagnostica facoltativi, saranno inclusi anche i dati indispensabili.

Come amministratori della propria organizzazione, sarà possibile utilizzare un'impostazione di criterio per scegliere il livello di dati di diagnostica da inviare a Microsoft. I dati di diagnostica facoltativi verranno inviati a Microsoft se non si modificano le impostazioni. I dati di diagnostica facoltativi consentono al team di progettazione di Office a Microsoft di rilevare, diagnosticare e ridurre in modo più efficiente i problemi e attenuare il loro impatto sulla propria organizzazione.

I propri utenti non saranno in grado di modificare il livello di dati di diagnostica per i dispositivi, se si trovano connessi a Teams con le credenziali dell'organizzazione, a volte definita azienda o istituto di istruzione.

Tali dati diagnostici non includono i nomi degli utenti, il proprio indirizzo di posta elettronica o il contenuto dei file di Office. Il sistema crea un ID univoco che si associa ai dati di diagnostica degli utenti. Alla ricezione di dati di diagnostica che mostrano l’arresto anomalo di Teams per 100 volte, questo ID univoco consente di determinare se si tratta di un singolo utente che ha subito l’arresto anomalo dell’app per 100 ore o se si tratta di 100 utenti diversi che hanno subito l’arresto anomalo dell’app una sola volta. Microsoft non usa l'ID univoco per identificare un utente specifico.

## <a name="required-service-data-for-connected-experiences"></a>Dati di servizio obbligatori per le esperienze connesse

I dati di servizio obbligatori sono dati che consentono di fornire queste esperienze connesse basate sul cloud garantendo che siano sicure e correttamente funzionanti. I dati di servizio obbligatori comprendono tre tipi di informazioni.

- **Contenuto dei clienti**, ovvero contenuto creato con Office dagli utenti, ad esempio il testo digitato in un documento di Word.
- **Dati funzionali**, che includono le informazioni necessarie alle esperienze connesse per eseguire le attività, ad esempio informazioni di configurazione dell'app.
- **Dati di diagnostica del servizio**, ovvero i dati necessari per mantenere il servizio sicuro, aggiornato e garantire le prestazioni ottimali previste. Poiché questi dati sono strettamente correlati all'esperienza connessa, sono separati dai livelli di dati di diagnostica indispensabili o facoltativi.

È possibile scegliere di non offrire questa funzionalità agli utenti. In questo caso, le informazioni non saranno fornite a Microsoft per supportare la funzionalità delle esperienze connesse. Sono disponibili altre informazioni sui [dati di servizio necessari](https://docs.microsoft.com/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Servizi essenziali per Microsoft Teams

Esiste anche una serie di servizi che sono essenziali per il funzionamento di Microsoft 365 Apps for enterprise e non possono essere disabilitati. Ad esempio, il servizio gestione licenze che conferma che si dispone di una licenza per Microsoft 365 Apps for enterprise. I dati di servizio obbligatori su questi servizi vengono raccolti e inviati a Microsoft indipendentemente dalle altre impostazioni dei criteri configurate.

Per altre informazioni, vedere [Servizi essenziali per Office](https://docs.microsoft.com/deployoffice/privacy/essential-services).
