---
title: Spostare gli utenti dal cloud a quello locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Informazioni su come spostare gli utenti Teams locale.
ms.openlocfilehash: 341edc3e74e78fd0e16b3b98f4d1158623a15a83
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596140"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Spostare gli utenti dal cloud a quello locale 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Se necessario, è possibile spostare un utente migrato in precedenza dall'Teams locale a quello locale. Per spostare gli utenti dalla modalità TeamsOnly a una distribuzione locale di Skype for Business Server, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali. Quando si sposta di nuovo un utente in una distribuzione locale, è necessario decidere in quale pool spostare l'utente.

> [!Important]
> Se l'utente era in precedenza in modalità TeamsOnly e si utilizza una versione precedente a Skype for Business Server 2015 con CU8, è inoltre necessario rimuovere l'assegnazione della modalità TeamsOnly di TeamsUpgradePolicy per tale utente. Gli utenti locali non devono avere mode= TeamsOnly.  Le versioni successive di Skype for Business Server rimuovere automaticamente questa assegnazione. Per ulteriori informazioni, [vedere Grant-CsTeamsUpgradePolicy.](/powershell/module/skype/grant-csteamsupgradepolicy)

## <a name="prerequisites"></a>Prerequisiti

- L'organizzazione deve avere Azure AD Connessione configurato correttamente e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [Configure Azure AD Connessione](configure-azure-ad-connect.md).
- L'utente da spostare di nuovo online in locale deve esistere già in Active Directory locale.
- Skype for Business ibrido deve essere configurato, come descritto in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti in locale

Dopo aver spostato un utente dal cloud di nuovo in locale:

- L'utente interagisce con la distribuzione Skype for Business Server per le sue funzionalità. 
- Tutti i contatti esistenti in Teams vengono migrati in Skype for Business Server. I due set di contatti vengono uniti e quindi migrati di nuovo in locale.  Inoltre, i contatti preesistenti in Teams rimangono in Teams.
- Se l'utente usa anche Teams, non potrà interagire con gli utenti di Skype for Business né sarà in grado di comunicare con gli utenti delle organizzazioni federate.

### <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione del servizio cloud (Microsoft 365), come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account Microsoft 365 con il ruolo amministrativo `-Credential` necessario.

Per spostare un utente in locale tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro -Target con il nome di dominio completo del pool locale desiderato che ospiterà l'utente.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365), utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Microsoft 365.
- Se l'account con autorizzazioni in Microsoft 365 non termina con "on.microsoft.com", è necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)amministrative obbligatorie.

La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Server e presuppone che la credenziale di Microsoft 365 sia un account separato e fornita come input per il prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Spostare gli utenti con il Skype for Business Server Pannello di controllo

1. Apri l'Skype for Business Server del Pannello di controllo.
2. Nel riquadro di spostamento sinistro scegliere **Utenti**.
3. Usa **Trova** per individuare gli utenti che vuoi spostare di nuovo in locale.
4. Selezionare gli utenti e quindi  scegliere Sposta gli utenti selezionati in locale nell'elenco a discesa Azione sopra **l'elenco.**
5. Nella procedura guidata selezionare il pool di utenti che ospiterà l'utente e fare clic su **Avanti.**
6. Se richiesto, accedere a Microsoft 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.

### <a name="removing-teamsonly-mode"></a>Rimozione della modalità TeamsOnly

Se si usa una versione precedente a Skype for Business 2015 con CU8 e l'utente viene spostato di nuovo in locale in modalità TeamsOnly, è necessario rimuovere l'istanza di UpgradeToTeams prima di spostare l'utente in `TeamsUpgradePolicy` locale. È possibile concedere esplicitamente un criterio con una modalità diversa o semplicemente rimuovere l'assegnazione di criteri esistente per tale utente per l'utilizzo del criterio globale (purché il criterio globale del tenant non sia UpgradeToTeams).

Per rimuovere l'assegnazione dell'utente di TeamsUpgradePolicy, eseguire il cmdlet seguente da una finestra Teams PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

In alternativa, per assegnare un'altra istanza di TeamsUpgradePolicy che non dispone di mode=TeamsOnly, è possibile specificare il nome dell'istanza desiderata come valore del parametro PolicyName nel cmdlet. Per visualizzare un elenco delle istanze disponibili di TeamsUpgradePolicy, eseguire Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vedere anche

[Move-CsUser](/powershell/module/skype/move-csuser)