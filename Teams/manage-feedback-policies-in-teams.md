---
title: Gestire i criteri di feedback in Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.reviewer: heprecel
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare i criteri di feedback per controllare se Teams utenti dell'organizzazione possono inviare feedback sulle Teams a Microsoft.
ms.openlocfilehash: 582c5e39fca8dc37cefe8b480b2ff886779f6fa0
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2021
ms.locfileid: "59942101"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Gestire i criteri di feedback in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Gli utenti dell'organizzazione possono inviare feedback su Microsoft Teams per farci sapere come stiamo facendo direttamente da Teams desktop, client Web e dispositivi mobili. Stiamo continuamente migliorando l'esperienza Teams e usiamo questo feedback per migliorare Teams migliori.

> [!NOTE]
> I criteri di feedback non sono disponibili nelle distribuzioni GCC, GCC high o DOD.

**Caratteristica **Invia feedback****

Gli utenti possono inviare commenti e suggerimenti su Teams a Microsoft andando su **Come** inviare feedback in Teams  >   desktop e Web.


![Opzione Invia feedback in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

Accedere al feedback su dispositivi **mobili usando Impostazioni** Guida &  >  **feedback**  >  **Inviare feedback**.

![Opzione Invia feedback in Teams per dispositivi mobili](media/feedback3.jpg)

 I dati inviati tramite Invia **feedback** e Invia **feedback** sono considerati come "Dati di supporto" ai sensi del contratto di Microsoft 365 o Office 365, incluse le informazioni che altrimenti verrebbero considerate "Dati dei clienti" o "Dati personali".


**Sondaggi**

Gli utenti possono anche valutare la loro esperienza con Teams e inviarci dettagli sulla valutazione che danno. Questo sondaggio popup viene visualizzato agli utenti di tanto in tanto in Teams. Quando un utente seleziona **Invia feedback** nella notifica, il sondaggio viene visualizzato per il completamento.

![la notifica e il modulo del sondaggio in Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>Specificare se gli utenti possono inviare commenti e suggerimenti Teams a Microsoft

Gli amministratori possono controllare se gli utenti dell'organizzazione possono inviare feedback sulle Teams a Microsoft e se ricevono il sondaggio. Per impostazione predefinita, a tutti gli utenti dell'organizzazione viene assegnato automaticamente il criterio globale (impostazione predefinita a livello di organizzazione) e la caratteristica di feedback e il sondaggio sono abilitati nel criterio. L'eccezione è Teams per l'istruzione, in cui le funzionalità sono abilitate per i docenti e disabilitate per gli studenti.

È possibile modificare i criteri globali o creare e assegnare criteri personalizzati. Dopo aver modificato i criteri globali o aver assegnato un criterio personalizzato, l'applicazione delle modifiche può richiedere alcune ore.

Si supponga, ad esempio, di voler consentire a tutti gli utenti dell'organizzazione di inviare feedback e ricevere sondaggi ad eccezione dei nuovi assunti in formazione. In questo scenario si crea un criterio personalizzato per disattivare entrambe le caratteristiche e assegnarlo ai nuovi assunti. Tutti gli altri utenti dell'organizzazione ottengono i criteri globali con le funzionalità attivate.  

Per gestire i criteri di feedback, usare PowerShell. Usare il cmdlet [ **New-CsTeamsFeedbackPolicy**](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) per creare un criterio personalizzato. Usare il cmdlet **Grant-CsTeamsFeedbackPolicy** per assegnarlo a uno o più utenti o gruppi di utenti, ad esempio un gruppo di sicurezza o un gruppo di distribuzione. Usare **Set-CsTeamsFeedbackPolicy** per impostare flag specifici.

Per disattivare e attivare le funzionalità, impostare i parametri seguenti:

 - **Inviare commenti** e suggerimenti: impostare **il parametro userInitiatedMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di inviare feedback. Se si imposta il **parametro su disabled,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non hanno la possibilità di inviare commenti e suggerimenti.
 - **Sondaggi:** impostare il **parametro receiveSurveysMode** su **enabled** per consentire agli utenti a cui è assegnato il criterio di ricevere il sondaggio. Per fare in modo che gli utenti ricevano il sondaggio e consentano loro di rifiutare esplicitamente, impostare il parametro **su enabledUserOverride**. In Teams, gli utenti possono quindi passare a Impostazioni privacy e scegliere se partecipare  >   ai sondaggi. Se si imposta il **parametro su disabled,** la caratteristica viene disattivata e gli utenti a cui è assegnato il criterio non riceveranno il sondaggio.
 - **Posta** elettronica: usare il flag **AllowEmailCollection** per aggiungere un campo di posta elettronica.
 - **Raccolta log:** usare il flag **AllowLogCollection** per aggiungere il consenso esplicito per la raccolta di log per gli utenti. La raccolta log è attualmente abilitata solo per dispositivi mobili. Per altre informazioni sui dati condivisi tramite i log, vedere altre [informazioni.](https://go.microsoft.com/fwlink/?linkid=2168178)

## <a name="create-a-custom-feedback-policy"></a>Creare criteri di feedback personalizzati

In questo esempio viene creato un criterio di feedback denominato Criteri di feedback per i nuovi assunti e viene disattivata la possibilità di inviare feedback tramite Invia **feedback** e il sondaggio.

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

- [Teams Panoramica di PowerShell](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
