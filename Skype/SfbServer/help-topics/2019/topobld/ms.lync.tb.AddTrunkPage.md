---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: 49411ca6416a99d30d7a889aca0151f3ef89b9f7a8b7e559c39366c585144378
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295423"
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