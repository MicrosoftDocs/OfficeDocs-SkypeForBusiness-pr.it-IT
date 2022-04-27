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
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare e testare gli operatori automatici per le organizzazioni di grandi dimensioni in Microsoft Teams.
ms.openlocfilehash: a0b50a83e54059dca68562c2140ece6253448dd0
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059097"
---
# <a name="set-up-an-auto-attendant"></a>Configurare un operatore automatico

Gli operatori automatici consentono alle persone di chiamare la tua organizzazione e di navigare in un sistema di menu per parlare con il reparto, la coda di chiamata, la persona o un operatore giusto. È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams o con PowerShell.

> [!TIP]
> Questo articolo è rivolto alle organizzazioni di grandi dimensioni. Se l'organizzazione è una piccola azienda, vedere [Configurare un operatore automatico - Esercitazione per le piccole imprese](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) .

Assicurati di aver letto [Piano per Teams operatori automatici e code di chiamata](plan-auto-attendant-call-queue.md) e segui i [passaggi iniziali](plan-auto-attendant-call-queue.md#getting-started) prima di seguire le procedure descritte in questo articolo.

Gli operatori automatici possono indirizzare le chiamate, in base all'input dei chiamanti, a una delle seguenti destinazioni: <a name="call-routing-options" ></a>

- **Operatore** - l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come una qualsiasi delle altre destinazioni in questo elenco.
- **Persona dell'organizzazione** : una persona dell'organizzazione che può ricevere chiamate vocali. Questa persona può essere un utente online o un utente ospitato in locale usando Skype for Business Server.
- **App vocale** : un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
- **Segreteria telefonica**: cassetta postale vocale associata a un gruppo di Microsoft 365 specificato. È possibile scegliere se si vogliono le trascrizioni della segreteria telefonica e "Lascia un messaggio dopo il tono". richiesta di sistema.
- **Numero di telefono esterno** : qualsiasi numero di telefono. (Vedere [i dettagli tecnici sul trasferimento esterno](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Annuncio (file audio):** riprodurre un file audio. Messaggio di annuncio registrato che viene caricato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere di dimensioni superiori a 5 MB. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.
- **Annuncio (digitato):** digitare un messaggio. Testo che si desidera venga letto dal sistema. È possibile immettere fino a 1000 caratteri. Il sistema riproduce l'annuncio e quindi torna al menu dell'operatore automatico.

Ti verrà richiesto di scegliere una di queste opzioni in varie fasi durante la configurazione di un operatore automatico.

Per configurare un operatore automatico, nell'interfaccia di amministrazione di Teams espandi **Voce**, seleziona **Operatori automatici** e quindi seleziona **Aggiungi**.

## <a name="video-demonstration"></a>Dimostrazione video

Questo video mostra un esempio di base su come creare un operatore automatico in Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>Informazioni generali

![Screenshot delle impostazioni dell'operatore automatico per il nome, l'operatore, il fuso orario, la lingua e gli input vocali.](media/auto-attendant-general-info-page-new.png)

1. Digita un nome per l'operatore automatico nella casella in alto.

2. Per designare un operatore, specificare la destinazione per le chiamate all'operatore. Questa designazione è facoltativa (ma consigliata). Impostare l'opzione **Operatore** per consentire ai chiamanti di uscire dai menu e parlare con una persona designata.

3. Specifica il fuso orario per questo operatore automatico. Il fuso orario viene usato per calcolare l'orario di ufficio se si [crea un flusso di chiamata separato per l'orario di chiusura](#call-flow-for-after-hours).

4. Specifica una [lingua supportata](create-a-phone-system-auto-attendant-languages.md) per questo operatore automatico. Questo è il linguaggio che verrà utilizzato per i comandi vocali generati dal sistema.

5. Scegli se abilitare gli input vocali. Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale. Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure "Vendite" per selezionare l'opzione di menu denominata "Vendite".

   > [!NOTE]
   > Se si sceglie una lingua nel passaggio 4 che non supporta gli input vocali, questa opzione verrà disabilitata.

6. Selezionare **Avanti**.

## <a name="call-flow"></a>Flusso delle chiamate

![Screenshot delle impostazioni del messaggio di saluto.](media/auto-attendant-call-flow-greeting-message.png)

Scegli se vuoi riprodurre un messaggio di saluto quando l'operatore automatico risponde a una chiamata.

Se si seleziona **Riproduci file audio**, è possibile usare il pulsante **Upload file** per caricare un messaggio di saluto registrato salvato come audio in . WAV, .MP3 o . Formato WMA. La registrazione non può essere di dimensioni superiori a 5 MB.

Se selezioni **Digita un messaggio di saluto** , il sistema leggerà il testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

![Screenshot delle impostazioni di routing delle chiamate.](media/auto-attendant-call-flow-route-call-message.png)

Scegliere come instradare la chiamata.

Se selezioni **Disconnetti**, l'operatore automatico riaggancia la chiamata.

Se selezioni **Reindirizza chiamata**, puoi scegliere una delle destinazioni per il routing delle chiamate.

Se si seleziona **Riproduci opzioni menu**, è possibile scegliere **Riproduci file audio** o **Digitare un messaggio di saluto** e quindi scegliere tra le opzioni di menu e la ricerca nella directory.

### <a name="menu-options"></a>Opzioni di menu

![Screenshot delle opzioni dei tasti di chiamata.](media/auto-attendant-call-flow-menu-options-complete.png)

Per le opzioni di chiamata, assegnare i tasti da 0 a 9 sulla tastiera del telefono a una delle destinazioni di instradamento delle chiamate. (I tasti \* (asterisco) e \# (cancelletto) sono riservati dal sistema e non possono essere riassegnati. Premendo uno di questi tasti verrà ripetuto il menu corrente.

> [!NOTE]
> Il tasto # esegue solo il backup dell'operatore automatico più recente. Una volta superato il limite di un nuovo operatore automatico, il tasto # non sarà in grado di portarti a quello precedente.

I mapping dei tasti non devono necessariamente essere continui. È possibile creare un menu con i tasti 0, 1 e 3 associati a opzioni, mentre il tasto numero 2 non viene usato.

Se ne hai configurato uno, ti consigliamo di associare il tasto zero all'operatore. Se l'operatore non è impostato su alcun tasto, viene disabilitato anche il comando vocale "Operatore".

Per ogni opzione di menu, specificare le impostazioni seguenti:

- **Tasto componi** : il tasto sulla tastiera del telefono per accedere a questa opzione. Se sono disponibili input vocali, i chiamanti possono anche pronunciare questo numero per accedere all'opzione.

- **Comando vocale** : definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati. Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e sedi". Ad esempio, il chiamante può premere 2, dire "due" o "Vendite" per selezionare l'opzione mappata ai due tasti. Questo testo viene anche visualizzato tramite sintesi vocale per la richiesta di conferma del servizio, che potrebbe essere qualcosa di simile a "Trasferimento della chiamata alle vendite".

- **Reindirizza a** : la destinazione di instradamento delle chiamate usata quando i chiamanti scelgono questa opzione. Se stai reindirizzando a un operatore automatico o a una coda di chiamata, scegli l'account della risorsa associato.

### <a name="directory-search"></a>Ricerca nella directory

Se si assegnano tasti di chiamata alle destinazioni, è **consigliabile scegliere Nessuno** per **la ricerca nella directory**. Se un chiamante tenta di comporre un nome o un'estensione usando chiavi assegnate a destinazioni specifiche, potrebbe essere instradato in modo imprevisto a una destinazione prima di completare l'immissione del nome o dell'estensione. Ti consigliamo di creare un operatore automatico separato per la ricerca in elenco e di disporre del collegamento principale dell'operatore automatico con un tasto di chiamata.

Se non hai assegnato i tasti di chiamata, scegli un'opzione per **la ricerca nella directory**.

**Chiamata per nome** : se si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale con Skype for Business Server, è un utente idoneo e può essere trovato con Chiamata per nome. È possibile impostare chi è o non è incluso nella directory nella pagina [Ambito](#dial-scope) chiamata.

**Chiamata per estensione** - Se si abilita questa opzione, i chiamanti possono connettersi con gli utenti dell'organizzazione componendo l'interno del telefono. Qualsiasi utente online o qualsiasi utente ospitato in locale usando Skype for Business Server, è un utente idoneo e può essere trovato con **Chiamata per estensione**. È possibile impostare chi è o non è incluso nella directory nella pagina [Ambito](#dial-scope) chiamata.

Gli utenti che desideri rendere disponibili per Chiamata per estensione devono avere un'estensione specificata come parte di uno dei seguenti attributi telefonici definiti in Active Directory (e sincronizzati tramite Azure AD Connessione) o Azure Active Directory. Per altre informazioni, vedere [Aggiungere utenti singolarmente o in blocco](/microsoft-365/admin/add-users/add-users) .

- OfficePhone/TelephoneNumber (AD e Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD e Azure AD)
- Altrotelefono (AD)

Il formato richiesto per immettere l'estensione nel campo del numero di telefono dell'utente può essere uno dei formati seguenti:

- *+\<phone number>;estensione=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Esempio 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Esempio 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- Esempio 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

È possibile impostare l'estensione nel [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) o [nell'interfaccia di amministrazione di Azure Active Directory](https://aad.portal.azure.com). Possono essere necessarie fino a 12 ore prima che le modifiche siano disponibili per gli operatori automatici e le code di chiamata.

> [!NOTE]
> Se desideri utilizzare sia le funzionalità **Chiamata per nome** che Chiamata per **estensione** , puoi assegnare un tasto di chiamata sull'operatore automatico principale per raggiungere un operatore automatico abilitato per **Chiamata per nome**. All'interno di quell'operatore automatico, puoi assegnare il tasto 1 (che non ha lettere associate) per raggiungere l'operatore automatico **Dial by extension** .

Per altre informazioni, vedere [Comando radiale e riferimento vocale](dial-voice-reference.md) .

Dopo aver selezionato un'opzione **di ricerca nella directory** , seleziona **Avanti**.

## <a name="call-flow-for-after-hours"></a>Flusso delle chiamate per fuori orario

![Screenshot delle impostazioni del giorno e dell'ora fuori orario.](media/auto-attendant-business-hours.png)

L'orario di ufficio può essere impostato per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni durante il giorno e tutti gli orari che non sono impostati come orario di ufficio vengono considerati fuori orario. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per l'orario di chiusura.

A seconda di come hai configurato gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo il routing delle chiamate fuori orario per gli operatori automatici con numeri di telefono diretti.

Se si vuole separare il routing delle chiamate per i chiamanti in orario di chiusura, specificare l'orario di ufficio per ogni giorno. Selezionare **Aggiungi nuovo orario** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.

Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per l'orario di chiusura. Le stesse opzioni sono disponibili per il routing delle chiamate in orario di ufficio specificato in precedenza.

Al **termine** , selezionare Avanti.

## <a name="call-flows-during-holidays"></a>Flussi delle chiamate durante le festività

![Screenshot delle impostazioni di saluto per le festività e le festività.](media/auto-attendant-holiday-greeting.png)

L'operatore automatico può avere un flusso delle chiamate per ogni [festività configurata](set-up-holidays-in-teams.md). È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina Impostazioni chiamata festività seleziona **Aggiungi**.

2. Digitare un nome per l'impostazione delle festività.

3. Nell'elenco a discesa **Festività** scegliere la festività da usare.

4. Scegliere il tipo di messaggio di saluto da usare.

    ![Screenshot delle impostazioni delle azioni delle chiamate natalizie.](media/auto-attendant-holiday-actions.png)

5. Scegliere se si vogliono **disconnettere**, **reindirizzare** o **riprodurre le opzioni del menu**.

6. Se si sceglie di reindirizzare, scegliere la destinazione del routing delle chiamate per la chiamata.

7. Se si sceglie di riprodurre le opzioni del menu, configurare le [opzioni del menu](#menu-options).

8. Selezionare **Salva**.

![Screenshot delle impostazioni delle festività con l'elenco delle festività.](media/auto-attendant-holiday-call-settings.png)

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

Dopo aver aggiunto tutte le festività, selezionare **Avanti**.

## <a name="dial-scope"></a>Ambito di chiamata

![Screenshot delle opzioni di inclusione ed esclusione dell'ambito di chiamata.](media/auto-attendant-dial-scope.png)

*L'ambito di chiamata* definisce quali utenti sono disponibili nella directory quando un chiamante usa l'opzione di chiamata per nome o dial-by-extension. Il valore predefinito **Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online o ospitati in locale tramite Skype for Business Server.

È possibile includere o escludere utenti specifici selezionando **Gruppo di utenti personalizzati** in **Includi** o **Escludi** e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di chiamata. Se un utente è presente in entrambi gli elenchi, verrà escluso dalla directory.

> [!NOTE]
> Potrebbero essere richieste fino a 36 ore prima che il nome di un nuovo utente sia elencato nella directory.

Dopo aver impostato l'ambito di chiamata, selezionare **Avanti**.

## <a name="resource-accounts"></a>Account delle risorse

Tutti gli operatori automatici devono avere un account di risorse associato.  Gli operatori automatici di primo livello avranno bisogno di almeno un account di risorse con un numero di servizio associato. Se lo desideri, puoi assegnare diversi account di risorse a un operatore automatico, ognuno con un numero di servizio separato.

![Screenshot del pannello Aggiungi account per l'account della risorsa.](media/auto-attendant-add-resource-account.png)

Per aggiungere un account della risorsa, selezionare **Aggiungi account** e cercare l'account da aggiungere. Seleziona **Aggiungi** e quindi **Aggiungi**.

![Screenshot dell'elenco di account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato.](media/auto-attendant-resource-account-assigned.png)

Dopo aver aggiunto gli account delle risorse, seleziona **Invia** per completare la configurazione dell'operatore automatico.

Per altre informazioni[, vedere Gestire Teams account delle risorse](manage-resource-accounts.md).

## <a name="external-phone-number-transfers---technical-details"></a>Trasferimenti di numeri di telefono esterni - dettagli tecnici

Fai riferimento ai [Prerequisiti](plan-auto-attendant-call-queue.md#prerequisites) per consentire agli operatori automatici di trasferire le chiamate esternamente.  Inoltre:

- Per un account di risorsa con una [licenza piano per chiamate](calling-plans-for-office-365.md) o [un numero di Connessione con operatore](operator-connect-plan.md), il numero di telefono di trasferimento esterno deve essere immesso nel formato E.164 (+[codice paese][prefisso][numero di telefono]).

- Per un account delle risorse con un criterio di routing vocale online licenza Telefono di Microsoft Teams e routing diretto, il formato del numero di telefono per trasferimento esterno dipende dalle impostazioni [SBC (Session Border Controller).](direct-routing-connect-the-sbc.md)

Il numero di telefono in uscita visualizzato viene determinato nel modo seguente:

  - Per Il Piano per chiamate e i numeri di Connessione con operatore, viene visualizzato il numero di telefono del chiamante originale.
  - Per i numeri di routing diretto, il numero inviato si basa sull'impostazione P-Asserted-Identity (PAI) in SBC, come indicato di seguito:
    - Se impostato su Disabilitato, viene visualizzato il numero di telefono del chiamante originale. Questa è l'impostazione predefinita e consigliata.
    - Se è impostato su Abilitato, viene visualizzato il numero di telefono dell'account della risorsa.

In un ambiente ibrido Skype for Business, per trasferire una chiamata di operatore automatico alla rete PSTN, creare un nuovo utente locale con l'inoltro di chiamata impostato sul numero PSTN. L'utente deve essere abilitato per VoIP aziendale e avere un criterio vocale assegnato. Per ulteriori informazioni, vedi [Trasferimento di chiamata operatore automatico a PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

## <a name="auto-attendant-cmdlets"></a>Cmdlet dell'operatore automatico

Windows PowerShell consente di creare e gestire gli operatori automatici tramite la riga di comando in modo batch o programmatico.

I cmdlet seguenti consentono di gestire gli operatori automatici:

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

Per gestire gli utenti, gli account delle risorse, le licenze di Telefono di Microsoft Teams, i numeri di telefono, i file audio e la lingua supportata, sono necessari anche i seguenti cmdlet aggiuntivi, che verranno utilizzati con le code di chiamata:

Utenti/Teams

- Utenti
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)

Account delle risorse:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

Licenze Teams Telefono virtuali:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

Telefono assegnazione di numeri:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

File audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

Lingue e fusi orari del supporto

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

Per una guida dettagliata alla creazione di operatori automatici con PowerShell, vedi [Creazione di operatori automatici con i cmdlet di PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="auto-attendant-diagnostic-tool"></a>Strumento di diagnostica operatore automatico

Se sei un amministratore, puoi usare il seguente strumento di diagnostica per verificare che un operatore automatico sia in grado di ricevere chiamate:

1. Selezionare **Esegui test** di seguito, per popolare la diagnostica nell’interfaccia Amministrazione Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Esegui test: operatore automatico Teams](https://aka.ms/TeamsAADiag)

2. Nel riquadro Esegui diagnostica immettere l'account di risorsa nel campo **Nome utente o Posta elettronica** e quindi selezionare **Esegui test**.

3. I test identificheranno le configurazioni di tenant, criteri o account delle risorse che impediscono all'operatore automatico di ricevere chiamate e forniscono i passaggi per risolvere eventuali problemi identificati.

## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa ottieni con Teams Telefono](./here-s-what-you-get-with-phone-system.md)

[Ottenere numeri telefonici di servizio](./getting-service-phone-numbers.md).

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
