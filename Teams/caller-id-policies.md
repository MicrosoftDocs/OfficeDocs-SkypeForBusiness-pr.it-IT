---
title: Gestire i criteri dell'ID chiamante in Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come usare e gestire i criteri ID chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante degli utenti di Teams nell'organizzazione.
ms.openlocfilehash: 4abeccb7a536885707ec43874d00f2a05a14551d
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414704"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri dell'ID chiamante in Microsoft Teams

Per impostazione predefinita, quando un utente di Teams effettua una chiamata a un telefono PSTN, il numero di telefono dell'utente di Teams è visibile. Analogamente, quando un chiamante PSTN effettua una chiamata a un utente di Teams, il numero di telefono del chiamante PSTN è visibile.

Gli amministratori possono usare i criteri ID chiamante per modificare o bloccare l'ID chiamante (noto anche come ID riga chiamante). È possibile usare i criteri ID chiamante per visualizzare un numero di telefono alternativo per gli utenti di Teams nell'organizzazione, bloccare il numero di telefono in uscita, bloccare la visualizzazione di un numero in arrivo o impostare il nome del chiamante (CNAM). Ad esempio, quando un utente effettua una chiamata, è possibile modificare l'ID chiamante in modo da visualizzare il numero di telefono principale e il nome della società dell'organizzazione al posto del numero di telefono dell'utente.

I criteri ID chiamante vengono gestiti tramite i **criteri ID chiamante** **vocale** >  nell'interfaccia di amministrazione di Microsoft Teams. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

## <a name="create-a-custom-caller-id-policy"></a>Creare criteri ID chiamante personalizzati

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare ai **criteri ID chiamante** **vocale** > .
2. Fare clic su **Aggiungi**. <br>
![Screenshot della pagina dei nuovi criteri ID chiamante nell'interfaccia di amministrazione.](media/caller-id-policies-add-policy.png)
3. Immettere un nome e una descrizione per il criterio.
4. Da qui scegliere le impostazioni desiderate:

    - **Blocca ID chiamante in arrivo**: attivare questa impostazione per bloccare la visualizzazione dell'ID chiamante delle chiamate in arrivo.
    - **Esegui l'override del criterio ID chiamante**: attiva questa impostazione per consentire agli utenti di ignorare le impostazioni del criterio relative alla visualizzazione del loro numero ai chiamanti o meno. Questo significa che gli utenti possono scegliere se visualizzare o meno il proprio ID chiamante. Per altre informazioni, vedere [Controllo dell'ID chiamante in uscita da parte dell'utente](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id) finale.
    - **Sostituire l'ID chiamante con**: Impostare l'ID chiamante da visualizzare per gli utenti selezionando una delle opzioni seguenti:

        - **Numero utente**: visualizza il numero dell'utente. 
        - **Numero di servizio**: consente di impostare un numero di telefono di servizio da visualizzare come ID chiamante.
        - **Anonimo**: visualizza l'ID chiamante come Anonimo.

    - **Sostituire l'ID chiamante con questo numero di servizio**: scegliere un numero di servizio per sostituire l'ID chiamante degli utenti. Questa opzione è disponibile se è stato selezionato **Numero di servizio** in **Sostituisci l'ID chiamante con**.

5. Fare clic su **Salva**.

## <a name="edit-a-caller-id-policy"></a>Modificare un criterio ID chiamante

È possibile modificare i criteri globali o i criteri personalizzati creati. 

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare ai **criteri ID chiamante** **vocale** > .
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Modificare le impostazioni desiderate e quindi fare clic su **Salva**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Assegnare criteri ID chiamante personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
