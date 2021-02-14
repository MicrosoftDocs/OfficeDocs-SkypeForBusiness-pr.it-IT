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
description: Informazioni su come installare e configurare l'app Open Source Learning Management System (LMS) Moodle per Microsoft Teams.
keywords: Plug-in di integrazione dell'app Teams Moodle
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
ms.openlocfilehash: 36b966748fe88b8fec803adc7f9f898e247cdec9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508333"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installazione dell'integrazione di Moodle con Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle,](https://moodle.org/)il sistema LMS (Learning Management System) open-source più diffuso al mondo, è ora integrato con Microsoft Teams. Questa integrazione consente a docenti e insegnanti di collaborare sui corsi Moodle, porre domande sui voti e sulle attività e rimanere aggiornati con le notifiche, direttamente all'interno di Teams.

Per aiutare gli amministratori IT a configurare facilmente questa integrazione, il plug-in Moodle open-source è stato aggiornato con le seguenti funzionalità:

* Registrazione automatica del server Moodle con Azure AD.
* Distribuzione con un clic del bot Assistente Moodle in Azure.
* Provisioning automatico dei team e sincronizzazione automatica delle iscrizioni dei team per tutti i corsi o selezione dei corsi Moodle.
* Installazione automatica della scheda Moodle e del bot Assistente Moodle in ogni team sincronizzato. (Presto disponibile)
* Pubblicazione con un solo clic dell'app Moodle nell'App Store privato di Teams. (Presto disponibile)

Per altre informazioni sulle funzionalità disponibili in questa integrazione, fare [clic qui.](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)

## <a name="prerequisites"></a>Prerequisiti

Per installare e configurare questa applicazione, è necessario:

1. Credenziali di amministratore Moodle
2. Credenziali di amministratore di Azure AD
3. Una sottoscrizione di Azure in cui puoi creare nuove risorse in

## <a name="step-1-install-the-moodle-plugin"></a>Passaggio 1: Installare il plug-in Moodle

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

L'integrazione di Moodle in Microsoft Teams è basata sul set di plug-in [Moodle open](https://github.com/Microsoft/o365-moodle)source. Per installare il plug-in nel server Moodle:

1. Prima di tutto, scaricare il [set di plug-in Moodle](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) e salvarlo nel computer locale. È necessario usare la versione 3.5 o successiva.
    * Con l'local_o365 plug-in verranno installati [auth_oidc](https://moodle.org/plugins/auth_oidc) e [boost_o365Teams plug-in.](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. Accedere al server Moodle come amministratore e selezionare Amministrazione **sito** nel riquadro di spostamento sinistro.
1. Selezionare la **scheda Plug-in** e quindi fare clic **su Installa plug-in.**
1. Nella sezione **Installare il plug-in da un file ZIP** fare clic sul pulsante Scegli un **file.**
1. Selezionare le **opzioni per caricare un file** nel riquadro di spostamento sinistro, individuare il file scaricato in precedenza e fare clic su Carica il **file.**
1. Selezionare di **nuovo l'opzione** Amministrazione sito nel riquadro di spostamento sinistro per tornare al dashboard di amministrazione. Scorrere verso il basso **fino ai plug-in locali** e fare clic sul collegamento Microsoft Office **365 Integration.** Tenere aperta questa pagina di configurazione in una scheda del browser separata in cui verrà utilizzata durante il resto del processo.

