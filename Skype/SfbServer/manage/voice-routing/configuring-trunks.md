---
title: Configurazione di Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come parte della distribuzione di VoIP aziendale, è possibile configurare un trunk tra un Mediation Server e uno o più peer per consentire la connettività PSTN (Public Switched Telephone Network) per i client e i dispositivi VoIP aziendali nell'organizzazione.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817016"
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
