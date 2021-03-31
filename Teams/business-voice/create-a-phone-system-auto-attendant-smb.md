---
title: Configurare un operatore automatico per Microsoft Teams - Esercitazione su Small Business
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
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
ms.openlocfilehash: fef89971ad99dff15332905d6f9b98a343af6ffd
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439721"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>Configurare un operatore automatico - Esercitazione sulle piccole imprese

Gli operatori automatici consentono alle persone di chiamare l'organizzazione e navigare in un sistema di menu per parlare al reparto, alla coda di chiamata, alla persona o a un operatore giusto. È possibile creare operatori automatici per l'organizzazione con l'interfaccia di amministrazione di Microsoft Teams.

#### <a name="before-you-begin"></a>Prima di iniziare

Ottenere i numeri di servizio necessari per gli operatori automatici a cui si vuole accedere tramite chiamata diretta dall'esterno dell'organizzazione. Questo può includere [il trasferimento di numeri da un altro provider o](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) la richiesta di nuovi numeri di [servizio.](../getting-service-phone-numbers.md)

Ottenere una [licenza Sistema telefonico - Utente virtuale](../teams-add-on-licensing/virtual-user.md) per ogni operatore automatico che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere un po' di più se decidi di apportare modifiche alla configurazione in futuro.

Se si vuole che l'operatore automatico instradi le chiamate in modo diverso durante le festività, creare le festività da usare prima di creare l'operatore automatico. [](../set-up-holidays-in-teams.md)

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Seguire questa procedura per configurare l'operatore automatico

# <a name="step-1brphone-number"></a>[Passaggio 1 <br> Numero di telefono](#tab/phone-number)

Ogni operatore automatico creato richiede un account della risorsa. È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona. In questo passaggio verrà creato l'account, verrà assegnato un sistema telefonico *Microsoft 365 -* licenza utente virtuale e quindi verrà assegnato un numero di servizio.

### <a name="create-a-resource-account"></a>Creare un account della risorsa

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

1. Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorsa** compilare **Nome** visualizzato , Nome **utente** e scegliere **Operatore** automatico per il **tipo di account risorsa**

    ![Screenshot dell'interfaccia utente per l'aggiunta di un account di risorsa](../media/resource-account-add.png)

4. Fare clic su **Salva**.

Il nuovo account verrà visualizzato nell'elenco degli account.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Assegnare una licenza

È necessario assegnare una licenza Sistema telefonico - Utente virtuale di *Microsoft 365* all'account della risorsa.

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.

2. Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**

