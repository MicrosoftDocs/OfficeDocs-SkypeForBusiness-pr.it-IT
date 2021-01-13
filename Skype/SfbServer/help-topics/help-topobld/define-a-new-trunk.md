---
title: Definire un nuovo trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:'
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833046"
---
# <a name="define-a-new-trunk"></a>Definire un nuovo trunk

È possibile definire un nuovo trunk SIP (Session Initiation Protocol) fornendo le informazioni seguenti:

- **Nome trunk**: nome univoco nella topologia che identificherà questo trunk

- **Gateway PSTN associato**: selezionare un gateway PSTN distribuito e configurato nella distribuzione dall'elenco

- **Porta di attesa per il gateway IP/PSTN**: porta che verrà ascoltata dal gateway IP-PBX o PSTN. Deve essere univoco da tutte le altre porte di ascolto del trunk configurate nella distribuzione

- **Protocollo di trasporto SIP**: selezionare dall'elenco TCP o TLS

- **Mediation Server associato**: selezionare nell'elenco un Mediation Server distribuito e configurato nella distribuzione

- **Porta Mediation Server associato**: impostare il valore della porta uguale al valore della porta TCP o TLS del Mediation Server che verrà utilizzato da questo trunk SIP

## <a name="see-also"></a>Vedere anche

[Trunk M:N in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Come implementare il trunking SIP](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
