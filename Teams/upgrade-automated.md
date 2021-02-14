---
title: Aggiornamenti automatizzati| Aggiornamento da Skype Business a Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti automatizzati da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b42785d4f8d765e7d9600c2e195e48d7ec60d8ba
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780655"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti automatizzati da Skype for Business online a Microsoft Teams

Microsoft offre aggiornamenti automatizzati a Teams per aiutare le piccole imprese a effettuare con successo la transizione da Skype for Business Online prima del ritiro del servizio il 31 luglio 2021. L'aggiornamento automatico riduce il numero di attività tecniche richieste dai clienti e consente di concentrarsi sulla preparazione dell'organizzazione, la consapevolezza dell'utente e la formazione su Teams.

Per eseguire correttamente l'aggiornamento da Skype for Business a Microsoft Teams, è necessario pianificare i requisiti tecnici e di conformità degli utenti. Quando sei pronto per iniziare, Microsoft [](upgrade-basic.md) offre un piano d'azione di aggiornamento con attività consigliate di base e risorse associate per implementare un passaggio di successo da Skype for Business a Teams.

## <a name="notifications-for-scheduled-customers"></a>Notifiche per i clienti pianificati

I clienti di Skype for Business online idonei per aggiornamenti automatizzati a Teams riceveranno una serie di notifiche di aggiornamento a partire da 30 giorni prima della data di aggiornamento pianificata. Queste notifiche verranno recapitate come post sulla pianificazione delle modifiche nel Centro messaggi di amministrazione, verranno aggiornati i messaggi di posta elettronica all'amministratore globale e i contrassegni in-app agli utenti finali. 

Queste notifiche comunicano la data pianificata dell'aggiornamento automatico, collegano le risorse per l'aggiornamento e la formazione per contribuire all'adozione e all'uso di Teams e offrono ai clienti la possibilità di posticipare l'aggiornamento automatico di altri 30 giorni nel caso in cui non siano pronti per l'aggiornamento entro la data pianificata.

## <a name="the-automated-upgrade-experience"></a>Esperienza di aggiornamento automatizzata

Gli aggiornamenti automatizzati vengono eseguiti nella data di aggiornamento pianificata, che viene comunicata nelle e-mail di notifica, nel Centro messaggi, nonché nel portale di amministrazione di Teams. L'aggiornamento richiederà circa 15 minuti durante i quali gli utenti finali avranno comunque accesso alle funzionalità di Skype for Business online. Una volta completato l'aggiornamento e dopo la disconnessione da Skype for Business online, gli utenti potranno utilizzare Teams solo per la messaggistica, le riunioni e le chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza post-aggiornamento

Al termine dell'aggiornamento automatico, la modalità di **coesistenza** viene impostata solo su Teams e può essere impostata solo su una modalità di coesistenza diversa da Microsoft. Gli amministratori devono prendere in [considerazione la modalità Solo teams prima](teams-only-mode-considerations.md) dell'aggiornamento. La tabella seguente offre una panoramica generale dell'esperienza utente di Teams Only.


|  |  |
|---------|---------|
|**Chat e chiamate**     | <UL><LI>Tutte le chiamate e le chat vengono avviate e ricevute in Teams<LI>Gli utenti possono interoperabilità (chat/chiamata) con qualsiasi utente di Skype for Business<LI>Gli utenti non possono comunicare con gli utenti che usano Skype for Consumer<LI>Gli utenti vengono reindirizzati a Teams se provano ad accedere a Skype for Business      </UL>  |
|**Riunioni**     |  <UL><LI>Gli utenti pianificano tutte le nuove riunioni in Teams (plug-in sostituito)    </UL>   |
|**Dati migrati**     |<UL><LI>Contatti esistenti di Skype for Business inclusi federati (ma nessuna lista di distribuzione)<LI>Le riunioni esistenti di Skype for Business (sia locali che online) vengono convertite in riunioni di Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posticipare l'aggiornamento automatico

Il successo delle transizioni da Skype for Business Online a Microsoft Teams richiede pianificazione tecnica e preparazione degli utenti per garantire che l'organizzazione sia pronta a sfruttare le funzionalità e le prestazioni espanse di Teams. Tuttavia, durante la pianificazione dell'aggiornamento, al momento l'organizzazione potrebbe non essere ancora pronta per l'aggiornamento a Teams.

Se ricevi una notifica relativa all'aggiornamento automatico pianificato a Teams e desideri posticiparlo a una data  successiva, l'amministratore globale può accedere al portale di amministrazione di Teams e fare clic sul pulsante Posticipa. In questo modo verrà push out la data di aggiornamento automatizzata di 30 giorni. Quando si aggiorna il portale di amministrazione di Teams dopo l'invio, viene visualizzata una notifica che include la nuova data di aggiornamento automatica.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Richieste di downgrade a Skype for Business

Consentiamo downgradi una sola volta da Teams a SfBO, per consentire ai tenant di prepararsi ulteriormente per l'aggiornamento a Teams. I tenant con downgrade verranno ri coinvolti per l'aggiornamento automatico 60 giorni dalla data di downgrade.

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerazioni sulla modalità Solo teams](teams-only-mode-considerations.md)