3. Fare clic **su Salva modifiche**.

    ![Screenshot dell'interfaccia utente per l'assegnazione delle licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>Assegnare un numero di servizio

Se è necessario che questo operatore automatico sia raggiungibile da un numero di telefono, assegnare tale numero all'account della risorsa.

1. Nella pagina Account risorse  dell'interfaccia di amministrazione di Teams selezionare l'account della risorsa a cui si vuole assegnare un numero di servizio e quindi fare clic su **Assegna/annulla assegnazione.**

2. **Nell'elenco a discesa Tipo** di numero di telefono scegliere il tipo di numero da usare.

3. Nella casella **Numero di telefono assegnato** cercare il numero da usare e fare clic su **Aggiungi.**

    ![Screenshot dell'interfaccia utente assegna numero di servizio](../media/resource-account-assign-phone-number.png)

4. Fare clic su **Salva**.

> [!div class="nextstepaction"]
> [Passaggio 2 - Informazioni generali sull'operatore automatico >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Passaggio 2 <br> Informazioni generali su Attendant](#tab/general-info)

Per configurare un operatore automatico

1. Nell'interfaccia di amministrazione di Teams espandere **Voce,** fare clic su **Operatori automatici** e quindi su **Aggiungi.**

2. Digitare un nome per l'operatore automatico nella casella in alto.

3. Se si vuole designare un operatore, specificare la destinazione per le chiamate all'operatore. Questa opzione è facoltativa (ma consigliata). È possibile impostare **l'opzione Operatore** per consentire ai chiamanti di uscire dal menu e parlare con una persona designata.

4. Specificare il fuso orario per questo operatore automatico. Il fuso orario viene usato per calcolare l'orario di ufficio se si crea un flusso di chiamata separato per le ore successive.

5. Specificare una lingua per l'operatore automatico. Questa è la lingua che verrà usata per le istruzioni vocali generate dal sistema.

6. Scegliere se abilitare gli input vocali. Se abilitata, il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale. Ad esempio, i chiamanti possono pronunciare "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure pronunciare "Vendite" per selezionare l'opzione di menu denominata "Vendite".

    ![Screenshot delle impostazioni dell'operatore automatico per nome, operatore, fuso orario, lingua e input vocali](../media/auto-attendant-general-info-page-new.png)

7. Fare clic su **Avanti**.

> [!div class="nextstepaction"]
> [Passaggio 3 - Flusso di chiamate >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Passaggio 3 <br> Flusso delle chiamate](#tab/call-flow)

Scegliere le opzioni del flusso di chiamata

1. Scegliere se si vuole riprodurre un messaggio di saluto quando l'operatore automatico risponde a una chiamata.

    Se si seleziona **Riproduci un file audio,** è possibile usare il pulsante Carica **file** per caricare un messaggio di saluto registrato salvato come audio in . WAV, . MP3 o . Formato WMA. La registrazione non può essere superiore a 5 MB.

    Se si seleziona Digita un messaggio di saluto, il sistema leggerà il testo digitato (fino **a** 1000 caratteri) quando l'operatore automatico risponde a una chiamata.

    ![Screenshot delle impostazioni dei messaggi di saluto](../media/auto-attendant-call-flow-greeting-message.png)

2. Scegli come instradare la chiamata.

    Se si seleziona **Disconnetti**, l'operatore automatico riaggancia la chiamata.

    Se si seleziona **Reindirizza chiamata,** è possibile scegliere una delle destinazioni di routing delle chiamate.

    Se si seleziona **Opzioni di menu** Riproduci , è possibile scegliere Riproduci un file **audio** o Digitare **un** messaggio di saluto e quindi scegliere tra le opzioni di menu e la ricerca nella directory.

    ![Screenshot delle impostazioni di routing delle chiamate](../media/auto-attendant-call-flow-route-call-message.png)

3. Se si vuole che i chiamanti usino i tasti di chiamata per spostarsi, in Imposta opzioni **di menu** scegliere cosa si vuole fare quando i chiamanti premono un tasto di chiamata. Se si sta creando questo operatore automatico come elenco aziendale, lasciare vuote le opzioni dei tasti di composizione.

    È possibile impostare uno dei tasti di chiamata per le destinazioni seguenti:

    - **Persona dell'organizzazione:** una persona dell'organizzazione che è in grado di ricevere chiamate vocali.
    - **App vocale:** un altro operatore automatico o una coda di chiamata.
    - **Numero di telefono esterno:** qualsiasi numero di telefono. Usare questo formato: +[codice paese][codice area][numero di telefono]
    - **Segreteria telefonica:** la cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.
    - **Operatore:** l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. L'operatore può essere definito come qualsiasi altra destinazione in questo elenco.

    È consigliabile impostare il tasto 0 sull'operatore.

    Per ogni opzione di menu, specificare quanto segue:

    - **Tasto di composizione:** il tasto sul tastierino del telefono per accedere a questa opzione.

    - **Comando vocale:** definisce il comando vocale che un chiamante può fornire per accedere a questa opzione, se gli input vocali sono abilitati. Può contenere più parole, ad esempio "Servizio clienti" o "Operazioni e motivi". 

    - **Reindirizza** a- dove vuoi che la chiamata vada quando i chiamanti scelgono questa opzione. Se si esegue il reindirizzamento a un operatore automatico o a una coda di chiamata, scegliere l'account della risorsa associato.

    ![Screenshot delle opzioni dei tasti di scelta](../media/auto-attendant-call-flow-menu-options-complete.png)

4. Se si vuole usare questo operatore automatico come directory aziendale, in **Ricerca directory** selezionare Chiama **per nome.** Quando si abilita questa opzione, i chiamanti possono pronunciare il nome dell'utente o digitarlo sulla tastiera del telefono. Qualsiasi utente online con licenza Sistema telefonico è un utente idoneo e può essere trovato con Chiama per nome. 

    È possibile scegliere Chiama **per interno,** tuttavia l'estensione deve essere configurata in Azure Active Directory.

5. Dopo aver selezionato **un'opzione di ricerca nella directory,** fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Passaggio 4 - Flusso di chiamate dopo l'>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Passaggio 4 <br> Dopo ore](#tab/after-hours)

È possibile impostare l'orario di ufficio per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni di orario durante il giorno e tutte le ore non impostate come ore lavorative vengono considerate dopo l'orario. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto per le ore successive.

A seconda di come sono stati configurati gli operatori automatici e le code di chiamata, potrebbe essere necessario specificare solo l'instradamento dopo l'orario di chiamata per gli operatori automatici con numeri di telefono diretti.

Se si vuole un instradamento delle chiamate separato per i chiamanti non lavorativi, specificare l'orario di ufficio per ogni giorno. Fare **clic su Aggiungi nuova** ora per specificare più set di ore per un determinato giorno, ad esempio per specificare una pausa pranzo.

![Screenshot delle impostazioni del giorno e dell'ora dopo l'ora](../media/auto-attendant-business-hours.png)

Dopo aver specificato l'orario di ufficio, scegliere le opzioni di instradamento delle chiamate per le ore successive. Sono disponibili le stesse opzioni per l'instradamento delle chiamate in orario di ufficio specificato nel **passaggio 3 - Flusso chiamate.**

Al **termine,** fare clic su Avanti.

> [!div class="nextstepaction"]
> [Passaggio 5 - Flusso delle chiamate natalizie >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Passaggio 5 <br> Festività](#tab/holidays)

Le chiamate all'operatore automatico possono essere instradati in modo diverso nei giorni festivi rispetto agli altri giorni. Se non si vuole avere un flusso di chiamate diverso per le festività, è possibile saltare questo passaggio.



L'operatore automatico può avere un flusso di chiamate per ogni festività impostata. È possibile aggiungere fino a 20 giorni festivi pianificati per ogni operatore automatico.

1. Nella pagina Impostazioni chiamata per le festività fare clic su **Aggiungi.**

2. Digitare un nome per questa impostazione di festività.

3. **Nell'elenco a** discesa Festività scegliere la festività da usare.

4. Scegliere il tipo di messaggio di saluto da usare.

    ![Screenshot delle impostazioni per le festività e le festività](../media/auto-attendant-holiday-greeting.png)

5. Scegliere se disconnettere **o** **reindirizzare** la chiamata.

6. Se si sceglie di reindirizzare la chiamata, scegliere la destinazione del routing delle chiamate per la chiamata.

    ![Screenshot delle impostazioni delle azioni di chiamata per le festività](../media/auto-attendant-holiday-actions.png)

7. Fare clic su **Salva**.

Ripetere la procedura in base alle esigenze per ogni festività aggiuntiva.

![Screenshot delle impostazioni delle festività con le festività elencate](../media/auto-attendant-holiday-call-settings.png)

Dopo aver aggiunto tutte le festività, fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Passaggio 6 - Scegliere chi è nella directory >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Passaggio 6 <br> Membri della directory](#tab/dial-scope)

*L'ambito di* chiamata definisce quali utenti sono disponibili nella directory quando un chiamante usa la chiamata per nome o la chiamata per interno. L'impostazione predefinita **di Tutti gli utenti online** include tutti gli utenti dell'organizzazione che sono utenti online con una licenza Sistema telefonico.

È possibile includere o escludere utenti specifici  selezionando  Gruppo di utenti personalizzato **in** Includi o Escludi e scegliendo uno o più gruppi di Microsoft 365, liste di distribuzione o gruppi di sicurezza. Ad esempio, è consigliabile escludere i dirigenti dell'organizzazione dalla directory di composizione. Se un utente si trova in entrambi gli elenchi, verrà escluso dalla directory.

![Screenshot delle opzioni di inclusione ed esclusione dell'ambito di chiamata](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> L'elenco del nome di un nuovo utente nella directory potrebbe richiedere fino a 36 ore.

Dopo aver impostato l'ambito di chiamata, fare clic su **Avanti.**

> [!div class="nextstepaction"]
> [Passaggio 7 - Assegnare un account >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Passaggio 7 <br> Account delle risorse](#tab/resource-accounts)

A tutti gli operatori automatici deve essere associato un account di risorsa.  Gli operatori automatici di primo livello dovranno avere almeno un account della risorsa a cui è associato un numero di servizio. Se si vuole, è possibile assegnare più account delle risorse a un operatore automatico, ognuno con un numero di servizio distinto.

Per aggiungere un account della risorsa

1. Fare **clic su Aggiungi account** e cercare l'account da aggiungere. Fare **clic su** Aggiungi e quindi su **Aggiungi.**

    ![Screenshot del riquadro Aggiungi account dell'account della risorsa](../media/auto-attendant-add-resource-account.png)

2. Dopo aver aggiunto gli account del servizio, fare clic su **Invia.**

    ![Screenshot dell'elenco degli account delle risorse che mostra l'account della risorsa con il numero di servizio assegnato](../media/auto-attendant-resource-account-assigned.png)

La configurazione dell'operatore automatico viene completata.

---


