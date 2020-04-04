---
title: Installare Moodle Integration con Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come installare e configurare l'app di integrazione di Moodle per Microsoft Teams
keywords: Plug-in integrazione app di Moodle Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3ee51fdbbda7c3d49ac5a7b2a65b977f8fb245
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137136"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installazione dell'integrazione di Moodle con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), il sistema LMS (Learning Management System) più diffuso e open-source nel mondo, ora è integrato con Microsoft teams. Questa integrazione aiuta gli educatori e gli insegnanti a collaborare nei corsi di Moodle, a porre domande sulle loro qualità e alle loro assegnazioni e a rimanere aggiornati con le notifiche, proprio all'interno di teams.

Per consentire agli amministratori IT di impostare facilmente questa integrazione, è stato aggiornato il plug-in Office 365 Moodle open-source con le funzionalità seguenti:

* Registrazione automatica del server Moodle con Azure AD.
* Distribuzione con un solo clic di Moodle Assistant bot in Azure.
* Provisioning automatico dei team e sincronizzazione automatica delle iscrizioni del team per tutti o selezionare corsi Moodle.
* Installazione automatica della scheda Moodle e di Moodle Assistant bot in ogni team sincronizzato. (Presto disponibile)
* Pubblicazione con un solo clic dell'app Moodle nell'App Store private teams. (Presto disponibile)

Per altre informazioni sulle funzionalità fornite da questa integrazione [, procedere come](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)segue.

## <a name="prerequisites"></a>Prerequisiti

Per installare e configurare questa applicazione è necessario:

1. Credenziali di amministratore di Moodle
2. Credenziali di amministratore di Azure AD
3. Un abbonamento a Azure in cui è possibile creare nuove risorse

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Passaggio 1: installare il plug-in di Office 365 Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L'integrazione di Moodle in Microsoft teams è alimentata dal [set di plug-in Office 365 Moodle](https://github.com/Microsoft/o365-moodle)open source. Per installare il plug-in nel server Moodle:

