---
title: Provisioning di Microsoft Teams su vasta scala per gli operatori sul campo
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Indicazioni su come usare gli script per distribuire o eseguire il provisioning di Microsoft Teams per gli operatori sul campo.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: a650b116f3a558594a2177fc4d53f713cf5d90e1488205573d370c5dd7124c40
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347162"
---
# <a name="how-to-provision-teams-at-scale-for-frontline-workers"></a>Come eseguire il provisioning di Microsoft Teams su vasta scala per gli operatori sul campo

Si deve eseguire l'onboarding di un numero elevato di utenti in Microsoft Teams e configurare un'esperienza semplificata per tali utenti? Nelle istruzioni seguenti viene indicato come eseguire rapidamente il provisioning delle identità e dei team e assegnare tutti i criteri appropriati per controllare l'esperienza dell'utente finale.

Questa procedura dettagliata illustra come:

- Creare un numero elevato di utenti.
- Creare un numero elevato di team e configurare i canali appropriati.
- Assegnare licenze su vasta scala.
- Creare criteri di messaggistica, criteri di installazione app e criteri di autorizzazione app appropriati in Teams.
- Applicare quei criteri agli utenti su vasta scala.
- Assegnare un numero elevato di utenti a un determinato team.

> [!NOTE]
> Se queste informazioni sono state esaminate e si ha ancora bisogno di assistenza o se si hanno domande, è possibile [**fare clic qui**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u) per contattare il supporto White Glove.

## <a name="prerequisites"></a>Prerequisiti

