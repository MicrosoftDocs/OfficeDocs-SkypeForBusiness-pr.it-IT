---
title: Aggiungere l'indirizzo IP interno del computer perimetrale (2010)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.
---

# <a name="add-edge-machine-internal-ip-2010"></a>Aggiungere Edge Machine Internal IP 2010

Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.

- In **Indirizzo IPv4 interno** digitare l'indirizzo IP del server perimetrale che si desidera aggiungere al pool.

- In **FQDN interno** digitare il nome di dominio completo (FQDN) del server perimetrale che si desidera aggiungere al pool.

L'FQDN specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).