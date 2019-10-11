---
title: Trasferire utenti dal cloud a locale
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: Informazioni su come trasferire gli utenti da Skype for business online in locale.
ms.openlocfilehash: ec3aa727753ed9ac6564712d591ab6d2beac4ebf
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434729"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>Trasferire utenti dal cloud a locale 

Se necessario, è possibile spostare un utente precedentemente migrato dal locale al cloud (se si usa Skype for business online o solo Teams) di nuovo in locale. Per trasferire di nuovo gli utenti dalla modalità Skype for business online o TeamsOnly a una distribuzione locale di Skype for Business Server, usare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali. Quando si riporta un utente in una distribuzione locale, è necessario decidere a quale pool trasferire l'utente.

> [!Important]
> Se l'utente è stato precedentemente in modalità TeamsOnly e si usa una versione precedente rispetto a Skype for Business Server 2015 con CU8, è necessario rimuovere anche l'assegnazione della modalità TeamsOnly di TeamsUpgradePolicy per l'utente. Gli utenti locali non devono avere la modalità = TeamsOnly.  Le versioni successive di Skype for Business Server rimuovono automaticamente l'assegnazione. Per altri dettagli, vedere [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy).

## <a name="prerequisites"></a>Prerequisiti

- L'organizzazione deve avere Azure AD Connect configurata correttamente e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [configurare Azure ad Connect](configure-azure-ad-connect.md).
- L'utente spostato da online di nuovo in locale deve essere già presente nell'Active Directory locale.
- Skype for business Hybrid deve essere configurato, come descritto in [Configurare Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).

## <a name="moving-users-back-to-on-premises"></a>Spostamento degli utenti di nuovo in locale

Dopo aver spostato un utente dal cloud di nuovo in locale:

- L'utente interagisce con la distribuzione di Skype for Business Server per le sue funzionalità. 
- Tutti i contatti esistenti in Skype for business online o in teams vengono migrati in Skype for Business Server. I due set di contatti vengono Uniti e quindi trasferiti di nuovo in locale.  Inoltre, i contatti preesistenti in teams rimangono in teams.
- Se l'utente usa anche teams, non sarà in grado di interagire con gli utenti di Skype for business, né potrà comunicare con gli utenti nelle organizzazioni federate.
- Le riunioni in Skype for business online *non* vengono automaticamente migrate di nuovo in locale. Gli utenti devono ripianificare le riunioni o, se necessario, usare lo [strumento di migrazione delle riunioni](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).

### <a name="move-users-with-move-csuser"></a>Trasferire gli utenti con Move-CsUser

Move-CsUser è disponibile nella finestra di PowerShell di Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel tenant di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile usare un singolo account con privilegi in entrambi gli ambienti oppure è possibile avviare una finestra di gestione di Skype for Business Server locale con le credenziali locali e usare il parametro per specificare le `-Credential` credenziali per un Office 365 account con il ruolo di amministratore di Office 365 necessario.

Per trasferire un utente in locale usando Move-CsUser:

- Specificare l'utente per lo stato di trasferimento usando il parametro Identity.
- Specifica il parametro-target con il nome di dominio completo del pool locale desiderato che ospiterà l'utente.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, usare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con le autorizzazioni in Office 365 non termina con "on.microsoft.com", devi specificare il parametro-HostedMigrationOverrideUrl con il valore corretto come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La sequenza di cmdlet seguente può essere usata per trasferire un utente in Skype for Business Server e presuppone che la credenziale di Office 365 sia un account distinto e fornito come input per il prompt di Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>Trasferire gli utenti con il pannello di controllo di Skype for Business Server

1. Aprire l'app Pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento sinistra scegliere **utenti**.
3. Usare **trova** per individuare gli utenti che si desidera spostare di nuovo in locale.
4. Selezionare gli utenti e quindi, nell'elenco a discesa delle **azioni** , fare clic **su spostati in locale**.
5. Nella procedura guidata selezionare il pool di utenti che ospiterà l'utente e fare clic su **Avanti**.
6. Se richiesto, accedere a Office 365 con un account che termina in onmicrosoft.com e disponga di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **quindi su un'altra** volta per trasferire l'utente.
8. Tieni presente che i messaggi di stato relativi a successo o errore vengono forniti nella parte superiore dell'app Pannello di controllo principale, non nella procedura guidata.

### <a name="removing-teamsonly-mode"></a>Rimozione della modalità TeamsOnly

Se si usa una versione precedente a Skype for business 2015 con CU8 e l'utente viene spostato di nuovo nella modalità locale in TeamsOnly, è necessario rimuovere l'istanza di UpgradeToTeams prima di `TeamsUpgradePolicy` spostare l'utente locale. Puoi concedere esplicitamente un criterio con una modalità diversa o semplicemente rimuovere l'assegnazione di criteri esistente affinché l'utente usi il criterio globale, purché il criterio globale del tenant non sia UpgradeToTeams.

Per rimuovere l'assegnazione dell'utente di TeamsUpgradePolicy, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for business online:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

In alternativa, per assegnare un'altra istanza di TeamsUpgradePolicy che non ha la modalità = TeamsOnly, puoi specificare il nome dell'istanza desiderata come valore del parametro PolicyName nel cmdlet. Per visualizzare un elenco delle istanze disponibili di TeamsUpgradePolicy, eseguire Get-CsTeamsUpgradePolicy.


## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
