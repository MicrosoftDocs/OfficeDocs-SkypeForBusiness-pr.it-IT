---
title: Aggiornamenti automatici | Aggiornamento di Skype Business to Teams
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: Panoramica degli aggiornamenti automatici da Skype for business a teams
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
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>Aggiornamenti automatici da Skype for business online a Microsoft Teams

Microsoft offre aggiornamenti automatici ai team per aiutare le piccole imprese a eseguire la transizione positiva da Skype for business online prima del 31 luglio 2021 del servizio di pensionamento. L'aggiornamento automatico riduce il numero di attività tecniche richieste dai clienti e consente di concentrarsi maggiormente sulla preparazione dell'organizzazione, sulla sensibilizzazione degli utenti e sulla formazione in teams.

Un aggiornamento riuscito da Skype for business a Microsoft teams richiede la pianificazione per la disponibilità di tecnici e utenti. Quando si è pronti per iniziare, Microsoft offre un [piano di azione di aggiornamento](upgrade-basic.md) con le attività consigliate di base e le risorse associate per l'implementazione di un passaggio riuscito da Skype for business a teams.

## <a name="notifications-for-scheduled-customers"></a>Notifiche per clienti pianificati

I clienti di Skype for business online idonei per gli aggiornamenti automatici ai team riceveranno una serie di notifiche di aggiornamento che iniziano 30 giorni prima della data di aggiornamento pianificata. Queste notifiche verranno recapitate come *piano per* i post di modifica nel centro messaggi di amministrazione, aggiornare i messaggi di posta elettronica all'amministratore globale e i contrassegni in-app agli utenti finali.

Queste notifiche comunicheranno la data programmata dell'aggiornamento automatizzato, collegherà le risorse di aggiornamento e la formazione per aiutare l'adozione e l'uso dei team e darà ai clienti l'opzione di posticipare l'aggiornamento automatico di altri 30 giorni, se non sono pronti per l'aggiornamento in base alla data prevista.

## <a name="the-automated-upgrade-experience"></a>Esperienza di aggiornamento automatizzata

Gli aggiornamenti automatici vengono eseguiti nella data di aggiornamento pianificata che viene comunicata nei messaggi di posta elettronica di notifica, nel centro messaggi e nel portale di amministrazione di teams. L'aggiornamento prenderà circa 15 minuti durante il quale gli utenti finali avranno comunque accesso alle funzionalità di Skype for business online. Una volta completato l'aggiornamento e la disconnessione degli utenti di Skype for business online, gli utenti potranno usare solo team per la messaggistica, le riunioni e le chiamate.

## <a name="the-post-upgrade-experience"></a>Esperienza di post-aggiornamento

Al termine dell'aggiornamento automatico, la **modalità di coesistenza** è impostata su teams only e può essere modificata solo in una modalità di coesistenza diversa da Microsoft. Gli amministratori devono rivedere le [considerazioni sulla modalità solo teams](teams-only-mode-considerations.md) prima di eseguire l'aggiornamento. La tabella seguente offre una panoramica di alto livello dell'esperienza utente di teams.


|  |  |
|---------|---------|
|**Chat e chiamate**     | <UL><LI>Tutte le chiamate e le chat vengono avviate e ricevute in teams<LI>Gli utenti possono interoperabilità (chat/Call) con qualsiasi utente Skype for business<LI>Gli utenti non possono comunicare con utenti che usano Skype for Consumer<LI>Gli utenti vengono reindirizzati a teams se provano ad accedere a Skype for business      </UL>  |
|**Riunioni**     |  <UL><LI>Gli utenti pianificano tutte le nuove riunioni in teams (plugin sostituito)    </UL>   |
|**Dati migrati**     |<UL><LI>Contatti esistenti da Skype for business, tra cui federazioni (ma nessuna lista di distribuzione)<LI>Le riunioni Skype for business esistenti (sia on-Prem che online) vengono convertite in riunioni di Teams</UL>         |

## <a name="postponing-your-automated-upgrade"></a>Posticipare l'aggiornamento automatico

Le transizioni di successo da Skype for business online a Microsoft teams richiedono pianificazione tecnica e disponibilità degli utenti per garantire che l'organizzazione sia pronta a sfruttare le funzionalità estese e le prestazioni dei team. Tuttavia, man mano che pianifichi l'aggiornamento, potresti trovare che l'organizzazione non è ancora pronta per l'aggiornamento a teams in questo momento.

Se si riceve una notifica relativa all'aggiornamento automatico programmato a teams e si vuole posticipare una data successiva, l'amministratore globale può accedere al portale di amministrazione di teams e fare clic sul pulsante *rinvia* . In questo modo si premerà la data di aggiornamento automatica di 30 giorni. Quando si aggiorna il portale di amministrazione di teams dopo il rinvio, viene visualizzata una notifica che include la nuova data di aggiornamento automatizzata.

## <a name="requests-to-downgrade-to-skype-for-business"></a>Richieste di downgrade a Skype for business

Consentiamo il downgrade di una tantum da Teams a SfBO, per consentire ai tenant di prepararsi ulteriormente per l'aggiornamento ai team. I tenant che hanno declassato verranno riattivati per l'aggiornamento automatizzato di 60 giorni dalla data di downgrade.

## <a name="related-content"></a>Contenuti correlati

- [Guida introduttiva all'aggiornamento di Microsoft Teams](upgrade-start-here.md)
- [Ritiro di Skype for Business Online](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [Considerazioni sulla modalità solo Teams](teams-only-mode-considerations.md)

