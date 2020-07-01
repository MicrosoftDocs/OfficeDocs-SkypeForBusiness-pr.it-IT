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
ms.openlocfilehash: 41466640f33769a64ce14d5d3dc47959c876a5bc
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938465"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri di ID chiamante in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Come amministratore, puoi usare i criteri di ID chiamante in Microsoft teams per cambiare o bloccare l'ID chiamante (noto anche come ID linea chiamante). Per impostazione predefinita, il numero di telefono degli utenti di teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono dei chiamanti PSTN può essere visualizzato quando chiamano un utente di teams. Puoi usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di team dell'organizzazione o bloccare un numero in arrivo.

Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante per visualizzare il numero di telefono principale dell'organizzazione anziché i numeri di telefono degli utenti.

Puoi gestire i criteri ID chiamante accedendo **Voice**ai  >  **criteri ID chiamante** vocale nell'interfaccia di amministrazione di Microsoft teams. Puoi usare il criterio globale (predefinito per l'intera organizzazione) oppure creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

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

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[New-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Assegnare criteri agli utenti in teams](assign-policies.md)
