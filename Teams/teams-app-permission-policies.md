---
title: Gestire i criteri di autorizzazione delle app in Microsoft Teams
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
description: Informazioni sui criteri di autorizzazione delle app in Microsoft teams e su come usarli per controllare quali app sono disponibili per gli utenti dell'organizzazione.
f1keywords:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: bc541b3b1bc7c7aba723d7573224679b5900a550
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952829"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gestire i criteri di autorizzazione delle app in Microsoft Teams

Come amministratore, puoi usare i criteri di autorizzazione delle app per controllare quali app sono disponibili per gli utenti di Microsoft teams nell'organizzazione. È possibile consentire o bloccare tutte le app o le app specifiche pubblicate da Microsoft, da terze parti e dall'organizzazione. Quando si blocca un'app, gli utenti non sono in grado di installarlo dall'app store teams.

Puoi gestire i criteri di autorizzazione delle app nell'interfaccia di amministrazione di Microsoft teams. È possibile applicare le impostazioni a livello di organizzazione, usare il criterio globale (predefinito per l'intera organizzazione) e creare e assegnare criteri personalizzati a singoli utenti o utenti di un gruppo.  

![Screenshot dei criteri di autorizzazione delle app](media/app-permission-policies.png)

> [!NOTE]
> Gli utenti dell'organizzazione otterranno automaticamente il criterio globale a meno che non si creino e non si assegnano criteri personalizzati. Le impostazioni dell'app a livello di organizzazione eseguono l'override dei criteri globali e di tutti i criteri personalizzati creati e assegnati agli utenti.

Se l'organizzazione è già in teams, le impostazioni dell'app configurate in **impostazioni a livello di tenant** nell'interfaccia di amministrazione di Microsoft 365 si riflettono nelle impostazioni dell'app a livello di organigramma. Se non si ha familiarità con i team e si è appena iniziato, per impostazione predefinita tutte le app sono consentite nel criterio globale. Sono incluse le app pubblicate da Microsoft, terze parti e dall'organizzazione.

Supponi ad esempio di voler bloccare tutte le app di terze parti e consentire ad app specifiche di Microsoft per il team HR dell'organizzazione. Si creerebbe un criterio personalizzato denominato criteri di autorizzazione delle app HR, lo si imposta per bloccare e consentire le app desiderate e quindi assegnarlo agli utenti nel team HR.

## <a name="manage-org-wide-app-settings"></a>Gestire le impostazioni dell'app a livello di organizzazione

