---
title: Aggiungere il computer Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere Define and Configure a Front End Pool nella documentazione relativa alla distribuzione.
ms.openlocfilehash: f0336e6e1561a9a5bc4de80d7058bf99c5fb6092
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811696"
---
# <a name="add-front-end-machine"></a>Aggiungere un computer front-end

Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Si noti che Generatore di topologie indica che in un pool possono essere presenti fino a 20 Front End Server. Il numero massimo supportato di server è 12. Nell'infrastruttura possono essere definiti fino a 20 server con stato, di cui 12 possono essere attivi e online in qualsiasi momento.


