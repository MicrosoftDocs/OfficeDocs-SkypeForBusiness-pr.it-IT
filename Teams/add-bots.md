---
title: Aggiungere bot per chat e canali privati in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: lucarras, jakon
description: Informazioni su come aggiungere bot in Microsoft teams per le chat personali, le chat di gruppo e i canali e caricare i propri bot per le chat personali, i gruppi di chat e i canali.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7837fd3a832a1764cfde3968b73337069762dab3
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516835"
---
<a name="add-bots-for-personal-chats-group-chats-and-channels-in-microsoft-teams"></a>Aggiungere bot per chat personali, chat di gruppo e canali in Microsoft Teams
==========================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

I bot sono programmi automatizzati che rispondono alle query o forniscono aggiornamenti e notifiche sui dettagli che gli utenti trovano interessanti o vogliono rimanere informati. I bot consentono agli utenti di interagire con i servizi cloud, come gestione delle attività, pianificazione e polling, tramite conversazioni in chat in Microsoft teams. I bot per Teams sono basati su [Microsoft bot Framework](https://go.microsoft.com/fwlink/?linkid=854370). I bot sviluppati con questo Framework possono essere facilmente abilitati per i team. Per altre informazioni, vedere [gestire le impostazioni di Microsoft teams per l'organizzazione](enable-features-office-365.md).

Attualmente, teams supporta i bot in chat personali, chat di gruppo e canali all'interno di un team. Gli amministratori possono controllare se l'uso dei bot è consentito o vietato all'interno del tenant di Office 365.<span id="_T-Bot" class="anchor"></span>

I bot sviluppati dalla community possono essere sfruttati in teams. La funzionalità del bot e la possibilità di caricare app personalizzate (nota anche come sideload) devono essere abilitate a livello di tenant per consentire ai bot personalizzati di essere funzionali. I bot possono essere usati in chat personali, chat di gruppo e canali. Per i canali, i proprietari del team o i membri possono aggiungere bot.

Per altre informazioni, Vedi [app e servizi](https://support.office.com/article/Apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b).

> [!IMPORTANT]
> Non è consigliabile aggiungere un bot per GUID, ad eccezione degli scopi di test. Limitando la funzionalità di un bot, l'operazione viene così grave. I bot in uso di produzione devono essere aggiunti ai team come parte di un'app. Vedere [creare un bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-create) e [testare ed eseguire il debug di Microsoft teams bot](https://docs.microsoft.com/microsoftteams/platform/concepts/bots/bots-test)

<a name="create-custom-bots-for-microsoft-teams"></a>Creare bot personalizzati per Microsoft Teams
--------------------------------------

Puoi creare facilmente un bot che si integra nelle tue applicazioni line-of-business usando il Microsoft bot Framework. Per informazioni su come sviluppare e pubblicare i propri bot, vedere la Guida [per la creazione e la verifica di un bot per Microsoft teams](https://go.microsoft.com/fwlink/?linkid=854371) .

Quando crei un bot e lo registri con il Framework bot, puoi scegliere di pubblicarlo. Se non la pubblichi, il bot rimane privato. Puoi anche richiedere agli utenti di eseguire l'accesso prima di usare il bot. La richiesta di accesso garantisce che solo i dipendenti dell'organizzazione possano accedere al bot, anche se l'ID applicazione del bot diventa noto. Vedere [*AuthBot*](https://go.microsoft.com/fwlink/?linkid=854372) su GitHub per un esempio di codice che illustra come autenticare gli utenti in Active Directory usando i bot.

I bot possono essere testati usando l' [emulatore di Framework bot](https://go.microsoft.com/fwlink/?linkid=854373) prima di essere distribuiti nei team.

<a name="upload-your-bot-for-personal-chat"></a>Caricare il bot per la chat personale
---------------------------------------

1. Dopo aver creato il bot, vai alle **impostazioni dell'applicazione** per il bot che hai sviluppato e quindi, in **impostazioni app**, copia il valore dell'impostazione **MicrosoftAppId** . ![Screenshot della pagina delle impostazioni dell'applicazione per un bot](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image5.png)

2.  Nel riquadro **chat** di teams selezionare l' **icona Aggiungi chat**. In **per**incollare l' **ID app Microsoft**del tuo bot. ![Screenshot di un riquadro chat con l'ID app Microsoft evidenziato](media/Add_bots_for_private_chats_and_channels_in_Microsoft_Teams_image6.png)

3. L'ID app si risolverà nel **nome del bot** e quindi potrai iniziare una conversazione di chat con quel bot.

<a name="upload-your-bot-for-group-chats-or-channels"></a>Caricare il bot per chat di gruppo o canali
-----------------------------------

Per condividere il bot con i colleghi, ecco come aggiungerlo alle chat di gruppo o ai canali di diversi team:

1. Dopo aver [creato un pacchetto dell'app per il tuo bot](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload), Apri teams e passa al team in cui dovrai caricare il bot.
2. Aggiungere **[App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)**, app a teams.
3. In App Studio selezionare la scheda **editor manifesto** . ![screenshot della scheda Editor manifesto.](media/Adding_Bot_To_Teams.png)
4. Per aggiungere il tuo bot, in funzionalità, seleziona il bot e scegli di aggiungere un bot esistente. Scegli quindi un bot esistente o immetti l'ID di un bot esistente.
![Mostra la selezione del bot già creato.](media/Select_Existing_Bot.png)
5. Passare al percorso del pacchetto dell'app, selezionarlo e quindi fare clic su **Apri**.
6. Selezionare il nome del bot. (Non dimenticare di selezionare la casella di controllo **chat di gruppo** o **Team** nella sezione ambito).
7. Selezionare **test e Distribuisci**.
8. Selezionare la chat di gruppo o il team in cui si vuole connettere il bot.

    Il tuo bot sarà disponibile nella chat di gruppo o nel team in teams.
