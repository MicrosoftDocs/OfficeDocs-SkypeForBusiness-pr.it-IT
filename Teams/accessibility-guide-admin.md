---
title: Guida all'accessibilità per gli amministratori di Microsoft Teams
ms.author: meghan
author: meganrmhan
ms.reviewer: eljones
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Migliorare l'accessibilità in Microsoft Teams attivando i sottotitoli e la trascrizione, fornendo l'accesso alle riunioni agli interpreti del linguaggio dei segni e ai sottotitoli CART, riducendo le distrazioni, migliorando la partecipazione e condividendo le risorse.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- M365-collaboration
ms.openlocfilehash: 7b089785695e9bef985107b5f1db8e5659c48c33
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614734"
---
# <a name="accessibility-guide-for-microsoft-teams-admins"></a>Guida all'accessibilità per gli amministratori di Microsoft Teams

L'amministratore di Microsoft Teams per l'organizzazione può contribuire a rendere l'ambiente di Teams il più inclusivo e accessibile possibile per tutti gli utenti. Seguire le guide e le risorse seguenti per configurare Microsoft Teams per un'accessibilità ottimale.

> [!NOTE]
> Molte delle opzioni di accessibilità sono attivate per impostazione predefinita, ma è possibile verificare che non siano state disattivate seguendo la procedura descritta in questa guida.

## <a name="turn-on-captions-and-transcription-for-meetings-and-calls"></a>Attivare i sottotitoli e la trascrizione per riunioni e chiamate

Creare riunioni e chiamate inclusive per gli utenti disabili in modo che tutti possano partecipare e contribuire.

### <a name="turn-on-live-captions-for-meetings"></a>Attivare i sottotitoli in tempo reale per le riunioni

I sottotitoli in tempo reale sono testo generato automaticamente in tempo reale di ciò che viene detto in una riunione. Vengono visualizzate alcune righe alla volta per un utente che le ha attivate e non vengono salvate.

Per attivare i sottotitoli in tempo reale per gli utenti:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** e quindi selezionare l'elenco a discesa **Criteri riunione**.

2. Selezionare il criterio da modificare.

3. Passare alla sezione **Partecipanti & guest** .

4. Impostare **Sottotitoli in tempo** reale su **Non abilitati, ma l'utente può eseguire l'override**.

5. Selezionare **Salva**.

> [!TIP]
> Condividere il collegamento seguente in modo che gli utenti possano imparare ad [attivare i sottotitoli in tempo reale durante le riunioni](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop).

> [!NOTE]
> I sottotitoli in tempo reale sono disponibili per le riunioni tenute in Commerciale e nelle organizzazioni U.S. Government Community Cloud (GCC).

### <a name="turn-on-transcription-for-calls"></a>Attivare la trascrizione per le chiamate

La trascrizione viene generata automaticamente, il testo registrato di ciò che è stato detto in una chiamata. Quando attivata, la trascrizione è disponibile per la revisione da parte degli utenti al termine di una chiamata.

Per attivare la trascrizione per gli utenti:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Voce** e quindi selezionare l'elenco a discesa **Criteri per le chiamate**.

2. Selezionare il criterio da modificare.

3. Imposta **Trascrizione** **su Attivato**, quindi seleziona **Salva**.

### <a name="why-captions-and-transcripts-are-important"></a>Perché le didascalie e le trascrizioni sono importanti

Le didascalie e le trascrizioni sono versioni testuali delle parole pronunciate da un utente. Offrono alle persone la possibilità di vedere il testo oltre all'audio o invece di solo. I sottotitoli sono utili anche per le persone non udenti o con problemi di udito, fornendo informazioni aggiuntive su ciò che alcuni utenti ricevono dall'interprete della lingua dei segni o dal sottotitolatore CART con cui potrebbero lavorare.

Le didascalie e la trascrizione sono utili in un'ampia gamma di situazioni, ma possono essere particolarmente utili per:

- Persone non udenti o con problemi di udito

- Persone con disabilità di apprendimento

- Persone che si trovano in un ambiente rumoroso o distratto e devono esaminare le informazioni condivise dopo la fine di una riunione

Per altre informazioni, vedere i collegamenti seguenti:

- [Impostazioni dei criteri riunione per la registrazione e la trascrizione](/Microsoftteams/meetings-policies-recording-and-transcription)

