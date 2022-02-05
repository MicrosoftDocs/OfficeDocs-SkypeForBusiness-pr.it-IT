---
title: Configurazione dei trunk in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Nell''ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell''organizzazione.'
---

# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurazione dei trunk in Skype for Business Server

Nell'ambito della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per fornire connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendale nell'organizzazione:

- Connessione con trunk SIP a un provider di servizi di telefonia Internet (ITSP)
- Gateway PSTN
- Centralino (PBX)

Per informazioni dettagliate, [vedere Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati l'uno all'altro. Per informazioni dettagliate, [vedere Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Come parte della configurazione trunk, è possibile abilitare la funzionalità Skype for Business Server bypass multimediale, che consente ai supporti di ignorare il Mediation Server. I trunk possono essere configurati con o senza il bypass multimediale abilitato, ma è consigliabile abilitarlo. Per informazioni dettagliate, vedere [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
