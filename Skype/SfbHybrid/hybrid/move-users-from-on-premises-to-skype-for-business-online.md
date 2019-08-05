---
title: Trasferire utenti da locali a Skype for business online
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
description: Informazioni su come trasferire utenti in Skype for business online.
ms.openlocfilehash: 90d225eb725690566f23b73b3626cbcf1f42c8c7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "36185519"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Trasferire utenti da locali a Skype for business online

Dopo aver spostato un utente da locale a Skype for business online, l'utente interagisce con Skype for business online per la sua funzionalità. Gli eventuali contatti presenti in locale saranno disponibili in Skype for business online e le eventuali riunioni esistenti che l'utente organizzerà per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for business online. Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.  Per trasferire gli utenti da un ambiente locale a Skype for business online, usare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali. 

Prima di spostare qualsiasi utente, assicurati di rivedere i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.
 
## <a name="move-users-with-move-csuser"></a>Trasferire gli utenti con Move-CsUser 

Move-CsUser è disponibile nella finestra di PowerShell di Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel tenant di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile usare un singolo account con privilegi in entrambi gli ambienti oppure è possibile avviare una finestra di Management Shell di Skype for Business Server locale con le credenziali locali e usare il parametro per specificare le `-Credential` credenziali per un Office 365 account con il ruolo di amministratore di Office 365 necessario.

Per trasferire un utente in online con Move-CsUser:

- Specificare l'utente per lo stato di trasferimento usando il parametro Identity.
- Specifica il parametro-target con il valore "sipfed. online. Lync. <span>com ".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, usare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con autorizzazioni in Office 365 non si conclude con "on. Microsoft. <span>com ", devi specificare il parametro-HostedMigrationOverrideUrl con il valore corretto come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

 > [!NOTE]
 > Devi determinare il valore di HostedMigrationOverrideUrl corretto per il tenant. Questa operazione può essere eseguita facilmente passando all'interfaccia di amministrazione di Skype for business legacy. determinare il prefisso XXXXXXX.online.lync.com e aggiungere/HostedMigration/hostedmigrationservice.svc. ad esempio: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc una volta identificato il valore, usalo per la variabile $URL come illustrato di seguito.

La sequenza di cmdlet seguente può essere usata per trasferire un utente in Skype for business online e presuppone che la credenziale di Office 365 sia un account distinto e fornito come input per il prompt di Get-Credential.

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se l'account dell'amministratore è AMF (autenticazione a più fattori) abilitato, non specificare il parametro-Credential. All'amministratore verranno richieste le credenziali.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Trasferire utenti con il pannello di controllo di Skype for Business Server 

1. Aprire l'app Pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento sinistra scegliere **utenti**.
3. Usare **trova** per individuare gli utenti che si desidera spostare in Skype for business online.
4. Selezionare l'utente o gli utenti e quindi, nell'elenco a discesa **azione** , scegliere **spostati in Skype for business online**.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Office 365 con un account che termina in onmicrosoft.com e disponga di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **** quindi su un'altra volta per trasferire l'utente.
8. Tieni presente che i messaggi di stato relativi a successo o errore vengono forniti nella parte superiore dell'app Pannello di controllo principale, non nella procedura guidata.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
