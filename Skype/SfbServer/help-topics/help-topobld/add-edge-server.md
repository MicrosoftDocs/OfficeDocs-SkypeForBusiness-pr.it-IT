---
title: Aggiungere Edge Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: Per incorporare un server perimetrale o un pool di server perimetrali nella progettazione della topologia, è necessario specificare il nome di dominio completo (FQDN) del server in cui si desidera distribuire il server perimetrale o il pool di server perimetrali. Prima di pubblicare una topologia che include il server perimetrale o il pool di server perimetrali e installare Skype for Business Server, è necessario aver completato tutti i prerequisiti per la distribuzione dell'accesso degli utenti esterni. Per informazioni dettagliate su questi prerequisiti, vedere Preparing for Installation of Servers in the Perimeter Network nella documentazione relativa alla distribuzione.
ms.openlocfilehash: 04ab27281bd382b95ec088a9db995237d6ff7d6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837868"
---
# <a name="add-edge-server"></a>Aggiungere Edge Server

Per incorporare un server perimetrale o un pool di server perimetrali nella progettazione della topologia, è necessario specificare il nome di dominio completo (FQDN) del server in cui si desidera distribuire il server perimetrale o il pool di server perimetrali. Prima di pubblicare una topologia che include il server perimetrale o il pool di server perimetrali e installare Skype for Business Server, è necessario aver completato tutti i prerequisiti per la distribuzione dell'accesso degli utenti esterni. Per informazioni dettagliate su questi prerequisiti, vedere [Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Il nome specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. È pertanto necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale o pool di server perimetrali non aggiunto a un dominio.

> [!TIP]
> Se si prevede di implementare in futuro un pool di server perimetrali, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con il carico bilanciato, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione. Quando si è pronti ad aggiungere più computer al pool in un secondo momento, è necessario di nuovo Generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di server perimetrali tramite la Distribuzione guidata di Skype for Business Server. È inoltre necessario aggiungere il nuovo membro del pool ai servizi o dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware. L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra interfaccia perimetrale. Ricordarsi di aggiungere il nuovo server membro al bilanciamento del carico appropriato.

È possibile aggiungere il supporto per l'accesso degli utenti esterni quando si distribuisce la topologia iniziale o dopo aver distribuito la topologia iniziale. Per informazioni dettagliate sull'aggiunta di server perimetrali o pool di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) nella documentazione relativa alla distribuzione di server perimetrali.