- [Linee guida per l'accessibilità dei contenuti Web (WCAG) 1.2.4.: Sottotitoli (live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

## <a name="give-meeting-access-to-sign-language-interpreters-and-cart-communication-access-real-time-translation-captioners"></a>Concedere l'accesso alle riunioni agli interpreti della lingua dei segni e ai sottotitoli CART (Communication Access Real-time Translation)

Fornire agli interpreti del linguaggio dei segni e ai sottotitoli CART (communication access real-time translation) l'accesso alle riunioni di Microsoft Teams in modo che possano lavorare in modo più efficace insieme agli utenti non udenti o con problemi di udito.

### <a name="admit-sign-language-interpreters-and-cart-captioners-to-meetings"></a>Ammettere interpreti del linguaggio dei segni e sottotitoli CART alle riunioni

Gli interpreti di lingue dei segni e i sottotitoli CART probabilmente non funzionano per l'organizzazione, ma è possibile invitarli alle riunioni di Microsoft Teams [concedendo loro l'accesso guest](/MicrosoftTeams/guest-access).

Dopo aver concesso l'accesso guest, per ammettere gli interpreti del linguaggio dei segni e i sottotitoli CART alle riunioni:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** e quindi selezionare l'elenco a discesa **Criteri riunione**.

2. Selezionare il criterio da modificare.

3. Passare alla sezione **Partecipanti & guest** .

4. Scegliere l'opzione in **Ammettere automaticamente le persone** più adatte ai requisiti di conformità e sicurezza dell'organizzazione. È possibile selezionare una delle opzioni seguenti:

   - Tutti (scelta non consigliata)

   - Persone dell'organizzazione e guest (scelta consigliata)

   - Utenti dell'organizzazione, organizzazioni attendibili e guest

   - Utenti dell’organizzazione

   - Solo organizzatore

   - Solo utenti invitati

5. Selezionare **Salva**.

> [!NOTE]
> L'impostazione **Ammettere automaticamente le persone** non si applica agli utenti che accedono all'accesso.

### <a name="turn-on-ip-video-feed-for-your-users"></a>Attivare il feed video IP per gli utenti

Offrire agli interpreti della lingua dei segni la possibilità di condividere feed video IP durante le riunioni di Microsoft Teams in modo che possano comunicare con utenti non udenti o con problemi di udito.

Per verificare se il feed video IP è attivato:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** e quindi selezionare l'elenco a discesa **Criteri riunione**.

2. Selezionare il criterio da modificare.

3. Passare alla sezione **Audio & video** .

4. Controlla che **video IP** **sia attivato,** quindi seleziona **Salva**.

