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
ms.openlocfilehash: 27c24ce632cb0803b5be27bd3c7f523815c6913e07a3983ebdad449d4e237d37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351166"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams

Le funzionalità di condivisione delle chiamate e di ritiro delle chiamate di gruppo di Microsoft Teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano quando l'utente non è disponibile.

Il ritiro delle chiamate di gruppo è meno dannoso per i destinatari rispetto ad altre forme di condivisione delle chiamate (ad esempio inoltro di chiamata o squillo simultaneo), perché gli utenti possono configurare la modalità di notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo o banner nell'app Teams) e possono decidere se rispondere.

Per condividere le chiamate con altri utenti, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi scelgono un anello simultaneo o un'impostazione in avanti. Per informazioni dettagliate, vedere Inoltro di chiamata [e squillo simultaneo Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) chiamata. Tieni presente che i dispositivi mobili riceveranno una notifica solo se sono impostati per banner e suonerie.

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamata e i membri del gruppo di chiamata devono essere in Teams modalità di distribuzione. Per altre informazioni sulle modalità Teams di distribuzione, vedere Informazioni sulla coesistenza e l'interoperabilità Microsoft Teams e [Skype for Business e sull'interoperabilità](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Agli utenti deve essere assegnata una Microsoft Teams Sistema telefonico per configurare e usare la condivisione delle chiamate e il ritiro delle chiamate di gruppo. Per altri dettagli sul modello di licenza, vedere Ecco cosa si ottiene con [Sistema telefonico.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)

## <a name="configure-group-call-pickup"></a>Configurare il ritiro delle chiamate di gruppo

Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non corrisponde a un gruppo di sicurezza o a un gruppo di Microsoft 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi, scelgono un'impostazione di inoltro di chiamata o squillo simultaneo. Per altre informazioni e procedure dettagliate, vedere Inoltro di chiamata e squillo simultaneo [in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Le preferenze per la creazione di gruppi di chiamate e le notifiche sono caratteristiche guidate dall'utente. gli amministratori non devono configurare queste funzionalità per gli utenti. I gruppi di chiamata non possono essere creati da gruppi di sicurezza o Microsoft 365 gruppi. devono essere creati in Teams.

Gli amministratori devono abilitare i gruppi di chiamate tramite **l'impostazione TeamsCallingPolicy AllowCallGroups per** un utente. Gli amministratori possono abilitarla anche tramite Teams di amministrazione.  Inoltre, l'utente configurato può anche configurare i gruppi di chiamate direttamente dal client. Gli amministratori o gli utenti finali non possono bloccare la configurazione tra loro, ma Teams portale di amministrazione e client di Teams devono mostrare questa relazione in modo accurato in entrambe le posizioni. 

Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo l'attivazione e la configurazione delle relazioni tra i gruppi di chiamate), gli amministratori devono pulire le relazioni del gruppo di chiamate per gli utenti nell'interfaccia di amministrazione di Teams per evitare un instradamento non corretto delle chiamate. 

## <a name="limitations"></a>Limitazioni

Ogni gruppo di chiamate configurato può contenere un massimo di 25 utenti o 32.768 caratteri. 

## <a name="more-information"></a>Altre informazioni

[Inoltro di chiamata e squillo simultaneo in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
