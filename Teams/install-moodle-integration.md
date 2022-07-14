---
title: Installare l'integrazione di Moodle con Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Informazioni su come installare e configurare l'app Open Source Learning Management System (LMS) di Moodle per Microsoft Teams.
keywords: Plug-in per l'integrazione dell'app Teams Moodle
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789541"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installazione dell'integrazione di Moodle con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), il sistema LMS (Learning Management System) più popolare e open source al mondo, è ora integrato con Microsoft Teams! Questa integrazione consente a insegnanti e studenti di collaborare ai corsi di Moodle, porre domande sui voti e sulle attività e rimanere aggiornati con le notifiche, direttamente all'interno di Teams!

Per aiutare gli amministratori IT a configurare facilmente questa integrazione, abbiamo aggiornato il plug-in Moodle open source con le funzionalità seguenti:

* Registrazione automatica del server Moodle con Azure AD.
* Distribuzione con un clic del bot Assistente Moodle in Azure.
* Provisioning automatico dei team e sincronizzazione automatica delle iscrizioni ai team per tutti o selezionare corsi Moodle.
* Installazione automatica della scheda Moodle e del bot di Moodle Assistant in ogni team sincronizzato. (Presto disponibile)
* Pubblicazione con un solo clic dell'app Moodle nel App Store privato di Teams. (Presto disponibile)

