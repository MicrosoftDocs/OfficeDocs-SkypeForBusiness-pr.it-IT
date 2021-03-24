---
title: Gestire i criteri dell'ID chiamante in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Informazioni su come usare e gestire i criteri id chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante degli utenti di Teams nell'organizzazione.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102782"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri dell'ID chiamante in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Gli amministratori possono usare i criteri id chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante (noto anche come ID linea chiamante). Per impostazione predefinita, il numero di telefono degli utenti di Teams può essere visualizzato quando effettuano una chiamata a un telefono PSTN e il numero di telefono di chiamanti PSTN può essere visualizzato quando chiamano un utente di Teams. È possibile usare i criteri id chiamante per visualizzare un numero di telefono alternativo per gli utenti di Teams nell'organizzazione o per impedire la visualizzazione di un numero in arrivo.

Ad esempio, quando gli utenti effettuano una chiamata, è possibile modificare l'ID chiamante in modo da visualizzare il numero di telefono principale dell'organizzazione invece dei numeri di telefono degli utenti.

Per gestire i criteri id chiamante, accedere **ai** criteri  >  **ID chiamante vocale** nell'interfaccia di amministrazione di Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

## <a name="create-a-custom-caller-id-policy"></a>Creare criteri ID chiamante personalizzati

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **ID chiamante vocale.**
2. Fare clic su **Aggiungi**. <br>
![Screenshot della nuova pagina dei criteri per l'ID chiamante nell'interfaccia di amministrazione](media/caller-id-policies-add-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. Da qui scegliere le impostazioni desiderate:

    - **Blocca ID chiamante in arrivo:** attiva questa impostazione per impedire la visualizzazione dell'ID chiamante delle chiamate in arrivo.
    - **Ignorare i criteri per l'ID** chiamante: attivare questa impostazione per consentire agli utenti di ignorare le impostazioni nel criterio relativo alla visualizzazione o meno del numero ai chiamanti. Questo significa che gli utenti possono scegliere se visualizzare l'ID chiamante. Per altre informazioni, vedere [Controllo utente finale dell'ID chiamante in uscita.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)
    - **Sostituire l'ID chiamante con**: Impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:

        - **Numero utente:** visualizza il numero dell'utente. 
        - **Numero servizio:** consente di impostare un numero di telefono del servizio da visualizzare come ID chiamante.
        - **Anonimo:** visualizza l'ID chiamante come anonimo.

    - **Sostituire l'ID chiamante con questo numero di servizio:** scegliere un numero di servizio per sostituire l'ID chiamante degli utenti. Questa opzione è disponibile se è stato selezionato **Numero servizio** in Sostituisci **l'ID chiamante con**.

5. Fare clic su **Salva**.

## <a name="edit-a-caller-id-policy"></a>Modificare i criteri per l'ID chiamante

È possibile modificare i criteri globali o i criteri personalizzati creati dall'utente. 

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare **a** Criteri  >  **ID chiamante vocale.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Modificare le impostazioni desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Assegnare criteri ID chiamante personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)