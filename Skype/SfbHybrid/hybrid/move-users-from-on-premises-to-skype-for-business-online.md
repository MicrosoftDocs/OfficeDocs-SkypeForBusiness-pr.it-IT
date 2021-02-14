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
description: Informazioni su come spostare gli utenti in Skype for Business online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221116"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Spostare utenti da ambiente locale a Skype for Business Online

Dopo aver spostato un utente dall'ambiente locale a Skype for Business online, l'utente interagisce con Skype for Business online per le sue funzionalità. Tutti i contatti esistenti in locale saranno disponibili in Skype for Business online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business online. Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.  Per spostare gli utenti da un ambiente locale a Skype for Business online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali. 

Prima di spostare gli utenti, assicurarsi di esaminare i [prerequisiti per](move-users-between-on-premises-and-cloud.md#prerequisites) spostare gli utenti nel cloud.
 
## <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser 

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione di Microsoft 365/Office 365, come descritto in Credenziali amministrative [necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account di `-Credential` Microsoft 365 o Office 365 con il ruolo amministrativo necessario.

Per spostare un utente online tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, usare il parametro -credential per fornire a un account autorizzazioni sufficienti in Office 365.
- Se l'account con autorizzazioni in Office 365 non termina con ".onmicrosoft. <span> com", quindi è necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La seguente sequenza di cmdlet può essere usata per spostare un utente in Skype for Business online. Si presuppone che la credenziale di Microsoft 365 o Office 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se l'account amministratore è abilitato per l'autenticazione a più fattori (Multi-Factor Authentication), non specificare il parametro -Credential. All'amministratore verranno richieste le credenziali.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Spostare gli utenti con il Pannello di controllo di Skype for Business Server 

1. Apri l'app Del Pannello di controllo di Skype for Business Server.
2. Nel riquadro di spostamento sinistro scegliere **Utenti.**
3. Utilizzare **Trova** per individuare gli utenti che si desidera spostare in Skype for Business online.
4. Selezionare gli utenti e quindi,  nell'elenco a discesa Azione sopra l'elenco, scegliere Sposta gli utenti selezionati **in Skype for Business online.**
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e quindi su **Avanti** ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
