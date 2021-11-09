---
title: Aggiungere l'indirizzo IP interno del computer perimetrale
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.
ms.openlocfilehash: c0d08bf0fb4b197b32a79172c3df2c494173faa5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842078"
---
# <a name="add-edge-machine-internal-ip"></a>Aggiungere Edge Machine External IP

Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.

L'FQDN specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).