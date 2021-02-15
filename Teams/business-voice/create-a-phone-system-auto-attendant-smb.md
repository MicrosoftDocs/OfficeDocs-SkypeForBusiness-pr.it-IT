---
title: Configurare un operatore automatico per Microsoft Teams - esercitazione per piccole aziende
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
description: Scopri come configurare e testare gli operatori automatici per Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909640"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurare un operatore automatico - esercitazione per piccole aziende

Gli operatori automatici consentono alle persone di chiamare l'organizzazione ed esplorare un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore. È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams.

#### <a name="before-you-begin"></a>Prima di iniziare

Ottenere i numeri di servizio necessari per gli operatori automatici che si desidera siano accessibili componendo direttamente dall'esterno dell'organizzazione. Può includere il [trasferimento di numeri da un altro provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la richiesta di nuovi numeri di [servizio.](../getting-service-phone-numbers.md)

Ottenere un [Sistema telefonico - Licenza Utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore prodotto se decidi di apportare modifiche alla configurazione in futuro.

Se si vuole impostare il percorso dell'operatore [](../set-up-holidays-in-teams.md) automatico in modo diverso durante le festività, creare le festività da usare prima di creare l'operatore automatico.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Seguire questa procedura per configurare l'operatore automatico

# <a name="step-1brphone-number"></a>[Passaggio 1 <br> Numero di telefono](#tab/phone-number)

Ogni operatore automatico che crei richiede un account delle risorse. È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona. In questo passaggio creeremo l'account, gli assegniamo una licenza Sistema telefonico - Utente virtuale di *Microsoft 365* e quindi assegniamo un numero di servizio.

### <a name="create-a-resource-account"></a>Creare un account delle risorse

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

1. Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorsa,** compilare **Nome visualizzato**, **Nome** utente e scegliere **Operatore** automatico per il **tipo di account Risorsa**

    ![Screenshot dell'interfaccia utente aggiungi account risorsa](../media/resource-account-add.png)

4. Fare clic su **Salva**.

Il nuovo account verrà visualizzato nell'elenco degli account.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Assegnare una licenza

È necessario assegnare una *licenza Sistema telefonico Microsoft 365 -* Utente virtuale all'account delle risorse.

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.

2. Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**

3. Fare clic **su Salva modifiche.**

    ![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se è necessario che questo operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account della risorsa.

1. Nell'interfaccia di amministrazione  di Teams, nella pagina Account risorse, selezionare l'account della risorsa a cui assegnare un numero di servizio e quindi fare clic su **Assegna/Annulla assegnazione.**

2. **Nell'elenco a** discesa Tipo di numero di telefono scegliere il tipo di numero da usare.

3. Nella casella **Numero di telefono assegnato,** cerca il numero che desideri utilizzare e fai clic su **Aggiungi.**

    ![Screenshot dell'interfaccia utente Assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Fase 2 - Informazioni generali sull'operatore >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Informazioni generali su Step 2 <br> Attendant](#tab/general-info)

Per impostare un operatore automatico

1. Nell'interfaccia di amministrazione di Teams espandi **Voce,** fai clic **su Operatori** automatici, quindi fai clic su **Aggiungi.**

2. Digita un nome per l'operatore automatico nella casella in alto.

3. Se si vuole designare un operatore, specificare la destinazione delle chiamate all'operatore. Questo passaggio è facoltativo (ma consigliato). È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.

4. Specifica il fuso orario per questo operatore automatico. Il fuso orario viene utilizzato per calcolare l'orario di ufficio se si crea un flusso delle chiamate separato per l'orario di uscita.

5. Specifica una lingua per l'operatore automatico. Questa è la lingua che verrà usata per i comandi vocali generati dal sistema.

6. Scegli se abilitare gli input vocali. Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale. Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1, oppure possono dire "Vendite" per selezionare l'opzione di menu denominata "Vendite".

    ![Schermata delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. Fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 3 - Flusso delle chiamate >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Passaggio 3 <br> Flusso delle chiamate](#tab/call-flow)

Scegliere le opzioni del flusso delle chiamate

1. Scegli se vuoi riprodurre un saluto quando l'operatore automatico risponde a una chiamata.

    Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Carica **file** per caricare un messaggio di saluto registrato salvato come audio in. WAV, . MP3, o . WMA. Le dimensioni della registrazione non possono essere superiori a 5 MB.

    Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

    ![Screenshot delle impostazioni del messaggio di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. Scegli come instradare la chiamata.

    Se si seleziona **Disconnetti,** l'operatore automatico ggancia la chiamata.

    Se si seleziona **Reindirizza** chiamata, è possibile scegliere una delle destinazioni di instradamento chiamate.

    Se si **selezionaNo le opzioni** del menu Riproduci, è possibile scegliere Riproduci file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni del menu e la ricerca in elenco.

    ![Schermata delle impostazioni di instradamento chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. Se si vuole che i chiamanti usino i tasti di composizione per navigare, in Imposta opzioni di **menu** scegli cosa vuoi fare quando i chiamanti premono un tasto di chiamata. Se stai creando questo operatore automatico come elenco aziendale, lascia vuote le opzioni dei tasti di composizione.

    Puoi impostare uno qualsiasi dei tasti di composizione per le destinazioni seguenti:

    - **Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali.
    - **App voce:** un altro operatore automatico o una coda di chiamata.
    - **Numero di telefono esterno:** qualsiasi numero di telefono. Usa questo formato: +[codice paese][codice area][numero di telefono]
    - **Segreteria telefonica:** cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.
    - **Operatore:** l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come una qualsiasi delle altre destinazioni dell'elenco.

    È consigliabile impostare il tasto 0 sull'operatore.

    Per ogni opzione di menu, specificare quanto segue:

    - **Tasto di composizione:** il tasto sulla tastiera del telefono per accedere a questa opzione.

    - **Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se sono abilitati gli input vocali. Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e basi". 

    - **Redirect to** - where you want the call to go when callers choose this option. Se stai effettuando il reindirizzamento a un operatore automatico o a una coda di chiamata, scegli l'account delle risorse associato.

    ![Schermata delle opzioni dei tasti di composizione](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Se desideri utilizzare questo operatore automatico come elenco aziendale, seleziona Chiamata per nome in **Ricerca** **elenco.** Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono. Qualsiasi utente online con licenza Sistema telefonico è un utente idoneo e può essere trovato con Chiamata per nome. 

    È possibile scegliere Chiamata **per interno,** tuttavia l'interno deve essere configurato in Azure Active Directory.

5. Dopo aver selezionato un'opzione **di ricerca nella directory,** fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Fase 4 - Flusso delle chiamate non in >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Passaggio 4 <br> Ore successive](#tab/after-hours)

L'orario di ufficio può essere impostato per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni durante il giorno e tutti gli orari non impostati come orario di ufficio sono considerati fuori orario. Puoi impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per il dopo orario.

A seconda di come hai configurato gli operatori automatici e le code di chiamata, potresti dover specificare l'instradamento delle chiamate in orario di instradamento solo per gli operatori automatici con numeri di telefono diretti.

Se si desidera un instradamento delle chiamate separato per i chiamanti non in orario di ufficio, specificare l'orario di ufficio per ogni giorno. Fare **clic su Aggiungi nuovo orario** per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.

![Screenshot delle impostazioni del giorno e dell'ora fuori orario](../media/auto-attendant-business-hours.png)

Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per l'orario di ufficio. Le stesse opzioni sono disponibili per l'instradamento delle chiamate in orario di ufficio specificato nel **Passaggio 3 - Flusso delle chiamate.**

Al **termine,** fare clic su Avanti.

> [!div class="nextstepaction"]
> [Passaggio 5 - Flusso delle chiamate per le >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Passaggio 5 <br> Festività](#tab/holidays)

Le chiamate all'operatore automatico possono essere instradati in modo diverso durante le festività rispetto agli altri giorni. Se non si vuole avere un flusso delle chiamate diverso per le festività, è possibile ignorare questo passaggio.



L'operatore automatico può avere un flusso delle chiamate per ogni festività impostata. È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina delle impostazioni delle chiamate per le festività fare clic su **Aggiungi.**

2. Digitare un nome per l'impostazione delle festività.

3. **Nell'elenco** a discesa Festività scegliere la festività da usare.

4. Scegliere il tipo di messaggio di saluto da usare.

    ![Screenshot delle impostazioni per le festività e le festività](../media/auto-attendant-holiday-greeting.png)

5. Scegli se vuoi disconnettere **o** **reindirizzare** la chiamata.

6. Se hai scelto di reindirizzare la chiamata, scegli la destinazione del routing delle chiamate.

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](../media/auto-attendant-holiday-actions.png)

7. Fare clic su **Salva**.

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

![Screenshot delle impostazioni delle festività con l'elenco delle festività](../media/auto-attendant-holiday-call-settings.png)

Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Passaggio 6 - Scegliere chi è nella directory >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Passaggio 6 <br> Membri della directory](#tab/dial-scope)

*L'ambito* di chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa chiamata per nome o per interno. L'impostazione predefinita **Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con licenza Sistema telefonico.

È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato in Includi o escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza.  Ad esempio, è possibile escludere i dirigenti dell'organizzazione dalla directory di composizione. Se un utente è in entrambi gli elenchi, verrà escluso dalla directory.

![Schermata delle opzioni di inclusione ed esclusione dell'ambito di chiamata](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> L'elenco dei nomi di un nuovo utente nella directory può richiedere fino a 36 ore.

Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Passaggio 7 - Assegnare un account delle risorse >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Passaggio 7 <br> Account delle risorse](#tab/resource-accounts)

Tutti gli operatori automatici devono avere un account delle risorse associato.  Gli operatori automatici di primo livello dovranno avere almeno un account delle risorse a cui è associato un numero di servizio. Se si desidera, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.

Per aggiungere un account di risorsa

1. Fare **clic su** Aggiungi account e cercare l'account che si vuole aggiungere. Fare **clic su** Aggiungi e quindi su **Aggiungi.**

    ![Screenshot del riquadro Aggiungi account dell'account della risorsa](../media/auto-attendant-add-resource-account.png)

2. Dopo aver aggiunto gli account del servizio, fare clic su **Invia.**

    ![Screenshot dell'elenco di account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

La configurazione dell'operatore automatico è stata completata.

---


