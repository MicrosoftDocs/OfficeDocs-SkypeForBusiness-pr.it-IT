---
title: Configurazione dei trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per fornire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi Enterprise Voice nell'organizzazione.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800116"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurazione dei trunk in Skype for Business Server

Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei seguenti peer per fornire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi Enterprise Voice nell'organizzazione:

- Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)
- Gateway PSTN
- Centralino (PBX)

Per ulteriori informazioni, vedere [pianificare la connettività PSTN in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati l'uno all'altro. Per ulteriori informazioni, vedere [definire un gateway in Generatore di topologie in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Come parte della configurazione trunk, è possibile abilitare la funzionalità di bypass multimediale di Skype for Business Server, che consente di bypassare il Mediation Server. I trunk possono essere configurati con o senza il bypass multimediale abilitato, ma è consigliabile abilitarlo. Per ulteriori informazioni, vedere [Plan for Media Bypass in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
