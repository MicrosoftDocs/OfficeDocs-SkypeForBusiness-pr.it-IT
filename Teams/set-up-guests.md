---
title: Attivare o disattivare l'accesso Guest a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Attivare o disattivare la funzionalità di accesso guest in Microsoft teams.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184348"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Attivare o disattivare l'accesso Guest a Microsoft Teams
===================================================

L'amministratore di Office 365 deve abilitare la funzionalità Guest prima che l'utente o gli utenti dell'organizzazione (in particolare i proprietari del team) possano aggiungere Guest.

Le impostazioni Guest sono impostate in Azure Active Directory. Le modifiche possono essere effettive nell'organizzazione di Office 365 in 2 ore e 24 ore. Se un utente vede il messaggio "Contatta l'amministratore" quando prova ad aggiungere un Guest al proprio team, è probabile che la caratteristica Guest non sia stata abilitata o che le impostazioni non siano ancora valide.

> [!IMPORTANT]
> Per consentire l'esperienza completa della funzionalità di accesso guest, è importante comprendere la dipendenza dalle autorizzazioni principali tra Microsoft teams, Azure Active Directory e Office 365. Per altre informazioni, vedere [autorizzare l'accesso guest in Microsoft teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Accesso guest e accesso esterno (Federazione)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Configurare l'accesso guest nell'interfaccia di amministrazione di Microsoft Teams

1.  Accedere all'interfaccia di amministrazione di Microsoft teams.

2.  Selezionare > **l'accesso Guest** **delle impostazioni a livello di organizzazione**.

3. Impostare l'opzione **Consenti accesso guest in Microsoft teams** **su**attivato.

    ![Consenti l'opzione di accesso Guest impostata su attivato ](media/set-up-guests-image1.png)

4.  Impostare i toggle in **chiamata**, **riunione**e **messaggistica** **su** attivato o **disattivato**, a seconda delle funzionalità che si desidera consentire agli utenti guest.

    - **Effettuare chiamate private** : attivare questa impostazione **** per consentire agli utenti di effettuare chiamate peer-to-peer.
    - **Consenti video IP** -attivare questa impostazione **** per consentire agli utenti di usare il video nelle chiamate e nelle riunioni.
    - **Modalità di condivisione dello schermo** : questa impostazione controlla la disponibilità della condivisione dello schermo per gli utenti guest. 
       - Attivare questa impostazione su **disabilitata** per rimuovere la possibilità per gli utenti di condividere i loro schermi in teams. 
       - Attivare questa impostazione su **singola applicazione** per consentire la condivisione di singole applicazioni. 
       - Attivare questa impostazione su **intero schermo** per consentire la condivisione completa dello schermo.
    - **Consenti riunione ora** : attivare questa impostazione **** per consentire agli utenti di usare la funzionalità incontra ora in Microsoft teams.
    - **Modifica messaggi inviati** -attivare questa impostazione **** per consentire agli utenti di modificare i messaggi inviati in precedenza.
    - **Gli utenti possono eliminare i messaggi inviati** : attivare **** questa impostazione per consentire agli utenti di eliminare i messaggi inviati in precedenza.
    - **Chat** : attiva questa impostazione **** per offrire agli utenti la possibilità di usare la chat in teams.
    - **Usare giphy nelle conversazioni** : attivare questa impostazione **** per consentire agli utenti di usare giphy nelle conversazioni. Giphy è un database online e un motore di ricerca che consente agli utenti di cercare e condividere file GIF animati. A ogni Giphy viene assegnata una valutazione del contenuto.
    - **Classificazione contenuto Giphy** -selezionare una classificazione nell'elenco a discesa:
       - **Consenti tutto il contenuto** : gli utenti potranno inserire tutte le giphy in chat, indipendentemente dalla valutazione del contenuto.
       - **Moderato** : gli utenti potranno inserire giphy in chat, ma saranno limitati a moderatamente dal contenuto per adulti.
       - **Strict** : gli utenti saranno in grado di inserire giphy in chat, ma verranno limitati dall'inserimento di contenuto per adulti.
    - **Usare memi nelle conversazioni** -attivare questa impostazione per **** consentire agli utenti di usare i memi nelle conversazioni.
    - **Usare gli adesivi nelle conversazioni** : attivare questa **** impostazione per consentire agli utenti di usare gli adesivi nelle conversazioni. 


5.  Fai clic su **Salva**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Usare PowerShell per attivare o disattivare l'accesso Guest

1.  Scaricare il modulo di PowerShell per Skype for business online dahttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Connettere una sessione di PowerShell all'endpoint di Skype for business online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Controlla la configurazione e, `AllowGuestUser` se `$False`lo è, usa il cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) per impostarlo su `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
È ora possibile avere utenti guest in teams per l'organizzazione.

## <a name="more-information"></a>Ulteriori informazioni

Guardare il video seguente per altre informazioni sull'accesso guest.

|  |  |
|---------|---------|
| Aggiunta di Guest in Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
