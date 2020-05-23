---
title: Gestire i criteri del routing delle chiamate di emergenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di routing delle chiamate di emergenza in Microsoft teams per configurare i numeri di emergenza e specificare la modalità di routing delle chiamate di emergenza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf47bc27ddc72d6f767815b5323b69f6e5fd00ca
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350210"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams

Se è stato distribuito il routing diretto del sistema telefonico nell'organizzazione, è possibile usare i criteri di routing delle chiamate di emergenza in Microsoft teams per configurare i numeri di emergenza e specificare il modo in cui le chiamate di emergenza vengono instradate. I criteri di routing delle chiamate di emergenza determinano se i servizi di emergenza avanzati sono abilitati per gli utenti a cui sono assegnati i criteri, i numeri usati per chiamare i servizi di emergenza, ad esempio 911 negli Stati Uniti, e la modalità di routing delle chiamate ai servizi di emergenza.

Puoi gestire i criteri di routing delle chiamate di **Voice**emergenza passando a  >  **criteri** per l'emergenza vocale nell'interfaccia di amministrazione di Microsoft teams o tramite Windows PowerShell. I criteri possono essere assegnati a utenti e [siti di rete](cloud-voice-network-settings.md).

Per gli utenti, è possibile usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti otterranno automaticamente il criterio globale a meno che non si creino e si assegnano criteri personalizzati. Tieni presente che puoi modificare le impostazioni nel criterio globale, ma non puoi rinominarle o eliminarle. Per i siti di rete, è possibile creare e assegnare criteri personalizzati.

Se i criteri di routing delle chiamate di emergenza sono stati assegnati a un sito di rete e a un utente e, se tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce quello assegnato all'utente.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Creare un criterio di routing delle chiamate di emergenza personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di routing delle chiamate** .
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Per abilitare servizi di emergenza avanzati, attivare **servizi di emergenza avanzati**. Quando sono abilitati i servizi di emergenza avanzati, i team recuperano le informazioni sui criteri e sulla posizione dal servizio e includono tali informazioni come parte della chiamata di emergenza.
5. Definire uno dei numeri di emergenza. Per eseguire questa operazione, in **numeri di emergenza**eseguire le operazioni seguenti:
    1. **Stringa di chiamata di emergenza**: immettere la stringa di chiamata di emergenza. Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza.
        > [!NOTE]
        > Per il routing diretto, ci si sta allontanando dai client di teams inviando chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza. Finché la transizione non viene completata, il modello di route vocale in modo che corrisponda a una stringa di chiamata di emergenza dovrebbe garantire che venga eseguita una corrispondenza per le stringhe che hanno e non hanno un "+" precedente, ad esempio 911 e + 911. Ad esempio, ^ \\ +? 911 o. *.
    2. **Maschera di chiamata di emergenza**: per ogni numero di emergenza è possibile specificare zero o più maschere di chiamate di emergenza. Una maschera di chiamata è il numero che si vuole tradurre nel valore della stringa di chiamata di emergenza. In questo modo, i numeri di emergenza alternativi possono essere chiamati e i servizi di emergenza raggiungono ancora la chiamata. <br>Ad esempio, Aggiungi 112 come maschera di chiamata di emergenza, che è il numero del servizio di emergenza per la maggior parte dell'Europa e 911 come stringa di chiamata di emergenza. Un utente di teams proveniente da Europa che sta visitando potrebbe non sapere che 911 è il numero di emergenza negli Stati Uniti e quando chiama 112, viene effettuata la chiamata a 911. Per definire più maschere di chiamata, separare ogni valore con un punto e virgola. Ad esempio, 112; 212.
    3. **Uso PSTN**: selezionare l'utilizzo PSTN (Public Switched Telephone Network). L'utilizzo PSTN viene usato per determinare quale route viene usata per instradare chiamate di emergenza da utenti autorizzati ad usarle. La route associata a questo uso deve puntare a un trunk SIP dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di risposta di sicurezza pubblica più vicino (PSAP).

    > [!NOTE]
    > Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio. Questo significa che per un criterio puoi definire più numeri di emergenza ed è possibile impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata solo una volta.

6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modificare i criteri di routing delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare il criterio globale o i criteri personalizzati creati.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di routing delle chiamate** .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi fare clic su **modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Assegnare criteri di routing delle chiamate di emergenza personalizzati agli utenti

### <a name="using-the-microsoft-teams-admin-center"></a>Usando l'interfaccia di amministrazione di Microsoft Teams.

Per assegnare un criterio a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.
2. Fare clic su **criteri**e quindi fare clic su **modifica**accanto a **criteri assegnati**.
3. In **criteri di routing delle chiamate di emergenza**selezionare il criterio che si vuole assegnare e quindi fare clic su **Salva**.

Per assegnare un criterio a più utenti alla volta:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi cerca gli utenti o filtra la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, fare clic sul &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Fare clic su **Modifica impostazioni**, apportare le modifiche desiderate e quindi fare clic su **applica**.  

Si può anche procedere nel modo seguente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Voice**selezionare  >  **criteri**per l'emergenza vocale e quindi fare clic sulla scheda **criteri di routing delle chiamate** .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio.
3. Scegliere **Gestisci utenti**.
4. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
5. Al termine dell'aggiunta di utenti, fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>Assegnare criteri di routing delle chiamate di emergenza personalizzati a un utente

Vedere [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>Assegnare criteri di routing delle chiamate di emergenza personalizzati agli utenti di un gruppo

È consigliabile assegnare criteri di routing delle chiamate di emergenza personalizzati a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti in un gruppo di sicurezza o di distribuzione. A tale scopo, è possibile connettersi al modulo di PowerShell per il grafico di Azure Active Directory e al modulo di PowerShell per Skype for business.

In questo esempio viene assegnato un criterio denominato criteri di routing delle chiamate di emergenza HR a tutti gli utenti del gruppo contoso HR.  

> [!NOTE]
> Prima di tutto, assicurati di connetterti a Azure Active Directory PowerShell per modulo grafico e modulo di PowerShell per Skype for business seguendo la procedura descritta in [Connetti a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Ottenere il GroupObjectId del gruppo specifico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
Ottenere i membri del gruppo specificato.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un determinato criterio teams. In questo esempio si tratta di criteri di routing delle chiamate di emergenza HR.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Assegnare criteri di routing delle chiamate di emergenza personalizzati a un sito di rete

Utilizzare il cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.

Questo esempio Mostra come assegnare un criterio denominato criteri di routing delle chiamate di emergenza 1 al sito di Microsoft1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri delle chiamate di emergenza in teams](manage-emergency-calling-policies.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)