Ulteriori informazioni su come installare i plug-in Moodle sono disponibili nella [documentazione di Moodle.](https://docs.moodle.org/34/en/Installing_plugins)

**Nota importante:** Mantenere aperta la pagina di configurazione del plug-in Moodle di Microsoft 365 o Office 365 in una scheda del browser separata per il rientro in questo set di pagine durante l'intero processo.

*Non hai già un sito Moodle?* Potresti voler controllare il nostro [repo](https://github.com/azure/moodle) Moodle in Azure, in cui puoi distribuire rapidamente un'istanza di Moodle in Azure e personalizzarla in base alle tue esigenze.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Passaggio 2: Configurare la connessione tra il plug-in di Microsoft 365 o Office 365 e Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Successivamente dovrai registrare Moodle come applicazione in Azure Active Directory. È stato fornito uno script di PowerShell che aiuta a completare il processo. Lo script di PowerShell esegue il provisioning di una nuova applicazione Azure AD per l'organizzazione di Microsoft 365 o Office 365, che verrà usata dal plug-in Moodle. Lo script eseguirà il provisioning dell'app per il tenant di Microsoft 365 o Office 365, configura tutti gli URL di risposta e le autorizzazioni necessari per l'app di cui è stato eseguito il provisioning e restituisce l'APPID e la chiave. È possibile usare il codice e l'APPID generati nella pagina di configurazione del plug-in Moodle per configurare il server Moodle con Azure AD. Per visualizzare le procedure manuali dettagliate che lo script di PowerShell sta automatizzando, sono disponibili nella documentazione completa [del plug-in.](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Scheda Moodle per il flusso di informazioni di Microsoft Teams

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Illustrazione della scheda Moodle per il flusso di informazioni di Microsoft Teams" />

1. Nella pagina del plug-in Microsoft 365 o Office 365 Integration selezionare la **scheda Setup.**
1. Fare clic **sul pulsante Scarica script di PowerShell** e salvarlo nel computer locale.
1. È necessario preparare lo script di PowerShell dal file ZIP. A tale scopo:
    * Scaricare ed estrarre il `Moodle-AzureAD-Powershell.zip` file.
    * Aprire la cartella estratta.
    * Fare clic con il pulsante destro del `Moodle-AzureAD-Script.ps1` mouse sul file e scegliere **Proprietà.**
    * Nella scheda **Generale** della finestra Proprietà selezionare la casella accanto `Unblock` all'attributo Sicurezza nella parte inferiore. 
    * Fare clic su **OK**.
    * Copiare il percorso della directory della cartella estratta.
1. Successivamente si eseguirà PowerShell come amministratore:
    * Fare clic su Start.
    * Digitare PowerShell.
    * Fare clic con il pulsante destro del mouse Windows PowerShell.
    * Fare clic su "Esegui come amministratore".
1. Passare alla directory decompressa digitando dove si `cd ...\...\Moodle-AzureAD-Powershell` trova il percorso della `...\...` directory.
1. Eseguire lo script di PowerShell:
    * Immettere `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` .
    * Immettere `.\Moodle-AzureAD-Script.ps1` .
    * Accedere all'account Microsoft 365 o Office 365 Administrator nella finestra popup.
    * Immettere il nome dell'applicazione Azure AD, ad esempio Moodle/Moodle plugin).
    * Immettere l'URL del server Moodle.
    * Copiare **l'ID** applicazione **e la chiave** dell'applicazione generati dallo script e salvarli.
1. Successivamente sarà necessario aggiungere l'ID e la chiave al plug-in Moodle. Tornare alla pagina di amministrazione dei plug-in (> plug-in > di Microsoft 365).
1. Nella scheda **Installazione** aggiungere **l'ID** applicazione e la **chiave applicazione** copiati in precedenza, quindi fare clic su **Salva modifiche.**
1. Dopo l'aggiornamento della pagina, dovrebbe essere visualizzata una nuova sezione **Scegli metodo di connessione.** Fare clic sulla casella di controllo **Predefinita** e quindi di **nuovo su Salva modifiche.**
1. Dopo l'aggiornamento della pagina, verrà visualizzata un'altra nuova sezione Con il consenso **dell'& altre informazioni.**
    * Fare clic **sul collegamento Fornisci** il consenso dell'amministratore, immettere le credenziali  di amministratore globale di Microsoft 365 o Office 365 e quindi accettare per concedere le autorizzazioni.
    * Accanto al campo **Tenant di Azure AD** fare clic sul **pulsante** Rileva.
    * Accanto **all'URL di OneDrive for Business** fare clic sul **pulsante** Rileva.
    * Dopo aver popolato i campi, fare di nuovo clic **sul pulsante Salva** modifiche.
1. Fare clic **sul pulsante** Aggiorna per verificare l'installazione, quindi salvare **le modifiche.**
1. Successivamente dovrai sincronizzare gli utenti tra il tuo server Moodle e Azure Active Directory. A seconda dell'ambiente, è possibile selezionare opzioni diverse durante questa fase. Si noti che la configurazione impostata qui verrà eseguita con ogni file Moodle cron run (in genere una volta al giorno) per mantenere sincronizzati tutti gli elementi. Per iniziare:
    * Passare alla scheda **Impostazioni di sincronizzazione**
    * Nella sezione **Sincronizzare gli utenti con Azure AD** selezionare le caselle di controllo applicabili all'ambiente. In genere è necessario selezionare almeno:
        * Creare account in Moodle per gli utenti in Azure AD
        * Aggiornare tutti gli account in Moodle per gli utenti in Azure AD
    * Nella sezione **Restrizione per la creazione** di utenti è possibile configurare un filtro per limitare gli utenti di Azure AD che verranno sincronizzati con Moodle.
    * La **sezione User Field Mapping** consente di personalizzare il mapping dei campi da Azure AD a Moodle User Profile.
    * Nella sezione **Teams Sync** puoi scegliere di creare automaticamente i gruppi (ad esempio Teams) per alcuni o tutti i tuoi corsi Moodle esistenti.
1. Per convalidare i processi di programmazione (ed eseguirli manualmente se  si vuole eseguire il primo processo), fare clic sul collegamento alla pagina di gestione delle attività programmate nella sezione Sincronizzare gli utenti con **Azure AD.** Verrà visualizzata la **pagina Attività programmate.**
    * Scorrere verso il basso e trovare il processo **sincronizzare gli utenti con il processo di Azure AD** e fare clic su Esegui **ora.**
    * Se si sceglie di creare gruppi in base a corsi esistenti, è anche possibile eseguire il processo Crea gruppi di utenti **in Office 365.**
1. Tornare alla pagina di amministrazione del plug-in (amministrazione del sito > plug-in > integrazione con Microsoft 365) e selezionare la pagina **Impostazioni di Teams.** Sarà necessario configurare alcune impostazioni di sicurezza per abilitare l'integrazione dell'app Teams.
    * Per abilitare OpenID Connect, fare clic sul **collegamento** Gestisci autenticazione e fare clic sull'icona a forma di occhio sulla linea **OpenId Connect** se è disattivata.
    * Successivamente sarà necessario abilitare l'incorporamento dei frame. Fare clic **sul collegamento Sicurezza HTTP,** quindi fare clic sulla casella di controllo accanto a Consenti **incorporamento di frame.**
    * Il passaggio successivo consiste nell'abilitare i servizi Web che abiliteranno le funzionalità delle API Moodle. Fare clic **sul collegamento Caratteristiche** avanzate, quindi verificare che la casella di controllo accanto ad Abilita servizi **Web** sia selezionata.
    * Infine, è necessario abilitato i servizi esterni per Microsoft 365 o Office 365. Fare clic **sul collegamento Servizi** esterni e quindi:
        * Fare **clic** su Modifica nella **riga Moodle Office 365 Webservices.**
        * Selezionare la casella di controllo accanto **a Abilitato** e quindi fare clic su **Salva modifiche**
    * Successivamente sarà necessario modificare le autorizzazioni utente autenticate per consentirgli di creare token di servizio Web. Fare clic **sul collegamento "Utente autenticato" per il ruolo di** modifica. Scorrere verso il basso e individuare **la funzionalità Crea un token di servizio Web** e selezionare la casella di **controllo** Consenti.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Passaggio 3: Distribuire il bot di Assistente Moodle in Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Il bot gratuito Assistente Moodle per Microsoft Teams aiuta insegnanti e studenti a rispondere a domande su corsi, attività, voti e altre informazioni su Moodle. Il bot invia anche notifiche Di Moodle agli studenti e ai docenti direttamente in Teams. Questo bot è un progetto open source gestito da Microsoft ed è [disponibile su GitHub.](https://github.com/microsoft/Moodle-Teams-Bot)

> [!NOTE]
> In questa sezione le risorse verranno distribuite nella sottoscrizione di Azure e tutte le risorse verranno configurate con il **livello** gratuito. A seconda dell'uso del bot, potrebbe essere necessario ridimensionare queste risorse.
> Se si vuole usare solo la scheda Moodle senza il bot, andare [al passaggio 4.](#step-4-deploy-your-microsoft-teams-app)

### <a name="moodle-bot-information-flow"></a>Flusso di informazioni del bot Moodle

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Illustrazione del bot Moodle per il flusso di informazioni di Microsoft Teams" />


Per installare il bot, devi prima registrarlo nella [piattaforma di identità Microsoft.](https://identity.microsoft.com/Landing) In questo modo il bot può autenticarsi rispetto agli endpoint Microsoft. Per registrare il bot:

1. Tornare alla pagina di amministrazione del plug-in (amministrazione del sito > plug-in > integrazione con Microsoft 365) e selezionare la **scheda Impostazioni di Teams.**
1. Fare clic **sul collegamento al portale di registrazione applicazioni Microsoft** e accedere con il proprio ID Microsoft.
1. Immetti un nome per l'app (ad esempio, MoodleBot) e fai clic **sul pulsante** Crea.
1. Copiare **l'ID** applicazione e incollarlo nel campo **ID applicazione Bot** della pagina Impostazioni **del** team.
1. Fare clic **sul pulsante Genera nuova password.** Copiare la password generata e incollarla nel campo **Password applicazione Bot** della pagina Impostazioni **del** team.
1. Scorrere fino alla fine del modulo e fare clic **su Salva modifiche.**

Ora che l'ID applicazione e la password sono stati generati, è il momento di distribuire il bot in Azure. Fare clic sul pulsante Distribuisci in **Azure** e compilare il modulo con le informazioni necessarie (ID applicazione Bot, Password applicazione  Bot e Moodle Secret sono disponibili nella pagina Impostazioni del **team** e le informazioni di Azure sono nella pagina di configurazione). Dopo aver compilato il modulo, fai clic sulla casella di controllo per  accettare i termini e le condizioni, quindi fai clic sul pulsante Acquista (tutte le risorse Azure vengono distribuite al livello gratuito).

Dopo aver completato la distribuzione delle risorse in Azure, sarà necessario configurare il plug-in Moodle con l'endpoint di messaggistica. Prima di tutto, dovrai ottenere l'endpoint dal bot in Azure. per farlo:

1. Se non lo hai già fatto, accedi al [portale di Azure.](https://portal.azure.com)
2. Nel riquadro sinistro selezionare **Gruppi di risorse.**
3. Nell'elenco selezionare il gruppo di risorse appena usato (o creato) durante la distribuzione del Bot.
4. Selezionare la **risorsa Bot WebApp** nell'elenco delle risorse del gruppo.
5. Copiare **l'endpoint di** messaggistica **dalla sezione** Panoramica.
6. In Moodle aprire la pagina **Impostazioni team** del plug-in Moodle.
7. Nel campo **Endpoint bot** incollare l'URL appena copiato e modificare la parola *messaggi in* *webhook.* L'URL dovrebbe ora essere simile a `https://botname.azurewebsites.net/api/webhook`
8. Fare clic **su Salva modifiche**
9. Dopo aver salvato le modifiche, tornare alla scheda Impostazioni del **team,** fare clic sul pulsante Scarica **file** manifesto e salvare il pacchetto manifesto nel computer (si userà nella sezione successiva).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Passaggio 4: Distribuire l'app Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Ora che il bot è stato distribuito in Azure e configurato per parlare con il server Moodle, è il momento di distribuire l'app Microsoft Teams. A questo scopo, verrà caricato il file manifesto scaricato dalla pagina delle impostazioni del team del plug-in Moodle nel passaggio precedente.

Prima di installare l'app, è necessario verificare che le app esterne e il sideload delle app siano abilitate. A questo scopo, eseguire [questa procedura.](https://docs.microsoft.com/MicrosoftTeams/admin-settings) Dopo aver fatto in modo che le app esterne siano abilitate, è possibile seguire la procedura seguente per distribuire l'app.

1. Aprire Microsoft Teams.
2. Fare clic **sull'icona** dello Store nell'angolo in basso a sinistra della barra di spostamento.
3. Fare clic **sul collegamento Carica un'app** personalizzata nell'elenco di opzioni. *Nota:* Se si è connessi come amministratore globale, sarà possibile caricare l'app nell'app store dell'organizzazione, altrimenti sarà possibile caricare solo l'app per Teams di cui si fa parte ("sideload").
4. Selezionare il `manifest.zip` pacchetto scaricato in precedenza e fare clic su **Salva.** Se il pacchetto manifesto non è ancora stato scaricato, è possibile farlo dalla scheda Impostazioni team della pagina di configurazione del plug-in in Moodle. 

Dopo aver installato l'app, è possibile aggiungere la scheda a qualsiasi canale a cui si ha accesso. Per farlo, passare al canale, fare clic sul **+** simbolo e selezionare l'app nell'elenco. Seguire le istruzioni visualizzate per completare l'aggiunta della scheda del corso Moodle a un canale.

Questo è tutto! Tu e il tuo team potete iniziare a lavorare con i corsi Moodle direttamente da Microsoft Teams.

Per condividere con noi eventuali richieste di funzionalità o feedback, visita la [nostra pagina User Voice.](https://microsoftteams.uservoice.com/forums/916759-moodle)
