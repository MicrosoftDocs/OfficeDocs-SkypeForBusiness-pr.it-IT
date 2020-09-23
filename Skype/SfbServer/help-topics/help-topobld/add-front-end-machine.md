---
title: Aggiungere il computer Front End Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere Define and Configure a Front End Pool nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218317"
---
# <a name="add-front-end-machine"></a>Aggiungere il computer Front End Server

Specificare il nome di dominio completo (FQDN) di ogni computer che si desidera aggiungere come Front End Server nel pool. Dopo aver aggiunto un computer all'elenco, è possibile aggiornare l'FQDN del computer o rimuoverlo dal pool in qualsiasi momento prima di pubblicare la topologia. Dopo aver pubblicato la topologia, per la modifica dell'FQDN è necessario eliminare il server nel Generatore di topologie e quindi aggiungere un nuovo server al pool con il nuovo FQDN. Per informazioni dettagliate sull'aggiunta di un pool Front End alla topologia, vedere [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Si noti che generatore di topologie indica che è possibile disporre di un massimo di 20 front end server in un pool. Il numero massimo supportato di server è 12. È possibile disporre di un massimo di 20 server statefull definiti nel tessuto, di cui 12 possono essere attivi e online in qualsiasi momento.


