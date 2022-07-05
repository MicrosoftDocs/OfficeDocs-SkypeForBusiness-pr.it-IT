---
title: Configurare un operatore automatico per Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
description: Informazioni su come configurare e gestire gli operatori automatici in Microsoft Teams.
ms.openlocfilehash: 384c7aae5e11c938a6bf8ab5f82924d0379a83aa
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616112"
---
# <a name="set-up-an-auto-attendant"></a>Configurare un operatore automatico

Gli operatori automatici consentono alle persone di chiamare la tua organizzazione e di navigare in un sistema di menu per parlare con il reparto, la coda di chiamata, la persona o un operatore giusto. È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams o con PowerShell.

Assicurarsi di aver letto [Piano per gli operatori automatici e le code di chiamata di Teams](plan-auto-attendant-call-queue.md) e di aver seguito i [passaggi iniziali](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure in questo articolo.

Gli operatori automatici possono indirizzare le chiamate, in base all'input dei chiamanti, a una delle seguenti destinazioni:

- **Operatore** - l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come una qualsiasi delle altre destinazioni in questo elenco.
- **Persona dell'organizzazione** : una persona dell'organizzazione che può ricevere chiamate vocali. Questa persona può essere un utente online o un utente ospitato in locale usando Skype for Business Server.
- **App vocale** : un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
- **Segreteria telefonica** : la cassetta postale vocale associata a un gruppo di Microsoft 365 specificata. È possibile scegliere se si vogliono le trascrizioni della segreteria telefonica e "Lascia un messaggio dopo il tono". richiesta di sistema.
  - In M365 Amministrazione Center abilitare l'opzione "Consenti agli utenti esterni all'organizzazione di inviare un messaggio di posta elettronica al team" per il gruppo di Microsoft 365 specificato
- **Numero di telefono esterno** : qualsiasi numero di telefono. Vedere [i dettagli tecnici sul trasferimento esterno](create-a-phone-system-auto-attendant.md?tabs=additional-resources).
- **Annuncio (file audio):** riprodurre un file audio. Messaggio di annuncio registrato che viene caricato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere di dimensioni superiori a 5 MB. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.
- **Annuncio (digitato):** digitare un messaggio. Testo che si desidera venga letto dal sistema. È possibile immettere fino a 1000 caratteri. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.

La procedura per aggiungere un operatore automatico è:

1. Configurare le informazioni generali.
1. Configurare un flusso delle chiamate di base.
1. Configurare un flusso delle chiamate fuori orario.
1. Impostare i flussi delle chiamate per le festività.
1. Configurare l'ambito di chiamata.
1. Configurare gli account delle risorse.

I passaggi descritti nell'articolo creano operatori automatici con l'interfaccia di amministrazione di Teams. Per istruzioni su **come creare operatori automatici con PowerShell**, vedi [Creazione di operatori automatici con i cmdlet di PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Segui questi passaggi per configurare l'operatore automatico

# <a name="step-1-general-info"></a>[Passaggio 1: Informazioni generali](#tab/general-info)

## <a name="step-1-set-the-auto-attendants-general-information"></a>Passaggio 1: impostare le informazioni generali dell'operatore automatico

Per configurare un operatore automatico, [nell'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) espandi **Voce**, seleziona **Operatori automatici** e quindi **aggiungi**.

1. Digita un nome per l'operatore automatico nella casella in alto.

2. Per designare un operatore, specificare la destinazione per le chiamate all'operatore. Questa designazione è facoltativa ma consigliata. Impostare l'opzione **Operatore** per consentire ai chiamanti di uscire dai menu e parlare con una persona designata.

3. Specifica il fuso orario per questo operatore automatico. Il fuso orario viene usato per calcolare l'orario di ufficio se si [crea un flusso di chiamata separato per l'orario di chiusura](?tabs=after-hours).

4. Specifica una [lingua supportata](create-a-phone-system-auto-attendant-languages.md) per questo operatore automatico. Questo è il linguaggio che verrà utilizzato per i comandi vocali generati dal sistema.

5. Scegli se abilitare gli input vocali. Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale. Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure "Vendite" per selezionare l'opzione di menu denominata "Vendite".

   > [!NOTE]
   > Se si sceglie una lingua nel passaggio 4 che non supporta gli input vocali, questa opzione verrà disabilitata.

Dopo aver impostato le informazioni generali dell'operatore automatico, seleziona **Avanti**.

# <a name="step-2-basic-call-flow"></a>[Passaggio 2: Flusso delle chiamate di base](#tab/call-flow)

## <a name="step-2-set-up-the-basic-call-flow"></a>Passaggio 2: Configurare il flusso delle chiamate di base

### <a name="set-a-greeting"></a>Impostare un messaggio di saluto

- Se si seleziona **Riproduci file audio** , è possibile usare il pulsante **Carica file** per caricare un messaggio di saluto registrato salvato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere di dimensioni superiori a 5 MB.

- Se selezioni **Digita un messaggio di saluto** , il sistema leggerà il testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

### <a name="route-the-call"></a>Instradare la chiamata

- Se selezioni **Disconnetti**, l'operatore automatico riaggancia la chiamata.
- Se selezioni **Reindirizza chiamata**, puoi scegliere una delle destinazioni per il routing delle chiamate.
- Se si seleziona **Riproduci opzioni menu**, è possibile scegliere **Riproduci file audio** o **Digitare un messaggio di saluto** e quindi scegliere tra le opzioni di menu e la ricerca nella directory.

#### <a name="play-menu-options"></a>Opzioni del menu Riproduci

Per le opzioni di chiamata, assegnare i tasti da 0 a 9 sulla tastiera del telefono a una delle destinazioni di instradamento delle chiamate. I tasti \* (asterisco) e \# (cancelletto) sono riservati dal sistema e non possono essere riassegnati. Premendo uno di questi tasti verrà ripetuto il menu corrente.

> [!NOTE]
> Il tasto # esegue solo il backup dell'operatore automatico più recente. Una volta superato il limite di un nuovo operatore automatico, il tasto # non sarà in grado di portarti a quello precedente.

I mapping dei tasti non devono necessariamente essere continui. È possibile creare un menu con i tasti 0, 1 e 3 associati a opzioni, mentre il tasto numero 2 non viene usato.

Se ne hai configurato uno, ti consigliamo di associare il tasto zero all'operatore. Se l'operatore non è impostato su alcun tasto, viene disabilitato anche il comando vocale "Operatore".

Per ogni opzione di menu, specificare le impostazioni seguenti:

- **Tasto componi** : il tasto sulla tastiera del telefono per accedere a questa opzione. Se sono disponibili input vocali, i chiamanti possono anche pronunciare questo numero per accedere all'opzione.

- **Comando vocale** : definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati. Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e sedi". Ad esempio, il chiamante può premere 2, dire "due" o "Vendite" per selezionare l'opzione mappata ai due tasti. Questo testo viene anche visualizzato tramite sintesi vocale per la richiesta di conferma del servizio, che potrebbe essere qualcosa di simile a "Trasferimento della chiamata alle vendite".

- **Reindirizza a** : la destinazione di instradamento delle chiamate usata quando i chiamanti scelgono questa opzione. Se stai reindirizzando a un operatore automatico o a una coda di chiamata, scegli l'account della risorsa associato.

##### <a name="directory-search"></a>Ricerca nella directory

Se si assegnano tasti di chiamata alle destinazioni, è **consigliabile scegliere Nessuno** per **la ricerca nella directory**. Se un chiamante tenta di comporre un nome o un'estensione usando chiavi assegnate a destinazioni specifiche, potrebbe essere instradato in modo imprevisto a una destinazione prima di completare l'immissione del nome o dell'estensione. Ti consigliamo di creare un operatore automatico separato per la ricerca in elenco e di disporre del collegamento principale dell'operatore automatico con un tasto di chiamata.

Se non hai assegnato i tasti di chiamata, scegli un'opzione per **la ricerca nella directory**.

**Chiamata per nome** : se si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server, è un utente idoneo e può essere trovato con Chiamata per nome.

**Chiamata per estensione** - Se si abilita questa opzione, i chiamanti possono connettersi con gli utenti dell'organizzazione componendo l'interno del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale usando Skype for Business Server, è un utente idoneo e può essere trovato con **Chiamata per estensione**. È possibile impostare chi è o non è incluso nella directory nella pagina [Ambito](?tabs=dial-scope) chiamata.

> [!NOTE]
> Se desideri utilizzare sia le funzionalità **Chiamata per nome** che Chiamata per **estensione** , puoi assegnare un tasto di chiamata sull'operatore automatico principale per raggiungere un operatore automatico abilitato per **Chiamata per nome**. All'interno di quell'operatore automatico, puoi assegnare il tasto 1 (che non ha lettere associate) per raggiungere l'operatore automatico **Dial by extension** .

Per ulteriori informazioni, consulta Il riferimento di [chiamata e la voce](dial-voice-reference.md).

Dopo aver impostato le opzioni di base per il flusso delle chiamate, selezionare **Avanti**.

# <a name="step-3-after-hours-call-flow"></a>[Passaggio 3: Flusso delle chiamate fuori orario](#tab/after-hours)

## <a name="step-3-set-up-call-flow-for-after-hours-optional"></a>Passaggio 3: Configurare il flusso delle chiamate per fuori orario (facoltativo)

L'orario di ufficio può essere impostato per ogni operatore automatico.

- Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito.
- L'orario di ufficio può essere impostato con interruzioni durante il giorno e tutti gli orari che non sono impostati come orario di ufficio vengono considerati fuori orario.
- È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per l'orario di chiusura.

A seconda di come hai configurato gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo il routing delle chiamate fuori orario per gli operatori automatici con numeri di telefono diretti.

Se si vuole separare il routing delle chiamate per i chiamanti in orario di chiusura, specificare l'orario di ufficio per ogni giorno.

1. Accanto al giorno della settimana nella tabella, modificare le date **Di inizio a** e **Fine a** .
1. Se necessario, seleziona **Aggiungi nuovo orario** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.
1. Scegliere le opzioni di routing delle chiamate per fuori orario. Le stesse opzioni generali per il flusso delle chiamate sono disponibili anche per le chiamate fuori orario.

Dopo aver aggiunto il flusso delle chiamate fuori orario, seleziona **Avanti**.

# <a name="step-4-holiday-call-flow"></a>[Passaggio 4: Flusso delle chiamate natalizie](#tab/holidays)

## <a name="step-4-set-up-call-flows-for-holidays-optional"></a>Passaggio 4: Configurare i flussi delle chiamate per le festività (facoltativo)

L'operatore automatico può avere un flusso delle chiamate per ogni [festività configurata](set-up-holidays-in-teams.md). È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina Impostazioni chiamata festività seleziona **Aggiungi**.

1. Digitare un nome per l'impostazione delle festività.

1. Nell'elenco a discesa **Festività** scegliere la festività da usare.

1. Scegliere il tipo di messaggio di saluto da usare.

1. Scegliere se **disconnettere** o **reindirizzare** la chiamata.

    1. Se si sceglie di reindirizzare, scegliere la destinazione del routing delle chiamate per la chiamata.
    1. Se scegli di riprodurre le opzioni del menu, configura le **opzioni del menu Riproduci**.

1. Selezionare **Salva**.

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

Dopo aver aggiunto tutte le ore di festività, selezionare **Avanti**.

# <a name="step-5-dial-scope"></a>[Passaggio 5: Ambito di chiamata](#tab/dial-scope)

## <a name="step-5-set-up-dial-scope-optional"></a>Passaggio 5: Configurare l'ambito di chiamata (facoltativo)

*L'ambito di chiamata* definisce quali utenti sono disponibili nella directory quando un chiamante usa l'opzione di chiamata per nome o dial-by-extension. Il valore predefinito **Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online o ospitati in locale tramite Skype for Business Server.

È possibile includere o escludere utenti specifici selezionando **Gruppo di utenti personalizzati** in **Includi** o **Escludi** e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di chiamata.

Se un utente è presente in entrambi gli elenchi, verrà escluso dalla directory.

> [!NOTE]
> Potrebbero essere richieste fino a 36 ore prima che il nome di un nuovo utente sia elencato nella directory.

Dopo aver selezionato le opzioni **dell'ambito di chiamata** , selezionare **Avanti**.

# <a name="step-6-resource-accounts"></a>[Passaggio 6: Account delle risorse](#tab/resource-accounts)

## <a name="step-6-set-up-resource-accounts-optional"></a>Passaggio 6: Configurare gli account delle risorse (facoltativo)

Tutti gli operatori automatici devono avere un account di risorse associato.  Gli operatori automatici di primo livello avranno bisogno di almeno un account di risorse con un numero di servizio associato. Se lo desideri, puoi assegnare diversi account di risorse a un operatore automatico, ognuno con un numero di servizio separato.

Per aggiungere un account della risorsa, selezionare **Aggiungi account** e cercare l'account da aggiungere. Seleziona **Aggiungi** e quindi **Aggiungi**.

Dopo aver aggiunto gli account delle risorse, selezionare **Avanti**.

Per altre informazioni, vedere [Gestire gli account delle risorse di Teams](manage-resource-accounts.md) .

---

## <a name="resources-for-complex-scenarios"></a>Risorse per scenari complessi

### <a name="external-phone-number-transfers---technical-details"></a>Trasferimenti di numeri di telefono esterni - dettagli tecnici

Fai riferimento ai [Prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) per consentire agli operatori automatici di trasferire le chiamate esternamente.  Inoltre:

- Per un account di risorse con licenza [Piano per chiamate](calling-plans-for-office-365.md) o [Numero di connessione operatore](operator-connect-plan.md) , il numero di telefono di trasferimento esterno deve essere immesso nel formato E.164 (+[codice paese][prefisso][numero di telefono]).

- Per un account delle risorse con un criterio di routing vocale online licenza Telefono di Microsoft Teams e routing diretto, il formato del numero di telefono per trasferimento esterno dipende dalle impostazioni [SBC (Session Border Controller).](direct-routing-connect-the-sbc.md)

Il numero di telefono in uscita visualizzato viene determinato nel modo seguente:

- Per i numeri del piano per chiamate e della connessione operatore, viene visualizzato il numero di telefono del chiamante originale.
- Per i numeri di routing diretto, il numero inviato si basa sull'impostazione P-Asserted-Identity (PAI) in SBC, come indicato di seguito:
  - Se impostato su Disabilitato, viene visualizzato il numero di telefono del chiamante originale. Questa è l'impostazione predefinita e consigliata.
  - Se è impostato su Abilitato, viene visualizzato il numero di telefono dell'account della risorsa.

In un ambiente ibrido Skype for Business, per trasferire una chiamata di operatore automatico alla rete PSTN, creare un nuovo utente locale con l'inoltro di chiamata impostato sul numero PSTN. L'utente deve essere abilitato per VoIP aziendale e avere un criterio vocale assegnato. Per ulteriori informazioni, vedi [Trasferimento di chiamata operatore automatico a PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Strumento di diagnostica operatore automatico

Se sei un amministratore, puoi usare il seguente strumento di diagnostica per verificare che un operatore automatico sia in grado di ricevere chiamate:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’interfaccia Amministrazione Microsoft 365.

   > [!div class="nextstepaction"]
   > [Eseguire test: Operatore automatico di Teams](https://aka.ms/TeamsAADiag)

2. Nel riquadro Esegui diagnostica immettere l'account di risorsa nel campo **Nome utente o Posta elettronica** e quindi selezionare **Esegui test**.

3. I test identificheranno le configurazioni di tenant, criteri o account delle risorse che impediscono all'operatore automatico di ricevere chiamate e forniscono i passaggi per risolvere eventuali problemi identificati.

### <a name="related-topics"></a>Argomenti correlati

[Ecco cosa ottieni con Teams Phone](./here-s-what-you-get-with-phone-system.md)

[Ottenere numeri telefonici di servizio](./getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
