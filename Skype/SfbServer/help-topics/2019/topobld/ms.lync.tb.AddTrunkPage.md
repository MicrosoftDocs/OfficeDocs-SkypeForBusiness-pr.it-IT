---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: 7e6c80b3f5762dc409a47ee4b9e6f7ff9053b84c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836898"
---
# <a name="define-a-new-trunk"></a>Definire un nuovo trunk

È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:

- **Nome trunk**: nome univoco nella topologia che identificherà questo trunk

- **Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco

- **Porta di attesa per il gateway IP/PSTN**: porta su cui il gateway IP-PBX o PSTN sarà in ascolto. Deve essere univoco da tutte le altre porte di attesa trunk configurate nella distribuzione

- **Protocollo di trasporto SIP**: selezionare nell'elenco TCP o TLS

- **Mediation Server associato:** selezionare nell'elenco un Mediation Server distribuito e configurato nella distribuzione

- **Porta Mediation Server associata**: impostare il valore della porta uguale al valore della porta TCP o TLS del Mediation Server che verrà utilizzato da questo trunk SIP

## <a name="see-also"></a>Vedere anche

[Trunk M:N in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Come si implementa il trunking SIP?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)