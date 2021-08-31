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
description: Informazioni su come usare e gestire i criteri id chiamante in Microsoft Teams per modificare o bloccare l'ID chiamante Teams utenti dell'organizzazione.
ms.openlocfilehash: 455bf7e6f2b0e29824188dab3c14ff6cc6b51c91
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731225"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Gestire i criteri dell'ID chiamante in Microsoft Teams

> [!NOTE]
> Per impostare l'ID chiamante su un numero di telefono dell'account della risorsa e per impostare il nome della parte chiamante, usare i cmdlet di PowerShell New-CsCallingLineIdentity o Set-CsCallingLineIdentity nel modulo di PowerShell 2.3.1 o versione successiva di Teams. Queste opzioni non sono attualmente disponibili nell'Microsoft Teams di amministrazione. 

Per impostazione predefinita, quando un Teams effettua una chiamata a un telefono PSTN, il numero di telefono Teams'utente è visibile. Allo stesso modo, quando un chiamante PSTN effettua una chiamata a un Teams utente, il numero di telefono del chiamante PSTN è visibile.

L'amministratore può usare i criteri per l'ID chiamante per modificare o bloccare l'ID chiamante (noto anche come ID linea chiamante). È possibile usare i criteri id chiamante per visualizzare un numero di telefono alternativo per gli utenti Teams dell'organizzazione, bloccare il numero di telefono in uscita, bloccare la visualizzazione di un numero in arrivo o impostare il nome della parte chiamante (CNAM). Ad esempio, quando un utente effettua una chiamata, è possibile modificare l'ID chiamante in modo da visualizzare il numero di telefono principale e il nome della società dell'organizzazione invece del numero di telefono dell'utente.

Per gestire i criteri id chiamante, accedere **ai** criteri ID chiamante vocale  >   nell'Microsoft Teams di amministrazione. È possibile usare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati. Gli utenti dell'organizzazione verranno assegnati automaticamente al criterio globale, a meno che non venga creato e assegnato un criterio personalizzato.

## <a name="create-a-custom-caller-id-policy"></a>Creare criteri ID chiamante personalizzati

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Criteri  >  **ID chiamante vocale.**
2. Fare clic su **Aggiungi**. <br>
![Screenshot della nuova pagina dei criteri per l'ID chiamante nell'interfaccia di amministrazione.](media/caller-id-policies-add-policy.png)
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

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare **a** Criteri  >  **ID chiamante vocale.**
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Modificare le impostazioni desiderate e quindi fare clic su **Salva.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Assegnare criteri ID chiamante personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Argomenti correlati

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity?view=skype-ps)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)