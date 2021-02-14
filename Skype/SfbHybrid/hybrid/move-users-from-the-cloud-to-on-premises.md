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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Informazioni su come spostare gli utenti da Skype for Business online a locale.
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221336"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Spostare gli utenti dal cloud a quello locale 

Se necessario, è possibile spostare di nuovo in locale un utente migrato in precedenza dall'ambiente locale al cloud (se si usa Skype for Business online o Solo Teams). Per spostare gli utenti dalla modalità Skype for Business Online o TeamsOnly a una distribuzione locale di Skype for Business Server, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali. Quando si sposta di nuovo un utente in una distribuzione locale, è necessario decidere in quale pool spostare l'utente.

> [!Important]
> Se l'utente era in precedenza in modalità Solo Teams e si utilizza una versione precedente a Skype for Business Server 2015 con CU8, è necessario rimuovere anche l'assegnazione della modalità TeamsOnly di TeamsUpgradePolicy per tale utente. Gli utenti locali non devono avere mode= TeamsOnly.  Le versioni successive di Skype for Business Server rimuovono automaticamente questa assegnazione. Per ulteriori informazioni, [vedere Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

## <a name="prerequisites"></a>Prerequisiti

- L'organizzazione deve avere Azure AD Connect configurato correttamente ed eseguire la sincronizzazione di tutti gli attributi rilevanti per l'utente, come descritto in [Configurare Azure AD Connect.](configure-azure-ad-connect.md)
- L'utente da spostare di nuovo online in locale deve esistere già in Active Directory locale.
- Skype for Business ibrido deve essere configurato, come descritto in [Configurare Skype for Business ibrido.](configure-federation-with-skype-for-business-online.md)

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti in locale

Dopo aver spostato un utente dal cloud a quello locale:

- L'utente interagisce con la distribuzione di Skype for Business Server per le sue funzionalità. 
- Tutti i contatti presenti in Skype for Business online o Teams vengono migrati in Skype for Business Server. I due set di contatti vengono uniti e quindi migrati nuovamente in locale.  Inoltre, i contatti preesistenti in Teams rimangono in Teams.
- Se l'utente usa anche Teams, non sarà in grado di interagire con gli utenti di Skype for Business né di comunicare con gli utenti delle organizzazioni federate.
- Le riunioni in Skype for Business online non *vengono* migrate automaticamente in locale. Gli utenti devono ripianificare le riunioni o, se lo si desidera, utilizzare lo [Strumento di migrazione delle riunioni.](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)

### <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione del servizio cloud (Microsoft 365 o Office 365), come descritto in Credenziali amministrative [necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account di `-Credential` Microsoft 365 o Office 365 con il ruolo amministrativo necessario.

Per spostare un utente in locale tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro -Target con il nome di dominio completo del pool locale desiderato che ospiterà l'utente.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365 o Office 365), usare il parametro -credential per fornire a un account autorizzazioni sufficienti in Microsoft 365 o Office 365.
- Se l'account con autorizzazioni in Microsoft 365 o Office 365 non termina con "on.microsoft.com", è necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto [in](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)Credenziali amministrative obbligatorie.

La sequenza di cmdlet seguente può essere usata per spostare un utente in Skype for Business Server e presuppone che le credenziali di Microsoft 365 o Office 365 siano un account separato e fornite come input per il prompt Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Spostare gli utenti con il Pannello di controllo di Skype for Business Server

1. Apri l'app Del Pannello di controllo di Skype for Business Server.
2. Nel riquadro di spostamento sinistro scegliere **Utenti.**
3. Utilizzare **Trova** per individuare gli utenti che si desidera spostare di nuovo in locale.
4. Selezionare gli utenti e quindi  nell'elenco a discesa Azione sopra l'elenco scegliere Sposta utenti selezionati **in locale.**
5. Nella procedura guidata selezionare il pool di utenti che ospiterà l'utente e fare clic su **Avanti.**
6. Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e quindi su **Avanti** ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.

### <a name="removing-teamsonly-mode"></a>Rimozione della modalità TeamsOnly

Se si utilizza una versione precedente a Skype for Business 2015 con CU8 e l'utente viene spostato di nuovo in locale in modalità Solo Teams, è necessario rimuovere l'istanza di UpgradeToTeams prima di spostare l'utente in `TeamsUpgradePolicy` locale. È possibile concedere esplicitamente un criterio con una modalità diversa oppure rimuovere semplicemente l'assegnazione di criteri esistente per tale utente per l'utilizzo del criterio globale (a meno che il criterio globale del tenant non sia UpgradeToTeams).

Per rimuovere l'assegnazione dell'utente di TeamsUpgradePolicy, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for Business online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

In alternativa, per assegnare un'altra istanza di TeamsUpgradePolicy che non dispone di mode=TeamsOnly, è possibile specificare il nome dell'istanza desiderata come valore del parametro PolicyName nel cmdlet. Per visualizzare un elenco delle istanze disponibili di TeamsUpgradePolicy, eseguire Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