Usa le impostazioni dell'app a livello di organizzazione per controllare quali app sono disponibili in tutta l'azienda. Le impostazioni dell'app a livello di organizzazione regolano il comportamento per tutti gli utenti ed eseguono l'override di qualsiasi altro criterio di autorizzazione dell'app assegnato agli utenti. Puoi usarle per controllare le app malevole o problematiche.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.
2. Selezionare **impostazioni a livello di organizzazione**. È quindi possibile configurare le impostazioni desiderate nel pannello. 
    ![Screenshot delle impostazioni dell'app a livello di organizzazione](media/app-permission-policies-org-wide-settings.png)
3. In **app di terze parti**disattivare o attivare queste impostazioni per controllare l'accesso alle app di terze parti:

    - **Consentire app di terze parti o personalizzate in teams**: controlla se gli utenti possono usare app di terze parti o personalizzate.
    - **Consenti a tutte le nuove app di terze parti pubblicate nello Store per impostazione predefinita**: questo controlla se le nuove app di terze parti pubblicate nell'app store teams diventano automaticamente disponibili in teams. Puoi impostare questa opzione solo se Consenti app di terze parti.

4. In **app personalizzate**disattivare o attivare **Consenti l'interazione con le app personalizzate**. Questa impostazione controlla se gli utenti possono interagire con le app personalizzate (sideload). Tieni presente che questo è diverso dal consentire agli utenti di *caricare* app personalizzate.
5. In **app bloccate**cercare e aggiungere le app che si desidera bloccare nell'organizzazione. Puoi scegliere le app dal Catalogo app tenant o dall'app teams Store.
6. Fare clic su **Salva** per applicare le impostazioni dell'app a livello di organizzazione.

## <a name="create-a-custom-app-permission-policy"></a>Creare un criterio di autorizzazione per le app personalizzate

Per controllare le app disponibili per diversi gruppi di utenti dell'organizzazione, creare e assegnare uno o più criteri di autorizzazione per le app personalizzate. È possibile creare e assegnare criteri personalizzati distinti a seconda che le app vengano pubblicate da Microsoft, da terze parti o dall'organizzazione. È importante sapere che dopo aver creato un criterio personalizzato, non è possibile modificarlo se le app di terze parti sono disabilitate in impostazioni a livello di organizzazione. 

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.
2. Fare clic su **Aggiungi**.
    ![Schermata dei criteri di autorizzazione per i nuovi app](media/app-permission-policies-new-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. In app **Microsoft**, **app di terze parti**e **app tenant**selezionare una delle opzioni seguenti:

    - **Consenti tutte le app**
    - **Consenti app specifiche e blocca tutte le altre**
    - **Bloccare app specifiche e consentire a tutti gli altri utenti**
    - **Bloccare tutte le app**

5. Se è stata selezionata l'opzione **Consenti app specifiche e blocca altre**, aggiungere le app che si vuole consentire:

    1. Selezionare **Consenti app**.
    1. Cercare le app che si desidera consentire e quindi fare clic su **Aggiungi**. I risultati della ricerca vengono filtrati in Publisher di app (app**Microsoft**, app di **terze parti**o **app tenant**).
    1. Dopo aver scelto l'elenco di app, fare clic su **Consenti**.

6. Allo stesso modo, se si è selezionato **Blocca app specifiche e si consente a tutti gli altri utenti**, cercare e aggiungere le app che si vuole bloccare.
7. Fai clic su **Salva**.

## <a name="edit-an-app-permission-policy"></a>Modificare i criteri di autorizzazione delle app

È possibile usare l'interfaccia di amministrazione di Microsoft teams per modificare un criterio, inclusi i criteri globali e i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Da qui apportare le modifiche desiderate. Puoi gestire le impostazioni in base all'App Publisher e aggiungere e rimuovere app in base all'impostazione Consenti/blocca.
4. Fai clic su **Salva**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Assegnare un criterio di autorizzazione app personalizzata agli utenti

Puoi usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio tutti gli utenti di un gruppo di sicurezza o di un gruppo di distribuzione.

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a>Assegnare un criterio di autorizzazione dell'app personalizzata a un utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**.
2. Selezionare l'utente facendo clic a sinistra del nome utente, quindi fare clic su **Modifica impostazioni**.
3. In **criteri di autorizzazione**per le app selezionare i criteri di autorizzazione per le app da assegnare e quindi fare clic su **applica**.

Per assegnare un criterio a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).

In alternativa, è anche possibile eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai > **criteri di autorizzazione**delle **app teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Selezionare **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per ogni utente che si vuole aggiungere.
5. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Assegnare criteri di autorizzazione per le app personalizzate agli utenti di un gruppo

È consigliabile assegnare un criterio di autorizzazione dell'app personalizzata a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

In questo esempio, assegniamo un criterio di autorizzazione delle app personalizzate denominato criteri di autorizzazione delle app HR a tutti gli utenti del gruppo di progetti HR di Contoso Pharmaceuticals.  

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
Assegna tutti gli utenti del gruppo a un determinato criterio di autorizzazione dell'app. In questo esempio si tratta di criteri di autorizzazione delle app HR.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="faq"></a>Domande frequenti

### <a name="working-with-app-permission-policies"></a>Uso dei criteri di autorizzazione delle app

#### <a name="can-i-control-line-of-business-lob-apps"></a>È possibile controllare le app line of business (LOB)?
Sì, è possibile usare i criteri di autorizzazione delle app per controllare l'implementazione e la distribuzione delle app personalizzate (line-of-business). È possibile creare criteri personalizzati o modificare i criteri globali per consentire o bloccare le app personalizzate in base alle esigenze dell'organizzazione.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>In che modo i criteri di autorizzazione delle app sono correlati alle app e ai criteri di configurazione delle app bloccati?

Puoi usare i criteri di configurazione delle app insieme ai criteri di autorizzazione per le app. Le app predefinite vengono selezionate dal set di app abilitate per un utente. Inoltre, se un utente ha un criterio di autorizzazione per le app che blocca un'app nei criteri di configurazione dell'app, l'app non verrà visualizzata in teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>È possibile usare I criteri di autorizzazione delle app per limitare il caricamento di app personalizzate (note anche come sideload)?

Usa le impostazioni a livello di organizzazione nei criteri di autorizzazione per le app per limitare il caricamento di app personalizzate per l'azienda.  

Per limitare gli utenti specifici dal caricamento delle app personalizzate, USA criteri per le app personalizzate (presto disponibile). Per altre informazioni, vedere [gestire i criteri e le impostazioni dell'app personalizzata in teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Il blocco di un'app si applica ai client per dispositivi mobili Teams?

Sì, quando blocchi un'app, l'app viene bloccata in tutti i client di teams.  

### <a name="user-experience"></a>Esperienza utente

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Che cosa fa un'esperienza utente quando un'app viene bloccata?

Gli utenti non possono interagire con un'app bloccata o le relative funzionalità, ad esempio bot, schede e estensioni di messaggistica. In un contesto condiviso, ad esempio un team o una chat di gruppo, i bot possono comunque inviare messaggi a tutti i partecipanti al contesto. Teams indica all'utente quando un'app è bloccata.

Ad esempio, quando un'app viene bloccata, gli utenti non possono eseguire una delle operazioni seguenti:

- Aggiungere l'app personalmente o in una chat o in un team
- Inviare messaggi al bot dell'app
- Eseguire le azioni dei pulsanti che restituiscono informazioni all'app, ad esempio i messaggi di azione  
- Visualizzare la scheda dell'app
- Configurare i connettori per la ricezione delle notifiche
- Usare l'estensione di messaggistica dell'app

Il portale Legacy ha consentito il controllo delle app a livello di organizzazione, il che significa che quando un'app viene bloccata, è bloccata per tutti gli utenti dell'organizzazione. L'impostazione dell'app a livello di organizzazione nei criteri di autorizzazione per le app funziona esattamente nello stesso modo.

Per i criteri di autorizzazione delle app assegnati a utenti specifici, se è stata consentita un'app con un bot o una funzionalità di connessione e quindi bloccata e se l'app è consentita solo per alcuni utenti in un contesto condiviso, i membri di una chat di gruppo o un canale che non hanno l'autorizzazione per l'app  può visualizzare la cronologia e i messaggi inviati dal bot o dal connettore, ma non possono interagire con esso.

 ## <a name="related-topics"></a>Argomenti correlati
- [Impostazioni di amministrazione per le app in Teams](admin-settings.md)
