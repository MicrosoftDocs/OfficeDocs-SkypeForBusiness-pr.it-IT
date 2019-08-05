---
title: Configurazione di Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Come parte della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione.
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187049"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurazione di Trunks in Skype for Business Server

Come parte della distribuzione VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più dei peer seguenti per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione:

- Connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP)
- Gateway PSTN
- PBX (Private Branch Exchange)

Per informazioni dettagliate, vedere [pianificare la connettività PSTN in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Prima di iniziare la configurazione del trunk, verificare che la topologia sia stata creata e che il Mediation Server e il relativo peer siano stati configurati e associati tra loro. Per informazioni dettagliate, vedere [definire un gateway in Generatore di topologia in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Come parte della configurazione trunk, puoi abilitare la caratteristica di bypass multimediale Skype for Business Server, che consente ai media di aggirare il server Mediation. I trunk possono essere configurati con o senza bypass multimediale abilitato, ma ti consigliamo vivamente di abilitarlo. Per informazioni dettagliate, vedere [pianificare il bypass multimediale in Skype for business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
