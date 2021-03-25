---
title: Aggiornamenti automatici| Aggiornamento da Skype Business a Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti automatici da Skype for Business a Teams
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
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120543"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti automatizzati da Skype for Business online a Microsoft Teams

Microsoft offre aggiornamenti automatizzati a Teams per aiutare le piccole imprese a eseguire correttamente la transizione da Skype for Business Online prima del ritiro del servizio il 31 luglio 2021. L'aggiornamento automatico riduce il numero di attività tecniche necessarie per i clienti e consente di concentrarsi più sulla preparazione dell'organizzazione, sulla consapevolezza degli utenti e sulla formazione di Teams.

Un aggiornamento riuscito da Skype for Business a Microsoft Teams richiede la pianificazione della conformità tecnica e dell'utente. Quando si è pronti per iniziare, Microsoft offre un piano d'azione per l'aggiornamento con attività consigliate di base e risorse associate per implementare un passaggio di successo da Skype for Business [a](upgrade-basic.md) Teams.

## <a name="notifications-for-scheduled-customers"></a>Notifiche per i clienti programmati

I clienti skype for Business online idonei per gli aggiornamenti automatici a Teams riceveranno una serie di notifiche di aggiornamento a partire da 30 giorni prima della data di aggiornamento pianificata. Queste notifiche verranno recapitate come post Di pianificazione per la modifica nell'interfaccia di amministrazione, aggiornano i messaggi di posta elettronica all'amministratore globale e i contrassegni in-app agli utenti finali. 

Queste notifiche comunicano la data pianificata dell'aggiornamento automatico, collegano le risorse di aggiornamento e la formazione per facilitare l'adozione e l'uso di Teams e offrono ai clienti la possibilità di posticipare l'aggiornamento automatico di altri 30 giorni nel caso in cui non siano pronti per l'aggiornamento entro la data pianificata.

## <a name="the-automated-upgrade-experience"></a>Esperienza di aggiornamento automatizzata

Gli aggiornamenti automatici vengono eseguiti alla data di aggiornamento pianificata, che viene comunicata nei messaggi di posta elettronica di notifica, nel Centro messaggi e nel portale di amministrazione di Teams. L'aggiornamento richiederà circa 15 minuti durante i quali gli utenti finali avranno ancora accesso alla funzionalità skype for business online. Una volta completato l'aggiornamento e gli utenti si discostono da Skype for Business online, gli utenti potranno usare Teams solo per messaggistica, riunioni e chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza post-aggiornamento

Al termine dell'aggiornamento automatico, la **modalità di coesistenza** è impostata su Solo Teams e può essere modificata solo in una modalità di coesistenza diversa da Microsoft. Gli amministratori devono esaminare le [considerazioni relative alla modalità Solo Teams prima](teams-only-mode-considerations.md) dell'aggiornamento. La tabella seguente fornisce una panoramica generale dell'esperienza utente solo di Teams.


|  |  |
|---------|---------|
|**Chat e chiamate**     | <UL><LI>Tutte le chiamate e le chat vengono avviate e ricevute in Teams<LI>Gli utenti possono interagire (chat/chiamata) con qualsiasi utente di Skype for Business<LI>Gli utenti non possono comunicare con gli utenti che usano Skype for Consumer<LI>Gli utenti vengono reindirizzati a Teams se provano ad accedere a Skype for Business      </UL>  |
|**Riunioni**     |  <UL><LI>Gli utenti pianificano tutte le nuove riunioni in Teams (plug-in sostituito)    </UL>   |
|**Dati migrati**     |<UL><LI>Contatti esistenti di Skype for Business inclusi federati (ma non liste di distribuzione)<LI>Le riunioni Skype for Business esistenti (sia online che online) vengono convertite in riunioni di Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posticipare l'aggiornamento automatico

Le transizioni riuscite da Skype for Business online a Microsoft Teams richiedono pianificazione tecnica e disponibilità dell'utente per assicurarsi che l'organizzazione sia pronta a sfruttare le funzionalità e le prestazioni espanse di Teams. Tuttavia, durante la pianificazione dell'aggiornamento, l'organizzazione potrebbe non essere ancora pronta per l'aggiornamento a Teams in questo momento.

Se si riceve una notifica relativa all'aggiornamento automatico pianificato a Teams e si vuole posticipare a  una data successiva, l'amministratore globale può accedere al portale di amministrazione di Teams e fare clic sul pulsante Posticipa. In questo modo verrà es spinta fuori la data di aggiornamento automatico di 30 giorni. Quando si aggiorna il portale di amministrazione di Teams dopo il rinvio, viene visualizzata una notifica che include la nuova data di aggiornamento automatico.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Richieste di downgrade a Skype for Business

Microsoft consente il downgrade di una sola volta da Teams a SfBO, per consentire ai tenant di prepararsi ulteriormente per l'aggiornamento a Teams. I tenant con downgrade verranno riabilitati per l'aggiornamento automatico a 60 giorni dalla data di downgrade.

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerazioni sulla modalità Solo Teams](teams-only-mode-considerations.md)