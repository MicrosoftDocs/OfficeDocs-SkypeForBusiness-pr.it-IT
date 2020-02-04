---
title: Aggiungere l'archivio file per Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 44c4cd746dca8fa1c03dd42c2d77476ab6c186c7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685069"
---
# <a name="add-persistent-chat-file-store"></a>Aggiungere l'archivio file per Chat persistente
 
È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
  
> [!IMPORTANT]
> La condivisione file per Skype for Business Server non può essere posizionata nel server front-end Enterprise Edition, ma può essere posizionata in un server Standard Edition. 
  
> [!IMPORTANT]
> È possibile definire la condivisione file in Generatore di topologie prima di crearla, ma è necessario crearla nel percorso definito prima di pubblicare la topologia. 
  
> [!IMPORTANT]
> Quando si aggiunge un server di chat persistente o un pool di server di chat persistente alla topologia, generatore di topologie deve essere in grado di configurare l'archivio di file e configurarne gli elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da usare per l'archivio di file. Per questo, quando si esegue Generatore di topologie per pubblicare la nuova topologia, è necessario essere connessi con un account dotato di autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file. 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype per Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisiti hardware e software per il server Chat persistente](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisiti server di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Elementi di base della topologia per Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
