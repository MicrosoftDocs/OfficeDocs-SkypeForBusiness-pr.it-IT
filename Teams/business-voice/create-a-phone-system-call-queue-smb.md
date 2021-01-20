---
title: Creare una coda di chiamata in Microsoft teams-esercitazione sulle piccole imprese
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
description: Informazioni su come configurare le code di chiamata con Microsoft 365 Business Voice.
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909635"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>Creare una coda di chiamata-esercitazione sulle piccole imprese

Le code di chiamata offrono un metodo per indirizzare i chiamanti alle persone dell'organizzazione che possono aiutarti con un problema o una domanda particolare. Le chiamate vengono distribuite una alla volta per gli utenti della coda (noti come *agenti*). 

Le code di chiamata includono:

- Messaggio di saluto.

- Musica mentre gli utenti attendono il blocco in una coda.

- Chiamata routing-in *First in, First out* (FIFO) Order-to Agents.

- Opzioni di gestione per l'overflow e il timeout delle code.

#### <a name="before-you-begin"></a>Prima di iniziare

Ottenere alcune [licenze per gli utenti virtuali nel sistema telefonico,](../teams-add-on-licensing/virtual-user.md) se non sono già disponibili. Ottenere uno per ogni coda di chiamata e operatore automatico che si prevede di configurare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche extra nel caso in cui decidi di apportare modifiche alla configurazione in futuro.

Poiché gli agenti in una coda di chiamata possono effettuare chiamate in uscita per restituire una chiamata al cliente, è consigliabile impostare l'ID chiamante per gli agenti di chiamata sul numero di telefono principale o sul numero di un operatore automatico appropriato. Per altre informazioni, vedere [gestire i criteri di ID chiamante in Microsoft teams](../caller-id-policies.md) .

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>Seguire questa procedura per configurare la coda di chiamata

# <a name="step-1brcreate-a-team"></a>[Passaggio 1 <br> creare un team](#tab/create-team)

Quando si crea una coda di chiamata, è possibile aggiungere singoli utenti alla coda oppure usare un gruppo di sicurezza esistente, un gruppo Microsoft 365 o un team di Microsoft teams. È consigliabile usare un team. Ciò consente ai membri della coda di chattare tra loro, condividere idee e creare documenti o altre risorse per aiutarli a aiutare i clienti. Un team offre anche una cassetta postale vocale per i chiamanti che lasciano un messaggio dopo le ore o se la coda raggiunge la sua capacità massima.

Per creare un team

1. Prima di tutto, fai clic su **Teams** sul lato sinistro dell'app, quindi fai clic su **partecipa o crea un team** nella parte inferiore dell'elenco teams.

2. Quindi fare clic su **Crea team** (prima carta, angolo in alto a sinistra).

3. Scegliere **Crea un team da zero**.

4. Scegliere quindi se si vuole un team pubblico o privato. È consigliabile **private** per la coda di chiamata per evitare che gli utenti involontariamente partecipino alla coda unendo il team.

5. Assegnare un nome al team e aggiungere una descrizione facoltativa.

6. Al termine, fare clic su **Crea**.

8. Digitare i nomi delle persone che si desidera includere nella coda di chiamata e quindi fare clic su **Aggiungi**.

9. Fare clic su **Chiudi**. Gli utenti aggiunti a un team riceveranno un messaggio di posta elettronica che informa che ora sono membri del team e che il team verrà visualizzato nell'elenco teams.

