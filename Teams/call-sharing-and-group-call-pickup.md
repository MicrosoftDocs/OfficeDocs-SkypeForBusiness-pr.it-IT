---
title: Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Condivisione chiamate e raccolta chiamate di gruppo consente agli utenti di condividere le chiamate in arrivo con i colleghi in modo che le chiamate possano essere acquisite quando l'utente non è disponibile.
ms.openlocfilehash: caf472f9829f9cf68ccb87a5081bc0b5cfae28f8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237166"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Condivisione delle chiamate e ritiro delle chiamate di gruppo in Microsoft Teams

Le funzionalità di condivisione chiamata e raccolta chiamate di gruppo di Microsoft teams consentono agli utenti di condividere le chiamate in arrivo con i colleghi in modo che i colleghi possano rispondere alle chiamate che si verificano mentre l'utente non è disponibile.

Il ritiro delle chiamate di gruppo è meno distruttivo per i destinatari rispetto ad altre forme di condivisione delle chiamate, ad esempio l'inoltro di chiamata o lo squillo simultaneo, perché gli utenti possono configurare il modo in cui vogliono ricevere una notifica di una chiamata condivisa in arrivo (tramite notifica audio e visiva, solo visivo, o banner nell'app Teams), che può decidere se rispondere.

Per condividere le chiamate con altre persone, un utente crea un gruppo di chiamate e aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi scelgono un anello o un'impostazione di inoltro simultaneo. Per informazioni dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Gli utenti, il proprietario del gruppo di chiamate e i membri del gruppo di chiamate devono essere solo in modalità di distribuzione in teams. Per altre informazioni sulle modalità di distribuzione dei team, vedere comprendere la coesistenza e l'interoperabilità di [Microsoft teams e Skype for business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licenza richiesta

Gli utenti devono essere abilitati a VoIP aziendale per configurare e usare la condivisione delle chiamate e il pick-up delle chiamate di gruppo. Per altre informazioni sul modello di licenza, vedere [licenze di Office 365 per Microsoft teams](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Configurare il ritiro delle chiamate di gruppo

Per configurare il ritiro delle chiamate di gruppo, un utente configura prima di tutto un gruppo di chiamate (non è uguale a un gruppo di sicurezza o a un gruppo di Office 365) e quindi aggiunge gli utenti con cui vogliono condividere le chiamate. Quindi scelgono un anello simultaneo o un'impostazione di inoltro di chiamata. Per altre informazioni e procedure dettagliate, vedere [inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Le preferenze per la creazione e la notifica di gruppi di chiamate sono caratteristiche guidate dall'utente; gli amministratori non devono configurare queste funzionalità per gli utenti. Non è possibile creare gruppi di chiamate da gruppi di sicurezza o gruppi di Office 365; devono essere creati in teams.

Gli amministratori dovrebbero abilitare i gruppi di chiamate tramite l'impostazione **TeamsCallingPolicy AllowCallGroups** per un utente. Gli amministratori possono anche abilitare questo tramite il portale di amministrazione di teams.  Inoltre, l'utente configurato può anche configurare i gruppi di chiamate direttamente tramite il client. L'amministratore o gli utenti finali non possono bloccare la configurazione a vicenda, ma il portale di amministrazione di teams e il client teams devono mostrare questa relazione accuratamente in entrambe le posizioni. 

Importante: quando gli amministratori disattivano i gruppi di chiamate per gli utenti (dopo che sono stati attivati e sono configurate le relazioni di gruppo delle chiamate), gli amministratori devono pulire le relazioni di gruppo delle chiamate per gli utenti nell'interfaccia di amministrazione del team per evitare il routing delle chiamate non corretto. 

## <a name="limitations"></a>Limitazioni

Un tenant può contenere un massimo di 32.768 gruppi di chiamate. In ogni gruppo di chiamate può essere disponibile un massimo di 25 utenti. 

## <a name="more-information"></a>Ulteriori informazioni

[Inoltro di chiamata e squillo simultaneo in teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
