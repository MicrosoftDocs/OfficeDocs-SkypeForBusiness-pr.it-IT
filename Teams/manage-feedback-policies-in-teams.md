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
ms.openlocfilehash: b489e574a1d1c2a2b1ac5faf69626e997dbbfaa9
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938485"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gestire i criteri di feedback in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft per farci sapere come procedere, direttamente dall'interno dei client desktop e Web teams. Stiamo migliorando continuamente l'esperienza dei team e usiamo questo feedback per migliorare le squadre.

**Funzionalità Invia feedback**

Gli utenti possono inviare commenti e suggerimenti su teams per **aiutarci**a  >  **fornire feedback** in teams. I dati inviati tramite il **feedback** vengono considerati come dati di supporto nell'ambito del contratto Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "dati del cliente" o "dati personali".

![Screenshot dell'opzione Invia feedback in teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Sondaggi**

Gli utenti possono anche valutare la propria esperienza con i team e inviarci i dettagli relativi alla valutazione assegnata. Questo sondaggio popup viene visualizzato agli utenti di tanto in tanto in teams. Quando un utente fa clic su **Fornisci un feedback** nella notifica, il sondaggio viene visualizzato per il completamento.

![Screenshot della notifica e del modulo del sondaggio in teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Impostare se gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft

Come amministratore, puoi controllare se gli utenti dell'organizzazione possono inviare commenti e suggerimenti su Teams a Microsoft tramite **feedback** e se ricevono il sondaggio. Per impostazione predefinita, a tutti gli utenti dell'organizzazione vengono assegnati automaticamente i criteri globali (per impostazione predefinita) e la funzionalità **Invia feedback** e il sondaggio sono abilitati nel criterio. L'eccezione è teams for Education, in cui le funzionalità sono abilitate per insegnanti e disabili per gli studenti.

È possibile modificare i criteri globali oppure creare e assegnare criteri personalizzati. Dopo aver modificato il criterio globale o assegnato un criterio personalizzato, è possibile che le modifiche apportate vengano applicate in poche ore.

Supponiamo, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite **feedback** e ricevere sondaggi, ad eccezione dei nuovi assunti in formazione. In questo scenario creerai un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti. Tutti gli altri utenti dell'organizzazione ottengono il criterio globale con le funzionalità attivate.  

Puoi gestire i criteri di feedback usando PowerShell. Usa il cmdlet **New-CsTeamsFeedbackPolicy** , *che può essere [trovato qui](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, per creare criteri personalizzati e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione.

Per disattivare e attivare le caratteristiche, impostare i parametri seguenti:

 - **Invia feedback**: imposta il parametro **userInitiatedMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di fornire commenti e suggerimenti. Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.
 - **Sondaggi**: imposta il parametro **receiveSurveysMode** su **Enabled** per consentire agli utenti a cui viene assegnato il criterio di ricevere il sondaggio. Per consentire agli utenti di ricevere il sondaggio e consentirne l'opt-out, imposta il parametro su **enabledUserOverride**. In teams gli utenti possono quindi accedere alla privacy **delle impostazioni**  >  **Privacy** e scegliere se partecipare ai sondaggi. Impostando il parametro su **disabled** si disattiva la caratteristica e gli utenti a cui viene assegnato il criterio non riceveranno il sondaggio.

## <a name="create-a-custom-feedback-policy"></a>Creare criteri di feedback personalizzati

In questo esempio creiamo i criteri di feedback denominati nuovi criteri di feedback sul noleggio e disattiviamo la possibilità di fornire feedback tramite **feedback** e il sondaggio.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Assegnare criteri di feedback personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In questo esempio vengono assegnati criteri personalizzati denominati nuovi criteri di feedback di noleggio a un utente denominato User1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell Teams](teams-powershell-overview.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)