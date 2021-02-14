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
description: La condivisione delle chiamate e il ritiro delle chiamate di gruppo consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620722"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Condivisione delle chiamate e ritiro di chiamate di gruppo in Microsoft Teams

Le funzionalità di condivisione delle chiamate e di ritiro chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile.

Il ritiro di una chiamata di gruppo è meno disturbante per i destinatari rispetto ad altre forme di condivisione delle chiamate (come l'inoltro di chiamata o lo squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo o banner nell'app di Teams) e possono decidere se rispondere.

Per condividere le chiamate con altri utenti, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi sceglie un'impostazione di inoltro o squillo simultaneo. Per [informazioni dettagliate, vedere Inoltro di chiamata e squillo simultaneo in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamata e i membri del gruppo di chiamata devono essere in modalità di distribuzione solo di Teams. Per maggiori dettagli sulle modalità di distribuzione di Teams, consulta Informazioni sulla coesistenza e [l'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md) di Microsoft Teams e Skype for Business

## <a name="license-required"></a>Licenza richiesta

Gli utenti devono essere VoIP aziendale abilitati per configurare e usare la condivisione delle chiamate e il ritiro delle chiamate di gruppo. Per ulteriori dettagli sul modello di licenza, vedere la descrizione [del servizio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="configure-group-call-pickup"></a>Configurare il ritiro delle chiamate di gruppo

Per impostare il ritiro delle chiamate di gruppo, un utente configura prima un gruppo di chiamata (non corrisponde a un gruppo di sicurezza o a un gruppo di Microsoft 365) e quindi aggiunge gli utenti con cui vuole condividere le chiamate. In questo modo sceglie un'impostazione per lo squillo o l'inoltro di chiamata simultaneo. Per altre informazioni e procedure dettagliate, vedere Inoltro di chiamata e [squillo simultaneo in Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

Le preferenze per la creazione di gruppi di chiamate e le notifiche sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste caratteristiche per gli utenti. Non è possibile creare gruppi di chiamate da gruppi di sicurezza o gruppi di Microsoft 365; devono essere create in Teams.

Gli amministratori devono abilitare i gruppi di chiamata tramite **l'impostazione AllowCallingPolicy AllowCallGroups** per un utente. Gli amministratori possono anche abilitare questa funzionalità tramite il portale di amministrazione di Teams.  Inoltre, l'utente configurato può anche configurare i propri gruppi di chiamate direttamente dal client. Gli amministratori o gli utenti finali non possono bloccare la configurazione tra loro, ma il portale di amministrazione di Teams e il client di Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni. 

Importante: quando gli amministratori disattivano i gruppi di chiamata per gli utenti (dopo l'attivazione e aver configurato le relazioni tra gruppi di chiamate), gli amministratori devono pulire le relazioni dei gruppi di chiamata per gli utenti nell'interfaccia di amministrazione di Teams per evitare un instradamento errato delle chiamate. 

## <a name="limitations"></a>Limitazioni

Un tenant può contenere al massimo 32.768 gruppi di chiamate. Ogni gruppo di chiamata può contenere al massimo 25 utenti. 

## <a name="more-information"></a>Altre informazioni

[Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
