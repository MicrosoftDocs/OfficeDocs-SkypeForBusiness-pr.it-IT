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
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Informazioni su come gli amministratori di Office 365 possono attivare o disattivare la funzionalità di accesso guest in Microsoft Teams.
ms.openlocfilehash: aaf37fda456f0e48d441e78f785a3ce450f1f42c
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786778"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Attivare o disattivare l'accesso guest in Microsoft Teams.

> [!Note]

> Fino al **febbraio 2021**, l'accesso Guest è disattivato per impostazione predefinita. È necessario attivare l'accesso guest per Teams prima che gli amministratori o i proprietari del team possano aggiungere guest. Dopo aver attivato l'accesso guest, potrebbe essere necessario qualche ora affinché le modifiche abbiano effetto. Se gli utenti vedono il messaggio **contattare l'amministratore** quando tentano di aggiungere un Guest al proprio team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora valide. 

> Dopo il **2021 febbraio**, l'accesso guest in Microsoft teams sarà attivato per impostazione predefinita per i nuovi clienti & clienti esistenti che non hanno configurato questa impostazione. Quando questa modifica viene implementata, se non è già stata configurata la funzionalità di accesso guest in Microsoft teams, tale funzionalità verrà abilitata nel tenant. Se si vuole che l'accesso Guest rimanga disabilitato per l'organizzazione, è necessario verificare che l'impostazione di accesso Guest sia impostata su **disattivato** al posto del **servizio predefinito**.

> [!IMPORTANT]
> L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365, SharePoint e Teams. Per maggiori informazioni, vedere [Collaborare con gli utenti guest in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurare l'accesso guest nell'interfaccia di amministrazione di Teams

1. Accedere all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).

2. Selezionare **Impostazioni a livello di organizzazione** > **Accesso guest**.

3. Impostare **Consenti accesso guest in Microsoft Teams** su **Attivato**.

    ![Consenti accesso guest impostato su Attivato ](media/set-up-guests-image1.png)

4. In **Chiamata**, **Riunione**, and **Messaggistica**, selezionare **Attivato** o **Disattivato** per ciascuna funzionalità, a seconda di ciò che si desidera consentire agli utenti guest.

      - **Effettua chiamate private**: passare questa impostazione su **Attivato** per consentire agli utenti guest di effettuare chiamate peer-to-peer.
      - **Consenti video IP**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare il video durante le chiamate e le riunioni.
      - **Modalità condivisione dello schermo**: questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest.
          - Passare questa impostazione su **Disattivato** per rimuovere la possibilità agli utenti guest di condividere i propri schermi in Teams.
          - Passare questa impostazione su **Singola applicazione** per consentire la condivisione di singole applicazioni.
          - Passare questa impostazione su **Schermo interno** per consentire la condivisione dello schermo completa.
      - **Consenti Riunione immediata**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare la funzionalità Riunione immediata in Microsoft Teams.
      - **Modifica messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di modificare i messaggi inviati in precedenza.
      - **Gli utenti guest possono eliminare i messaggi inviati**: passare questa impostazione su **Attivato** per consentire agli utenti guest di eliminare i messaggi inviati in precedenza.
      - **Chat**: passare questa impostazione su **Attivato** per dare agli utenti guest la possibilità di usare la chat in Teams.
      - **Usa Giphys nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare Giphy nelle conversazioni. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una classificazione dei contenuti.
      - **Classificazione contenuti Giphy**: selezionare una classificazione dall’elenco a discesa:
          - **Consenti tutti i contenuti**: gli utenti guest potranno inserire tutti i contenuti Giphy nelle chat, indipendentemente dalla loro classificazione.
          - **Moderato**: gli utenti guest potranno inserire contenuti Giphy nelle chat, ma i contenuti per adulti saranno moderatamente limitati.
          - **Strict** : gli utenti possono inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.
      - **Usa meme nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare meme nelle conversazioni.
      - **Usa adesivi nelle conversazioni**: passare questa impostazione su **Attivato** per consentire agli utenti guest di usare adesivi nelle conversazioni.

    ![Impostazioni autorizzazioni guest in Teams](media/manage-guest-access-image1.png)

5. Selezionare **Salva**.

## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>Vedere anche

[Configurare la collaborazione sicura con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[Bloccare gli utenti guest di un team specifico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