Scaricare le risorse disponibili [qui](https://aka.ms/flwteamsscale).

> [!IMPORTANT]
> Gli script accessibili tramite il collegamento indicato sopra sono forniti così come sono da Microsoft e devono essere modificati in base alle proprie esigenze.

## <a name="technical-requirements"></a>Requisiti tecnici

- Nel tenant deve essere disponibile il numero appropriato di licenze che includano Microsoft Teams. Se non si dispone ancora di queste licenze, consultare [Teams Exploratory](teams-exploratory.md) per un abbonamento di valutazione gratuito.
- Per eseguire questa procedura, è necessario che i ruoli seguenti siano assegnati in Azure AD: amministratore globale, amministratore utenti e all'amministratore del servizio Teams.
- È necessario che l'utente abbia i diritti necessari per installare e configurare il software nel computer locale.

## <a name="step-by-step-process-overview"></a>Panoramica della procedura

1. **Configurare l'ambiente**
    1. Scaricare da GitHub il repository contenente gli script di esempio e la documentazione di PowerShell
    1. Configurare l'ambiente locale
    1. Configurare le credenziali
    1. Configurare i moduli di PowerShell e le variabili di ambiente
1. **Creare e configurare i team**
    1. Creare i team
    1. Procedura per la creazione di team
    1. Creare canali per i team
1. **Creare criteri di Teams**
    1. Creare criteri di messaggistica di Teams
    1. Creare criteri di installazione app di Teams
    1. Creare criteri di autorizzazione app di Teams
1. **Utenti e gruppi di sicurezza**
    1. Creare utenti e gruppi di sicurezza
    1. Assegnare licenze agli utenti tramite le licenze basate sui gruppi
1. **Assegnare utenti e criteri**
    1. Assegnare gli utenti ai team
    1. Assegnare i criteri di Teams agli utenti
    1. Facoltativo: convertire il tipo di appartenenza al gruppo
1. **Eseguire il test e la convalida**
    1. Accedere a Teams con un utente di test
    1. Verificare la presenza di errori
    1. Gestione degli errori
1. **Altre informazioni**

## <a name="set-up-your-environment"></a>Configurare l'ambiente

La procedura seguente consente di configurare l'ambiente:

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a>Scaricare da GitHub il repository contenente gli script di esempio e la documentazione di PowerShell

Prima di procedere, è necessario scaricare gli script disponibili [qui](https://aka.ms/flwteamsscale).

### <a name="configure-the-local-environment"></a>Configurare l'ambiente locale

Se si configurano le variabili di ambiente locali, gli script di riferimento devono essere eseguiti usando i percorsi relativi. Il rootPath è la radice della posizione in cui è stato clonato il repository e il tenantName è nel formato **yourTenant.onmicrosoft.com** (HTTPS non deve essere incluso).

1. Aprire una sessione di PowerShell e passare alla cartella degli script nel repository GIT clonato.
1. Eseguire lo script .SetConfig.ps1 -tenantName [nome del tenant] -rootPath "percorso completo alla radice del repository GIT".

Ad esempio: .\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"

### <a name="set-up-credentials"></a>Configurare le credenziali

> [!IMPORTANT]
> La modalità di gestione delle credenziali in questi script potrebbe non essere appropriata, pertanto può essere facilmente modificata in base alle esigenze dell'utente. Seguire sempre le norme e le procedure aziendali per la protezione degli account di servizio e delle identità gestite.

Gli script usano le credenziali archiviate come file XML nel $ENV:LOCALAPPDATA\keys, ossia la cartella AppData\Local. La funzione helper **Set-Creds** nel modulo **BulkAddFunctions.psm1** deve essere chiamata per impostare le credenziali usate per l'esecuzione degli script. In questo modo si elimina la necessità di eseguire l'autenticazione in tutti gli endpoint di servizio, mantenendo le credenziali in un archivio locale. Dall'interno di ognuno degli script, le credenziali appropriate vengono lette con la funzione helper **GetCreds** e queste credenziali vengono usate per connettersi ai vari servizi.

Quando si chiama la funzione **Set-Creds**, viene chiesto di specificare un nome per il file XML che verrà scritto nel $ENV:LOCALAPPDATA\keys. Sono disponibili credenziali diverse per i vari servizi. Ad esempio, se si hanno credenziali diverse per MicrosoftTeams, AzureAD e MSonline, è possibile eseguire **SetCred** più volte, salvando ogni file delle credenziali con il relativo nome significativo.

Esempi: Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml

Eseguire lo script **SetCreds.ps1** per salvare le credenziali. Verrà chiesto di eseguire l'operazione "Export-Clixml", immettere "Y" per approvare.

> [!NOTE]
> L'account usato per le credenziali non può richiedere l'autenticazione a più fattori.

Ecco un esempio di come i vari script usano le credenziali salvate per eseguire l'autenticazione:

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a>Configurare i moduli di PowerShell e le variabili di ambiente

È necessario installare e connettersi a diversi moduli di PowerShell, tra cui Azure AD, MSAL, MSCloudUtils e MicrosoftTeams.

1. Trovare **ConfigurePowerShellModules.ps1** nella cartella degli script nel repository.
1. In PowerShell eseguire lo script **ConfigurePowerShellModules.ps1**.

## <a name="create-and-set-up-teams"></a>Creare e configurare i team

Per comunicare e collaborare con gli operatori sul campo, è necessario prima di tutto creare una serie di team e aggiungere canali standard a quei team, come illustrato di seguito.

### <a name="create-teams"></a>Creare i team

I team sono una insieme di persone, contenuti e strumenti all'interno dell'organizzazione. Per la maggior parte delle organizzazioni orientate agli operatori sul campo, è consigliabile associare un team a una posizione fisica. Ad esempio, un team per ognuna delle seguenti posizioni:

- Store
- Centro di distribuzione
- Stabilimento di produzione
- Ospedale
- Supermercato

*Discussione sulle procedure consigliate*: quando si progettano i team, è importante tenere in considerazione i [limiti e le specifiche per Teams](limits-specifications-teams.md). Per le organizzazioni più piccole, è possibile usare un team a livello di organizzazione per snellire le comunicazioni e integrare una struttura di posizioni fisiche. Per altre, una convenzione di denominazione dei team basata su una posizione fisica strutturata agevola le comunicazioni aziendali facilitando la pubblicazione trasversale a più team contemporaneamente. Ad esempio, è possibile cercare e inviare post a tutti i team nel cui nome è presente US per raggiungere tutte le posizioni negli Stati Uniti. Altre informazioni a questo proposito sono disponibili [qui](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).

#### <a name="steps-to-create-teams"></a>Procedura per la creazione di team

1. Trovare il file **TeamsInformation.csv** nella cartella dati nel repository.
1. Aggiornare le informazioni nel file **TeamsInformation.csv** con le informazioni specifiche dell'organizzazione. Tenere presenti le procedure consigliate descritte in precedenza.
1. Trovare lo script **CreateTeams.ps1**.
1. In PowerShell eseguire lo script **CreateTeams.ps1**.

### <a name="create-channels-for-teams"></a>Creare canali per i team

I canali sono sezioni dedicate all'interno di un team in cui le conversazioni sono organizzate per argomento, progetto, interesse e così via. Ogni team dispone automaticamente di un canale Generale, ma è possibile personalizzare la struttura in base alle esigenze dell'azienda. Ad esempio, la struttura dei canali potrebbe includere:

- **Produzione**: Sicurezza, Linea 1, Linea 2, Comunicazioni aziendali, Formazione
- **Alimentari**: Prodotti da forno, Frutta e verdura, Carne, Comunicazioni aziendali, Formazione
- **Sanità**: Infermieri, Medici, Terapia intensiva 1, Terapia intensiva 2
- **Accoglienza** - Front desk, Manutenzione, Pulizia, Parcheggio e facchinaggio, Comunicazioni aziendali, Formazione
- **Vendita al dettaglio**: Vendita, Magazzino, Comunicazioni aziendali, Formazione

> [!NOTE]
> I canali non devono essere considerati come delimitazioni di sicurezza. Sono uno strumento per organizzare i lavoratori nell'ottica della collaborazione.

*Discussione sulle procedure consigliate*: quando si progetta la struttura di un canale, è importante semplificarla al massimo, soprattutto se si intende eseguire l'onboarding di un numero elevato di utenti. Resistere alla tentazione di aggiungere canali per ogni situazione, ruolo o argomento per ridurre al massimo la necessità di formazione. Scegliere 3-5 canali al massimo per iniziare. Se necessario, sarà possibile aggiungere facilmente altri canali. Per il momento, in realtà, è sufficiente usare solo il canale Generale.

#### <a name="steps-to-create-channels-for-teams"></a>Procedura per la creazione di canali per i team

1. Trovare il file **TeamsChannels.csv** nella cartella degli script nel repository.
1. Aggiornare il file **TeamsChannels.csv** con le informazioni specifiche dell'organizzazione. Tenere presenti le procedure consigliate descritte in precedenza.
1. Trovare lo script **CreateTeamsChannels.ps1** nella cartella degli script nel repository.
1. In PowerShell eseguire lo script **CreateTeamsChannels.ps1**.

## <a name="create-teams-policies"></a>Creare criteri di Teams

L'amministratore può usare i criteri per i team in Microsoft Teams per controllare ciò che gli utenti dell'organizzazione possono vedere. Ad esempio, è possibile controllare quali applicazioni sono bloccate sulla barra di sinistra nel browser desktop o Web o sulla barra inferiore dei dispositivi mobili, per semplificare l'esperienza dell'utente finale durante l'onboarding di una grande quantità di utenti. Alcuni di questi criteri possono essere creati con PowerShell, mentre altri devono essere creati manualmente nell'interfaccia di amministrazione di Teams.

*Discussione sulle procedure consigliate*: per ognuno dei criteri seguenti, decidiamo di creare due criteri, uno per gli operatori sul campo e uno per i manager sul campo. È possibile crearne un numero qualsiasi, in base alle proprie preferenze. Per la maggior parte dei clienti, due è un numero sufficiente per iniziare, anche se inizialmente si assegnano le stesse impostazioni a ciascun gruppo. Man mano che si acquisisce esperienza con Teams, si potrà decidere di differenziare ulteriormente l'esperienza e i due criteri separati già creati possono semplificare questa operazione.

### <a name="create-teams-messaging-policies"></a>Creare criteri di messaggistica di Teams

I criteri di messaggistica vengono usati per controllare le funzionalità di messaggistica disponibili in chat e canali per gli utenti di Microsoft Teams.

*Discussione sulle procedure consigliate*: anche se è possibile usare il criterio globale predefinito che viene creato automaticamente, abbiamo deciso di creare un criterio personalizzato usando la procedura descritta di seguito per offrire un'esperienza più definita, semplice e differenziata per i manager sul campo e gli operatori sul campo.

#### <a name="steps-to-create-teams-messaging-policies"></a>Procedura per la creazione di criteri di messaggistica di Teams

1. Trovare il file **TeamsMessagingPolicies.csv** nella cartella degli script nel repository.
1. Aggiornare il file **TeamsMessagingPolicies.csv** con le informazioni specifiche dell'organizzazione. Altre informazioni su alcune delle opzioni sono disponibili [qui](./messaging-policies-in-teams.md#messaging-policy-settings).
1. Trovare lo script **CreateTeamsMessagePolicies.ps1** nella cartella degli script nel repository.
1. In PowerShell eseguire lo script **CreateTeamsMessagePolicies.ps1**.

### <a name="create-teams-app-setup-policies"></a>Creare criteri di installazione app di Teams

Gli amministratori possono usare i criteri di installazione app per eseguire le operazioni seguenti:

- Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegliere le app da aggiungere e impostare l'ordine in cui vengono visualizzate. L'aggiunta di app consente di mettere in evidenza le app di cui gli utenti dell'organizzazione hanno bisogno, incluse quelle create da terze parti o dagli sviluppatori dell'organizzazione.
- Controllare se gli utenti possono aggiungere app a Teams.

Le app vengono aggiunte alla barra dell'app. Questa barra si trova sul lato del client desktop di Teams e nella parte inferiore dei client per dispositivi mobili (iOS e Android) di Teams.

|Client desktop di Teams  |         |Client per dispositivi mobili di Teams  |
|---------|---------|---------|
|![Screenshot del client desktop di Teams con le app aggiunte alla barra inferiore.](media/flw-teams-desktop-client.png)         |         |![Screenshot del client per dispositivi mobili di Teams con le app aggiunte alla barra inferiore.](media/flw-teams-mobile-client.png) |

*Discussione sulle procedure consigliate*: i criteri di installazione app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Non possono essere creati con PowerShell. È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione verranno automaticamente assegnati al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. In questo caso, stiamo creando due nuovi criteri per gli operatori sul campo e per i manager sul campo, per offrire loro una soluzione più semplice e più snella per semplificare l'onboarding di un numero elevato di utenti contemporaneamente. È possibile decidere di personalizzare l'esperienza in base alle esigenze aziendali.

#### <a name="create-the-frontline-manager-app-setup-policy"></a>Creare i criteri di installazione app per i manager sul campo

Le impostazioni seguenti possono essere personalizzate in base alle esigenze aziendali. Le opzioni consigliate sono state scelte in base alle procedure consigliate e per semplificare l'onboarding di nuovi utenti su vasta scala. Per altre informazioni, fare clic [qui](teams-app-setup-policies.md).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a  **App di Teams** > **Criteri di configurazione**.
2. Fare clic su  **Aggiungi**.  
3. Immettere un nome e una descrizione per il criterio. Ad esempio, Criteri di installazione app per i manager sul campo.
    :::image type="content" source="media/flw-flm-app-setup-policy.png" alt-text="Screenshot del nome e della descrizione di esempio per i criteri di installazione app per i manager sul campo":::

4. Disattivare **Carica app personalizzate**.
5. Disattivare **Consenti di aggiungere un utente**.
    :::image type="content" source="media/flw-allow-user-pinning.png" alt-text="Screenshot dell'impostazione Consenti di aggiungere un utente":::

6. Se non è già presente nell'elenco, aggiungere l'app **Turni**. Per altre informazioni su [Turni](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md), fare clic qui.
    :::image type="content" source="media/flw-add-pinned-apps.png" alt-text="Screenshot della schermata Aggiungi app bloccate, con il pulsante Aggiungi per l'app Turni":::

7. Rimuovere Chiamata, se presente. Quando questa funzionalità viene rimossa, non viene disabilitata per l'utente ma si impedisce che venga visualizzata sulla barra delle app, per semplificare l'esperienza dell'utente finale.
8. Disporre le app nell'ordine seguente per specificare l'ordine in cui vengono visualizzate sulla barra delle app di Teams, quindi fare clic su  **Salva**.

    - Attività
    - Chat
    - Teams
    - Calendario
    - Turni

    :::image type="content" source="media/flw-manager-pinned-apps.png" alt-text="Screenshot delle app per i manager sul campo elencate in ordine":::

#### <a name="create-the-frontline-worker-app-setup-policy"></a>Creare i criteri di installazione app per gli operatori sul campo

Le impostazioni seguenti possono essere personalizzate in base alle esigenze aziendali. Le opzioni consigliate sono state scelte in base alle procedure consigliate e per semplificare l'onboarding di nuovi utenti su vasta scala. Per altre informazioni, fare clic [qui](teams-app-setup-policies.md).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a  **App di Teams** > **Criteri di configurazione**.
2. Fare clic su  **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio. Ad esempio, Criterio di configurazione app per gli operatori sul campo.
    :::image type="content" source="media/flw-flw-app-setup-policy.png" alt-text="Screenshot del nome e della descrizione di esempio per i criteri di installazione app per gli operatori sul campo":::

4. Disattivare **Carica app personalizzate**.
5. Disattivare **Consenti di aggiungere un utente**.
    :::image type="content" source="media/flw-allow-user-pinning.png" alt-text="Screenshot dell'impostazione Consenti di aggiungere un utente":::

6. Se non è già presente nell'elenco, aggiungere l'app **Turni**. Per altre informazioni su [Turni](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md), fare clic qui.

    :::image type="content" source="media/flw-add-pinned-apps.png" alt-text="Screenshot della schermata Aggiungi app bloccate, con il pulsante Aggiungi per l'app Turni":::

7. Rimuovere Riunioni e Chiamata, se presenti. Quando queste funzionalità vengono rimosse, non vengono disabilitate per l'utente ma si impedisce che vengano visualizzate sulla barra delle app, per semplificare l'esperienza dell'utente finale.
8. Disporre le app nell'ordine seguente per specificare l'ordine in cui vengono visualizzate sulla barra delle app di Teams, quindi fare clic su  **Salva**.
    - Attività
    - Chat
    - Teams
    - Turni

    :::image type="content" source="media/flw-worker-pinned-apps.png" alt-text="Screenshot delle app per gli operatori sul campo elencate in ordine":::

### <a name="create-teams-app-permission-policies"></a>Creare criteri di autorizzazione app di Teams

Gli amministratori possono usare i criteri di autorizzazione app per controllare quali app sono disponibili per gli utenti di Microsoft Teams dell'organizzazione. È possibile consentire o bloccare tutte le app o determinate app pubblicate da Microsoft, da terze parti e dall'organizzazione. Quando si blocca un'app, gli utenti a cui è assegnato il criterio non possono a installarla dallo store delle app di Teams. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

*Discussione sulle procedure consigliate*: i criteri di installazione app vengono gestiti nell'interfaccia di amministrazione di Microsoft Teams. Non possono essere creati con PowerShell. È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. In questo caso, stiamo creando due nuovi criteri per gli operatori sul campo e per i manager sul campo, per offrire loro una soluzione sicura e più snella per semplificare l'onboarding di un numero elevato di utenti contemporaneamente. Naturalmente si può decidere di personalizzare l'esperienza in base alle esigenze aziendali.

#### <a name="create-the-frontline-manager-app-permission-policy"></a>Creare i criteri di autorizzazione app per i manager sul campo

Le impostazioni seguenti possono essere personalizzate in base alle esigenze aziendali. Queste sono opzioni raccomandate in base alle procedure consigliate che possono semplificare l'onboarding di nuovi utenti su vasta scala. Per altre informazioni, fare clic [qui](teams-app-permission-policies.md).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a  **App di Teams** > **Criteri di autorizzazione**.
2. Fare clic su  **Aggiungi**.

    :::image type="content" source="media/flw-add-app-permission-policy.png" alt-text="Screenshot della pagina Aggiungi i criteri di autorizzazione app":::

3. Immettere un nome e una descrizione per il criterio. Ad esempio, Criterio di autorizzazione app per manager sul campo.
4. In  **App Microsoft**, selezionare **Consenti tutte le app**.
5. In  **App di terze parti**, selezionare **Consenti tutte le app**.
6. In **App personalizzate**, selezionare **Consenti tutte le app**.
7. Fare clic su  **Salva**.

#### <a name="create-the-frontline-worker-app-permission-policy"></a>Creare i criteri di autorizzazione app per gli operatori sul campo

Le impostazioni seguenti possono essere personalizzate in base alle esigenze aziendali. Queste sono opzioni raccomandate in base alle procedure consigliate che possono semplificare l'onboarding di nuovi utenti su vasta scala. Per altre informazioni, fare clic [qui](teams-app-permission-policies.md).

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a  **App di Teams** > **Criteri di autorizzazione**.
2. Fare clic su  **Aggiungi**.

    :::image type="content" source="media/flw-add-app-permission-policy.png" alt-text="Screenshot della pagina Aggiungi i criteri di autorizzazione app":::

3. Immettere un nome e una descrizione per il criterio. Ad esempio, Criterio di autorizzazione app per operatori sul campo.
4. In  **App Microsoft**, selezionare **Consenti tutte le app**.
5. In  **App di terze parti**, selezionare **Blocca tutte le app**.
6. In **App personalizzate**, selezionare **Consenti tutte le app**.
7. Fare clic su  **Salva**.

## <a name="users-and-security-groups"></a>Utenti e gruppi di sicurezza

### <a name="create-users-and-security-groups"></a>Creare utenti e gruppi di sicurezza

Per lavorare con un numero considerevole di utenti in Teams, prima di tutto è necessario creare gli utenti in Azure AD. Ci sono molti modi per eseguire il provisioning di un numero elevato di utenti, ma in questo caso si evidenzia quanto segue:

- Se questi utenti sono già presenti in uno dei seguenti sistemi HR, usare i collegamenti seguenti per configurarne il provisioning:
  - SAP SuccessFactors - [Esercitazione: configurare il provisioning degli utenti SAP SuccessFactors in Active Directory](/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Workday - [Esercitazione: configurare Workday per il provisioning automatico degli utenti](/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Se le informazioni degli utenti sono archiviate in altri sistemi, procedere con i passaggi successivi.

Per gestire questi utenti su vasta scala in modo più efficace, è necessario creare due gruppi di sicurezza per i manager sul campo e per gli operatori sul campo ed eseguire il provisioning degli utenti direttamente nei gruppi di sicurezza, seguendo questa procedura:

1. Trovare il file **Users.csv** nella cartella degli script nel repository.
1. Aggiornare il file **Users.csv** con le informazioni specifiche dell'organizzazione.
    1. Per impostazione predefinita, lo script fornito creerà un utente con una password temporanea che deve essere cambiata al primo accesso. Se non si vuole usare la password predefinita, modificare lo script **CreateUsers.ps1** in base ai propri requisiti.
    1. Assicurarsi di aggiornare il campo SecurityGroup in modo da riflettere il nome appropriato creato in precedenza.
1. Trovare il file **SecurityGroups.csvv** nella cartella degli script nel repository.
1. Aggiornare il file **SecurityGroups.csv** con le informazioni specifiche del gruppo di sicurezza dell'organizzazione.
    1. Aggiornare i campi **MessagePolicy**, **AppPermissionPolicy** e **AppSetupPolicy** in modo da associarli ai criteri appropriati creati in precedenza.
    1. Aggiornare il campo **LicensePlan** per riflettere la licenza che si intende assegnare a ogni utente. Per altre informazioni sui nomi dei prodotti e sugli identificatori dei piani di servizio, vedere la documentazione [qui](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. In PowerShell eseguire lo script **CreateUsers.ps1** presente nelle risorse.

### <a name="assign-licensing-to-users-via-group-based-licensing"></a>Assegnare licenze agli utenti tramite le licenze basate sui gruppi

I servizi cloud Microsoft a pagamento, come Microsoft 365, Office 365, Enterprise Mobility + Security, Dynamics 365 e altri prodotti simili, richiedono apposite licenze. Queste licenze vengono assegnate a ogni utente che deve avere accesso a questi servizi. Per gestire le licenze, gli amministratori usano i portali di gestione (Office o Azure) e i cmdlet di PowerShell. Azure Active Directory (Azure AD) è l'infrastruttura sottostante che supporta la gestione delle identità per tutti i servizi cloud Microsoft. Azure AD archivia le informazioni sugli stati di assegnazione delle licenze per gli utenti.

Per consentire la gestione delle licenze su vasta scala, Azure AD ora include le licenze basate sui gruppi ed è per questo motivo che sono stati creati i gruppi di sicurezza più indietro in questo articolo. È possibile assegnare una o più licenze di prodotto a un gruppo. Azure AD assicura che le licenze vengano assegnate a tutti i membri del gruppo. A tutti i nuovi membri che entrano a far parte del gruppo vengono assegnate le licenze appropriate. Le licenze vengono rimosse dai membri che lasciano il gruppo. Questa gestione delle licenze elimina la necessità di automatizzare la gestione delle licenze tramite PowerShell per riflettere le modifiche nella struttura dell'organizzazione e del reparto o a livello di singoli utenti.

## <a name="assign-users-and-policies"></a>Assegnare utenti e criteri

### <a name="assign-users-to-teams"></a>Assegnare gli utenti ai team

Dopo avere creato gli utenti e creato i team, occorre inserire tutti gli utenti nei team appropriati.

1. Trovare il file **Users.csv** nella cartella dati nel repository e assicurarsi che in questo file sia presente il mapping corretto ai team.
1. In PowerShell eseguire lo script **AssignUserstoTeams.ps1** presente nella cartella degli script nel repository.

### <a name="assign-teams-policies-to-users"></a>Assegnare i criteri di Teams agli utenti

Dopo avere creato gli utenti e i criteri per modificarne la loro esperienza in Teams, occorre assegnare tali criteri agli utenti corretti.

1. Trovare il file **SecurityGroups.csv** nella cartella dati nel repository e assicurarsi che in questo file sia presente il mapping corretto tra i criteri e i gruppi.
1. In PowerShell eseguire lo script **AssignPoliciestoUsers.ps1** presente nella cartella degli script nel repository.

### <a name="optional-convert-group-membership-type"></a>Facoltativo: convertire il tipo di appartenenza al gruppo

> [!NOTE]
> Questo passaggio è per gli utenti che hanno Azure AD P1 o versione successiva.

Se si ha una licenza di Azure AD P1 o versione successiva, è possibile usare l'appartenenza a gruppi dinamici anziché l'appartenenza assegnata. Gli script che hanno creato i team hanno creato anche i Gruppi di Office con il tipo di appartenenza assegnato, che significa che i membri devono essere aggiunti in modo esplicito.

Se si usa l'appartenenza dinamica, vengono scritte delle regole che determinano se un utente è un membro del team o meno.

> [!NOTE]
> Quando si esegue questo script, l'appartenenza corrente del gruppo verrà rimossa, ad eccezione dei proprietari, e i nuovi membri verranno aggiunti quando è in esecuzione il processo di sincronizzazione dell'appartenenza.

1. Trovare il file **migrateGroups.csv** nella cartella dati nel repository.
1. Aggiornare il file CSV **migrateGroups.csv** con i gruppi da migrare e la regola relativa all'appartenenza dinamica.
1. Trovare il file **ConvertGroupMembershipType.ps1** nella cartella script nel repository.
1. In PowerShell eseguire lo script **ConvertGroupMembershipType.ps1**

## <a name="test-and-validate"></a>Eseguire il test e la convalida

### <a name="sign-in-to-teams-with-a-test-user"></a>Accedere a Teams con un utente di test

Dopo aver completato tutti i passaggi, verificare il lavoro completato.

1. L'utente creato avrà una password iniziale che si trova nello script CreateUsers.ps1, che deve essere cambiata al primo accesso.
1. Verificare che l'aspetto di Teams sia quello previsto. In caso contrario, rivedere le sezioni **Creare criteri di Teams** e **Assegnare i criteri di Teams agli utenti**.
1. Verificare che l'utente si trovi nel team corretto. In caso contrario, rivedere le sezioni **Creare e configurare gli utenti** e **Assegnare gli utenti ai team**.

> [!NOTE]
> Se il provisioning degli operatori sul campo viene gestito tramite il team di gestione delle identità e degli accessi, sarà necessario seguire il relativo processo per fornire agli operatori le credenziali.

### <a name="check-for-errors"></a>Verificare la presenza di errori

Durante l'esecuzione degli script precedenti, le eccezioni o gli errori sono stati scritti in un file CSV che si trova nella cartella logs nella copia del repository. Questo file può essere usato per analizzare eventuali problemi che potrebbero essersi verificati.

Si può verificare un'eccezione, ad esempio, se si tenta di creare un team che esiste già nel tenant.

1. Trovare la cartella **logs** e rivedere tutti i file CSV che potrebbe contenere. Se non ci sono eccezioni, il file delle eccezioni potrebbe non essere presente qui.

### <a name="error-handling"></a>Gestione degli errori

Le funzionalità minime di gestione degli errori è stata implementata in questi script di esempio. Esistono blocchi Try/Catch e, se vengono attivati, l'errore viene archiviato in una variabile nel blocco Catch. La gestione degli errori aggiuntiva deve essere implementata in base alle preferenze.

## <a name="further-reading"></a>Altre informazioni

- [Nuovo canale del team (PowerShell)](/powershell/module/teams/new-teamchannel?view=teams-ps)
- [Nuovi criteri di messaggistica dei team (PowerShell)](/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [Assegnare i criteri agli utenti in Microsoft Teams](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module) 
- [Assegnare le licenze e gli account utente con PowerShell di Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
