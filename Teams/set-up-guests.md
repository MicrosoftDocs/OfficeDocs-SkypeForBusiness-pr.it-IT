---
title: Attivare o disattivare l'accesso Guest a Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Informazioni su come attivare o disattivare la caratteristica di accesso guest in Microsoft teams come amministratore di Office 365.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9e91f51bb809b9917036dce1d074ec694cb113f
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761152"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Attivare o disattivare l'accesso Guest a Microsoft Teams
===================================================

L'accesso guest è disabilitato per impostazione predefinita. Come amministratore di Microsoft 365 o Office 365, è necessario attivare l'accesso guest per i team prima che l'amministratore o i proprietari del team possano aggiungere Guest. Per attivare l'accesso guest, [collaborare con gli ospiti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Dopo aver attivato l'accesso guest, potrebbe essere necessario qualche ora affinché le modifiche abbiano effetto. Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che l'accesso guest non sia stato attivato o che le impostazioni non siano ancora valide.

> [!IMPORTANT]
> L'attivazione dell'accesso guest dipende dalle impostazioni in Azure Active Directory, Microsoft 365 o Office 365, SharePoint Online e teams. Per altre informazioni, vedere [autorizzare l'accesso guest in teams](Teams-dependencies.md).



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurare l'accesso guest nell'interfaccia di amministrazione di Teams

1. Accedere all'interfaccia di amministrazione di Microsoft teams.

2. Selezionare l'accesso Guest **delle impostazioni a livello di organizzazione**  >  **Guest access**.

3. Impostare **Consenti accesso guest in Microsoft teams** **su**attivato.

    ![Consenti l'opzione di accesso Guest impostata su attivato ](media/set-up-guests-image1.png)

4. In **chiamate**, **riunioni**e **messaggistica** **selezionare attivato** o **disattivato** per ogni funzionalità, a seconda di cosa si vuole consentire agli utenti guest.

      - **Effettuare chiamate private** : attivare **questa impostazione per consentire agli utenti** di effettuare chiamate peer-to-peer.
      - **Consenti video IP** -attivare questa impostazione per consentire agli utenti di **usare il video** nelle chiamate e nelle riunioni.
      - **Modalità di condivisione dello schermo** : questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest. 
          - Attivare questa impostazione su **disabilitata** per rimuovere la possibilità per gli utenti di condividere i loro schermi in teams. 
          - Attivare questa impostazione su **singola applicazione** per consentire la condivisione di singole applicazioni. 
          - Attivare questa impostazione su **intero schermo** per consentire la condivisione completa dello schermo.
      - **Consenti riunione ora** : attivare **questa impostazione per consentire agli utenti** di usare la funzionalità incontra ora in Microsoft teams.
      - **Modifica messaggi inviati** -attivare **questa impostazione per consentire agli utenti** di modificare i messaggi inviati in precedenza.
      - **Gli utenti possono eliminare i messaggi inviati** : attivare **questa impostazione per consentire agli utenti** di eliminare i messaggi inviati in precedenza.
      - **Chat** : attiva **questa impostazione per offrire agli utenti** la possibilità di usare la chat in teams.
      - **Usare giphy nelle conversazioni** : attivare **questa impostazione per consentire agli utenti** di usare giphy nelle conversazioni. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una valutazione del contenuto.
      - **Classificazione contenuto Giphy** -selezionare una classificazione nell'elenco a discesa:
          - **Consenti tutto il contenuto** : gli utenti potranno inserire tutte le giphy in chat, indipendentemente dalla valutazione del contenuto.
          - **Moderato** : gli utenti potranno inserire giphy in chat, ma saranno limitati a moderatamente dal contenuto per adulti.
          - **Strict** : gli utenti saranno in grado di inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.
      - **Usare memi nelle conversazioni** -attivare **questa impostazione per consentire agli utenti** di usare i memi nelle conversazioni.
      - **Usare gli adesivi nelle conversazioni** : attivare questa **impostazione per consentire agli utenti** di usare gli adesivi nelle conversazioni. 

5. Fare clic su **Salva**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usare PowerShell per attivare o disattivare l'accesso Guest

Leggere [usare PowerShell per attivare o disattivare l'accesso Guest](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off).

## <a name="external-access-federation-vs-guest-access"></a>Accesso esterno (federazione) e accesso guest

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
