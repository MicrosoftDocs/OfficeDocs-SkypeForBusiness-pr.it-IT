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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di ID chiamante in Microsoft teams per modificare o bloccare l'ID chiamante degli utenti di teams nell'organizzazione.
ms.openlocfilehash: dde534d0c74b11b3c3131a7d5c9eb8611135f70f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349780"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri di ID chiamante in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Come amministratore, puoi usare i criteri di ID chiamante in Microsoft teams per cambiare o bloccare l'ID chiamante (noto anche come ID linea chiamante). Per impostazione predefinita, il numero di telefono degli utenti di teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono dei chiamanti PSTN può essere visualizzato quando chiamano un utente di teams. Puoi usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di team dell'organizzazione o bloccare un numero in arrivo.

Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante per visualizzare il numero di telefono principale dell'organizzazione anziché i numeri di telefono degli utenti.

Puoi gestire i criteri ID chiamante accedendo **Voice**ai  >  **criteri ID chiamante** vocale nell'interfaccia di amministrazione di Microsoft teams. È possibile usare il criterio globale (predefinito per l'intera organizzazione) o creare criteri personalizzati e assegnarli agli utenti. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente.

## <a name="create-a-custom-caller-id-policy"></a>Creare un criterio ID chiamante personalizzato

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.
2. Fare clic su **Aggiungi**. <br>
![Screenshot della nuova pagina dei criteri ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. Da qui scegliere le impostazioni desiderate:

    - **Bloccare l'ID chiamante in arrivo**: attivare questa impostazione per bloccare l'ID chiamante delle chiamate in arrivo dalla visualizzazione.
    - **Eseguire l'override dei criteri ID chiamante**: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni dei criteri relativi alla visualizzazione del loro numero per i chiamanti. Ciò significa che gli utenti possono scegliere se visualizzare l'ID chiamante. Per altre informazioni, vedere [controllo dell'utente finale dell'ID chiamante in uscita](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).
    - **Sostituire l'ID chiamante con**: impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:

        - **Numero dell'utente**: Visualizza il numero dell'utente. 
        - **Numero di servizio**: consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.
        - **Anonymous**: Visualizza l'ID chiamante come anonimo.

    - **Sostituire l'ID chiamante con questo numero di servizio**: scegliere un numero di servizio per sostituire l'ID chiamante degli utenti. Questa opzione è disponibile se è **stato selezionato numero di servizio** in **Sostituisci l'ID chiamante con**.

5. Fare clic su **Salva**.

## <a name="edit-a-caller-id-policy"></a>Modificare un criterio ID chiamante

È possibile modificare il criterio globale o i criteri personalizzati creati. 

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**, passa a  >  **criteri ID chiamante**vocale.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Modificare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Assegnare un criterio ID chiamante personalizzato agli utenti

È possibile usare l'interfaccia di amministrazione di Microsoft teams per assegnare un criterio personalizzato a uno o più utenti o al modulo di PowerShell di Skype for business per assegnare un criterio personalizzato agli utenti di un gruppo, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a>Assegnare un criterio ID linea chiamante personalizzato agli utenti

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri ID chiamante**selezionare il criterio che si vuole assegnare e quindi scegliere **Salva**.

Per assegnare un criterio a più utenti alla volta:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi cerca gli utenti o filtra la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.  

Si può anche procedere nel modo seguente:

1. Accedere ai **Microsoft Teams admin center**  >  **Voice**  >  **criteri ID chiamante**vocale dell'interfaccia di amministrazione di Microsoft teams.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
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
- [Assegnare criteri agli utenti in teams](assign-policies.md)
