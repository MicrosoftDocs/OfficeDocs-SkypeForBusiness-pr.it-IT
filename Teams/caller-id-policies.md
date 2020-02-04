---
title: Gestire i criteri di ID chiamante in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di ID chiamante in Microsoft teams per modificare o bloccare l'ID chiamante degli utenti di teams nell'organizzazione.
ms.openlocfilehash: f5a1d52f10bb60ced33b05339f81ecd0a6a363f5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695591"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri di ID chiamante in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Come amministratore, puoi usare i criteri di ID chiamante in Microsoft teams per cambiare o bloccare l'ID chiamante (noto anche come ID linea chiamante). Per impostazione predefinita, il numero di telefono degli utenti di teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono dei chiamanti PSTN può essere visualizzato quando chiamano un utente di teams. Puoi usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di team dell'organizzazione o bloccare un numero in arrivo.

Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante per visualizzare il numero di telefono principale dell'organizzazione anziché i numeri di telefono degli utenti.

Puoi gestire i criteri ID chiamante accedendo ai**criteri ID chiamante** **vocale** > nell'interfaccia di amministrazione di Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione otterranno automaticamente il criterio globale a meno che non si creino e non si assegnano criteri personalizzati.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.

## <a name="create-a-custom-caller-id-policy"></a>Creare un criterio ID chiamante personalizzato

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a**criteri ID chiamante** **vocale** > .
2. Fare clic su **Aggiungi**.
![Screenshot della nuova pagina dei criteri ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. Da qui scegliere le impostazioni desiderate:

    - **Bloccare l'ID chiamante in arrivo**: attivare questa impostazione per bloccare l'ID chiamante delle chiamate in arrivo dalla visualizzazione.
    - **Gli utenti possono eseguire l'override del criterio ID chiamante**: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni dei criteri relativi alla visualizzazione del numero ai chiamanti. Ciò significa che gli utenti possono scegliere se visualizzare l'ID chiamante.
    - **Sostituisci ID chiamante**: impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:

        - **Numero dell'utente**: Visualizza il numero dell'utente. 
        - **Numero di servizio**: consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.
        - **Anonymous**: Visualizza l'ID chiamante come anonimo.

    - **Numero di servizio da usare per sostituire l'ID chiamante**: scegliere un numero di servizio per sostituire l'ID chiamante degli utenti. Questa opzione è disponibile se il **numero di servizio è stato** selezionato in **Sostituisci ID chiamante**.

5. Fai clic su **Salva**.

## <a name="edit-a-caller-id-policy"></a>Modificare un criterio ID chiamante

È possibile modificare il criterio globale o i criteri personalizzati creati. 

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a**criteri ID chiamante** **vocale** > .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Modificare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Assegnare un criterio ID chiamante personalizzato agli utenti

È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare criteri personalizzati a gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>Assegnare un criterio ID linea chiamante personalizzato a un utente

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri ID chiamante**selezionare il criterio che si vuole assegnare e quindi scegliere **Salva**.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>Assegnare criteri di ID linea di chiamata personalizzati a più utenti alla volta

Per assegnare un criterio ID linea chiamante personalizzato a più utenti alla volta, vedere [modificare le impostazioni utente di teams in blocco](edit-user-settings-in-bulk.md).

In alternativa, è anche possibile eseguire le operazioni seguenti:

1. Accedere ai**criteri ID chiamante** > **vocale** > dell'interfaccia di **amministrazione di Microsoft teams**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Selezionare **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per ogni utente che si vuole aggiungere.
5. Al termine dell'aggiunta di utenti, selezionare **Salva**.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Assegnare criteri di ID chiamante personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business. Per altre informazioni sull'uso di PowerShell per la gestione dei team, vedere [Cenni preliminari su teams PowerShell](teams-powershell-overview.md).

In questo esempio, assegniamo un criterio lID chiamante personalizzato denominato criteri ID chiamante supporto per tutti gli utenti del gruppo di supporto contoso.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Ottenere i membri del gruppo specificato.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un determinato criterio ID chiamante. In questo esempio è supportato il criterio ID chiamante.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

 ## <a name="related-topics"></a>Argomenti correlati

- [New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

