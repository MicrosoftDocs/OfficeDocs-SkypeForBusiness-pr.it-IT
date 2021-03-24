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
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110622"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Spostare utenti da ambiente locale a Skype for Business Online

Dopo aver spostato un utente da locale a Skype for Business online, l'utente interagisce con Skype for Business online per le sue funzionalità. Tutti i contatti esistenti in locale saranno disponibili in Skype for Business online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business online. Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.  Per spostare gli utenti da un ambiente locale a Skype for Business online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali. 

Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.
 
## <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser 

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione di Microsoft 365/Office 365, come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un `-Credential` account di Microsoft 365 o Office 365 con il ruolo amministrativo necessario.

Per spostare un utente online tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Office 365.
- Se l'account con autorizzazioni in Office 365 non termina con ".onmicrosoft. <span> com", è quindi necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La sequenza di cmdlet seguente può essere usata per spostare un utente in Skype for Business online. Presuppone che la credenziale di Microsoft 365 o Office 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Se l'account amministratore è abilitato per L'autenticazione a più fattori( Multi-Factor Authentication), non specificare il parametro -Credential. All'amministratore verranno richieste le credenziali.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Spostare gli utenti con il Pannello di controllo di Skype for Business Server 

1. Apri l'app Del Pannello di controllo di Skype for Business Server.
2. Nel riquadro di spostamento sinistro scegliere **Utenti**.
3. Usa **Trova** per individuare gli utenti che vuoi spostare in Skype for Business online.
4. Selezionare gli utenti e quindi, nell'elenco **a** discesa Azione sopra l'elenco, scegliere Sposta gli utenti selezionati **in Skype for Business online.**
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](/powershell/module/skype/move-csuser)