> [!div class="nextstepaction"]
> [Passaggio 2->degli account risorse ](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[<br>Account delle risorse del passaggio 2](#tab/resource-account)

Ogni coda di chiamata creata richiede un account di risorse. Questo è simile a un account utente, ad eccezione del fatto che l'account è associato a un operatore automatico o a una coda di chiamata invece che a una persona. In questo passaggio creeremo l'account, gli assegnaremo un *sistema telefonico Microsoft 365-* licenza per gli utenti virtuali e lo useremo per iniziare a creare la coda di chiamata.

### <a name="create-a-resource-account"></a>Creare un account di risorse

È possibile creare un account risorse nell'interfaccia di amministrazione di teams.

1. Nell'interfaccia di amministrazione di teams espandere **impostazioni a livello di organizzazione** e quindi fare clic su **account risorse**.

2. Fare clic su **Aggiungi**.

3. Nel riquadro **Aggiungi account risorse** compilare **nome visualizzato**, **nomeutente** e scegliere **coda di chiamata** per il **tipo di account risorse**.

    ![Screenshot dell'interfaccia utente Aggiungi account risorse](../media/resource-account-add-cq.png)

4. Fare clic su **Salva**.

Il nuovo account verrà visualizzato nell'elenco degli account.

![Screenshot di un elenco di account delle risorse](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>Assegnare una licenza

È necessario assegnare un *sistema telefonico Microsoft 365-licenza utente virtuale* per l'account delle risorse.

1. Nell'interfaccia di amministrazione di Microsoft 365 fare clic sull'account delle risorse a cui si vuole assegnare una licenza.

2. Nella scheda **licenze e app** , in **licenze**, selezionare **Microsoft 365 Phone System-Virtual User**.

3. Fare clic su **Salva modifiche**.

    ![Screenshot dell'interfaccia utente di assegnazione licenze nell'area di amministrazione di Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>Creare una coda di chiamata

Inizieremo quindi a creare una nuova coda di chiamata e ad assegnare l'account delle risorse.

1. Nell'interfaccia di amministrazione di teams espandere **Voice**, fare clic su **code di chiamata** e quindi fare clic su **Aggiungi**.

1. Digitare un nome per la coda di chiamata. Gli agenti vedranno questo nome quando ricevono una chiamata in arrivo dalla coda.

2. Fare clic su **Aggiungi account**, cercare l'account risorse che si vuole usare con la coda di chiamata, fare clic su **Aggiungi** e quindi fare clic su **Aggiungi**.

3. Scegliere una lingua. Questa lingua verrà usata per le istruzioni vocali generate dal sistema e la trascrizione della segreteria telefonica (se abilitate).

    ![Screenshot delle impostazioni dell'account delle risorse e della lingua](../media/call-queue-name-language.png)

4. Specificare se si vuole riprodurre un saluto ai chiamanti quando arrivano in coda. È necessario caricare un file MP3, WAV o WMA contenente il messaggio di saluto che si vuole riprodurre.

5. Teams offre musica predefinita ai chiamanti mentre sono in attesa in una coda. Se si vuole riprodurre un file audio specifico, scegliere **Riproduci un file audio** e caricare un file MP3, WAV o WMA.

> [!NOTE]
> La registrazione caricata non può essere superiore a 5 MB.
> La musica predefinita fornita nelle code delle chiamate di teams è priva di qualsiasi royalties pagabile dall'organizzazione. 

> [!div class="nextstepaction"]
> [Passaggio 3-chiamare gli agenti >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[Passaggio 3 <br> chiama agenti](#tab/call-agents)

Per aggiungere agenti alla coda di chiamata, aggiungiamo il team creato in precedenza.

1. Fare clic su **Aggiungi gruppi**.
2. Digitare il nome del team creato.
3. Fare clic su **Aggiungi** e quindi su **Aggiungi**.

    ![Screenshot delle impostazioni di utenti e gruppi per le code di chiamata](../media/call-queue-users-groups-smb.png)

È possibile aggiungere fino a 20 agenti singolarmente e fino a 200 agenti tramite gruppi o team.

> [!NOTE]
> Quando si aggiungono nuovi utenti al team, possono essere necessarie fino a otto ore per la prima chiamata in arrivo.

> [!div class="nextstepaction"]
> [Passaggio 4->degli account risorse ](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[Passaggio 4 <br> chiamata di routing](#tab/call-routing)

Scegliere il metodo di routing delle chiamate che si vuole usare.

1. Impostare la **modalità conferenza** su **auto**.

2. Scegliere il **metodo di routing** che si vuole usare. In questo modo viene determinato l'ordine in cui gli agenti ricevono chiamate dalla coda. È consigliabile un **routing seriale** o  **Round Robin**. Scegliere una delle opzioni seguenti:

    - Il **routing di Attendant** squilla tutti gli agenti della coda contemporaneamente. Il primo agente di chiamata a prendere la chiamata riceve la chiamata.

    - Il **routing seriale** squilla tutti gli agenti di chiamata uno alla volta. Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.

    - **Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda. Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.

    - Le rotte **inattive più lunghe** ogni chiamata all'agente che è stato inattivo il tempo più lungo. Gli agenti il cui stato presenza è stato assente per più di 10 minuti non sono inclusi.

    ![Screenshot della modalità conferenza e delle impostazioni del metodo di routing](../media/call-queue-conference-mode-routing-method.png)

3. Attivare il **routing basato sulla presenza** . Questo instrada le chiamate agli agenti di cui è **disponibile** lo stato presenza.

4. Scegliere se si vuole consentire agli agenti di rifiutare le chiamate.

5. Impostare il **tempo di avviso** di un agente per specificare la durata dell'interlinea telefonica di un agente prima che la chiamata venga reindirizzata all'agente successivo.

    ![Screenshot delle impostazioni di routing, disattivazione e ora di avviso](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [Passaggio 5->di overflow delle chiamate ](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[Passaggio 5- <br> overflow delle chiamate](#tab/call-overflow)

Scegliere la modalità di gestione delle chiamate che superano il massimo nella coda.

1. Impostare le **chiamate massime nella coda**.

2. Scegliere cosa si vuole fare quando viene raggiunto il numero massimo di chiamate. È possibile disconnettere la chiamata o reindirizzarla. È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:
    - **Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali
    - **App vocale** : un operatore automatico o un'altra coda di chiamata. Scegliere l'account delle risorse associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
    - **Numero di telefono esterno** -qualsiasi numero di telefono. Usare questo formato: + [codice paese] [prefisso] [numero di telefono]
    - **Segreteria telefonica** : è possibile usare la cassetta postale vocale del team creato.

    ![Screenshot delle impostazioni di overflow delle chiamate](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [Passaggio 6-Timeout chiamata >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[Passaggio 6 <br> timeout chiamata](#tab/call-timeout)

Scegliere cosa si vuole fare quando le chiamate sono state attese in coda troppo a lungo.

1. Impostare il **timeout della chiamata: tempo massimo di attesa**.

2. Scegliere cosa si vuole fare quando si esce da una chiamata. È possibile disconnettere la chiamata o reindirizzarla. È consigliabile reindirizzare la chiamata a una delle destinazioni seguenti:
    - **Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali
    - **App vocale** : un operatore automatico o un'altra coda di chiamata. Scegliere l'account delle risorse associato all'operatore automatico o alla coda di chiamata quando si sceglie questa destinazione.
    - **Numero di telefono esterno** -qualsiasi numero di telefono. Usare questo formato: + [codice paese] [prefisso] [numero di telefono]
    - **Segreteria telefonica** : è possibile usare la cassetta postale vocale del team creato.

    ![Screenshot delle impostazioni di timeout delle chiamate](../media/call-queue-timeout-handling.png)

3. Fare clic su **Salva**.

In questo articolo viene completata la configurazione della coda di chiamata. È quindi consigliabile [configurare un operatore automatico](create-a-phone-system-auto-attendant-smb.md).

---

