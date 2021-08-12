---
title: Aggiungere il computer Front End Server
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo la pubblicazione della topologia, per poter modificare l'FQDN, è necessario eliminare il server in Generatore di topologie e quindi aggiungere al pool un nuovo server con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere Define and Configure a Front End Pool nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 912b4599db1882fda9741573ce1ac2637584ca84990d54ca3964037f4e00d396
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342151"
---
# <a name="add-front-end-machine"></a>Aggiungere un computer front-end

Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo la pubblicazione della topologia, per poter modificare l'FQDN, è necessario eliminare il server in Generatore di topologie e quindi aggiungere al pool un nuovo server con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Si noti che Generatore di topologie indica che è possibile disporre di un massimo di 20 Front End Server in un pool. Il numero massimo supportato di server è 12. Nell'infrastruttura possono essere definiti fino a 20 server statefull, di cui 12 possono essere attivi e online in qualsiasi momento.