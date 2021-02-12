---
title: Gestire i criteri di feedback in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Informazioni su come usare i criteri di feedback per controllare se gli utenti di Teams nell'organizzazione possono inviare feedback su Teams a Microsoft.
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804696"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gestire i criteri di feedback in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gli utenti della tua organizzazione possono inviare feedback su Teams a Microsoft per farci sapere come stiamo facendo, direttamente dai client desktop e web di Teams. Facciamo del nostro meglio per migliorare l'esperienza di Teams e usiamo questo feedback per migliorare Teams.

> [!NOTE]
> I criteri di feedback non sono disponibili nelle distribuzioni GCC, GCC High o DOD.

**La funzionalità Invia feedback**

Gli utenti possono inviarci commenti e suggerimenti su Teams selezionando **Aiutaci a**  >  **inviare feedback** in Teams. I dati inviati tramite Invia **feedback** sono considerati come "Dati di supporto" ai sensi del contratto di Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "Dati dei clienti" o "Dati personali".

![Screenshot dell'opzione Invia feedback in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

**Sondaggi**

Gli utenti possono anche valutare la loro esperienza con Teams e inviarci dettagli sulla valutazione che assegnano. Questo sondaggio popup viene visualizzato di tanto in tanto agli utenti in Teams. Quando un utente fa **clic su Invia feedback** nella notifica, il sondaggio viene visualizzato per il completamento.

![Screenshot della notifica e del modulo del sondaggio in Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Stabilire se gli utenti possono inviare feedback su Teams a Microsoft

Gli amministratori possono controllare se gli utenti dell'organizzazione possono inviare feedback su Teams a Microsoft tramite Invia **feedback** e se ricevono o meno il sondaggio. Per impostazione predefinita, a tutti gli utenti dell'organizzazione viene assegnato automaticamente il criterio globale (impostazione predefinita a livello di organizzazione) e la caratteristica Invia **feedback** e il sondaggio sono abilitati nel criterio. L'eccezione è Teams per l'istruzione, in cui le funzionalità sono abilitate per gli insegnanti e disabilitate per gli studenti.

È possibile modificare i criteri globali o creare e assegnare criteri personalizzati. Dopo aver modificato i criteri globali o aver assegnato un criterio personalizzato, l'applicazione delle modifiche può richiedere alcune ore.

Si supponga, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback tramite Invia **feedback** e ricevere sondaggi ad eccezione dei nuovi assunti in formazione. In questo scenario viene creato un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti. Tutti gli altri utenti dell'organizzazione ottengono i criteri globali con le caratteristiche attivate.  

È possibile gestire i criteri di feedback con PowerShell. Usare il cmdlet **New-CsTeamsFeedbackPolicy,** disponibile qui, per creare un criterio personalizzato e il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione. *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*

Per disattivare e attivare le funzionalità, impostare i parametri seguenti:

 - **Inviare feedback:** impostare **il parametro userInitiatedMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di fornire feedback. Se si imposta il **parametro su disabilitato,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.
 - **Sondaggi:** impostare il **parametro receiveSurveysMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di ricevere il sondaggio. Per fare in modo che gli utenti ricevano il sondaggio e consentano loro di rifiutare esplicitamente, impostare il parametro **su enabledUserOverride.** In Teams, gli utenti possono quindi accedere **a**  >  **Impostazioni privacy** e scegliere se partecipare ai sondaggi. Impostando il parametro **su disabled,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non riceveranno il sondaggio.

## <a name="create-a-custom-feedback-policy"></a>Creare criteri di feedback personalizzati

In questo esempio vengono creati criteri di feedback denominati Criteri di feedback per i nuovi assunti e viene disattivata la possibilità di inviare feedback tramite Invia **feedback** e il sondaggio.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>Assegnare criteri di feedback personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

In questo esempio viene assegnato un criterio personalizzato denominato Criteri di feedback per i nuovi assunti a un utente denominato utente1.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Teams su PowerShell](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)