---
title: Configurare la conferma di chiamata in uscita della riunione per gli utenti in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Scopri come configurare Teams per richiedere una conferma di chiamata in uscita per impedire ai sistemi di segreteria telefonica di connettersi alle riunioni quando la persona chiamata non è in grado di rispondere alla chiamata.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271561"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurare la conferma di chiamata in uscita per gli utenti in Microsoft Teams

Le chiamate in uscita e le chiamate telefoniche tramite telefono sono utili per invitare i partecipanti a partecipare a una riunione e per consentire ai partecipanti esistenti di partecipare a una riunione usando un telefono cellulare o tradizionale. Tuttavia, quando la persona chiamata non è in grado di rispondere alla chiamata e alla chiamata risponde un sistema di segreteria telefonica, il sistema di segreteria telefonica è connesso alla riunione. I partecipanti potranno ascoltarlo finché non viene rimosso dalla riunione.

Per impedire ai sistemi di segreteria telefonica di connettersi alle riunioni quando una chiamata in uscita della riunione viene inviata a un numero di telefono e la persona chiamata non è in grado di rispondere alla chiamata, puoi configurare Teams in modo da richiedere alla persona chiamata la conferma di partecipare alla riunione. Se la persona chiamata non è in grado di rispondere alla chiamata e alla chiamata risponde un sistema di segreteria telefonica, il sistema di segreteria telefonica non verrà connesso alla riunione perché non fornirà una conferma per partecipare.

Quando questa funzionalità è abilitata, le persone che ricevono una chiamata in uscita o chiamami devono confermare di voler partecipare alla riunione premendo 1 sul telefono tradizionale o mobile o dicendo "Ok". La conferma impedirà al messaggio della segreteria telefonica dell'utente di partecipare alla riunione.

Per abilitare questa funzionalità per tutte le riunioni dell'organizzazione, imposta il ```EnableDialOutJoinConfirmation``` parametro del cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su ```true```. Per impostare questo parametro, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Argomenti correlati

- [Configurare la funzionalità Chiamami per gli utenti](set-up-the-call-me-feature-for-your-users.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
