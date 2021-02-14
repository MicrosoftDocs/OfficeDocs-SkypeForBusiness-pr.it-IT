---
title: Impostare la conferma di chiamata in uscita per una riunione per gli utenti in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare Teams per richiedere una conferma di chiamata in uscita per impedire ai sistemi di segreteria telefonica di connettersi alle riunioni quando la persona chiamata non è in grado di rispondere alla chiamata.
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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Impostare la conferma di chiamata in uscita per una riunione per gli utenti in Microsoft Teams

Le chiamate in uscita e le chiamate telefoniche per le riunioni sono modi molto utili per invitare i partecipanti a partecipare a una riunione e per i partecipanti esistenti a partecipare a una riunione usando un telefono cellulare o tradizionale. Tuttavia, quando la persona chiamata non è in grado di rispondere alla chiamata e la chiamata riceve una risposta da un sistema di segreteria telefonica, il sistema di segreteria telefonica è collegato alla riunione e i partecipanti saranno in grado di ascoltarla finché non viene rimossa dalla riunione.

Per impedire ai sistemi di segreteria telefonica di connettersi alle riunioni quando viene inviata una chiamata in uscita a un numero di telefono e la persona chiamata non è in grado di rispondere alla chiamata, puoi configurare Teams in modo da richiedere alla persona chiamata di partecipare alla riunione con una conferma. Se la persona chiamata non può rispondere alla chiamata e la risposta alla chiamata viene data da un sistema di segreteria telefonica, il sistema di segreteria telefonica non sarà collegato alla riunione perché non fornirà la conferma di partecipazione.

Quando questa funzionalità è abilitata, le persone che ricevono una chiamata in uscita o mi chiamano devono confermare che vogliono partecipare alla riunione premendo 1 sul loro telefono tradizionale o cellulare.

Per abilitare questa funzionalità per tutte le riunioni dell'organizzazione, imposta il parametro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su ```true``` . Per farlo, eseguire il comando seguente:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Argomenti correlati

- [Configurare la funzionalità Chiamami per gli utenti](set-up-the-call-me-feature-for-your-users.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)