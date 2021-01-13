---
title: Configurare la chiamata in uscita della riunione per gli utenti in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare i team per richiedere una conferma di chiamata in uscita per evitare che i sistemi di segreteria telefonica si connettano alle riunioni quando la persona chiamata non è in grado di rispondere alla chiamata.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806146"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurare la conferma della chiamata in uscita della riunione per gli utenti in Microsoft Teams

I partecipanti alla riunione e le chiamate chiamami sono modi molto utili per invitare gli utenti a partecipare a una riunione e per partecipare a una riunione con un telefono tradizionale o cellulare. Tuttavia, quando la persona chiamata non è in grado di rispondere alla chiamata e la chiamata viene risolta da un sistema di segreteria telefonica, il sistema di segreteria telefonica è connesso alla riunione e i partecipanti potranno ascoltarlo finché non viene rimosso dalla riunione.

Per evitare che i sistemi di segreteria telefonica si connettano alle riunioni quando viene inviata una chiamata in uscita a un numero di telefono e la persona chiamata non è in grado di rispondere, è possibile configurare i team per richiedere una conferma da parte della persona chiamata per partecipare alla riunione. Se la persona chiamata non riesce a rispondere alla chiamata e la chiamata viene risolta da un sistema di segreteria telefonica, il sistema di segreteria telefonica non verrà connesso alla riunione perché non offre una conferma per partecipare.

Quando questa funzionalità è abilitata, le persone che ricevono una chiamata in uscita o chiamata telefonica devono confermare di voler partecipare alla riunione premendo 1 sul telefono tradizionale o mobile.

Per abilitare questa funzionalità per tutte le riunioni dell'organizzazione, imposta il ```EnableDialOutJoinConfirmation``` parametro del cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su ```true``` . Per farlo, eseguire il comando seguente:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Argomenti correlati

- [Configurare la funzionalità Chiamami per gli utenti](set-up-the-call-me-feature-for-your-users.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)