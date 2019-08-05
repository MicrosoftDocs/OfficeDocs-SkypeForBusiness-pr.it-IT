---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189506"
---
# <a name="define-a-new-trunk"></a>Definire un nuovo trunk

Si definisce un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:

- **Trunk Name**: nome univoco nella topologia che identificherà questo trunk

- **Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco

- **Porta di ascolto per il gateway IP/PSTN**: porta che verrà ascoltata dal gateway IP-PBX o PSTN. Deve essere univoco da tutte le altre porte di ascolto del trunk configurate nella distribuzione

- **Protocollo di trasporto SIP**: selezionare dall'elenco TCP o TLS

- **Mediation Server associato**: selezionare dall'elenco un Mediation Server distribuito e configurato nella distribuzione

- **Porta Mediation Server associata**: imposta il valore della porta uguale al valore della porta TCP o TLS del server di mediazione che verrà usato da questo trunk SIP

## <a name="see-also"></a>Vedere anche

[Trunk M:N in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Come implementare il trunking SIP](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
