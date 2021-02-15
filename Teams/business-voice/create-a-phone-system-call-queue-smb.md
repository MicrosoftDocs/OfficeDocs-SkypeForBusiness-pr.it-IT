---
title: Creare una coda di chiamata in Microsoft Teams - esercitazione aziendale
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
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Scopri come impostare code di chiamata con Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909635"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>Creare una coda di chiamata - esercitazione per piccole aziende

Le code di chiamata sono un metodo per instradare i chiamanti all'interno dell'organizzazione che possono aiutare a risolvere un particolare problema o domanda. Le chiamate vengono distribuite una alla volta alle persone in coda (che sono noti come *agenti).* 

Le code di chiamata forniscono:

- Un messaggio di saluto.

- Musica persone sono in attesa di blocco in una coda.

- Instradamento delle chiamate ( in *ordine FIFO ,First In, First Out)* - agli agenti.

- Opzioni di gestione per l'overflow e il timeout della coda.

#### <a name="before-you-begin"></a>Prima di iniziare

Ottieni alcune [licenze Sistema telefonico - Utente virtuale,](../teams-add-on-licensing/virtual-user.md) se non le hai già. Ottieni un'opzione per ogni coda di chiamata e operatore automatico che hai intenzione di impostare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore prodotto se decidi di apportare modifiche alla configurazione in futuro.

Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato. Per [altre informazioni, vedere Gestire i criteri ID chiamante in Microsoft Teams.](../caller-id-policies.md)

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>Seguire questa procedura per impostare la coda di chiamata

# <a name="step-1brcreate-a-team"></a>[Passaggio <br> 1: Creare un team](#tab/create-team)

Quando crei una coda di chiamata, puoi aggiungere singoli utenti alla coda oppure puoi utilizzare un gruppo di sicurezza esistente, un gruppo di Microsoft 365 o un team di Microsoft Teams. È consigliabile usare un team. In questo modo i membri della coda possono chattare tra loro, condividere idee e creare documenti o altre risorse per aiutarli a aiutare i clienti. Un team fornisce anche una cassetta postale vocale in cui i chiamanti possono lasciare un messaggio fuori orario o se la coda raggiunge la sua capacità massima.

Per creare un team

1. Prima di tutto, fai clic su **Teams** sul lato sinistro dell'app, quindi fai clic su **Partecipa o crea** un team in fondo all'elenco dei team.

2. Quindi fai **clic su Crea team** (prima scheda, angolo in alto a sinistra).

3. Scegliere **Crea un team da zero.**

4. Successivamente, scegliere se si vuole un team pubblico o privato. Si consiglia **di usare** il servizio privato per la coda di chiamata per evitare che le persone diventino involontariamente parte della coda partecipando al team.

5. Assegnare un nome al team e aggiungere una descrizione facoltativa.

6. Al termine, fare clic su **Crea.**

8. Digita i nomi delle persone che desideri inserire nella coda di chiamata, quindi fai clic su **Aggiungi.**

9. Fare clic **su Chiudi.** Le persone che si aggiungono a un team riceveranno un messaggio di posta elettronica che le informa che sono ora membri del team e il team verrà visualizzato nell'elenco dei team.

