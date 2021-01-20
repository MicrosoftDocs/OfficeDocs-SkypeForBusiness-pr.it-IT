---
title: Configurare un operatore automatico per Microsoft teams-Small Business tutorial
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Informazioni su come configurare e testare gli operatori automatici per Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909640"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurare un operatore automatico-esercitazione sulle piccole imprese

Gli operatori automatici consentono alle persone di chiamare l'organizzazione e di spostarsi in un sistema di menu per parlare con il reparto di destra, la coda di chiamata, la persona o un operatore. È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft teams.

#### <a name="before-you-begin"></a>Prima di iniziare

Ottenere i numeri di servizio necessari per gli operatori automatici a cui si vuole accedere tramite chiamata diretta dall'esterno dell'organizzazione. Questo potrebbe includere il [trasferimento di numeri da un altro provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la [richiesta di nuovi numeri di servizio](../getting-service-phone-numbers.md).

Ottenere un [sistema telefonico-licenza utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche extra nel caso in cui decidi di apportare modifiche alla configurazione in futuro.

Per fare in modo che le chiamate di routing per l'operatore automatico vengano effettuate diversamente durante le festività, [creare le festività che si desidera utilizzare prima di](../set-up-holidays-in-teams.md) creare l'operatore automatico.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Seguire questa procedura per configurare l'operatore automatico

# <a name="step-1brphone-number"></a>[Numero di <br> telefono passaggio 1](#tab/phone-number)

Ogni operatore automatico creato richiede un account di risorse. Questo è simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona. In questo passaggio verrà creato l'account, assegnato a *Microsoft 365 Phone System-licenza utente virtuale* e quindi assegnato un numero di servizio.

### <a name="create-a-resource-account"></a>Creare un account di risorse

È possibile creare un account risorse nell'interfaccia di amministrazione di teams.

1. Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato**, **nomeutente** e scegliere **operatore automatico** per il **tipo di account risorse**

    ![Screenshot dell'interfaccia utente Aggiungi account risorse](../media/resource-account-add.png)

4. Fare clic su **Salva**.

Il nuovo account verrà visualizzato nell'elenco degli account.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Assegnare una licenza

È necessario assegnare un *sistema telefonico Microsoft 365-licenza utente virtuale* per l'account delle risorse.

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.

2. Nella scheda **licenze e app** , in **licenze**, selezionare **Microsoft 365 Phone System-Virtual User**.

3. Fare clic su **Salva modifiche**.

    ![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se è necessario che l'operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account delle risorse.

1. Nell'interfaccia di amministrazione di teams, nella pagina **account risorse** , selezionare l'account delle risorse a cui si vuole assegnare un numero di servizio e quindi fare clic su **assegna/Annulla assegnazione**.

2. Nell'elenco a discesa **tipo di numero di telefono** scegliere il tipo di numero che si vuole usare.

3. Nella casella **numero di telefono assegnato** cercare il numero che si vuole usare e fare clic su **Aggiungi**.

    ![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Passaggio 2-informazioni generali sull'operatore automatico >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Informazioni generali su Step 2 <br> Attendant](#tab/general-info)

Per configurare un operatore automatico

1. Nell'interfaccia di amministrazione di teams espandere **Voice**, fare clic su **operatore automatico** e quindi fare clic su **Aggiungi**.

2. Digitare un nome per l'operatore automatico nella casella nella parte superiore.

3. Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore. Questa opzione è facoltativa (ma consigliata). Puoi impostare l'opzione **operator** per consentire ai chiamanti di uscire dai menu e parlare con una persona designata.

4. Specificare il fuso orario per l'operatore automatico. Il fuso orario viene usato per calcolare le ore lavorative se si crea un flusso di chiamata separato per le ore successive.

5. Specificare una lingua per l'operatore automatico. Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.

6. Scegliere se si desidera abilitare gli input vocali. Quando è abilitata, il nome di ogni opzione del menu diventa una parola chiave per il riconoscimento vocale. Ad esempio, i chiamanti possono pronunciare "uno" per selezionare l'opzione di menu mappata con il tasto 1 oppure possono dire "vendite" per selezionare l'opzione di menu denominata "Sales".

    ![Screenshot delle impostazioni di operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. Fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 3->flusso delle chiamate ](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Passaggio 3 <br> flusso delle chiamate](#tab/call-flow)

Scegliere le opzioni di flusso delle chiamate

1. Scegliere se si vuole riprodurre un saluto quando l'operatore automatico risponde a una chiamata.

    Se si seleziona **Riproduci un file audio** , è possibile usare il pulsante **Carica file** per caricare un messaggio di saluto registrato salvato come audio. WAV,. MP3 o. Formato WMA. La registrazione non può essere superiore a 5 MB.

    Se si seleziona **digita un messaggio di saluto** , il sistema leggerà il testo del testo digitato (fino a 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

    ![Screenshot delle impostazioni dei messaggi di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. Scegliere come si vuole instradare la chiamata.

    Se si seleziona **Disconnetti**, l'operatore automatico bloccherà la chiamata.

    Se si seleziona **reindirizza chiamata**, è possibile scegliere una delle destinazioni di routing delle chiamate.

    Se si seleziona **Opzioni di menu Riproduci**, è possibile scegliere di **riprodurre un file audio** o **digitare un messaggio di saluto** e quindi scegliere tra le opzioni del menu e la ricerca nella directory.

    ![Screenshot delle impostazioni di routing delle chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. Se si vuole che i chiamanti usino i tasti di scelta rapida per spostarsi, quindi in **Opzioni del menu imposta** scegliere cosa si vuole che si verifichi quando i chiamanti premiano un tasto di scelta rapida. Se si sta creando questo operatore automatico come directory aziendale, uscire dalle opzioni del tasto di selezione vuoto.

    È possibile impostare una qualsiasi delle chiavi di chiamata per le destinazioni seguenti:

    - **Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali.
    - **App vocale** : un altro operatore automatico o una coda di chiamata.
    - **Numero di telefono esterno** -qualsiasi numero di telefono. Usare questo formato: + [codice paese] [prefisso] [numero di telefono]
    - **Segreteria telefonica** : casella vocale associata a un gruppo Microsoft 365 specificato.
    - **Operator** : l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come una qualsiasi delle altre destinazioni in questo elenco.

    Ti consigliamo di impostare il tasto 0 per l'operatore.

    Per ogni opzione di menu, specificare quanto segue:

    - **Tasto** di scelta rapida: il tasto sulla tastiera del telefono per accedere a questa opzione.

    - **Comando vocale** : definisce il comando vocale che può essere dato da un chiamante per accedere a questa opzione, se gli input vocali sono abilitati. Può contenere più parole come "Customer Service" o "Operations and grounds". 

    - **Reindirizza a** -dove vuoi che la chiamata vada quando i chiamanti scelgono questa opzione. Se si reindirizza a un operatore automatico o a una coda di chiamata, scegliere l'account delle risorse associato.

    ![Screenshot delle opzioni dei tasti di scelta rapida](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Se si vuole usare l'operatore automatico come directory aziendale, in **ricerca directory** selezionare **Componi per nome**. Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono. Qualsiasi utente online con una licenza di sistema telefonico è un utente idoneo e può essere trovato con chiamata per nome. 

    Puoi scegliere **dial by Extension**, ma l'estensione deve essere configurata in Azure Active Directory.

5. Dopo aver selezionato un'opzione di **ricerca della directory** , fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 4-ore dopo il flusso delle chiamate >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Passaggio 4 <br> dopo le ore](#tab/after-hours)

Gli orari di ufficio possono essere impostati per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. Gli orari di ufficio possono essere impostati con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orari di ufficio sono considerate after-hours. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e i messaggi di saluto per le ore successive.

A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, è possibile che sia necessario specificare il routing delle chiamate after-hours per gli operatori automatici con numeri di telefono diretti.

Se si vuole eseguire il routing delle chiamate separate per i chiamanti dopo le ore, specificare gli orari di ufficio per ogni giorno. Fare clic su **Aggiungi nuovo orario** per specificare più set di ore per un giorno specifico, ad esempio per specificare una pausa pranzo.

![Screenshot delle impostazioni giorno e ora dopo ore](../media/auto-attendant-business-hours.png)

Dopo aver specificato gli orari di ufficio, scegliere le opzioni di routing delle chiamate per le ore successive. Le stesse opzioni sono disponibili per il routing delle chiamate in orario di ufficio specificato nel **passaggio 3-flusso delle chiamate**.

Al termine, fare clic su **Avanti** .

> [!div class="nextstepaction"]
> [Passaggio 5-flusso delle chiamate festive >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Passaggio 5 <br> festività](#tab/holidays)

È possibile che le chiamate all'operatore automatico vengano instradate in modo diverso durante le festività rispetto agli altri giorni. Se non si vuole avere un flusso di chiamata diverso per le festività, è possibile ignorare questo passaggio.



L'operatore automatico può avere un flusso di chiamata per ogni festività configurata. È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina delle impostazioni delle chiamate festive fare clic su **Aggiungi**.

2. Digitare un nome per l'impostazione festività.

3. Nell'elenco a discesa **festività** scegliere la festività che si vuole usare.

4. Scegliere il tipo di saluto che si vuole usare.

    ![Schermata delle impostazioni di saluto delle festività e delle festività](../media/auto-attendant-holiday-greeting.png)

5. Scegliere se si vuole **disconnettere** o **reindirizzare** la chiamata.

6. Se si è scelto di reindirizzare, scegliere la destinazione di routing delle chiamate per la chiamata.

    ![Schermata delle impostazioni di azione delle chiamate per le festività](../media/auto-attendant-holiday-actions.png)

7. Fare clic su **Salva**.

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

![Screenshot delle impostazioni per le festività con le festività elencate](../media/auto-attendant-holiday-call-settings.png)

Dopo aver aggiunto tutte le festività, fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 6-scegliere gli utenti nella directory >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Passaggio 6 <br> membri della directory](#tab/dial-scope)

L' *ambito di chiamata* definisce gli utenti disponibili nella directory quando un chiamante usa la chiamata per nome o il dial-by-Extension. Il valore predefinito di **tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con una licenza per il sistema telefonico.

È possibile includere o escludere utenti specifici selezionando un **gruppo di utenti personalizzato** in **Includi** o **Escludi** e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. Ad esempio, potresti voler escludere i dirigenti dell'organizzazione dalla directory di chiamata. Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.

![Screenshot dell'ambito di chiamata include ed Escludi le opzioni](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> Per un nuovo utente potrebbe essere necessario un massimo di 36 ore per avere il nome elencato nella directory.

Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 7-assegnare un account di risorse >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<br>Account delle risorse del passaggio 7](#tab/resource-accounts)

Tutti gli operatori automatici devono avere un account di risorse associato.  Per gli operatori automatici di primo livello sarà necessario almeno un account delle risorse con un numero di servizio associato. Se lo si desidera, è possibile assegnare più account di risorse a un operatore automatico, ognuno con un numero di servizio distinto.

Per aggiungere un account di risorse

1. Fare clic su **Aggiungi account** e cercare l'account che si vuole aggiungere. Fare clic su **Aggiungi** e quindi su **Aggiungi**.

    ![Screenshot del pannello account risorse Aggiungi account](../media/auto-attendant-add-resource-account.png)

2. Dopo aver aggiunto gli account del servizio, fare clic su **Invia**.

    ![Screenshot dell'elenco di account risorse che mostra l'account delle risorse con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

Viene completata la configurazione dell'operatore automatico.

---


