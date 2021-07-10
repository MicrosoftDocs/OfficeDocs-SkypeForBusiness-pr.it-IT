---
title: Gestire i criteri di routing delle chiamate di emergenza per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare la modalità di instradamento delle chiamate di emergenza.
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: 86f73bed2e086efee666e5592ca3f42e9756096c
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354306"
---
# <a name="manage-emergency-call-routing-policies-for-direct-routing"></a>Gestire i criteri di routing delle chiamate di emergenza per il routing diretto

Se nell'organizzazione è stato distribuito [Sistema telefonico Routing](direct-routing-landing-page.md) diretto, è possibile usare i criteri di routing delle chiamate di emergenza in Microsoft Teams per configurare i numeri di emergenza e specificare la modalità di instradamento delle chiamate di emergenza. Un criterio di routing delle chiamate di emergenza determina se i servizi di emergenza migliorati sono abilitati per gli utenti a cui è assegnato il criterio, i numeri usati per chiamare i servizi di emergenza (ad esempio, il 911 negli Stati Uniti) e la modalità di instradamento delle chiamate ai servizi di emergenza.

Per gestire i criteri di routing delle chiamate di emergenza, è possibile accedere ai criteri di emergenza vocali nell'interfaccia di amministrazione di Microsoft Teams o usando  >   Windows PowerShell. I criteri possono essere assegnati a utenti e [siti di rete.](cloud-voice-network-settings.md)

Per gli utenti, è possibile usare i criteri globali (impostazione predefinita a livello di organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti riceveranno automaticamente i criteri globali a meno che non si creino e assegnino criteri personalizzati. Tenere presente che è possibile modificare le impostazioni nel criterio globale, ma non è possibile rinominarlo o eliminarlo. Per i siti di rete, è possibile creare e assegnare criteri personalizzati.

Se è stato assegnato un criterio di routing delle chiamate di emergenza a un sito di rete e a un utente e tale utente si trova in tale sito di rete, il criterio assegnato al sito di rete sostituisce il criterio assegnato all'utente.

## <a name="create-a-custom-emergency-call-routing-policy"></a>Creare un criterio di routing delle chiamate di emergenza personalizzato

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda Criteri **routing chiamate.**
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio.
4. Per abilitare le chiamate di emergenza dinamiche, attiva **Chiamate di emergenza dinamiche.** Quando le chiamate di emergenza dinamiche sono abilitate, Teams recupera le informazioni sui criteri e sulla posizione dal servizio e le include come parte della chiamata di emergenza.
5. Definire uno o più numeri di emergenza. A questo scopo, in **Numeri di emergenza** fare clic su **Aggiungi** e quindi eseguire le operazioni seguenti:
    1. **Stringa di chiamata di emergenza:** immettere la stringa di chiamata di emergenza. Questa stringa di chiamata indica che una chiamata è una chiamata di emergenza.
        > [!NOTE]
        > Per il routing diretto, ci stiamo allontanando dai client Teams che inviano chiamate di emergenza con un "+" davanti alla stringa di chiamata di emergenza. Finché la transizione non viene completata, il modello di percorso vocale per la corrispondenza con una stringa di chiamata di emergenza deve verificare che sia stata trovata una corrispondenza per le stringhe che hanno e non hanno un "+" precedente, ad esempio 911 e +911. Ad esempio, ^ \\ +?911 o .*.
    2. **Maschera di chiamata di emergenza:** per ogni numero di emergenza, è possibile specificare zero o più maschere di chiamata di emergenza. Una maschera di chiamata è il numero che si vuole tradurre nel valore della stringa di chiamata di emergenza. In questo modo è possibile comporre numeri di emergenza alternativi e consentire comunque alla chiamata di raggiungere i servizi di emergenza. <br>Ad esempio, si aggiunge 112 come maschera di chiamata di emergenza, che è il numero del servizio di emergenza per la maggior parte dell'Europa, e 911 come stringa di chiamata di emergenza. Un Teams dall'Europa che sta visitando potrebbe non sapere che 911 è il numero di emergenza negli Stati Uniti e quando compone il 112, la chiamata viene effettuata al 911. Per definire più maschere di chiamata, separare ogni valore con un punto e virgola. Ad esempio, 112;212.
    3. **Record di utilizzo PSTN:** selezionare il record di utilizzo PSTN (Public Switched Telephone Network). Il record di utilizzo PSTN viene usato per determinare quale percorso viene usato per instradare le chiamate di emergenza da parte di utenti autorizzati a usarle. La route associata a questo utilizzo deve puntare a un trunk SIP (Session Initiation Protocol) dedicato alle chiamate di emergenza o a un gateway ELIN (Emergency Location Identification Number) che instrada le chiamate di emergenza al punto di risposta per la sicurezza pubblica (PSAP) più vicino.

    > [!NOTE]
    > Le stringhe di chiamata e le maschere di chiamata devono essere univoche all'interno di un criterio. Questo significa che per un criterio è possibile definire più numeri di emergenza ed è possibile impostare più maschere di chiamata per una stringa di chiamata, ma ogni stringa di chiamata e maschera di chiamata deve essere usata una sola volta.

6. Fare clic su **Salva**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [New-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/new-csteamsemergencycallroutingpolicy).

## <a name="edit-an-emergency-call-routing-policy"></a>Modificare un criterio di routing delle chiamate di emergenza

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione, passare a Criteri di emergenza vocale e quindi fare  >  clic sulla scheda Criteri **routing chiamate.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Apportare le modifiche desiderate e quindi fare clic su **Salva.**

### <a name="using-powershell"></a>Utilizzo di PowerShell

Vedere [Set-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/set-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>Assegnare un criterio di routing delle chiamate di emergenza personalizzato agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

Vedere anche [Grant-CsTeamsEmergencyCallRoutingPolicy](/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>Assegnare un criterio di routing delle chiamate di emergenza personalizzato a un sito di rete

Usare il cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) per assegnare un criterio di routing delle chiamate di emergenza a un sito di rete.

Questo esempio mostra come assegnare un criterio denominato Criterio routing chiamate di emergenza 1 al sito Sito1.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>Argomenti correlati

[Gestire i criteri per le chiamate di emergenza in Teams](manage-emergency-calling-policies.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)