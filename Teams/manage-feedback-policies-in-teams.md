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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare i criteri di feedback per controllare se gli utenti dei team dell'organizzazione possono inviare commenti e suggerimenti sui team a Microsoft.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184681"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gestire i criteri di feedback in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft per **contribuire** > a**fornire feedback** nei client teams. Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto di Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft

Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft. Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita a livello globale) e la funzionalità è abilitata nel criterio. L'eccezione è teams for Education, in cui la funzionalità è abilitata per insegnanti e disabili per gli studenti.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Se a un utente viene assegnato un criterio personalizzato, tale criterio si applica all'utente. Se a un utente non viene assegnato un criterio personalizzato, il criterio globale si applica all'utente. Dopo aver modificato il criterio globale o assegnato un criterio, possono essere necessarie fino a 24 ore affinché le modifiche abbiano effetto.

Supponiamo, ad esempio, di consentire a tutti gli utenti dell'organizzazione di inviare commenti e suggerimenti ad eccezione dei nuovi assunti in formazione. In questo scenario creerai un criterio personalizzato per disattivare la caratteristica e assegnarla ai nuovi assunti. Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con la funzionalità attivata.  

Puoi usare il cmdlet **New-CsTeamsFeedbackPolicy** per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione. 

Imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di inviare commenti e suggerimenti. Impostando il parametro **** su Disabled si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.

## <a name="create-a-custom-feedback-policy"></a>Creare criteri di feedback personalizzati

In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire commenti e suggerimenti.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>Assegnare un criterio di feedback personalizzato

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>Assegnare un criterio di feedback personalizzato a un utente

In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>Assegnare criteri di feedback personalizzati agli utenti di un gruppo

È consigliabile assegnare un criterio di feedback personalizzato a più utenti già identificati. Ad esempio, potresti voler assegnare un criterio a tutti gli utenti di un gruppo di sicurezza.

In questo esempio, assegniamo i criteri di feedback personalizzati denominati nuovi criteri di feedback di noleggio a tutti gli utenti nel gruppo nuove assunzioni Contoso.  

Ottenere il GroupObjectId del gruppo specifico.
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
Ottenere i membri del gruppo specificato.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Assegnare tutti gli utenti del gruppo a un particolare criterio di feedback. In questo esempio si tratta di nuovi criteri di feedback sulle assunzioni.
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
A seconda del numero di membri del gruppo, questo comando può richiedere diversi minuti per l'esecuzione.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)