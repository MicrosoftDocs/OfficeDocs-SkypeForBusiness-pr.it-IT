---
title: Attivare o disattivare l'accesso guest in Microsoft Teams.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Informazioni su come gli amministratori di Office 365 possono attivare o disattivare la funzionalità di accesso guest in Microsoft Teams.
ms.openlocfilehash: 2b444b8357d8edef9aaa1c9c8e72ae6762f5bd52
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138242"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Attivare o disattivare l'accesso guest in Microsoft Teams.

> [!Note]
>
> Fino **a febbraio 2021,** l'accesso guest è disattivato per impostazione predefinita. È necessario attivare l'accesso guest per Teams prima che gli amministratori o i proprietari del team possano aggiungere guest. Dopo aver attivo l'accesso guest, l'applicazione delle modifiche potrebbe richiedere alcune ore. Se gli utenti  visualizzano il messaggio Contattare l'amministratore quando provano ad aggiungere un guest al team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora efficaci.
>
> Dopo **febbraio 2021,** l'accesso guest in Microsoft Teams verrà attivato per impostazione predefinita per i nuovi clienti & clienti esistenti che non hanno configurato questa impostazione. Quando questa modifica viene implementata, se non è già stata configurata la funzionalità di accesso guest in Microsoft Teams, tale funzionalità verrà abilitata nel tenant. Se si vuole che l'accesso guest rimanga disabilitato per l'organizzazione, è necessario verificare che l'impostazione di accesso guest sia impostata su Disattivato **invece** che su **Servizio predefinito.**

> [!IMPORTANT]
> L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365, SharePoint e Teams. Per maggiori informazioni, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurare l'accesso guest nell'interfaccia di amministrazione di Teams

1. Accedere all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selezionare **Utenti**  >  **Accesso guest**.

3. Impostare **Consenti accesso guest in Teams** su Su **.**

    ![Opzione Consenti accesso guest impostata su Attivata .](media/guest-access-setting.png)

4. In **Chiamate,** **Riunioni** e **Messaggi** selezionare **On** o **Off** per ogni funzionalità, a seconda di ciò che si vuole consentire ai guest.

      - **Effettua chiamate private**: passare questa impostazione su **Attivato** per consentire agli utenti guest di effettuare chiamate peer-to-peer.
      - **Video IP:** attivare questa **impostazione** per consentire agli utenti guest di usare il video nelle chiamate e nelle riunioni.
      - **Modalità di condivisione dello schermo:** questa impostazione controlla la disponibilità della condivisione dello schermo per gli ospiti.
          - Passare questa impostazione su **Disattivato** per rimuovere la possibilità agli utenti guest di condividere i propri schermi in Teams.
          - Passare questa impostazione su **Singola applicazione** per consentire la condivisione di singole applicazioni.
          - Passare questa impostazione su **Schermo interno** per consentire la condivisione dello schermo completa.
      - **Incontra ora:** attivare questa **impostazione** per consentire agli utenti guest di usare la funzionalità Meet Now in Microsoft Teams.
      - **Modifica messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di modificare i messaggi inviati in precedenza.
      - **Elimina messaggi inviati:** attivare questa **impostazione** per consentire ai guest di eliminare i messaggi inviati in precedenza.
      - **Chat**: passare questa impostazione su **Attivato** per dare agli utenti guest la possibilità di usare la chat in Teams.
      - **Giphy nelle conversazioni:** attivare questa **impostazione** per consentire agli utenti guest di usare Giphys nelle conversazioni. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una classificazione dei contenuti.
      - **Classificazione contenuti Giphy**: selezionare una classificazione dall’elenco a discesa:
          - **Consenti tutti i contenuti**: gli utenti guest potranno inserire tutti i contenuti Giphy nelle chat, indipendentemente dalla loro classificazione.
          - **Moderato**: gli utenti guest potranno inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno moderatamente limitati.
          - **Rigorosa:** gli ospiti possono inserire Giphys nelle chat, ma non potranno inserire contenuti per adulti.
      - **Meme nelle conversazioni:** attivare questa **impostazione** per consentire agli utenti guest di usare Memes nelle conversazioni.
      - **Adesivi nelle conversazioni:** attivare questa **impostazione** per consentire agli utenti guest di usare gli adesivi nelle conversazioni.
      - **Lettore immersivo per i** messaggi: attivare questa **impostazione** per consentire agli utenti guest di usare lo strumento di lettura [immersiva in Teams.](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)

    ![Impostazioni delle autorizzazioni guest in Teams.](media/manage-guest-access-image1.png)

5. Selezionare **Salva**.

## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Vedere anche

[Configurare la collaborazione sicura con Microsoft 365](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloccare gli utenti guest di un team specifico](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
