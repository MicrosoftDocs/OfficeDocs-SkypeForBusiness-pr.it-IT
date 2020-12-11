---
title: Condivisione delle chiamate e risposta alle chiamate di gruppo
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Condivisione chiamate e raccolta chiamate di gruppo consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620722"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams

Le funzionalità di condivisione chiamata e raccolta chiamate di gruppo di Microsoft teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano mentre l'utente non è disponibile.

Il ritiro delle chiamate di gruppo è meno distruttivo per i destinatari rispetto ad altre forme di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare il modo in cui vogliono ricevere una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visuale o banner nell'app Teams) e possono decidere se rispondere.

Per condividere le chiamate con altre persone, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi scelgono un anello o un'impostazione di inoltro simultaneo. Per informazioni dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) . Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamate e i membri del gruppo di chiamate devono essere solo in modalità di distribuzione in teams. Per altre informazioni sulle modalità di distribuzione dei team, vedere [comprendere la coesistenza e l'interoperabilità di Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Gli utenti devono essere abilitati a VoIP aziendale per configurare e usare la condivisione delle chiamate e il pick-up delle chiamate di gruppo. Per altre informazioni sul modello di licenza, vedere [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="configure-group-call-pickup"></a>Configurare il ritiro delle chiamate di gruppo

Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non è uguale a un gruppo di sicurezza o a un gruppo di Microsoft 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi scelgono un anello simultaneo o un'impostazione di inoltro di chiamata. Per altre informazioni e procedure dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Le preferenze per la creazione e la notifica di gruppi di chiamate sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste funzionalità per gli utenti. I gruppi di chiamate non possono essere creati da gruppi di sicurezza o da gruppi Microsoft 365; devono essere creati in teams.

Gli amministratori dovrebbero abilitare i gruppi di chiamate tramite l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente. Gli amministratori possono anche abilitare questo tramite il portale di amministrazione di teams.  Inoltre, l'utente configurato può anche configurare i gruppi di chiamate direttamente tramite il client. L'amministratore o gli utenti finali non possono bloccare la configurazione a vicenda, ma il portale di amministrazione di teams e il client teams devono mostrare questa relazione accuratamente in entrambe le posizioni. 

Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo che sono stati attivati e sono configurate le relazioni di gruppo delle chiamate), gli amministratori devono pulire le relazioni di gruppo delle chiamate per gli utenti nell'interfaccia di amministrazione del team per evitare il routing delle chiamate non corretto. 

## <a name="limitations"></a>Limitazioni

Un tenant può contenere un massimo di 32.768 gruppi di chiamate. In ogni gruppo di chiamate può essere disponibile un massimo di 25 utenti. 

## <a name="more-information"></a>Altre informazioni

[Inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