> [!TIP]
> Condividere i collegamenti seguenti con gli utenti in modo che possano modificare il modo in cui usano Teams per massimizzare la loro capacità di partecipare, concentrarsi e collaborare alle riunioni:
> - [Personalizzare la visualizzazione della riunione](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)
> - [Usare i sottotitoli CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

### <a name="why-its-important-to-include-sign-language-interpreters-and-cart-captioners"></a>Perché è importante includere interpreti del linguaggio dei segni e sottotitoli CART

Alcuni utenti potrebbero preferire l'uso dei sottotitoli CART perché possono essere più accurati per specifici gergo, accenti e altro ancora rispetto ai sottotitoli generati automaticamente.

Gli utenti il cui metodo di comunicazione principale è il linguaggio dei segni, richiedono l'interpretazione del linguaggio dei segni, che richiede la presenza di un interprete umano.

Per ulteriori informazioni, vedere [Web Content Accessibility Guide (WCAG) 1.2.6.: Sign Language Interpretation](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded).

## <a name="reduce-distractions-in-meetings"></a>Ridurre le distrazioni nelle riunioni

Incoraggiare la partecipazione degli utenti attivando i filtri video per ridurre le distrazioni nelle riunioni di Teams.

### <a name="turn-on-video-filters"></a>Attivare i filtri video

I filtri video consentono di ridurre le distrazioni durante le riunioni.

Per attivare i filtri video:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** e quindi selezionare l'elenco a discesa **Criteri riunione**.

2. Selezionare il criterio da modificare.

3. Passare alla sezione **Condivisione del contenuto** .

4. Scegliere l'opzione in **Selezionare i filtri video** più adatti ai requisiti di conformità e sicurezza dell'organizzazione. Selezionare una delle opzioni seguenti:

   - Solo sfocatura dello sfondo

   - Sfocatura dello sfondo e immagini predefinite

   - Tutti i filtri

5. Selezionare **Salva**.

> [!TIP]
> Condividere i collegamenti seguenti in modo che gli utenti possano modificare le preferenze delle riunioni di Teams per ridurre le distrazioni:
> - [Modificare gli effetti dello sfondo nelle riunioni di Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)
> - [Ridurre il rumore di fondo nelle riunioni di Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

### <a name="why-its-helpful-to-reduce-distractions"></a>Perché è utile ridurre le distrazioni

Alcune persone dell'organizzazione potrebbero avere difficoltà a concentrarsi durante le videochiamate e le chiamate a causa di movimenti, luce e altre distrazioni negli sfondi dei partecipanti. L'uso dei filtri video consente agli utenti di controllare le distrazioni e partecipare completamente.

*Gli effetti sfondo* possono aiutare gli utenti a concentrarsi sull'altoparlante anziché sullo sfondo dell'altoparlante. Microsoft Teams ha una raccolta di sfondi e gli utenti possono anche caricare i propri.

*La sfocatura dello sfondo* consente di migliorare la visibilità e la messa a fuoco durante le riunioni o le chiamate perché riduce le distrazioni in background, ma mantiene gli utenti a fuoco.

I filtri video sono utili in un'ampia gamma di situazioni, ma possono essere particolarmente utili per:

- Persone neurodiverse

- Persone non udenti o con problemi di udito

Per altre informazioni, vedere [Web Content Accessibility Guideline (WCAG) 1.4.8.: Visual Presentation](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html).

## <a name="improve-participation-in-microsoft-teams-meetings"></a>Migliorare la partecipazione alle riunioni di Microsoft Teams

Incoraggiare la partecipazione degli utenti con più opzioni di controllo e flessibilità attivando **chat nelle riunioni** e criteri di messaggistica come la modifica della chat, **Strumento di lettura immersiva** ed emoji.

### <a name="turn-on-chat-in-meetings"></a>Attivare la chat nelle riunioni

La chat rende più semplice per molti utenti porre domande o aggiungere informazioni nelle riunioni di Teams.

Per verificare se la chat in riunione è attivata:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** e quindi selezionare l'elenco a discesa **Criteri riunione**.

2. Selezionare il criterio da modificare.

3. Passare alla sezione **Partecipanti & guest** .

4. Scegliere l'opzione **in Chatta nelle riunioni** più adatta ai requisiti di conformità e sicurezza dell'organizzazione. È possibile selezionare una delle opzioni seguenti:

   - Attivala per tutti gli utenti (scelta consigliata)

   - Disattivala per tutti (scelta non consigliata)

   - Attivarlo per tutti gli utenti tranne gli utenti anonimi

5. Selezionare **Salva**.

### <a name="use-messaging-policies-for-increased-flexibility-and-control"></a>Usare i criteri di messaggistica per una maggiore flessibilità e controllo

Le opzioni di chat flessibili consentono a molti utenti di comprendere più facilmente i messaggi degli altri, rivedere i propri messaggi ed esprimere se stessi.

Per verificare se queste opzioni di chat flessibili sono attivate:

**Nell'interfaccia di amministrazione di Microsoft Teams**:

1. Nell'interfaccia di amministrazione di Microsoft Teams passare a **Criteri di messaggistica**.

2. Selezionare il criterio da modificare.

3. Verificare che gli elementi seguenti **siano attivati**:

   - **Elimina i messaggi inviati**

   - **Modifica i messaggi inviati**

   - **Chat**

   - **Giphy nelle conversazioni**

   - **Meme nelle conversazioni**

   - **Adesivi nelle conversazioni**

   - **Anteprime degli URL**

   - **Tradurre messaggi**

   - **Strumento di lettura immersiva per i messaggi**

4. Selezionare **Salva**.

> [!TIP]
> Condividere il collegamento [su come scrivere testo alternativo efficace](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2) con l'organizzazione per aiutare gli utenti a comprendere i messaggi non di testo condivisi in chat.

### <a name="why-alternate-participation-options-matter"></a>Perché le opzioni di partecipazione alternative sono importanti

Le opzioni di chat flessibili offrono agli utenti una maggiore flessibilità nell'uso dei contenuti della chat durante la riunione e un maggiore controllo sul modo in cui partecipano a una riunione con la chat.

*La chat all'interno della riunione* offre alle persone un altro modo per partecipare alla discussione della riunione. Per alcune persone con disabilità, la chat potrebbe essere preferibile alla lingua vocale o dei segni come modo per contribuire alle discussioni delle riunioni.

*Strumento di lettura immersiva*, uno strumento progettato per le persone affette da dislessia e dislessia, semplifica la comprensione del testo. Include anche la traduzione in linea per le persone che preferiscono comunicare in una lingua diversa. Ecco alcune delle caratteristiche principali di Strumento di lettura immersiva:

- Aggiunta dell'opzione per la lettura ad alta voce del contenuto

- Modifica delle dimensioni del testo e del colore di sfondo

- Suddividere le parole in sillabe

- Aumentare lo spazio tra le lettere

- Evidenziazione di una o più righe di testo

- Evidenziare parti del discorso

Le opzioni di chat flessibili sono utili in un'ampia gamma di situazioni, ma possono essere particolarmente utili per:

- Persone non vedenti o ipovedenti

- Persone neurodiverse (ad esempio dislessia o dislessia)

Per ulteriori informazioni, vedere [Web Content Accessibility Guidelines (WCAG) 1.1.1.: Text Alternatives](https://www.w3.org/TR/WCAG21/#text-alternatives).

## <a name="share-resources-with-users-to-further-accessibility-awareness"></a>Condividere risorse con gli utenti per una maggiore consapevolezza dell'accessibilità

Esistono altri passaggi che gli utenti possono eseguire per migliorare la loro esperienza di accessibilità. Condividere i collegamenti seguenti con l'organizzazione e gli utenti guest.

### <a name="reference-links"></a>Collegamenti di riferimento

L'Answer Desk per l'accessibilità di Microsoft include guide per l'utente finale per personalizzare la propria esperienza in base alle esigenze di accessibilità:

- [Attivare i sottotitoli in tempo reale durante le riunioni](https://support.microsoft.com/office/use-live-captions-in-a-teams-meeting-4be2d304-f675-4b57-8347-cbd000a21260#ID0EBD=Desktop)

- [Personalizzare la visualizzazione della riunione](https://support.microsoft.com/office/customize-your-meeting-view-95aaeaf8-0f22-46cf-a6f9-34ca9b04a1b2)

- [Usare i sottotitoli CART](https://support.microsoft.com/office/use-cart-captions-in-a-microsoft-teams-meeting-human-generated-captions-2dd889e8-32a8-4582-98b8-6c96cf14eb47#:~:text=Use%20CART%20captions%20in%20a%20Microsoft%20Teams%20meeting,out%20of%20your%20captions.%20...%204%20See%20also)

- [Modificare gli effetti dello sfondo nelle riunioni di Teams](https://support.microsoft.com/office/change-your-background-for-a-teams-meeting-f77a2381-443a-499d-825e-509a140f4780#ID0EDD=Desktop)

- [Ridurre il rumore di fondo nelle riunioni di Teams](https://support.microsoft.com/office/reduce-background-noise-in-teams-meetings-1a9c6819-137d-4b3b-a1c8-4ab20b234c0d)

- [Scrivere testo alternativo efficace](https://support.microsoft.com/office/everything-you-need-to-know-to-write-effective-alt-text-df98f884-ca3d-456c-807b-1a1fa82f5dc2)

- [Strumenti di accessibilità per Microsoft Teams](https://support.microsoft.com/office/accessibility-tools-for-microsoft-teams-2d4009e7-1300-4766-87e8-7a217496c3d5?ui=en-us&rs=en-us&ad=us)

### <a name="reference-web-content-accessibility-guidelines-wcag"></a>Linee guida di riferimento per l'accessibilità del contenuto Web (WCAG)

WCAG è una serie di standard internazionali progettati per migliorare l'accessibilità Web. Il criterio di successo a cui si fa riferimento in questa guida include:

- [WCAG 1.2.4.: Sottotitoli (live)](https://www.w3.org/WAI/WCAG21/Understanding/captions-live)

- [WCAG 1.2.6.: interpretazione del linguaggio dei segni](https://www.w3.org/TR/WCAG21/#sign-language-prerecorded)

- [WCAG 1.4.8.: Presentazione visiva](https://www.w3.org/WAI/WCAG21/Understanding/visual-presentation.html)

- [WCAG 1.1.1.: Alternative testuali](https://www.w3.org/TR/WCAG21/#text-alternatives)
