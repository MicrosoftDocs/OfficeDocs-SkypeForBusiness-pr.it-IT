---
title: Spostare gli utenti dal cloud all'ambiente locale
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
description: Informazioni su come spostare gli utenti da Skype for business online a locale.
ms.openlocfilehash: 0b2143a1705aff3f0b74fb0194d3d10e3d55771b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726736"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Spostare gli utenti dal cloud all'ambiente locale 

Se necessario, è possibile spostare un utente che in precedenza è stato migrato da locale al cloud (se si utilizza Skype for business online o solo Teams) di nuovo in locale. Per spostare gli utenti dalla modalità Skype for business online o TeamsOnly in una distribuzione locale di Skype for Business Server, utilizzare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali. Quando si sposta un utente in una distribuzione locale, è necessario decidere il pool in cui spostare l'utente.

> [!Important]
> Se l'utente si trovava in precedenza in modalità TeamsOnly e si utilizza una versione precedente rispetto a Skype for Business Server 2015 con CU8, è necessario rimuovere anche l'assegnazione della modalità TeamsOnly di TeamsUpgradePolicy per tale utente. Gli utenti locali non devono avere la modalità = TeamsOnly.  Le versioni successive di Skype for Business Server rimuovono automaticamente questa assegnazione. Per ulteriori informazioni, vedere [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Prerequisiti

- L'organizzazione deve disporre di Azure AD Connect configurata in modo appropriato e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [Configure Azure ad Connect](configure-azure-ad-connect.md).
- L'utente da spostare da online Torna a locale deve esistere già in Active Directory locale.
- È necessario configurare l'ambiente ibrido di Skype for business, come descritto in [Configure Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti in locale

Dopo aver spostato un utente dal cloud all'ambiente locale:

- L'utente interagisce con la distribuzione di Skype for Business Server per la sua funzionalità. 
- Tutti i contatti esistenti in Skype for business online o in teams vengono migrati su Skype for Business Server. I due gruppi di contatti vengono Uniti e quindi trasferiti di nuovo in locale.  Inoltre, i contatti preesistenti nei team rimangono in teams.
- Se l'utente usa anche i team, non avrà la possibilità di interagire con gli utenti di Skype for business, né potrà comunicare con gli utenti di organizzazioni federative.
- Le riunioni in Skype for business online *non* vengono automaticamente migrate di nuovo in locale. Gli utenti devono ripianificare le riunioni o, se lo si desidera, utilizzare lo [strumento di migrazione delle riunioni](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell della shell di gestione di Skype for business locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel tenant di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile utilizzare un singolo account che disponga di privilegi in entrambi gli ambienti oppure è possibile avviare una finestra della shell di gestione di Skype for Business Server locale con le credenziali locali e utilizzare il `-Credential` parametro per specificare le credenziali di un account di Office 365 con il ruolo amministrativo di Office 365 necessario.

Per spostare un utente in locale tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro-target con il nome di dominio completo del pool locale desiderato che ospiterà l'utente.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con le autorizzazioni in Office 365 non termina con "on.microsoft.com", è necessario specificare il parametro-HostedMigrationOverrideUrl con il valore corretto descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Server e presuppone che la credenziale Office 365 sia un account separato e fornito come input per il prompt di Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Spostare gli utenti con il pannello di controllo di Skype for Business Server

1. Aprire l'app del pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento a sinistra, scegliere **utenti**.
3. Utilizzare **trova** per individuare gli utenti che si desidera spostare di nuovo in locale.
4. Selezionare l'utente o gli utenti, quindi fare clic **su Sposta selezionati in locale**dall'elenco a discesa **azione** .
5. Nella procedura guidata, selezionare il pool di utenti che ospiterà l'utente e fare clic su **Avanti**.
6. Se richiesto, accedere a Office 365, con un account che termina con. onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **quindi su Avanti per** spostare l'utente.
8. Si noti che i messaggi di stato relativi a esito positivo o negativo sono forniti nella parte superiore dell'app del pannello di controllo principale, non nella procedura guidata.

### <a name="removing-teamsonly-mode"></a>Rimozione della modalità TeamsOnly

Se si utilizza una versione precedente a Skype for business 2015 con CU8 e l'utente viene spostato di nuovo in modalità locale in TeamsOnly, è necessario rimuovere l'istanza di UpgradeToTeams prima di `TeamsUpgradePolicy` spostare l'utente locale. È possibile concedere esplicitamente un criterio con una modalità diversa oppure è sufficiente rimuovere l'assegnazione di criteri esistente per l'utente per l'utilizzo dei criteri globali (purché il criterio globale del tenant non sia UpgradeToTeams).

Per rimuovere l'assegnazione dell'utente di TeamsUpgradePolicy, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for business online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

In alternativa, per assegnare un'altra istanza di TeamsUpgradePolicy che non disponga della modalità = TeamsOnly, è possibile specificare il nome dell'istanza desiderata come valore del parametro PolicyName nel cmdlet. Per visualizzare un elenco delle istanze disponibili di TeamsUpgradePolicy, eseguire Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
