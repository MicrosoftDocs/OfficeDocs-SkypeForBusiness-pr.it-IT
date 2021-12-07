---
title: Configurare la conferma di chiamata in uscita della riunione per gli utenti in Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come configurare Teams per richiedere una conferma di chiamata in uscita per impedire ai sistemi di segreteria telefonica di connettersi alle riunioni quando la persona chiamata non è in grado di rispondere alla chiamata.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae670cec7adcca3dada49a3dcda0ae11f3d1b7b7
ms.sourcegitcommit: 70bba31b0ca4615a3c6a90f42d3568450ea51b82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2021
ms.locfileid: "61327254"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurare la conferma di chiamata in uscita della riunione per gli utenti in Microsoft Teams

Le chiamate in uscita delle riunioni e le chiamate chiamami sono modi utili per invitare i partecipanti a partecipare a una riunione e per i partecipanti esistenti a partecipare a una riunione usando un telefono tradizionale o cellulare. Tuttavia, quando la persona chiamata non è in grado di rispondere alla chiamata e la chiamata viene risposto da un sistema di segreteria telefonica, il sistema di segreteria telefonica è connesso alla riunione. I partecipanti potranno ascoltarla finché non viene rimossa dalla riunione.

Per evitare che i sistemi di segreteria telefonica si connettono alle riunioni quando una chiamata in uscita viene inviata a un numero di telefono e la persona chiamata non è in grado di rispondere alla chiamata, è possibile configurare Teams per richiedere una conferma alla persona chiamata per consentire loro di partecipare alla riunione. Se la persona chiamata non è in grado di rispondere alla chiamata e la chiamata viene risposta da un sistema di segreteria telefonica, il sistema di segreteria telefonica non sarà connesso alla riunione perché non fornirà una conferma per partecipare.

Quando questa funzionalità è abilitata, le persone che ricevono una chiamata in uscita o una chiamata in uscita devono confermare di voler partecipare alla riunione premendo 1 sul telefono tradizionale o cellulare o pronunciando "Ok".

Per abilitare questa funzionalità per tutte le riunioni dell'organizzazione, impostare il parametro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su ```true``` . Per impostare questo parametro, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Argomenti correlati

- [Configurare la funzionalità Chiamami per gli utenti](set-up-the-call-me-feature-for-your-users.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
