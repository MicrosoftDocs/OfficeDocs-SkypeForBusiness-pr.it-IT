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
description: Informazioni su come spostare gli utenti in Skype for Business Online.
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863197"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Spostare utenti da ambiente locale a Skype for Business Online

Dopo aver spostato un utente da locale a Skype for Business Online, l'utente interagisce con Skype for Business Online per le sue funzionalità. Tutti i contatti esistenti in locale saranno disponibili in Skype for Business Online e tutte le riunioni esistenti organizzate dall'utente per il futuro verranno aggiornate in modo che i collegamenti puntino a Skype for Business Online. Se l'utente è abilitato per l'audioconferenza, le riunioni includeranno anche le coordinate di accesso esterno.  Per spostare gli utenti da un ambiente locale a Skype for Business Online, utilizzare il cmdlet Move-CsUser o il Pannello di controllo di Skype for Business Server, entrambi strumenti locali. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud.

> [!NOTE]
> In preparazione del prossimo ritiro di Skype for Business Online, Microsoft ha semplificato il modo in cui le organizzazioni passano a Teams. Quando si spostano gli utenti dall'ambiente locale al cloud, agli utenti viene automaticamente assegnata la modalità TeamsOnly e le riunioni dall'ambiente locale vengono convertite automaticamente in riunioni Teams, come se fosse stato specificato il commutatore, indipendentemente dal fatto che il commutatore sia stato effettivamente `-MoveToTeams` specificato.  Prima del ritiro di Skype for Business Online, le organizzazioni che richiedono lo spostamento degli utenti da locale a Skype for Business Online possono ottenere questo risultato in due passaggi aggiornando la modalità dell'utente dopo che l'utente è stato spostato in *TeamsOnly.* Tuttavia, nel prossimo futuro, non sarà più possibile assegnare una modalità diversa da TeamsOnly agli utenti ospitati nel cloud.  
 
## <a name="move-users-with-move-csuser"></a>Spostare gli utenti con Move-CsUser 

Move-CsUser è disponibile da una finestra di PowerShell Skype for Business Management Shell locale. È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nell'organizzazione Microsoft 365, come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account Microsoft 365 con il ruolo amministrativo `-Credential` necessario.

Per spostare un utente online tramite Move-CsUser:

- Specificare l'utente da spostare utilizzando il parametro Identity.
- Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Microsoft 365, utilizzare il parametro -credential per fornire a un account autorizzazioni sufficienti in Microsoft 365.
- Se l'account con autorizzazioni in Microsoft 365 non termina con ".onmicrosoft. <span> com", è quindi necessario specificare il parametro -HostedMigrationOverrideUrl, con il valore corretto come descritto in [Credenziali amministrative obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in Skype for Business Online e assegnare la modalità predefinita tenant all'utente. Presuppone che la credenziale Microsoft 365 sia un account separato e fornita come input per il prompt Get-Credential richiesta.

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

Se l'account amministratore è abilitato per L'autenticazione a più fattori( Multi-Factor Authentication), non specificare il parametro -Credential. All'amministratore verranno richieste le credenziali.

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>Spostare gli utenti con Skype for Business Server pannello di controllo e Teams di amministrazione

1. Apri l'Skype for Business Server del Pannello di controllo.
2. Nel riquadro di spostamento sinistro scegliere **Utenti**.
3. Usa **Trova** per individuare gli utenti che vuoi spostare in Skype for Business Online.
4. Selezionare gli utenti e quindi nell'elenco a discesa Azione sopra l'elenco scegliere Sposta gli utenti selezionati **in Skype for Business Online** o Sposta gli utenti selezionati in **Teams**.  Entrambe le opzioni inizialmente spostano l'utente in modalità TeamsOnly, ma dopo lo spostamento puoi assegnare un'altra modalità. 
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.
9. Apri l Teams'interfaccia di amministrazione e seleziona "Utenti" nel riquadro di spostamento a sinistra. 
10. Fai clic sull'utente desiderato nella visualizzazione elenco. 
11. Fare clic **su** Modifica nella sezione che indica **Teams aggiornamento**.
12. Nel riquadro a comparsa a destra selezionare la modalità di coesistenza desiderata e fare clic su **Applica.**
 

## <a name="see-also"></a>Vedere anche

[Move-CsUser](/powershell/module/skype/move-csuser)
