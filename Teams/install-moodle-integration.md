---
title: Installare l'integrazione di Moodle con Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come installare e configurare l'app open source Moodle Learning Management System (LMS) per Microsoft Teams.
keywords: Teams Plug-in di integrazione dell'app Moodle
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fca7bc34eeaf0f7b2c6bd552038b9b2567c872351d91c264936ec9072957bc2b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344019"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installazione dell'integrazione moodle con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle,](https://moodle.org/)il sistema Learning Management System (LMS) più popolare e open source al mondo, è ora integrato con Microsoft Teams! Questa integrazione consente a docenti e docenti di collaborare intorno ai corsi moodle, porre domande sui voti e sulle attività e rimanere aggiornati con le notifiche, direttamente all'interno di Teams!

Per aiutare gli amministratori IT a configurare facilmente questa integrazione, abbiamo aggiornato il plug-in Moodle open source con le funzionalità seguenti:

* Registrazione automatica del server Moodle con Azure AD.
* Distribuzione con un solo clic del bot assistente Moodle in Azure.
* Provisioning automatico dei team e sincronizzazione automatica delle iscrizioni al team per tutti i corsi moodle o selezionati.
* Installazione automatica della scheda Moodle e del bot Assistente Moodle in ogni team sincronizzato. (Prossimamente)
* Pubblicazione con un solo clic dell'app Moodle nel Teams App Store. (Prossimamente)

