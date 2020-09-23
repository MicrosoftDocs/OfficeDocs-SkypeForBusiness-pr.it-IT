---
title: Aggiungere l'archivio file di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 76169673848d9cbace41642d5058bfb60e90508a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218677"
---
# <a name="add-persistent-chat-file-store"></a>Aggiungere l'archivio file di Chat persistente
 
È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
  
> [!IMPORTANT]
> La condivisione file per Skype for Business Server non può essere posizionata in Enterprise Edition Front End Server, ma può essere posizionata in un server Standard Edition. 
  
> [!IMPORTANT]
> È possibile definire la condivisione file in Generatore di topologie prima di creare la condivisione file ma è necessario crearla nel percorso definito prima di pubblicare la topologia. 
  
> [!IMPORTANT]
> Quando si aggiunge un server Chat persistente o un pool di server Chat persistente alla topologia, il generatore di topologie deve essere in grado di impostare l'archivio file e di configurare gli elenchi di controllo di accesso discrezionale nella condivisione file da utilizzare per l'archivio file. Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file. 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Nozioni di base sulla topologia per Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
