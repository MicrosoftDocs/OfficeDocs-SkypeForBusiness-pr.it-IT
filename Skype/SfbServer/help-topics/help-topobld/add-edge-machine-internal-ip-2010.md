---
title: Add Edge computer IP interno 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno per il server perimetrale.
ms.openlocfilehash: 53b4a3d7d7347a151cc34195236f50d492206825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195597"
---
# <a name="add-edge-machine-internal-ip-2010"></a>Add Edge computer IP interno 2010

Usare questa pagina per specificare l'indirizzo IP interno e il nome di dominio completo (FQDN) interno per il server perimetrale.

- Nell' **indirizzo IPv4 interno**Digitare l'indirizzo IP del server perimetrale che si vuole aggiungere al pool.

- In **FQDN interno**Digitare il nome di dominio completo (FQDN) dell'Edge Server che si vuole aggiungere al pool.

L'FQDN specificato deve essere identico al nome del computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. È quindi necessario configurare un suffisso DNS (Domain Name System) sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere [configurare DNS per il supporto Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)


