---
title: Gestire i criteri di configurazione delle app in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di configurazione delle app in Microsoft teams per gli utenti dell'organizzazione.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 89b1a8a756cba44435098e5cd446294004029eac
ms.sourcegitcommit: b5c747e2daad6dd3c1d91f4e61ae6f26db5c77f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064481"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gestire i criteri di configurazione delle app in Microsoft Teams

> [!NOTE]
> Se hai abilitato l'impostazione dell'app a livello di organizzazione, **Consenti l'interazione con**le app personalizzate, potresti non vedere i criteri di configurazione delle app ancora nell'interfaccia di amministrazione di Microsoft teams. Attualmente viene implementato e sarà presto disponibile nell'organizzazione.

Gli amministratori possono usare i criteri di installazione app per eseguire le operazioni seguenti:

- Personalizzare Teams in modo da evidenziare le app più importanti per gli utenti. Scegli le app da aggiungere e imposta l'ordine in cui vengono visualizzate. L'aggiunta di app consente di mettere in evidenza le app di cui gli utenti dell'organizzazione hanno bisogno, incluse quelle create da terze parti o dagli sviluppatori dell'organizzazione.
- Controllare se gli utenti possono aggiungere app a Teams.
- Installare app per conto degli utenti **(in anteprima)**. Scegli le app da installare per impostazione predefinita per gli utenti quando avviano teams. Tieni presente che gli utenti possono ancora installare le app se i [criteri di autorizzazione dell'app](teams-app-permission-policies.md) assegnati consentiti.

Le app vengono aggiunte alla barra delle app. Questa barra si trova sul lato del client Teams desktop e nella parte inferiore dei client Teams per dispositivi mobili (iOS e Android).

|Client desktop Teams  |Client per dispositivi mobili Teams |
|---------|---------|
|![Screenshot che mostra il client desktop Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Schermata che mostra teams mobile client](media/app-setup-policies-mobile-app-bar.png)      |

Per vedere le app preinstallate, nella barra dell'app gli utenti fanno clic su **... Altre app** nei client desktop e Web teams e scorrere rapidamente verso l'alto nei client per dispositivi mobili.

Puoi gestire i criteri di configurazione delle app nell'interfaccia di amministrazione di Microsoft teams. È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato. Per gestire questi criteri, è necessario essere un amministratore globale o un amministratore del servizio Teams.

Per includere le app desiderate, è possibile modificare le impostazioni del criterio globale. Se si desidera personalizzare i team per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.

![Schermata che mostra la pagina Criteri di configurazione dell'app](media/app-setup-policies.png)

> [!NOTE]
> Se si dispone di team per l'istruzione, è importante sapere che l'app assegnazioni è bloccata per impostazione predefinita nel criterio globale, anche se attualmente non viene visualizzata nell'elenco dei criteri globali. Sarà la quarta app nell'elenco delle app aggiunte nei client di teams.

## <a name="create-a-custom-app-setup-policy"></a>Creare criteri di configurazione dell'app personalizzati

Puoi usare l'interfaccia di amministrazione di Microsoft teams per creare criteri personalizzati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di configurazione**delle **app teams**.
2. Fare clic su **Aggiungi**.
    ![Schermata che mostra la pagina Aggiungi criteri di configurazione dell'app](media/app-setup-policies-add.png)
3. Immettere un nome e una descrizione per il criterio.
4. Attivare o disattivare **carica app personalizzate**, a seconda che si voglia consentire agli utenti di caricare app personalizzate in teams. Non potrai modificare questa impostazione se Consenti le **app di terze parti** è disattivata nelle [impostazioni dell'app a livello di organizzazione](manage-apps.md#manage-org-wide-app-settings).
5. Attivare o disattivare Consenti il **blocco dell'utente**, a seconda che si voglia consentire agli utenti di personalizzare la barra dell'app per bloccare le app.
6. Per installare le app per gli utenti **(in anteprima)**, eseguire le operazioni seguenti:

    1. In **app installate**fare clic su **Aggiungi app**.
    2. Nel riquadro **Aggiungi app installate** Cerca le app che vuoi installare automaticamente per gli utenti quando avviano teams. Puoi anche filtrare le app per i criteri di autorizzazione dell'app. Dopo aver scelto l'elenco di app, fare clic su **Aggiungi**.

        ![Screenshot che mostra il riquadro Aggiungi app installate](media/app-setup-policies-add-installed-apps.png)

7. Per aggiungere le app, eseguire le operazioni seguenti:

    1. In **app**bloccate fare clic su **Aggiungi app**.
    2. Nel riquadro **Aggiungi app** aggiunte cercare le app da aggiungere e quindi fare clic su **Aggiungi**. Puoi anche filtrare le app per i criteri di autorizzazione dell'app. Dopo aver scelto l'elenco di app da aggiungere, fare clic su **Aggiungi**.

         ![Screenshot che mostra il riquadro Aggiungi app aggiunte](media/app-setup-policies-add-apps.png)

    3. Disporre le app nell'ordine in cui si vuole che vengano visualizzate in teams e quindi fare clic su **Salva**.

        ![Schermata che mostra la sezione app appuntata](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modificare i criteri di configurazione di un'app

È possibile usare l'interfaccia di amministrazione di Microsoft teams per modificare un criterio, inclusi i criteri globali (a livello di organizzazione) e i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di configurazione**delle **app teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Da qui apportare le modifiche desiderate.
4. Fare clic su **Salva**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Assegnare criteri di configurazione dell'app personalizzati agli utenti

Puoi usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a singoli utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

### <a name="assign-a-custom-app-setup-policy-to-users"></a>Assegnare criteri di configurazione dell'app personalizzati agli utenti

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.
2. Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.
3. In **criteri di configurazione delle app**selezionare i criteri di configurazione dell'app che si desidera assegnare e quindi fare clic su **applica**.

Per assegnare un criterio a più utenti alla volta, vedere [modificare le impostazioni degli utenti di Teams in blocco](edit-user-settings-in-bulk.md).

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di configurazione**delle **app teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Dopo avere aggiunto gli utenti, selezionare **Salva**.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Assegnare criteri di configurazione dell'app personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio di configurazione dell'app personalizzata a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

In questo esempio, assegniamo un criterio di configurazione dell'app personalizzata denominato criteri di configurazione dell'app HR per tutti gli utenti del gruppo di progetti HR di Contoso Pharmaceuticals.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Ottenere i membri del gruppo specificato.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegna tutti gli utenti del gruppo a un determinato criterio di configurazione dell'app. In questo esempio si tratta di criteri di configurazione delle app HR.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-setup-policies"></a>Uso dei criteri di configurazione delle app

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quali criteri di configurazione delle app incorporati sono inclusi nell'interfaccia di amministrazione di Microsoft Teams?

- **Globale (impostazione predefinita a livello di organizzazione)**: questo criterio predefinito si applica a tutti gli utenti dell'organizzazione, a meno che non si assegni un altro criterio. Modificare il criterio globale per aggiungere le app più importanti per gli utenti.
- **FirstLineWorker**: questo criterio è per gli operatori di i FIRSTLINE. È possibile assegnarla ai dipendenti di I FIRSTLINE nell'organizzazione. È importante sapere che, come i criteri personalizzati creati, è necessario assegnare i criteri agli utenti affinché le impostazioni siano attive. Per altre informazioni, vedere la sezione [assegnazione di un criterio di configurazione dell'app personalizzata per gli utenti](#assign-a-custom-app-setup-policy-to-users) di questo articolo.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Perché non è possibile trovare un'app nel riquadro Aggiungi app aggiunte?

Non tutte le app possono essere aggiunte ai team tramite criteri di configurazione dell'app. Alcune app potrebbero non supportare questa funzionalità. Per trovare le app che possono essere bloccate, Cerca l'app nel riquadro **Aggiungi app Pinned** . Le schede che hanno un ambito personale (schede statiche) e i bot possono essere aggiunte al client desktop di teams e queste app sono disponibili nel riquadro **Aggiungi app Pinned** .

Tieni presente che nell'app store teams sono elencate tutte le app teams mentre il riquadro **Aggiungi app aggiunti** include solo le app che possono essere aggiunte ai team tramite criteri. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Sono un team per l'Education admin. Cosa occorre sapere sui criteri di configurazione delle app in teams per l'istruzione?

L'app chiamante non è disponibile in teams per l'istruzione. Quando crei un nuovo criterio di configurazione dell'app personalizzata, l'app chiamante viene visualizzata nell'elenco delle app. Tuttavia, l'app non viene aggiunta ai client e ai team di teams per l'istruzione gli utenti non vedranno l'app chiamate in teams.

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a>Quante app bloccate possono essere aggiunte a un criterio?

Un minimo di due app deve essere aggiunto ai client per dispositivi mobili Teams (iOS e Android). Se un criterio include meno di due app, i client mobili non riflettono le impostazioni dei criteri e invece continueranno a usare la configurazione esistente.

Il numero di app pinne che è possibile aggiungere a un criterio non contiene alcun limite.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Quanto tempo occorre per applicare le modifiche ai criteri?

Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.

### <a name="user-experience"></a>Esperienza utente

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>In che modo gli utenti possono visualizzare tutte le app aggiunte in teams?

Per visualizzare tutte le app bloccate per un utente, è possibile che gli utenti debbano eseguire le operazioni seguenti, a seconda del numero di app installate e delle dimensioni della finestra del client teams.

|Client desktop Teams |Client per dispositivi mobili Teams |
|---------|---------|
|Nella barra dell'app sul lato dei team fare clic su **... Altre app**.| Nella barra dell'app nella parte inferiore del team scorrere rapidamente verso l'alto.|
|![Screenshot che Mostra più app nel client desktop Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Screenshot che Mostra più app nel client per dispositivi mobili Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Cosa occorre sapere sull'esperienza di teams mobile?

I client mobili di Teams (iOS e Android) attualmente non supportano le app personali con schede statiche. A seconda delle app impostate nel criterio, le app aggiunte al client desktop teams potrebbero non essere visualizzate nei client per dispositivi mobili teams. I bot personali verranno comunque visualizzati in chat su client mobili.

Con i client di teams per dispositivi mobili, gli utenti vedranno le app di core team, come attività, chat e team, ed è possibile aggiungere alcune app di primo tipo da Microsoft, ad esempio turni.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Gli utenti possono modificare l'ordine delle app bloccati da un criterio?

Gli utenti possono modificare l'ordine delle app aggiunte nei client desktop e mobili di teams se l'opzione **Consenti il blocco utente** è attivata. Gli utenti non possono modificare l'ordine delle app aggiunte nei client Web di teams.

#### <a name="does-user-pinning-take-precedence"></a>Il blocco degli utenti ha la precedenza?

Se i criteri di configurazione dell'app assegnati all'utente vengono modificati per bloccare il blocco delle app degli utenti, i team rimuovono tutte le app aggiunte alla barra dell'app. Se il criterio viene quindi modificato in modo da consentire il blocco delle app degli utenti, gli utenti devono ripetere l'aggiunta delle app precedentemente bloccate.

### <a name="custom-teams-apps"></a>App Team personalizzate

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>La mia organizzazione ha creato un'app teams personalizzata e pubblicata, in AppSource o nel catalogo dell'app tenant, ma l'icona dell'app non viene visualizzata come previsto quando l'app viene bloccata alla barra dell'app in teams. Come è possibile risolvere il problema?

Prima di inviare l'app, assicurati di seguire le linee guida per il logo. Per altre informazioni, vedere [elenco di controllo per l'invio del dashboard del venditore](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview). 

 ## <a name="related-topics"></a>Argomenti correlati

- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
