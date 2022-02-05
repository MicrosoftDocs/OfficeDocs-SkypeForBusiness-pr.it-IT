---
title: Aggiungere l'indirizzo IP interno del computer perimetrale
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: 'NOINDEX, NOFOLLOW'
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.
---

# <a name="add-edge-machine-internal-ip"></a>Aggiungere Edge Machine External IP

Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno del server perimetrale.

L'FQDN specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).