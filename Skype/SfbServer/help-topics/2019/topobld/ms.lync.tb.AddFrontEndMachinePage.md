---
title: Aggiungere un computer front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si vuole aggiungere come server front-end in questo pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima della pubblicazione della topologia. Dopo aver pubblicato la topologia, la modifica dell'FQDN richiede l'eliminazione del server in Generatore di topologia e l'aggiunta di un nuovo server al pool con il nuovo nome di dominio completo. Per informazioni dettagliate sull'aggiunta di un pool Front-end alla topologia, vedere definire e configurare un pool Front end nella documentazione relativa alla distribuzione.
ms.openlocfilehash: a4ff4ce7a7fc775e33657dc2f8602d62163ed1d4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798543"
---
# <a name="add-front-end-machine"></a>Aggiungere un computer front-end

Specificare il nome di dominio completo (FQDN) di ogni computer che si vuole aggiungere come server front-end in questo pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima della pubblicazione della topologia. Dopo aver pubblicato la topologia, la modifica dell'FQDN richiede l'eliminazione del server in Generatore di topologia e l'aggiunta di un nuovo server al pool con il nuovo nome di dominio completo. Per informazioni dettagliate sull'aggiunta di un pool Front-end alla topologia, vedere [definire e configurare un pool Front End](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Tieni presente che generatore di topologie indica che puoi avere fino a 20 server front-end in un pool. Il numero massimo supportato di server è 12. È possibile avere fino a 20 server statefull definiti nel tessuto, di cui 12 possono essere attivi e online in qualsiasi momento.


