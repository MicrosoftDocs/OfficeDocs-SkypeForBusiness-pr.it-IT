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
ms.openlocfilehash: ed0e5aa3a39147238bf0ade57df509a31f0f13e8
ms.sourcegitcommit: 7579dda8018691eb1a724cb0311b53333dc3ae5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2021
ms.locfileid: "53142812"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Panoramica sui controlli dei criteri di Microsoft Teams

Microsoft si impegna a fornire le informazioni e i controlli necessari per scegliere le modalità di raccolta e utilizzo dei dati quando si usa Microsoft Teams, incluso in Microsoft 365.

Questo articolo ha lo scopo di fornire informazioni sui controlli per la privacy per le aree seguenti:

- **Dati di diagnostica** che vengono raccolti e inviati a Microsoft sul software client di Office in uso nei computer che eseguono Teams e Office all'interno della propria organizzazione.
- **Esperienze connesse** che usano funzionalità basate sul cloud per offrire funzionalità avanzate di Teams e Office agli utenti.

Nell'ambito di queste modifiche, nell'interfaccia utente vengono introdotti nuovi elementi e nuove impostazioni dei criteri.

> [!IMPORTANT]
> Per ulteriori letture, consultare [Panoramica dei controlli della privacy per Microsoft 365 Apps for enterprise](/deployoffice/privacy/overview-privacy-controls).

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

Per visualizzare un elenco degli eventi dei dati di diagnostica obbligatori necessari e delle relative proprietà, vedere gli articoli seguenti:

- [Dati di diagnostica necessari per dispositivo mobile di Microsoft Teams](policy-control-diagnostic-data-mobile.md)
- [Dati di diagnostica necessari per la versione desktop di Microsoft Teams](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Dati di diagnostica inviati da Teams a Microsoft

Questi dati di diagnostica raccolti e inviati a Microsoft riguardano il software Teams in uso su computer che eseguono Windows all'interno della propria organizzazione.

Esistono tre livelli di dati di diagnostica per il software Teams tra cui è possibile scegliere:

- **Obbligatorio** I dati minimi necessari per mantenere Office sicuro, aggiornato e correttamente funzionante nel dispositivo sono installati. 
- **Facoltativo** Dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi.
- **Nessuno** Nessun dato diagnostico sul software Teams in esecuzione nel dispositivo dell’utente viene raccolto o inviato a Microsoft. Questa opzione, tuttavia, limita in modo significativo la possibilità di rilevare, diagnosticare e risolvere i problemi che gli utenti potrebbero riscontrare durante l’uso di Teams.

I dati di diagnostici necessari possono includere, ad esempio, informazioni sulla versione del client di Teams installata nel dispositivo, o informazioni che indicano che Teams si arresta in modo anomalo quando si prova a partecipare alle riunioni. I dati di diagnostica facoltativi possono includere informazioni sul tempo necessario per avviare una telefonata, che potrebbero indicare un problema relativo alla connettività o alle prestazioni della rete.

Se si sceglie di inviare i dati di diagnostica facoltativi, saranno inclusi anche i dati indispensabili.

Come amministratori della propria organizzazione, sarà possibile utilizzare un'impostazione di criterio per scegliere il livello di dati di diagnostica da inviare a Microsoft. I dati di diagnostica facoltativi verranno inviati a Microsoft se non si modificano le impostazioni. I dati di diagnostica facoltativi consentono al team di progettazione di Office a Microsoft di rilevare, diagnosticare e ridurre in modo più efficiente i problemi e attenuare il loro impatto sulla propria organizzazione. 

Per scegliere il livello di dati di diagnostica che ci viene inviato, utilizzare il [servizio criteri cloud di Office](/deployoffice/overview-office-cloud-policy-service) e configurare l'impostazione dei criteri *Configura il livello dei dati di diagnostica del software client inviati da Office a Microsoft*. Si tratta della stessa impostazione dei criteri usata per configurare il livello di dati di diagnostica inviato da altre app di Office (ad esempio Word, Excel e PowerPoint) che sono incluse tra le app di Microsoft 365 Apps for enterprise.

I propri utenti non saranno in grado di modificare il livello di dati di diagnostica per i dispositivi, se si trovano connessi a Teams con le credenziali dell'organizzazione, a volte definita azienda o istituto di istruzione.

Questi dati di diagnostica non includono i nomi degli utenti, i loro messaggi di posta elettronica o altri contenuti utente quali file Office condivisi in Teams, un messaggio di chat in Teams o un testo di un post pubblicato in un canale di Teams. Il sistema crea un ID univoco che si associa ai dati di diagnostica degli utenti. Alla ricezione di dati di diagnostica che mostrano l’arresto anomalo di Teams per 100 volte, questo ID univoco consente di determinare se si tratta di un singolo utente che ha subito l’arresto anomalo dell’app per 100 ore o se si tratta di 100 utenti diversi che hanno subito l’arresto anomalo dell’app una sola volta. Microsoft non usa l'ID univoco per identificare un utente specifico.

Per visualizzare i dati di diagnostica inviati a Microsoft, è possibile usare il visualizzatore dati di diagnostica che può essere scaricato e installato da Microsoft Store. Per altre informazioni, vedere [Uso di Visualizzatore dati di diagnostica con Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).

> [!NOTE]
> Il supporto per il Visualizzatore dati di diagnostica è disponibile per Teams nei dispositivi che eseguono Android. Il supporto per Teams nei dispositivi che eseguono Windows, macOS o iOS è in fase di sviluppo.

## <a name="required-service-data-for-connected-experiences"></a>Dati di servizio obbligatori per le esperienze connesse

I dati di servizio obbligatori sono dati che consentono di fornire queste esperienze connesse basate sul cloud garantendo che siano sicure e correttamente funzionanti. È possibile scegliere di non offrire questa funzionalità agli utenti. In questo caso, le informazioni non saranno fornite a Microsoft per supportare la funzionalità delle esperienze connesse. Sono disponibili altre informazioni sui [dati di servizio necessari](/deployoffice/privacy/required-service-data).

## <a name="essential-services-for-microsoft-teams"></a>Servizi essenziali per Microsoft Teams

Esiste anche una serie di servizi che sono essenziali per il funzionamento di Microsoft 365 Apps for enterprise e non possono essere disabilitati. Ad esempio, il servizio gestione licenze che conferma che si dispone di una licenza per Microsoft 365 Apps for enterprise. I dati di servizio obbligatori su questi servizi vengono raccolti e inviati a Microsoft indipendentemente dalle altre impostazioni dei criteri configurate.

Per altre informazioni, vedere [Servizi essenziali per Office](/deployoffice/privacy/essential-services).