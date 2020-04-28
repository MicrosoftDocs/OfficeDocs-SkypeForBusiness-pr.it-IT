---
title: Gestire i criteri delle chiamate di emergenza in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri delle chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e697e05c4ade1e14ee2f59da5b60413e60e2367
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905108"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gestire i criteri delle chiamate di emergenza in Microsoft Teams

Se l'organizzazione usa i piani di chiamata o il routing diretto del sistema telefonico distribuito, è possibile usare i criteri per le chiamate di emergenza in Microsoft teams per definire cosa succede quando un utente di Teams dell'organizzazione effettua una chiamata di emergenza. Puoi impostare gli utenti a cui inviare una notifica e il modo in cui vengono informati quando un utente a cui viene assegnato il criterio chiama i servizi di emergenza. Ad esempio, è possibile configurare le impostazioni dei criteri per comunicare automaticamente alla scrivania di sicurezza dell'organizzazione e farli ascoltare in chiamate di emergenza.  

Puoi gestire i criteri delle chiamate di emergenza passando ai**criteri di emergenza** **vocale** > nell'interfaccia di amministrazione di Microsoft teams oppure usando Windows PowerShell. I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).

Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati. Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle. Per i siti di rete, è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio per le chiamate di emergenza a un sito di rete e a un utente e se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.

## <a name="create-a-custom-emergency-calling-policy"></a>Creare un criterio di chiamata di emergenza personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Impostare il modo in cui si vuole informare gli utenti dell'organizzazione, in genere il servizio di sicurezza, quando viene effettuata una chiamata di emergenza. A questo scopo, in **modalità notifica**selezionare una delle opzioni seguenti:
    - **Solo notifica**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati.
    - **In conferenza ma in sordina**: viene inviato un messaggio di chat di teams agli utenti e ai gruppi specificati, che possono ascoltare, ma non partecipare, nella conversazione tra il chiamante e l'operatore di PSAP.
5.  Se è stata selezionata la modalità di notifica **in conferenza ma disattivato** , nella casella **Numero chiamata in uscita per le notifiche** è possibile immettere un numero di telefono PSTN di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. Ad esempio, immettere il numero del servizio di sicurezza dell'organizzazione, che riceverà una chiamata quando viene effettuata una chiamata di emergenza e potrà quindi ascoltare o partecipare alla chiamata.
6. Cercare e selezionare uno o più utenti o gruppi, ad esempio il servizio di sicurezza dell'organizzazione, per avvisare quando viene effettuata una chiamata di emergenza.  La notifica può essere inviata agli indirizzi di posta elettronica di utenti, gruppi di distribuzione e gruppi di sicurezza. Può essere notificato un massimo di 50 utenti.
7. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modificare un criterio per le chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Assegnare un criterio di chiamata di emergenza personalizzato agli utenti

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri**per le chiamate di emergenza selezionare i criteri da assegnare e quindi fare clic su **Salva**.

Per assegnare un criterio teams personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare criteri per l'**emergenza** **vocale** > e quindi fare clic sulla scheda **criteri di chiamata** .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>Assegnare un criterio di chiamata di emergenza personalizzato a un utente

Vedere [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>Assegnare un criterio di chiamata di emergenza personalizzato agli utenti di un gruppo

È consigliabile assegnare un criterio di chiamata di emergenza personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.

In questo esempio assegniamo un criterio denominato criteri per le chiamate di emergenza per tutti gli utenti del gruppo operazioni contoso.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
Ottenere i membri del gruppo specificato.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un determinato criterio teams. In questo esempio, i criteri di routing delle chiamate di emergenza delle operazioni.
```
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Assegnare un criterio di chiamata di emergenza personalizzato a un sito di rete

Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio per le chiamate di emergenza a un sito di rete.

L'esempio seguente mostra come assegnare un criterio denominato criteri di chiamata di emergenza contoso 1 al sito di Microsoft1.

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di routing delle chiamate di emergenza in teams](manage-emergency-call-routing-policies.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