> [!div class="nextstepaction"]
> [Passaggio 2 - Account delle risorse >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[Account delle risorse del passaggio 2 <br>](#tab/resource-account)

Per ogni coda di chiamata creata è necessario un account delle risorse. È simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona. In questo passaggio creeremo l'account, gli assegniamo una licenza Sistema telefonico *Microsoft 365 -* Utente virtuale e quindi lo useremo per iniziare a creare la coda di chiamata.

### <a name="create-a-resource-account"></a>Creare un account delle risorse

È possibile creare un account delle risorse nell'interfaccia di amministrazione di Teams.

1. Nell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di organizzazione** e quindi fare clic su Account **risorse.**

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorsa,** compilare **Nome** visualizzato **,** Nome utente e scegliere Coda di chiamata **per** il tipo di account **risorsa.**

    ![Screenshot dell'interfaccia utente aggiungi account risorsa](../media/resource-account-add-cq.png)

4. Fare clic su **Salva**.

Il nuovo account verrà visualizzato nell'elenco degli account.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Assegnare una licenza

È necessario assegnare una *licenza Sistema telefonico Microsoft 365 -* Utente virtuale all'account delle risorse.

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account della risorsa a cui si vuole assegnare una licenza.

2. Nella scheda **Licenze e app,** in **Licenze,** selezionare Sistema telefonico **Microsoft 365 - Utente virtuale.**

3. Fare clic **su Salva modifiche.**

    ![Screenshot dell'interfaccia utente Assegna licenze nell'interfaccia di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>Creare una coda di chiamata

A questo punto, inizieremo a creare una nuova coda di chiamata e ad assegnare l'account delle risorse.

1. Nell'interfaccia di amministrazione di Teams espandi **Voce,** fai clic su **Code di** chiamata, quindi fai clic su **Aggiungi.**

1. Digitare un nome per la coda di chiamata. Gli agenti riceveranno questo nome quando ricevono una chiamata in arrivo dalla coda.

2. Fare **clic su Aggiungi** account, cercare l'account delle risorse da usare con questa coda di chiamata, fare clic su Aggiungi e quindi su **Aggiungi.** 

3. Scegliere una lingua. Questa lingua verrà utilizzata per i comandi vocali generati dal sistema e per la trascrizione della segreteria telefonica (se li abiliti).

    ![Screenshot delle impostazioni dell'account della risorsa e della lingua](../media/call-queue-name-language.png)

4. Specificare se si vuole riprodurre un messaggio di saluto ai chiamanti quando arrivano in coda. È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto da riprodurre.

5. Teams offre musica predefinita ai chiamanti mentre sono in attesa in coda. Se si vuole riprodurre un file audio specifico, scegliere Riproduci **un file audio** e caricare un file MP3, WAV o WMA.

> [!NOTE]
> Le dimensioni della registrazione caricata non possono essere superiori a 5 MB.
> La musica predefinita fornita nelle code di chiamata di Teams è gratuita di tutte le royalties pagate dall'organizzazione. 

> [!div class="nextstepaction"]
> [Fase 3 - Chiamare gli agenti >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[Passaggio <br> 3: Agenti di chiamata](#tab/call-agents)

Per aggiungere agenti alla coda di chiamata, aggiungeremo il team che abbiamo creato in precedenza.

1. Fare **clic su Aggiungi gruppi.**
2. Digitare il nome del team creato.
3. Fare **clic su** Aggiungi e quindi su **Aggiungi.**

    ![Schermata delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups-smb.png)

È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 tramite gruppi o team.

> [!NOTE]
> Quando vengono aggiunti nuovi utenti al team, per l'arrivo della prima chiamata possono essere necessario fino a otto ore.

> [!div class="nextstepaction"]
> [Passaggio 4 - Account delle risorse >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[Passaggio 4 Routing <br> delle chiamate](#tab/call-routing)

Scegliere il metodo di instradamento chiamate da usare.

1. Impostare **la modalità conferenza** su **Auto.**

2. Scegliere **il metodo** di instradamento da usare. Determina l'ordine in cui gli agenti ricevono le chiamate dalla coda. È consigliabile **il routing seriale** **o il round robin.** Scegliere una delle opzioni seguenti:

    - **Il routing** dell'operatore chiama tutti gli agenti nella coda contemporaneamente. Il primo agente di chiamata a ritirare la chiamata riceve la chiamata.

    - **L'instradamento** seriale squilla tutti gli agenti di chiamata uno alla volta. Se un agente ignora o non riceve una chiamata, la chiamata squillerà sul successivo agente e proverà tutti gli agenti fino al ritiro o al timeout.

    - **Round Robin** bilancia l'instradamento delle chiamate in arrivo in modo che ogni agente di chiamata riceve lo stesso numero di chiamate dalla coda. Può essere desiderabile in un ambiente di vendita in entrata per assicurare la stessa opportunità tra tutti gli agenti di chiamata.

    - **L'inattività** più lunga instrada ogni chiamata all'agente che è rimasto inattivo più a lungo. Gli agenti il cui stato presenza è Fuori rete da più di 10 minuti non sono inclusi.

    ![Schermata delle impostazioni per la modalità conferenza e il metodo di instradamento](../media/call-queue-conference-mode-routing-method.png)

3. Attivare **il routing basato sulla** presenza. In questo modo le chiamate vengono instrade agli agenti il cui stato presenza è **Disponibile.**

4. Scegli se consentire agli agenti di rifiutare esplicitamente le chiamate.

5. Imposta un **orario di avviso per l'agente** per specificare per quanto tempo il telefono di un agente squillerà prima che la coda reindirizza la chiamata all'agente successivo.

    ![Screenshot delle impostazioni per l'instradamento, il rifiuto esplicito e l'ora degli avvisi](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [Fase 5 - Overflow della chiamata >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[Passaggio 5 <br> Overflow chiamata](#tab/call-overflow)

Scegliere come gestire le chiamate che superano il valore massimo in coda.

1. Impostare il **numero massimo di chiamate in coda.**

2. Scegli l'operazione da eseguire quando viene raggiunto il numero massimo di chiamate. Puoi disconnettere la chiamata o reindirizzarla. È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:
    - **Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali
    - **App voce:** un operatore automatico o un'altra coda di chiamata. Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
    - **Numero di telefono esterno:** qualsiasi numero di telefono. Usa questo formato: +[codice paese][codice area][numero di telefono]
    - **Casella vocale:** è possibile usare la casella vocale del team creato.

    ![Schermata delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [Fase 6 - Timeout della chiamata >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[Passaggio 6 <br> Timeout chiamata](#tab/call-timeout)

Scegli cosa vuoi fare quando le chiamate sono in coda da troppo tempo.

1. Impostare il **timeout della chiamata: tempo massimo di attesa.**

2. Scegli l'operazione da eseguire al timeout di una chiamata. Puoi disconnettere la chiamata o reindirizzarla. È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:
    - **Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali
    - **App voce:** un operatore automatico o un'altra coda di chiamata. Scegliere l'account della risorsa associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
    - **Numero di telefono esterno:** qualsiasi numero di telefono. Usa questo formato: +[codice paese][codice area][numero di telefono]
    - **Casella vocale:** è possibile usare la casella vocale del team creato.

    ![Schermata delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. Fare clic su **Salva**.

L'impostazione della coda di chiamata viene completata. Successivamente, puoi impostare [un operatore automatico.](create-a-phone-system-auto-attendant-smb.md)

---

