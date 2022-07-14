---
title: Condivisione delle chiamate e risposta alle chiamate di gruppo
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: La condivisione delle chiamate e il ritiro delle chiamate di gruppo consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 70b1be389309d52b01852e575d08093ef7095a04
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789951"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams

Le funzionalità di condivisione delle chiamate e di ritiro delle chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile.

Il ritiro delle chiamate di gruppo è meno fastidioso per i destinatari rispetto ad altre forme di condivisione delle chiamate (ad esempio l'inoltro di chiamata o lo squillo simultaneo) perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visiva o banner nell'app Teams) e possono decidere se rispondere.

Per condividere le chiamate con altri utenti, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vuole condividere le chiamate. Quindi scelgono un'impostazione di inoltro o squillo simultaneo. Per informazioni dettagliate, vedere [Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) . Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamata e i membri del gruppo di chiamata devono essere in modalità di distribuzione solo in Teams. Per altri dettagli sulle modalità di distribuzione di Teams, vedere [Informazioni su Microsoft Teams e la coesistenza e l'interoperabilità di Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="license-required"></a>Licenza richiesta

Agli utenti deve essere assegnata una licenza di sistema Telefono di Microsoft Teams per configurare e utilizzare la condivisione delle chiamate e il ritiro delle chiamate di gruppo. Per altri dettagli sul modello di licenza, vedi [Ecco cosa ottieni con Sistema telefonico](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="configure-group-call-pickup"></a>Configurare il ritiro delle chiamate di gruppo

Per configurare il ritiro delle chiamate di gruppo, un utente configura innanzitutto un gruppo di chiamate (diverso da un gruppo di sicurezza o un gruppo di Microsoft 365), quindi aggiunge gli utenti con cui vuole condividere le chiamate. Quindi, scelgono un'impostazione di inoltro di chiamata o squillo simultaneo. Per altre informazioni e procedure dettagliate, vedere [Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Le preferenze per la creazione di gruppi di chiamata e le preferenze di notifica sono funzionalità basate sull'utente; gli amministratori non devono configurare queste funzionalità per gli utenti. I gruppi di chiamata non possono essere creati da gruppi di sicurezza o gruppi di Microsoft 365; devono essere creati in Teams.

Gli amministratori devono abilitare i gruppi di chiamata tramite l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente. Gli amministratori possono anche abilitarlo tramite il portale di Teams Amministrazione.  Inoltre, l'utente configurato può anche configurare i propri gruppi di chiamate direttamente tramite il client. Amministrazione o gli utenti finali non possono bloccarsi reciprocamente la configurazione, ma Teams Amministrazione portale e client di Teams devono mostrare questa relazione in modo accurato in entrambi i luoghi. 

Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo che sono stati attivati e le relazioni dei gruppi di chiamata sono configurate), gli amministratori devono pulire le relazioni del gruppo di chiamate per gli utenti nell'interfaccia di amministrazione di Teams per evitare il routing delle chiamate errato. 

## <a name="limitations"></a>Limitazioni

Ogni gruppo di chiamata configurato può avere un massimo di 25 utenti o 32.768 caratteri. 

## <a name="more-information"></a>Altre informazioni

[Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
