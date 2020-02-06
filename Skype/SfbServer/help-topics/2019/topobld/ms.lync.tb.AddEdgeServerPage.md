---
title: Aggiungere il server perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
ROBOTS: NOINDEX, NOFOLLOW
description: Per inserire un server perimetrale o un pool di server perimetrali nella progettazione della topologia, è necessario specificare il nome di dominio completo (FQDN) del server in cui si vuole distribuire il server perimetrale o il pool di server perimetrali. Prima di pubblicare una topologia che include il pool di Edge Server o Edge Server e l'installazione di Skype for Business Server, è necessario che siano stati completati tutti i prerequisiti per la distribuzione dell'accesso degli utenti esterni. Per informazioni dettagliate su questi prerequisiti, vedere Preparing for Installation of Servers in the Perimeter Network nella documentazione relativa alla distribuzione.
ms.openlocfilehash: fd8e6f5fb398904f26ac5d62c4f9c1fc9b9caa80
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798143"
---
# <a name="add-edge-server"></a>Aggiungere il server perimetrale

Per inserire un server perimetrale o un pool di server perimetrali nella progettazione della topologia, è necessario specificare il nome di dominio completo (FQDN) del server in cui si vuole distribuire il server perimetrale o il pool di server perimetrali. Prima di pubblicare una topologia che include il pool di Edge Server o Edge Server e l'installazione di Skype for Business Server, è necessario che siano stati completati tutti i prerequisiti per la distribuzione dell'accesso degli utenti esterni. Per informazioni dettagliate su questi prerequisiti, vedere [Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx) nella documentazione relativa alla distribuzione.

> [!IMPORTANT]
> Il nome specificato deve essere uguale al nome del computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. Per questo motivo, è necessario configurare un suffisso DNS (Domain Name System) per il nome del computer da distribuire come server perimetrale o pool di server perimetrali non aggiunto a un dominio.

> [!TIP]
> Se si prevede di implementare in futuro un pool di server perimetrali, selezionare **Pool di più computer**. Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di un singolo computer e un FQDN del pool per questo computer. Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario di nuovo generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di Edge Server tramite la distribuzione guidata di Skype for Business Server. È anche necessario aggiungere il nuovo membro del pool ai servizi o dispositivi di bilanciamento del carico adatti per il pool, come il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware. L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra. Ricordarsi di aggiungere il nuovo server membro al bilanciamento del carico corrispondente.

È possibile aggiungere supporto per l'accesso degli utenti esterni durante o dopo la distribuzione della topologia iniziale. Per informazioni dettagliate sull'aggiunta di server perimetrali o pool di server perimetrali a una topologia esistente, vedere [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) nella documentazione relativa alla distribuzione di server perimetrali.


