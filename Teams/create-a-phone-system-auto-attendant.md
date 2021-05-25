---
title: Configurare un operatore automatico per Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per organizzazioni di grandi dimensioni in Microsoft Teams.
ms.openlocfilehash: 270a2e613e387b797cb70914ad400da80b15b1ca
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628945"
---
# <a name="set-up-an-auto-attendant"></a>Configurare un operatore automatico

Gli operatori automatici consentono alle persone di chiamare l'organizzazione e navigare in un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore giusto. È possibile creare operatori automatici per l'organizzazione con l'Microsoft Teams di amministrazione o con PowerShell.

> [!TIP]
> Questo articolo contiene organizzazioni di grandi dimensioni. Se l'organizzazione è un'azienda smaall, vedere Configurare un operatore automatico [- esercitazione per le piccole](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) imprese.

Assicurarsi di aver letto Pianificare [gli](plan-auto-attendant-call-queue.md) operatori Teams e le [](plan-auto-attendant-call-queue.md#getting-started) code di chiamata e di aver seguito i passaggi introduttivi prima di seguire le procedure descritte in questo articolo.

Gli operatori automatici possono indirizzare le chiamate, in base all'input dei chiamanti, a una delle destinazioni seguenti: <a name="call-routing-options" ></a>

- **Operatore:** l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come qualsiasi altra destinazione in questo elenco.
- **Persona dell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali. Questa persona può essere un utente online o un utente ospitato in locale usando Skype for Business Server.
- **App vocale:** un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
- **Segreteria telefonica:** la cassetta postale vocale associata a Microsoft 365 gruppo specificato dall'utente.
- **Numero di telefono esterno:** qualsiasi numero di telefono. (Vedere [dettagli tecnici sul trasferimento esterno).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Annuncio (file audio)** - Riprodurre un file audio. Messaggio di annuncio registrato caricato salvato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere superiore a 5 MB. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.
- **Annuncio (digitato):** digitare un messaggio. Testo che deve essere letto dal sistema. È possibile immettere fino a 1000 caratteri. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.

Durante la configurazione di un operatore automatico, verrà richiesto di scegliere una di queste opzioni in varie fasi.

> [!NOTE]
> Quando si sceglie Segreteria telefonica come destinazione, sono disponibili due opzioni aggiuntive:
> - **Trascrizione** (impostazione predefinita: disattivata): se abilitato, il messaggio della segreteria telefonica verrà trascritto e incluso come parte del messaggio di posta elettronica.
> - **Elimina messaggio di** saluto (impostazione predefinita: disattivato): se abilitato, il messaggio di sistema standard "Lascia un messaggio dopo il tono. Al termine, riagganciare o premere il tasto hash per altre opzioni". verrà soppresso.

Per configurare un operatore automatico, nell'interfaccia Teams di amministrazione espandere **Voce,** selezionare **Operatori automatici** e quindi **selezionare Aggiungi**.

## <a name="video-demonstration"></a>Dimostrazione video

Questo video mostra un esempio di base di come creare un operatore automatico in Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>Informazioni generali

![Screenshot delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](media/auto-attendant-general-info-page-new.png)

1. Digitare un nome per l'operatore automatico nella casella in alto.

2. Per designare un operatore, specificare la destinazione per le chiamate all'operatore. Questa designazione è facoltativa (ma consigliata). Impostare **l'opzione** Operatore per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.

3. Specificare il fuso orario per questo operatore automatico. Il fuso orario viene usato per calcolare l'orario di ufficio se si [crea un flusso di chiamata separato per le ore successive.](#call-flow-for-after-hours)

4. Specificare una [lingua supportata per](create-a-phone-system-auto-attendant-languages.md) questo operatore automatico. Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.

5. Scegliere se abilitare gli input vocali. Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale. Ad esempio, i chiamanti possono pronunciare "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure pronunciare "Vendite" per selezionare l'opzione di menu denominata "Vendite".

> [!NOTE]
> Se si sceglie una lingua nel passaggio 4 che non supporta gli input vocali, questa opzione verrà disabilitata.

6. Selezionare **Avanti**.

## <a name="call-flow"></a>Flusso delle chiamate

![Screenshot delle impostazioni dei messaggi di saluto](media/auto-attendant-call-flow-greeting-message.png)

Scegliere se si vuole riprodurre un messaggio di saluto quando l'operatore automatico risponde a una chiamata.

Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Upload **file per** caricare un messaggio di saluto registrato salvato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere superiore a 5 MB.

Se si seleziona **Digita un messaggio** di saluto, il sistema leggerà il testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

![Screenshot delle impostazioni di routing delle chiamate](media/auto-attendant-call-flow-route-call-message.png)

Scegli come instradare la chiamata.

Se si seleziona **Disconnetti**, l'operatore automatico riaggancia la chiamata.

Se si seleziona **Reindirizza chiamata,** è possibile scegliere una delle destinazioni di routing delle chiamate.

Se si seleziona **Opzioni di menu** Riproduci , è possibile scegliere Riproduci un file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni di menu e la ricerca nella directory.

### <a name="menu-options"></a>Opzioni di menu

![Screenshot delle opzioni dei tasti di scelta](media/auto-attendant-call-flow-menu-options-complete.png)

Per le opzioni di composizione, assegnare i tasti da 0 a 9 sul tastierino del telefono a una delle destinazioni di routing delle chiamate. (I tasti \* (Ripeti) e (Indietro) sono riservati dal sistema e non possono \# essere riassegnati.

Non è necessario che i mapping dei tasti siano continui. È possibile creare un menu con i tasti 0, 1 e 3 mappati alle opzioni, mentre il tasto numero 2 non viene usato.

Se ne è stato configurato uno, è consigliabile eseguire il mapping della chiave zero all'operatore. Se l'operatore non è impostato su alcun tasto, viene disabilitato anche il comando vocale "Operatore".

Per ogni opzione di menu, specificare le impostazioni seguenti:

- **Tasto di composizione:** il tasto sul tastierino del telefono per accedere a questa opzione. Se sono disponibili input vocali, i chiamanti possono anche pronunciare questo numero per accedere all'opzione.

- **Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati. Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e motivi". Ad esempio, il chiamante può premere 2, pronunciare "due" o "Vendite" per selezionare l'opzione mappata ai due tasti. Questo testo viene visualizzato anche tramite sintesi vocale per la richiesta di conferma del servizio, che potrebbe essere simile a "Trasferimento della chiamata alle vendite".

- **Reindirizza** a: destinazione del routing delle chiamate usata quando i chiamanti scelgono questa opzione. Se si esegue il reindirizzamento a un operatore automatico o a una coda di chiamata, scegliere l'account della risorsa associato.

### <a name="directory-search"></a>Ricerca nella directory

Se si assegnano i tasti di chiamata alle destinazioni, è **consigliabile** scegliere Nessuno per la **ricerca nella directory.** Se un chiamante prova a comporre un nome o un interno usando i tasti assegnati a destinazioni specifiche, potrebbe essere instradato in modo imprevisto a una destinazione prima di completare l'immissione del nome o dell'interno. È consigliabile creare un operatore automatico separato per la ricerca nella directory e impostare il collegamento dell'operatore automatico principale con un tasto di chiamata.

Se non sono stati assegnati tasti di chiamata, scegliere un'opzione per **La ricerca nella directory**.

**Chiama per nome:** se si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sul tastierino del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server, è un utente idoneo e può essere trovato con Chiama per nome. È possibile impostare chi è e non è incluso nella directory nella [pagina Ambito di](#dial-scope) chiamata.

**Chiama per interno:** se si abilita questa opzione, i chiamanti possono connettersi con gli utenti dell'organizzazione componendo l'interno del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server, è un utente idoneo e può essere trovato con **Chiamata per interno.** È possibile impostare chi è e non è incluso nella directory nella [pagina Ambito di](#dial-scope) chiamata.

Gli utenti che si vogliono rendere disponibili per l'estensione Chiamata per interno devono avere un'estensione specificata come parte di uno degli attributi dei telefoni seguenti definiti in Active Directory o Azure Active Directory (per altre informazioni, vedere Aggiungere utenti singolarmente o [in](/microsoft-365/admin/add-users/add-users) blocco).

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

Il formato necessario per immettere l'interno nel campo del numero di telefono dell'utente può essere uno dei formati seguenti:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- Esempio 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"
- Esempio 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Esempio 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

È possibile impostare l'estensione [nell'interfaccia Microsoft 365 o](https://admin.microsoft.com/) nell'Azure Active Directory di [amministrazione.](https://aad.portal.azure.com) Possono essere necessarie fino a 12 ore prima che le modifiche siano disponibili per gli operatori automatici e le code di chiamata.

> [!NOTE]
> Se si vogliono usare  sia le  funzionalità Chiama per nome che Chiama per interno, è possibile assegnare un tasto di composizione all'operatore automatico principale per raggiungere un operatore automatico abilitato per Chiama **per nome.** All'interno di tale operatore automatico, è possibile assegnare il tasto 1 (a cui non sono associate lettere) per raggiungere l'operatore automatico Chiama **per** interno.

Dopo aver selezionato **un'opzione di ricerca nella directory,** selezionare **Avanti**.

## <a name="call-flow-for-after-hours"></a>Flusso delle chiamate per le ore successive

![Screenshot delle impostazioni del giorno e dell'ora dopo l'ora](media/auto-attendant-business-hours.png)

È possibile impostare l'orario di ufficio per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni di orario durante il giorno e tutte le ore non impostate come ore lavorative vengono considerate dopo l'orario. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per le ore successive.

A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo l'instradamento dopo l'orario di chiamata per gli operatori automatici con numeri di telefono diretti.

Se si vuole un instradamento delle chiamate separato per i chiamanti non lavorativi, specificare l'orario di ufficio per ogni giorno. Selezionare **Aggiungi nuova ora** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.

Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per le ore successive. Sono disponibili le stesse opzioni per il routing delle chiamate in orario di ufficio specificato in precedenza.

Al **termine,** selezionare Avanti.

## <a name="call-flows-during-holidays"></a>Flussi di chiamate durante le festività

![Screenshot delle impostazioni per le festività e le festività](media/auto-attendant-holiday-greeting.png)

L'operatore automatico può avere un flusso di chiamata per ogni festività [impostata.](set-up-holidays-in-teams.md) È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina Impostazioni chiamata per le festività selezionare **Aggiungi**.

2. Digitare un nome per questa impostazione di festività.

3. **Nell'elenco a** discesa Festività scegliere la festività da usare.

4. Scegliere il tipo di messaggio di saluto da usare.

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](media/auto-attendant-holiday-actions.png)

5. Scegliere se disconnettere **o** **reindirizzare** la chiamata.

6. Se si sceglie di reindirizzare la chiamata, scegliere la destinazione del routing delle chiamate per la chiamata.

7. Selezionare **Salva**.

![Screenshot delle impostazioni delle festività con le festività elencate](media/auto-attendant-holiday-call-settings.png)

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

Dopo aver aggiunto tutte le festività, selezionare **Avanti.**

## <a name="dial-scope"></a>Ambito di chiamata

![Screenshot delle opzioni di inclusione ed esclusione dell'ambito di chiamata](media/auto-attendant-dial-scope.png)

*L'ambito di* chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa la chiamata per nome o la chiamata per interno. L'impostazione predefinita **di Tutti gli** utenti online include tutti gli utenti dell'organizzazione che sono utenti online o ospitati in locale usando Skype for Business Server.

È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato in Includi o Escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza.  Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di composizione. Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.

> [!NOTE]
> L'elenco del nome di un nuovo utente nella directory potrebbe richiedere fino a 36 ore.

Dopo aver impostato l'ambito di chiamata, selezionare **Avanti**.

## <a name="resource-accounts"></a>Account delle risorse

A tutti gli operatori automatici deve essere associato un account di risorsa.  Gli operatori automatici di primo livello dovranno avere almeno un account della risorsa a cui è associato un numero di servizio. Se si vuole, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.

![Screenshot del riquadro Aggiungi account dell'account della risorsa](media/auto-attendant-add-resource-account.png)

Per aggiungere un account della risorsa, selezionare **Aggiungi account** e cercare l'account da aggiungere. Selezionare **Aggiungi** e quindi **Aggiungi**.

![Screenshot dell'elenco degli account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](media/auto-attendant-resource-account-assigned.png)

Dopo aver aggiunto gli account del servizio, **selezionare** Invia per completare la configurazione dell'operatore automatico.

## <a name="external-phone-number-transfers---technical-details"></a>Trasferimenti di numeri di telefono esterni - dettagli tecnici

Fare riferimento ai [Prerequisiti per](plan-auto-attendant-call-queue.md#prerequisites) consentire agli operatori automatici di trasferire le chiamate esternamente.  Inoltre:

- Per un account della risorsa con una licenza piano per [chiamate,](calling-plans-for-office-365.md)il numero di telefono per il trasferimento esterno deve essere immesso nel formato E.164 (+[codice paese][codice area][numero di telefono]).

- Per un account della risorsa con criteri di routing vocale Sistema telefonico License e Direct Routing online, il formato del numero di telefono per il trasferimento esterno dipende dalle impostazioni [SBC (Session Border Controller).](direct-routing-connect-the-sbc.md)

Il numero di telefono in uscita visualizzato viene determinato nel modo seguente:

  - Per i numeri del piano di chiamata, viene visualizzato il numero di telefono del chiamante originale.
  - Per i numeri di instradamento diretto, il numero inviato si basa sull'impostazione P-Asserted-Identity (PAI) del SBC, come indicato di seguito:
    - Se è impostato su Disabilitato, viene visualizzato il numero di telefono del chiamante originale. Questa è l'impostazione predefinita e consigliata.
    - Se è impostato su Abilitato, viene visualizzato il numero di telefono dell'account della risorsa.

In un Skype for Business ibrido, per trasferire una chiamata dell'operatore automatico alla rete PSTN, creare un nuovo utente locale con l'inoltro di chiamata impostato sul numero PSTN. L'utente deve essere abilitato per VoIP aziendale e avere assegnato un criterio vocale. Per altre informazioni, vedere [Trasferimento di chiamata dell'operatore automatico a PSTN.](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>Creare un operatore automatico con PowerShell

È anche possibile usare PowerShell per creare e configurare operatori automatici. Ecco i cmdlet necessari per gestire un operatore automatico:

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>Argomenti correlati

[Vantaggi offerti dal Sistema telefonico](./here-s-what-you-get-with-phone-system.md)

[Ottenere numeri telefonici di servizio](./getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
