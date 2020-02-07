---
title: Gestire i criteri di feedback in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i criteri di feedback per controllare se gli utenti dei team dell'organizzazione possono inviare commenti e suggerimenti sui team a Microsoft.
ms.openlocfilehash: 70771f4a5e7c1376970ac3ac96cb9a4f822882a8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837546"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gestire i criteri di feedback in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft per farci sapere come procedere, direttamente dall'interno dei client desktop e Web teams. Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.

**Funzionalità Invia feedback**

Gli utenti possono inviare commenti e suggerimenti su teams per **aiutarci** > a**fornire feedback** in teams. I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto di Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Sondaggi**

Gli utenti possono anche valutare la propria esperienza con i team e inviarci i dettagli relativi alla valutazione assegnata. Questo sondaggio popup viene visualizzato agli utenti di tanto in tanto in teams. Quando un utente fa clic su **Fornisci un feedback** nella notifica, il sondaggio viene visualizzato per il completamento.

![Screenshot della notifica e del modulo del sondaggio in teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft

Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft tramite **feedback** e se ricevono il sondaggio. Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita) e la funzionalità **Invia feedback** e il sondaggio sono abilitati nel criterio. L'eccezione è teams for Education, in cui le funzionalità sono abilitate per insegnanti e disabili per gli studenti.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente. Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.

Supponiamo, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite **feedback** e ricevere sondaggi, ad eccezione dei nuovi assunti in formazione. In questo scenario creerai un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti. Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con le funzionalità attivate.  

Si usa il cmdlet **New-CsTeamsFeedbackPolicy** , *che può essere [trovato qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

Per disattivare e attivare le caratteristiche, impostare i parametri seguenti:

 - **Invia feedback**: imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di fornire commenti e suggerimenti. Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.
 - **Sondaggi**: imposta il parametro **receiveSurveysMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di ricevere il sondaggio. Per consentire agli utenti di ricevere il sondaggio e consentirne l'opt-out, imposta il parametro su **enabledUserOverride**. In teams gli utenti possono quindi accedere alla**privacy** **delle impostazioni** > e scegliere se partecipare ai sondaggi. Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non riceveranno il sondaggio.

## <a name="create-a-custom-feedback-policy"></a>Creare criteri di feedback personalizzati

In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire feedback tramite **feedback** e il sondaggio.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Assegnare un criterio di feedback personalizzato

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Assegnare un criterio di feedback personalizzato a un utente

In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Assegnare criteri di feedback personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio di feedback personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.

In questo esempio, assegniamo i criteri di feedback personalizzati denominati nuovi criteri di feedback di noleggio a tutti gli utenti nel gruppo nuove assunzioni Contoso.  

Ottenere il GroupObjectId del gruppo specifico.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Ottenere i membri del gruppo specificato.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un particolare criterio di feedback. In questo esempio si tratta di nuovi criteri di feedback sulle assunzioni.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)