Per altre informazioni sulle funzionalità fornite da questa integrazione, vedere [Installazione dell'integrazione di Moodle con Microsoft Teams](/microsoftteams/platform/resources/moodleinstructions).

## <a name="prerequisites"></a>Prerequisiti

Per installare e configurare questa applicazione sono necessari:

1. Credenziali di amministratore Moodle
2. Credenziali di amministratore di Azure AD
3. Una sottoscrizione di Azure in cui è possibile creare nuove risorse

## <a name="step-1-install-the-moodle-plugin"></a>Passaggio 1: Installare il plug-in Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L'integrazione di Moodle in Microsoft Teams si basa sul [open source set di plug-in Moodle](https://github.com/Microsoft/o365-moodle). Per installare il plug-in nel server Moodle:

1. Prima di tutto, scaricare il [set di plug-in Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salvarlo nel computer locale. Dovrai usare la versione 3.5 o successiva.
    * Con l'installazione del plug-in local_o365 verranno installati anche i [plug-in auth_oidc](https://moodle.org/plugins/auth_oidc) e [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) .
1. Accedere al server Moodle come amministratore e selezionare **Amministrazione sito** nel riquadro di spostamento sinistro.
1. Selezionare la scheda **Plug-in** e quindi fare clic su **Installa plug-in**.
1. Nella sezione **Installare il plug-in dal file ZIP** fare clic sul pulsante **Scegli un file** .
1. Selezionare l'opzione **Carica un file** nel riquadro di spostamento sinistro, cercare il file scaricato in precedenza e fare clic su **Carica il file**.
1. Selezionare di nuovo l'opzione **Amministrazione sito** nel riquadro di spostamento sinistro per tornare al dashboard di amministrazione. Scorrere verso il basso fino ai **plug-in locali** e fare clic sul collegamento **Microsoft Office 365 Integration**. Mantieni aperta questa pagina di configurazione in una scheda del browser separata, in quanto la userai durante il resto del processo.

Ulteriori informazioni su come installare i plug-in Moodle sono disponibili nella [documentazione di Moodle](https://docs.moodle.org/34/en/Installing_plugins).

**Nota importante:** Mantieni aperta la pagina di configurazione del plug-in Moodle di Microsoft 365 o Office 365 in una scheda del browser separata mentre tornerai a questo set di pagine durante questo processo.

*Non hai già un sito di Moodle?* È consigliabile controllare il [repository](https://github.com/azure/moodle) di Moodle in Azure in cui è possibile distribuire rapidamente un'istanza di Moodle in Azure e personalizzarla in base alle proprie esigenze.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Passaggio 2: Configurare la connessione tra il plug-in Microsoft 365 o Office 365 e Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Successivamente sarà necessario registrare Moodle come applicazione in Azure Active Directory. È stato fornito uno script di PowerShell che consente di completare questo processo. Lo script di PowerShell esegue il provisionsing di una nuova applicazione Azure AD per l'organizzazione di Microsoft 365 o Office 365, che verrà usata dal plug-in Moodle. Lo script eseguirà il provisioning dell'app per il tenant di Microsoft 365 o Office 365, imposterà tutti gli URL di risposta e le autorizzazioni necessari per l'app di cui è stato eseguito il provisioning e restituirà l'ID app e la chiave. È possibile usare il codice e l'ID app generati nella pagina di configurazione del plug-in Moodle per configurare il server Moodle con Azure AD. Per visualizzare i passaggi manuali dettagliati che lo script di PowerShell automatizza, è possibile trovarli nella [documentazione completa del plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Scheda Moodle per il flusso di informazioni di Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustrazione della scheda Moodle per il flusso di informazioni di Microsoft Teams" />

1. Nella pagina del plug-in Microsoft 365 o Office 365 Integration selezionare la scheda **Setup**.
1. Fare clic sul pulsante **Scarica script di PowerShell** e salvarlo nel computer locale.
1. È necessario preparare lo script di PowerShell dal file ZIP. A tale scopo:
    * Scaricare ed estrarre il `Moodle-AzureAD-Powershell.zip` file.
    * Aprire la cartella estratta.
    * Fare clic con il pulsante destro del `Moodle-AzureAD-Script.ps1` mouse sul file e scegliere **Proprietà**.
    * Nella scheda **Generale** del Finestra Proprietà selezionare la `Unblock` casella accanto all'attributo **Security** nella parte inferiore.
    * Fare clic su **OK**.
    * Copiare il percorso della directory della cartella estratta.
1. Quindi eseguiRai PowerShell come amministratore:
    * Fare clic su Start.
    * Digitare PowerShell.
    * Fare clic con il pulsante destro del mouse su Windows PowerShell.
    * Fare clic su "Esegui come amministratore".
1. Passare alla directory decompressa digitando `cd ...\...\Moodle-AzureAD-Powershell` dove `...\...` si trova il percorso della directory.
1. Eseguire lo script di PowerShell:
    * Immettere `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * Immettere `.\Moodle-AzureAD-Script.ps1`.
    * Accedere all'account di Microsoft 365 o Office 365 Administrator nella finestra popup.
    * Immettere il nome dell'applicazione Azure AD, ad esempio plug-in Moodle/Moodle).
    * Immettere l'URL del server Moodle.
    * Copiare **l'ID applicazione** e la **chiave dell'applicazione** generati dallo script e salvarli.
1. Successivamente sarà necessario aggiungere l'ID e il tasto al plug-in Moodle. Tornare alla pagina di amministrazione del plug-in (Amministrazione sito > Plug-in > Integrazione di Microsoft 365).
1. Nella scheda **Configurazione** aggiungere **l'ID applicazione** e la **chiave applicazione** copiati in precedenza, quindi fare clic su **Salva modifiche**.
1. Dopo l'aggiornamento della pagina dovrebbe essere visualizzata una nuova sezione **Scegliere il metodo di connessione**. Fare clic sulla casella di controllo **Predefinita** e quindi fare di nuovo clic su **Salva modifiche** .
1. Dopo l'aggiornamento della pagina, verrà visualizzata **un'altra nuova sezione Amministrazione il consenso & informazioni aggiuntive**.
    * Fare clic sul collegamento **Fornisci il consenso Amministrazione**, immettere le credenziali di Amministratore globale di Microsoft 365 o Office 365, quindi **accettare** per concedere le autorizzazioni.
    * Accanto al campo **Tenant di Azure AD** fare clic sul pulsante **Rileva** .
    * Accanto **all'URL OneDrive for Business** fare clic sul pulsante **Rileva**.
    * Dopo aver popolato i campi, fare di nuovo clic sul pulsante **Salva modifiche** .
1. Fai clic sul pulsante **Aggiorna** per verificare l'installazione, quindi su **Salva modifiche**.
1. Successivamente sarà necessario sincronizzare gli utenti tra il server Moodle e Azure Active Directory. A seconda dell'ambiente, è possibile selezionare opzioni diverse durante questa fase. Si noti che la configurazione impostata qui verrà eseguita con ogni esecuzione di Moodle cron (in genere una volta al giorno) per mantenere tutto sincronizzato. Per iniziare:
    * Passare alla **scheda Impostazioni di sincronizzazione**
    * Nella sezione **Sincronizzare gli utenti con Azure AD** selezionare le caselle di controllo applicabili all'ambiente. In genere è necessario selezionare almeno:
        * Creare account in Moodle per gli utenti in Azure AD
        * Aggiornare tutti gli account in Moodle per gli utenti in Azure AD
    * Nella sezione **Restrizione per la creazione utente** è possibile configurare un filtro per limitare gli utenti di Azure AD che verranno sincronizzati con Moodle.
    * La sezione **Mapping campi utente** consente di personalizzare il mapping dei campi da Azure AD a Moodle User Profile.
    * Nella sezione **Teams Sync** è possibile scegliere di creare automaticamente i gruppi (ad esempio Teams) per alcuni o tutti i corsi Moodle esistenti.
1. Per convalidare i processi cron (ed eseguirli manualmente se si vuole eseguire la prima esecuzione) fare clic sul collegamento alla **pagina Gestione attività pianificate** nella sezione **Sincronizzare gli utenti con Azure AD** . Verrà visualizzata la pagina **Attività pianificate** .
    * Scorrere verso il basso e trovare il processo **Sincronizzare gli utenti con il processo di Azure AD** e fare clic su **Esegui ora**.
    * Se si è scelto di creare gruppi in base ai corsi esistenti, è anche possibile eseguire il processo **Crea gruppi di utenti in Office 365**.
1. Tornare alla pagina di amministrazione del plug-in (Amministrazione sito > Plug-in > Integrazione di Microsoft 365) e selezionare la pagina **Impostazioni di Teams** . È necessario configurare alcune impostazioni di sicurezza per abilitare l'integrazione dell'app Teams.
    * Per abilitare OpenID Connect, fare clic sul collegamento **Gestisci autenticazione** e fare clic sull'icona a occhio sulla linea **OpenId Connect** se è disattivata.
    * Successivamente sarà necessario abilitare l'incorporamento dei frame. Fare clic sul collegamento **Sicurezza HTTP** , quindi fare clic sulla casella di controllo accanto a **Consenti incorporamento frame**.
    * Il passaggio successivo consiste nell'abilitare i servizi Web che abiliteranno le funzionalità dell'API Moodle. Fare clic sul collegamento **Caratteristiche avanzate** , quindi verificare che la casella di controllo accanto a **Abilita servizi Web** sia selezionata.
    * Infine, è necessario abilitare i servizi esterni per Microsoft 365 o Office 365. Fare clic sul collegamento **Servizi esterni** , quindi:
        * Fare clic su **Modifica** nella riga **Moodle Office 365 Webservices**.
        * Selezionare la casella di controllo accanto a **Abilitato** e quindi fare clic su **Salva modifiche**
    * Successivamente sarà necessario modificare le autorizzazioni utente autenticate per consentire loro di creare token del servizio Web. Fare clic sul collegamento **"Utente autenticato" del ruolo modifica** . Scorrere verso il basso e trovare la casella di controllo **Crea un token di servizio Web** e contrassegnare la casella **di controllo Consenti** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Passaggio 3: Distribuire il bot di Moodle Assistant in Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Il bot gratuito Assistente Moodle per Microsoft Teams consente a insegnanti e studenti di rispondere alle domande su corsi, attività, voti e altre informazioni in Moodle. Il bot invia anche notifiche di Moodle a studenti e insegnanti direttamente in Teams. Questo bot è un progetto open source gestito da Microsoft ed è [disponibile su GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> In questa sezione si distribuiranno le risorse nell'abbonamento ad Azure e tutte le risorse verranno configurate usando il livello **gratuito** . A seconda dell'uso del bot, potrebbe essere necessario ridimensionare queste risorse.
> Se vuoi semplicemente usare la scheda Moodle senza il bot, vai al [passaggio 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Flusso di informazioni di Moodle Bot

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustrazione di Moodle bot per il flusso di informazioni di Microsoft Teams" />


Per installare il bot, devi prima registrarlo nella [piattaforma di gestione delle identità Microsoft](https://identity.microsoft.com/Landing). In questo modo il bot può eseguire l'autenticazione in base agli endpoint Microsoft. Per registrare il bot:

1. Tornare alla pagina di amministrazione del plug-in (Amministrazione sito > Plug-in > Integrazione di Microsoft 365) e selezionare la scheda **Impostazioni di Teams** .
1. Fai clic sul collegamento **Microsoft Application Registration Portal** e accedi con il tuo ID Microsoft.
1. Immetti un nome per l'app (ad esempio, MoodleBot) e fai clic sul pulsante **Crea** .
1. Copiare **l'ID applicazione** e incollarlo nel campo **ID applicazione Bot** della pagina **Impostazioni team** .
1. Fare clic sul pulsante **Genera nuova password** . Copiare la password generata e incollarla nel campo **Password applicazione Bot** della pagina **Impostazioni team** .
1. Scorrere fino alla fine della maschera e fare clic su **Salva modifiche**.

Ora che hai generato l'ID applicazione e la password, è il momento di distribuire il bot in Azure. Fare clic sul pulsante **Distribuisci in Azure** e compilare il modulo con le informazioni necessarie (Id applicazione Bot, Password dell'applicazione Bot e Moodle Secret sono nella pagina **Impostazioni del team** e le informazioni di Azure si trovano nella pagina **Configurazione** ). Dopo aver compilato il modulo, fare clic sulla casella di controllo per accettare i termini e le condizioni, quindi fare clic sul pulsante **Acquista** (tutte le risorse di Azure vengono distribuite nel livello gratuito).

Al termine della distribuzione delle risorse in Azure, è necessario configurare il plug-in Moodle con il relativo endpoint di messaggistica. Prima di tutto, è necessario ottenere l'endpoint dal bot in Azure. Per farlo:

1. Se non lo sei già, accedi alla [portale di Azure](https://portal.azure.com).
2. Nel riquadro sinistro selezionare **Gruppi di risorse**.
3. Nell'elenco selezionare il gruppo di risorse appena usato (o creato) durante la distribuzione del bot.
4. Selezionare la risorsa **Bot WebApp** nell'elenco delle risorse del gruppo.
5. Copiare **l'endpoint di messaggistica** dalla sezione **Panoramica** .
6. In Moodle aprire la pagina **Impostazioni team** del plug-in Moodle.
7. Nel campo **Endpoint bot** incollare l'URL appena copiato e modificare la parola *messaggi* in *webhook*. L'URL dovrebbe ora avere l'aspetto `https://botname.azurewebsites.net/api/webhook`
8. Fare clic su **Salva modifiche**
9. Dopo aver salvato le modifiche, tornare alla scheda **Impostazioni team** , fare clic sul pulsante **Scarica file manifesto** e salvare il pacchetto manifesto nel computer (lo si userà nella sezione successiva).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Passaggio 4: Distribuire l'app Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ora che il bot è stato distribuito in Azure e configurato per parlare con il server Moodle, è il momento di distribuire l'app Microsoft Teams. A questo scopo, il file manifesto scaricato dalla pagina Delle impostazioni del team di Moodle Plugin verrà caricato nel passaggio precedente.

Prima di installare l'app è necessario verificare che le app esterne e il sideload delle app siano abilitati. A questo scopo, è possibile seguire [questa procedura](./admin-settings.md). Dopo aver verificato che le app esterne sono abilitate, è possibile seguire la procedura seguente per distribuire l'app.

1. Apri Microsoft Teams.
2. Fare clic sull'icona **Store** nell'angolo in basso a sinistra della barra di spostamento.
3. Fare clic sul collegamento **Carica un'app personalizzata** dall'elenco di opzioni. *Nota:* Se sei connesso come amministratore globale, avrai la possibilità di caricare l'app nell'app store della tua organizzazione, altrimenti potrai caricare l'app solo per Teams di cui fai parte ("sideload").
4. Selezionare il `manifest.zip` pacchetto scaricato in precedenza e fare clic su **Salva**. Se il pacchetto manifesto non è ancora stato scaricato, è possibile farlo dalla scheda **Impostazioni team** della pagina di configurazione del plug-in in Moodle.

Una volta installata l'app, è possibile aggiungere la scheda a qualsiasi canale a cui si ha accesso. A questo scopo, passare al canale, fare clic sul **+** simbolo e selezionare l'app nell'elenco. Seguire le istruzioni visualizzate per completare l'aggiunta della scheda del corso Moodle a un canale.

Questo è tutto! Tu e il tuo team potete iniziare a lavorare con i corsi moodle direttamente da Microsoft Teams.

Per condividere eventuali richieste di funzionalità o feedback con noi, visita il [portale di Feedback](https://feedbackportal.microsoft.com).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