1. Prima di tutto, scaricare il set di plug-in di [Office 365](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salvarlo nel computer locale. È necessario usare la versione 3,5 o successiva.
    * L'installazione del plug-in local_o365 installerà anche i plug-in [auth_oidc](https://moodle.org/plugins/auth_oidc) e [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) .
1. Accedere al server Moodle come amministratore e selezionare **Amministrazione sito** dal riquadro di spostamento sinistro.
1. Selezionare la scheda **plug** -in e quindi fare clic su **Installa plug**-in.
1. Nella sezione **install plugin from zip file** fare clic sul pulsante **Scegli un file** .
1. Selezionare le opzioni di **caricamento di un file** dal riquadro di spostamento sinistro, individuare il file scaricato sopra e fare clic su **carica**file.
1. Selezionare di nuovo l'opzione **Amministrazione sito** dal riquadro di spostamento sinistro per tornare al dashboard di amministrazione. Scorrere verso il basso fino a i plug-in **locali** e fare clic sul collegamento **Microsoft Office 365 Integration** . Tieni aperta questa pagina di configurazione in una scheda del browser separata mentre la usi per tutto il resto del processo.

Per altre informazioni, vedere come installare i plug-in Moodle nella [documentazione di Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Nota importante:** La pagina di configurazione del plug-in di Office 365 Moodle viene aperta in una scheda del browser separata durante il processo di ritorno a questo set di pagine.

*Non si ha già un sito Moodle?* Potresti voler controllare la nostra Moodle su [repository](https://github.com/azure/moodle) di Azure in cui è possibile distribuire rapidamente un'istanza di Moodle in Azure e personalizzarla in base alle proprie esigenze.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Passaggio 2: configurare la connessione tra il plug-in di Office 365 e Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Quindi devi registrare Moodle come applicazione in Azure Active Directory. È stato fornito uno script di PowerShell che consente di completare il processo. Lo script di PowerShell applica una nuova applicazione Azure AD per il tenant di Office 365, che verrà usata dal plug-in di Office 365 Moodle. Lo script provisionerà l'app per il tenant di Office 365, configurerà tutti gli URL di risposta e le autorizzazioni necessari per l'app di cui è stato eseguito il provisioning e restituirà l'AppID e la chiave. Puoi usare l'AppID e la chiave generati nella pagina di configurazione del plug-in di Office 365 Moodle per configurare il server Moodle con Azure AD. Per visualizzare i passaggi manuali dettagliati che lo script di PowerShell sta automatizzando, è possibile trovarli nella [documentazione completa per il plug](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)-in.

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Scheda Moodle per il flusso di informazioni di Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustrazione della scheda Moodle per il flusso di informazioni di Microsoft Teams" />

1. Nella pagina del plug-in di integrazione di Microsoft Office 365 Slect la scheda **Setup** .
1. Fare clic sul pulsante **Scarica script di PowerShell** e salvarlo nel computer locale.
1. È necessario preparare lo script di PowerShell dal file ZIP. Per eseguire questa operazione:
    * Scaricare ed estrarre il `Moodle-AzureAD-Powershell.zip` file.
    * Aprire la cartella estratta.
    * Fare clic con il pulsante `Moodle-AzureAD-Script.ps1` destro del mouse sul file e scegliere **Proprietà**.
    * Nella scheda **generale** della finestra Proprietà selezionare la `Unblock` casella di controllo accanto all'attributo di **sicurezza** nella parte inferiore.
    * Fare clic su **OK**.
    * Copiare il percorso della directory della cartella estratta.
1. Verrà quindi eseguito PowerShell come amministratore:
    * Fare clic su Start.
    * Digitare PowerShell.
    * Fare clic con il pulsante destro del mouse su Windows PowerShell.
    * Fare clic su "Esegui come amministratore".
1. Passare alla directory decompressa digitando `cd ...\...\Moodle-AzureAD-Powershell` `...\...` il percorso della directory.
1. Eseguire lo script di PowerShell per:
    * Invio `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Invio `.\Moodle-AzureAD-Script.ps1`.
    * Accedere all'account di amministratore di Office 365 nella finestra popup.
    * Immettere il nome dell'applicazione Azure AD (es. Plug-in Moodle/Moodle).
    * Immettere l'URL del server Moodle.
    * Copiare l' **ID applicazione** e la **chiave dell'applicazione** generati dallo script e salvarli.
1. Quindi è necessario aggiungere l'ID e la chiave al plug-in di Office 365 Moodle. Tornare alla pagina di amministrazione dei plug-in (amministrazione del sito > i plug-in > integrazione di Microsoft Office 365).
1. Nella scheda **configurazione** aggiungere l' **ID applicazione** e la **chiave dell'applicazione** copiati in precedenza, quindi fare clic su **Salva modifiche**.
1. Una volta che la pagina viene aggiornata, ora è necessario vedere una nuova sezione **scegliere il metodo di connessione**. Fare clic sulla casella di controllo contrassegnata come **predefinita** e quindi fare di nuovo clic su **Salva modifiche** .
1. Dopo l'aggiornamento della pagina verrà visualizzato un nuovo consenso per l' **amministratore della sezione & informazioni aggiuntive**.
    * Fare clic sul collegamento **Fornisci l'autorizzazione** amministratore, immettere le credenziali di amministratore globale di Office3 365, quindi **accettare** di concedere le autorizzazioni.
    * Accanto al campo **tenant di Azure ad** fare clic sul pulsante **rileva** .
    * Accanto all' **URL di OneDrive for business** fai clic sul pulsante **rileva** .
    * Dopo aver popolato i campi, fare di nuovo clic sul pulsante **Salva modifiche** .
1. Fare clic sul pulsante **Aggiorna** per verificare l'installazione e quindi **salvare le modifiche**.
1. Sarà quindi necessario sincronizzare gli utenti tra il server Moodle e Azure Active Directory. A seconda dell'ambiente, è possibile selezionare opzioni diverse durante questa fase. Tieni presente che la configurazione che hai impostato qui verrà eseguita con ogni esecuzione di Moodle cron (in genere una volta al giorno) per tenere tutto sincronizzato. Per iniziare:
    * Passare alla **scheda Impostazioni di sincronizzazione**
    * Nella sezione **Sincronizza utenti con Azure ad** selezionare le caselle di controllo valide per l'ambiente. In genere si seleziona almeno:
        * Creare account in Moodle per gli utenti in Azure AD
        * Aggiornare tutti gli account in Moodle per gli utenti in Azure AD
    * Nella sezione **restrizione per la creazione degli** utenti puoi configurare un filtro per limitare gli utenti di Azure ad che verranno sincronizzati con Moodle.
    * La sezione **mapping campi utente** ti consente di personalizzare il mapping dei campi del profilo utente di Azure ad in Moodle.
    * Nella sezione **sincronizzazione teams** è possibile scegliere di creare automaticamente gruppi (ad esempio Team) per alcuni o tutti i corsi di Moodle esistenti.
1. Per convalidare i processi di cron (ed eseguirli manualmente se si vuole per la prima esecuzione), fare clic sul collegamento **pagina Gestione attività pianificata** nella sezione **Sincronizza utenti con Azure ad** . In questo modo verrà riportata la pagina **attività pianificate** .
    * Scorrere verso il basso e trovare gli **utenti di job Sync con Azure ad** job e fare clic su **Esegui ora**.
    * Se si è scelto di creare gruppi in base a corsi esistenti, è anche possibile eseguire il processo **di creazione di gruppi di utenti in Office 365** .
1. Tornare alla pagina di amministrazione del plug-in (amministrazione sito > i plug-in > integrazione di Microsoft Office 365) e selezionare la pagina **impostazioni team** . È necessario configurare alcune impostazioni di sicurezza per abilitare l'integrazione delle app teams.
    * Per abilitare OpenID Connect, fare clic sul collegamento **Gestisci autenticazione** e fare clic sull'icona dell'occhio nella linea **OpenID Connect** se è disattivata.
    * Quindi è necessario abilitare l'incorporamento di frame. Fare clic sul collegamento **sicurezza http** , quindi fare clic sulla casella di controllo accanto a **Consenti incorporamento frame**.
    * Il passaggio successivo consiste nell'abilitare i servizi Web che consentiranno le funzionalità API di Moodle. Fare clic sul collegamento **funzionalità avanzate** , quindi verificare che la casella di controllo accanto a **Abilita servizi Web** sia selezionata.
    * Infine, è necessario abilitare i servizi esterni per Office 365. Fare clic sul collegamento **servizi esterni** , quindi:
        * Fare clic su **modifica** nella riga **Moodle Office 365 WebServices** .
        * Contrassegnare la casella di controllo accanto a **abilitata**, quindi fare clic su **Salva modifiche**
    * Sarà quindi necessario modificare le autorizzazioni degli utenti autenticati per consentire loro di creare token di servizio Web. Fare clic sul collegamento **"utente autenticato" del ruolo di modifica** . Scorrere verso il basso e individuare la funzionalità **Crea un token di servizio Web** e selezionare la casella di controllo **Consenti** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Passaggio 3: distribuire Moodle Assistant bot in Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Il Free Moodle Assistant bot per Microsoft teams aiuta gli insegnanti e gli studenti a rispondere alle domande sui corsi, le assegnazioni, i voti e altre informazioni in Moodle. Il bot invia anche le notifiche di Moodle agli studenti e agli insegnanti direttamente in teams. Questo bot è un progetto open source gestito da Microsoft ed è [disponibile su GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> In questa sezione verranno distribuite le risorse per l'abbonamento a Azure e tutte le risorse verranno configurate con il livello **libero** . A seconda dell'uso del bot, potrebbe essere necessario ridimensionare queste risorse.
> Se si vuole usare semplicemente la scheda Moodle senza il bot, passare al [passaggio 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flusso di informazioni di Moodle bot

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustrazione del flusso di informazioni di Moodle bot per Microsoft Teams" />


Per installare il bot, è necessario prima di tutto registrarlo nella [piattaforma Microsoft Identity](https://identity.microsoft.com/Landing). In questo modo il tuo bot verrà autenticato in base agli endpoint Microsoft. Per registrare il bot:

1. Tornare alla pagina di amministrazione del plug-in (amministrazione sito > i plug-in > integrazione di Microsoft Office 365) e selezionare la scheda **impostazioni team** .
1. Fare clic sul collegamento **portale di registrazione applicazioni Microsoft** ed effettuare l'accesso con il proprio ID Microsoft.
1. Immettere un nome per l'app (ad esempio. MoodleBot) e fare clic sul pulsante **Crea** .
1. Copiare l' **ID applicazione** e incollarlo nel campo **ID applicazione bot** nella pagina **impostazioni del team** .
1. Fare clic sul pulsante **genera nuova password** . Copiare la password generata e incollarla nel campo **password applicazione bot** nella pagina impostazioni del **Team** .
1. Scorrere fino alla fine della maschera e fare clic su **Salva modifiche**.

Ora che hai generato l'ID applicazione e la password, è il momento di distribuire il tuo bot in Azure. Fare clic sul pulsante **Distribuisci in Azure** e compilare il modulo con le informazioni necessarie (l'ID applicazione bot, la password dell'applicazione bot e il segreto Moodle si trovano nella pagina **impostazioni del team** e le informazioni di Azure sono nella pagina di **configurazione** ). Dopo aver compilato il modulo, fare clic sulla casella di controllo per accettare i termini e le condizioni, quindi fare clic sul pulsante **acquisto** (tutte le risorse di Azure vengono distribuite nel livello gratuito).

Dopo aver completato la distribuzione di risorse in Azure, è necessario configurare il plug-in di Office 365 Moodle con l'endpoint di messaggistica. Prima di tutto è necessario ottenere l'endpoint da bot in Azure. per farlo:

1. Se non è già stato fatto, accedere al [portale di Azure](https://portal.azure.com).
2. Nel riquadro sinistro selezionare **gruppi di risorse**.
3. Nell'elenco selezionare il gruppo di risorse appena usato (o creato) durante la distribuzione del bot.
4. Selezionare la risorsa **Web App bot** nell'elenco delle risorse del gruppo.
5. Copiare l' **endpoint della messaggistica** dalla sezione **Panoramica** .
6. In Moodle aprire la pagina **impostazioni del team** del plug-in di Office 365 Moodle.
7. Nel campo **endpoint bot** incollare l'URL appena copiato e cambiare i *messaggi* di Word in *webhook*. Ora l'URL dovrebbe essere simile`https://botname.azurewebsites.net/api/webhook`
8. Fare clic su **Salva modifiche**
9. Dopo aver salvato le modifiche, tornare alla scheda **impostazioni del team** , fare clic sul pulsante **Scarica manifesto file** e salvare il pacchetto manifesto nel computer (lo si userà nella sezione successiva).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Passaggio 4: distribuire l'app Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ora che il tuo bot è stato distribuito in Azure e configurato per comunicare con il tuo server Moodle, è il momento di distribuire l'app Microsoft teams. Per eseguire questa operazione, è possibile caricare il file manifesto scaricato dalla pagina impostazioni del plug-in di Office 365 Moodle nel passaggio precedente.

Prima di installare l'app è necessario assicurarsi che le app esterne e sideload delle app siano abilitate. Per eseguire questa procedura, è possibile eseguire [le operazioni](https://docs.microsoft.com/MicrosoftTeams/admin-settings)seguenti. Dopo avere assicurato che le app esterne sono abilitate, puoi seguire la procedura seguente per distribuire la tua app.

1. Aprire Microsoft teams.
2. Fare clic sull'icona dello **Store** nell'angolo in basso a sinistra della barra di spostamento.
3. Fare clic sul collegamento **carica un'app personalizzata** nell'elenco di opzioni. *Nota:* Se si è effettuato l'accesso come amministratore globale si avrà la possibilità di caricare l'app nell'App Store dell'organizzazione, altrimenti sarà possibile caricare l'app solo per i team che fanno parte di ("sideload").
4. Selezionare il `manifest.zip` pacchetto scaricato in precedenza e fare clic su **Salva**. Se il pacchetto manifesto non è ancora stato scaricato, è possibile farlo dalla scheda **impostazioni del team** della pagina di configurazione del plug-in in Moodle.

Ora che l'app è installata, puoi aggiungere la scheda a qualsiasi canale a cui hai accesso. Per farlo, passa al canale, fai clic sul **+** simbolo e seleziona la tua app nell'elenco. Seguire le istruzioni per completare l'aggiunta della scheda corso Moodle a un canale.

Questo è tutto! Ora puoi iniziare a lavorare con i corsi Moodle direttamente da Microsoft teams.

Per condividere eventuali richieste di funzionalità o commenti e suggerimenti, visitare la [pagina vocale dell'utente](https://microsoftteams.uservoice.com/forums/916759-moodle).