Per altre informazioni sulle funzionalità fornite da questa integrazione, vedere Installazione [dell'integrazione moodle con Microsoft Teams.](/microsoftteams/platform/resources/moodleinstructions)

## <a name="prerequisites"></a>Prerequisiti

Per installare e configurare questa applicazione, è necessario:

1. Credenziali di amministratore moodle
2. Credenziali di amministratore di Azure AD
3. Una sottoscrizione di Azure in cui è possibile creare nuove risorse

## <a name="step-1-install-the-moodle-plugin"></a>Passaggio 1: Installare il plug-in Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L'integrazione moodle in Microsoft Teams è basata sul set di [plug-in Moodle](https://github.com/Microsoft/o365-moodle)open source. Per installare il plug-in nel server Moodle:

1. Prima di tutto, scaricare il [set di plug-in Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salvarlo nel computer locale. È necessario usare la versione 3.5 o successiva.
    * L'installazione local_o365 plug-in installerà anche auth_oidc [e](https://moodle.org/plugins/auth_oidc) [boost_o365Teams plug-in.](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. Accedere al server Moodle come amministratore e selezionare **Amministrazione sito** nel riquadro di spostamento sinistro.
1. Selezionare la **scheda Plug-in** e quindi fare clic **su Installa plug-in.**
1. Nella sezione **Installa plug-in da file ZIP** fare clic sul pulsante Scegli un **file.**
1. Selezionare **l'Upload un file** nel riquadro di spostamento sinistro, cercare il file scaricato in precedenza e fare clic su Upload **file**.
1. Selezionare di **nuovo l'opzione** Amministrazione sito nel riquadro di spostamento sinistro per tornare al dashboard di amministrazione. Scorrere verso il basso fino **a Plug-in locali** e fare clic sul **collegamento Microsoft Office 365 integrazione.** Mantenere aperta questa pagina di configurazione in una scheda del browser separata perché verrà utilizzata durante il resto del processo.

Per altre informazioni su come installare i plug-in Moodle, vedere la [documentazione di Moodle.](https://docs.moodle.org/34/en/Installing_plugins)

**Nota importante:** Mantenere aperta Microsoft 365 o Office 365 di configurazione del plug-in Moodle in una scheda del browser separata mentre si torna a questo set di pagine durante questo processo.

*Non hai già un sito Moodle?* È consigliabile consultare il [repo](https://github.com/azure/moodle) Moodle su Azure, in cui è possibile distribuire rapidamente un'istanza di Moodle in Azure e personalizzarla in base alle proprie esigenze.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Passaggio 2: Configurare la connessione tra Microsoft 365 o Office 365 plug-in e Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Sarà quindi necessario registrare Moodle come applicazione nel Azure Active Directory. È stato fornito uno script di PowerShell che consente di completare questo processo. Lo script di PowerShell esegue il provisioning di una nuova applicazione Azure AD per l'organizzazione Microsoft 365 o Office 365, che verrà usata dal plug-in Moodle. Lo script eseguirà il provisioning dell'app per il tenant di Microsoft 365 o Office 365, configura tutti gli URL e le autorizzazioni di risposta necessari per l'app di cui è stato eseguito il provisioning e restituisce l'AppID e la chiave. È possibile usare l'AppID e la chiave generati nella pagina di configurazione del plug-in Moodle per configurare il server Moodle con Azure AD. Per visualizzare i passaggi manuali dettagliati che lo script di PowerShell sta automatizzando, è possibile trovarli nella documentazione completa [del plug-in.](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Scheda Moodle per Microsoft Teams flusso di informazioni

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustrazione della scheda Moodle per Microsoft Teams flusso di informazioni" />

1. Nella pagina Microsoft 365 o Office 365 plug-in integrazione selezionare la **scheda** Configurazione.
1. Fare clic **sul pulsante Scarica script di PowerShell** e salvarlo nel computer locale.
1. È necessario preparare lo script di PowerShell dal file ZIP. A questo scopo:
    * Scaricare ed estrarre il `Moodle-AzureAD-Powershell.zip` file.
    * Aprire la cartella estratta.
    * Fare clic con il pulsante destro del `Moodle-AzureAD-Script.ps1` mouse sul file e scegliere **Proprietà.**
    * Nella scheda **Generale** della finestra Proprietà selezionare la casella accanto `Unblock` **all'attributo** Sicurezza nella parte inferiore.
    * Fare clic su **OK**.
    * Copiare il percorso della directory della cartella estratta.
1. Quindi si eseguirà PowerShell come amministratore:
    * Fare clic su Start.
    * Digitare PowerShell.
    * Fare clic con il pulsante destro del mouse Windows PowerShell.
    * Fare clic su "Esegui come amministratore".
1. Passare alla directory decompressa digitando dove si `cd ...\...\Moodle-AzureAD-Powershell` trova il percorso della `...\...` directory.
1. Eseguire lo script di PowerShell per:
    * Immettere `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` .
    * Immettere `.\Moodle-AzureAD-Script.ps1` .
    * Accedere al proprio account Microsoft 365 o Office 365 administrator nella finestra popup.
    * Immettere il nome dell'applicazione Azure AD (ad esempio. Plug-in Moodle/Moodle).
    * Immettere l'URL del server Moodle.
    * Copiare **l'ID applicazione** **e la chiave** dell'applicazione generati dallo script e salvarli.
1. A questo punto sarà necessario aggiungere l'ID e la chiave al plug-in Moodle. Tornare alla pagina di amministrazione del plug-in (Amministrazione > plug-in > Microsoft 365 integrazione).
1. Nella scheda **Configurazione aggiungere** **l'ID** applicazione e il codice **application key** copiati in precedenza, quindi fare clic su **Salva modifiche.**
1. Dopo l'aggiornamento della pagina dovrebbe essere visualizzata una nuova sezione **Scegliere il metodo di connessione.** Fare clic sulla casella di controllo **Predefinita** e quindi di **nuovo su Salva** modifiche.
1. Dopo l'aggiornamento della pagina, verrà visualizzata un'altra nuova sezione con il consenso **dell'& altre informazioni.**
    * Fare clic **sul collegamento Fornisci** il consenso dell'amministratore, immettere  Microsoft 365 o Office 365 credenziali di amministratore globale e quindi accettare per concedere le autorizzazioni.
    * Accanto al campo **Tenant di Azure AD** fare clic sul **pulsante** Rileva.
    * Accanto **all'URL OneDrive for Business fare** clic sul **pulsante** Rileva.
    * Dopo aver popolato i campi, fare di nuovo clic **sul pulsante** Salva modifiche.
1. Fare clic **sul pulsante** Aggiorna per verificare l'installazione e quindi su **Salva modifiche.**
1. Sarà quindi necessario sincronizzare gli utenti tra il server Moodle e Azure Active Directory. A seconda dell'ambiente, è possibile selezionare opzioni diverse durante questa fase. Si noti che la configurazione impostata verrà eseguita con ogni esecuzione di Moodle cron (in genere una volta al giorno) per mantenere sincronizzati tutti gli elementi. Per iniziare:
    * Passare alla scheda **Impostazioni sincronizzazione**
    * Nella sezione **Sincronizzare gli utenti con Azure AD** selezionare le caselle di controllo applicabili all'ambiente. In genere è necessario selezionare almeno:
        * Creare account in Moodle per gli utenti in Azure AD
        * Aggiornare tutti gli account in Moodle per gli utenti in Azure AD
    * Nella sezione **Restrizione creazione utenti** è possibile configurare un filtro per limitare gli utenti di Azure AD che verranno sincronizzati con Moodle.
    * La **sezione Mapping campi utente** consente di personalizzare il mapping dei campi del profilo utente di Azure AD in Moodle.
    * Nella sezione **Teams Sincronizzazione** è possibile scegliere di creare automaticamente i gruppi (ad esempio Teams) per alcuni o tutti i corsi Moodle esistenti.
1. Per convalidare i processi cron (ed eseguirli manualmente se  si vuole per la prima esecuzione) fare clic sul collegamento pagina Gestione attività pianificate nella sezione Sincronizzare gli utenti con **Azure AD.** Verrà visualizzata la pagina **Attività pianificate.**
    * Scorrere verso il basso e trovare il processo **Sincronizzare gli utenti con il processo di Azure AD** e fare clic su Esegui **adesso**.
    * Se si è scelto di creare gruppi in base ai corsi esistenti, è anche possibile eseguire il processo Crea gruppi di utenti **in Office 365** lavoro.
1. Tornare alla pagina di amministrazione del plug-in (Amministrazione > plug-in > Microsoft 365 integrazione) e selezionare la Teams Impostazioni **pagina.** È necessario configurare alcune impostazioni di sicurezza per abilitare l'integrazione Teams'app.
    * Per abilitare OpenID Connessione, fare  clic sul collegamento Gestisci autenticazione e fare clic sull'icona a forma di occhio nella riga **Connessione OpenId** se è disattivata.
    * Sarà quindi necessario abilitare l'incorporamento dei frame. Fare clic **sul collegamento Sicurezza HTTP,** quindi fare clic sulla casella di controllo accanto a **Consenti incorporamento frame.**
    * Il passaggio successivo consiste nell'abilitare i servizi Web che abilitano le funzionalità api Moodle. Fare clic **sul collegamento Caratteristiche** avanzate, quindi verificare che la casella di controllo accanto a Abilita servizi **Web** sia selezionata.
    * Infine, sarà necessario abilitare i servizi esterni per Microsoft 365 o Office 365. Fare clic **sul collegamento Servizi** esterni e quindi:
        * Fare **clic su** Modifica nella riga **Moodle Office 365 Webservices.**
        * Selezionare la casella di controllo accanto a **Abilitato** e quindi fare clic **su Salva modifiche**
    * Sarà quindi necessario modificare le autorizzazioni degli utenti autenticati per consentire loro di creare token di servizio Web. Fare clic **sul collegamento Modifica ruolo "Utente autenticato".** Scorrere verso il basso e trovare **la funzionalità Crea un token di servizio Web** e selezionare la casella di **controllo** Consenti.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Passaggio 3: Distribuire il bot assistente Moodle in Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Il bot moodle assistant gratuito per Microsoft Teams aiuta insegnanti e studenti a rispondere a domande sui loro corsi, attività, voti e altre informazioni in Moodle. Il bot invia anche notifiche moodle a studenti e insegnanti direttamente all'interno Teams. Questo bot è un progetto open source gestito da Microsoft ed è [disponibile in GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> In questa sezione si distribuiranno le risorse nella sottoscrizione di Azure e tutte le risorse verranno configurate usando il **livello** gratuito. A seconda dell'uso del bot, potrebbe essere necessario ridimensionare queste risorse.
> Se si vuole usare semplicemente la scheda Moodle senza il bot, andare [al passaggio 4.](#step-4-deploy-your-microsoft-teams-app)

### <a name="moodle-bot-information-flow"></a>Flusso di informazioni sul bot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustrazione del bot Moodle per Microsoft Teams flusso di informazioni" />


Per installare il bot, è necessario prima di tutto registrarlo in [Microsoft Identity Platform.](https://identity.microsoft.com/Landing) In questo modo il bot può eseguire l'autenticazione con gli endpoint Microsoft. Per registrare il bot:

1. Tornare alla pagina di amministrazione del plug-in (Amministrazione > plug-in > Microsoft 365 integrazione) e selezionare la Teams Impostazioni **impostazioni.**
1. Fare clic **sul collegamento Microsoft Application Registration Portal** ed eseguire l'accesso con il proprio ID Microsoft.
1. Immetti un nome per l'app (ad esempio. MoodleBot) e fai clic **sul pulsante** Crea.
1. Copiare **l'ID** applicazione e incollarlo nel campo ID applicazione **bot** nella **pagina Impostazioni** team.
1. Fare clic **sul pulsante Genera nuova** password. Copiare la password generata e incollarla nel campo **Password applicazione bot** nella pagina **Impostazioni** team.
1. Scorrere fino alla fine del modulo e fare clic su **Salva modifiche**.

Dopo aver generato l'ID applicazione e la password, è il momento di distribuire il bot in Azure. Fare clic sul pulsante Distribuisci in **Azure** e compilare il modulo con le informazioni necessarie (l'ID applicazione Bot, la password dell'applicazione bot e il moodle secret si trova nella pagina **Team Impostazioni e** le informazioni di Azure si trova nella pagina Configurazione).  Dopo aver compilato il modulo, fare clic sulla casella di controllo per  accettare i termini e le condizioni, quindi fare clic sul pulsante Acquista (tutte le risorse di Azure vengono distribuite al livello gratuito).

Al termine della distribuzione delle risorse in Azure, sarà necessario configurare il plug-in Moodle con il relativo endpoint di messaggistica. Prima di tutto, è necessario ottenere l'endpoint dal bot in Azure. per farlo:

1. Se non lo si è già fatto, accedere al [portale di Azure.](https://portal.azure.com)
2. Nel riquadro sinistro selezionare **Gruppi di risorse**.
3. Nell'elenco selezionare il gruppo di risorse appena usato (o creato) durante la distribuzione del bot.
4. Selezionare la **risorsa Bot WebApp** nell'elenco delle risorse del gruppo.
5. Copiare **l'endpoint di** messaggistica dalla **sezione** Panoramica.
6. In Moodle apri la **pagina Team Impostazioni** del plug-in Moodle.
7. Nel campo **Endpoint bot** incollare l'URL appena copiato e modificare la parola *messaggi* in *webhook*. L'URL dovrebbe ora avere l'aspetto `https://botname.azurewebsites.net/api/webhook`
8. Fare clic **su Salva modifiche**
9. Dopo aver salvato le modifiche, tornare alla scheda **Team Impostazioni,** fare clic sul pulsante Scarica **file** manifesto e salvare il pacchetto manifesto nel computer (verrà utilizzato nella sezione successiva).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Passaggio 4: Distribuire l'app Microsoft Teams app

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ora che il bot è stato distribuito in Azure e configurato per parlare con il server Moodle, è il momento di distribuire l'app Microsoft Teams. A questo scopo, caricare il file manifesto scaricato dalla pagina Impostazioni team del plug-in Moodle nel passaggio precedente.

Prima di installare l'app, è necessario assicurarsi che le app esterne e il sideload delle app siano abilitati. A questo scopo, è possibile seguire [questa procedura.](./admin-settings.md) Dopo aver accertato che le app esterne siano abilitate, è possibile seguire la procedura seguente per distribuire l'app.

1. Aprire Microsoft Teams.
2. Fare clic **sull'icona** dello Store nell'angolo in basso a sinistra della barra di spostamento.
3. Fare clic **Upload collegamento a un'app** personalizzata nell'elenco di opzioni. *Nota:* Se si è connessi come amministratore globale, è possibile caricare l'app nell'app store dell'organizzazione, altrimenti sarà possibile caricare l'app solo per Teams di cui si fa parte ("sideload").
4. Selezionare il `manifest.zip` pacchetto scaricato in precedenza e fare clic su **Salva.** Se il pacchetto manifesto non è ancora stato scaricato, è possibile farlo dalla scheda **Team Impostazioni** della pagina di configurazione del plug-in Moodle.

Dopo aver installato l'app, è possibile aggiungere la scheda a qualsiasi canale a cui si ha accesso. A questo scopo, passare al canale, fare clic sul **+** simbolo e selezionare l'app nell'elenco. Seguire le istruzioni visualizzate per completare l'aggiunta della scheda del corso Moodle a un canale.

Questo è tutto! Tu e il tuo team ora potete iniziare a lavorare con i corsi Moodle direttamente da Microsoft Teams.

Per condividere con noi eventuali richieste di funzionalità o feedback, visita la [nostra pagina User Voice.](https://microsoftteams.uservoice.com/forums/916759-moodle)

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]