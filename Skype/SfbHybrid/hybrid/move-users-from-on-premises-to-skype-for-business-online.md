---
title: Spostare utenti da ambiente locale a Skype for Business Online
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
description: Informazioni su come spostare gli utenti in Skype for business online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221116"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Spostare utenti da ambiente locale a Skype for Business Online

Dopo aver spostato un utente da locale a Skype for business online, l'utente interagisce con Skype for business online per la sua funzionalità. Tutti i contatti che esistevano in locale saranno disponibili in Skype for business online e tutte le riunioni esistenti che l'utente organizzerà per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for business online. Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.  Per spostare gli utenti da un ambiente locale a Skype for business online, utilizzare il cmdlet Move-CsUser o il pannello di controllo di Skype for Business Server, entrambi strumenti locali. 

Prima di spostare gli utenti, assicurarsi di esaminare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.
 
## <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser 

Move-CsUser è disponibile da una finestra di PowerShell della shell di gestione di Skype for business locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale sia nell'organizzazione di Microsoft 365/Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile utilizzare un singolo account che disponga di privilegi in entrambi gli ambienti oppure è possibile avviare una finestra della shell di gestione di Skype for Business Server locale con le credenziali locali e utilizzare il `-Credential` parametro per specificare le credenziali di un account di Microsoft 365 o di Office 365 con il ruolo amministrativo necessario.

Per spostare un utente in online tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro-target con il valore "sipfed. online. Lync. <span> com ".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro-Credential per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con le autorizzazioni in Office 365 non termina in ". onmicrosoft. <span> com ", è necessario specificare il parametro-HostedMigrationOverrideUrl, con il valore corretto come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Per spostare un utente in Skype for business online, è possibile utilizzare la sequenza di cmdlet seguente. Si presuppone che la credenziale Microsoft 365 o Office 365 sia un account separato e fornito come input per il prompt di Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se l'account Administrator è Mae (multi-factor authentication) abilitato, non specificare il parametro-Credential. All'amministratore verranno richieste le credenziali.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Spostare gli utenti con il pannello di controllo di Skype for Business Server 

1. Aprire l'app del pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento a sinistra, scegliere **utenti**.
3. Utilizzare **trova** per individuare gli utenti che si desidera spostare in Skype for business online.
4. Selezionare l'utente o gli utenti e quindi, nell'elenco a discesa **azione** sopra la lista, scegliere **Move users selected to Skype for business online**.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con. onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **quindi su Avanti per** spostare l'utente.
8. Si noti che i messaggi di stato relativi a esito positivo o negativo sono forniti nella parte superiore dell'app del pannello di controllo principale, non nella procedura guidata.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
