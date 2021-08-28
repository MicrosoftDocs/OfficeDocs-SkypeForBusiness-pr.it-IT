---
title: Aggiungere l'archivio file di Chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
ms.openlocfilehash: 17ef0ff681b3a583c9423c5ea693f88b35db904d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615742"
---
# <a name="add-persistent-chat-file-store"></a>Aggiungere l'archivio file di Chat persistente
 
È necessario specificare una condivisione file da usare come archivio file per il server Standard Edition o il pool Enterprise Edition Front End. È possibile usare una condivisione file esistente per l'archivio file oppure specificarne una nuova indicando il nome di dominio completo (FQDN) del file server in cui deve trovarsi la condivisione file, oltre a un nome di cartella per la nuova condivisione file.
  
> [!IMPORTANT]
> La condivisione file per Skype for Business Server non può essere posizionata nel Front End Server di edizione Enterprise, ma può trovarsi in un server edizione Standard server. 
  
> [!IMPORTANT]
> È possibile definire la condivisione file in Generatore di topologie prima di creare la condivisione file ma è necessario crearla nel percorso definito prima di pubblicare la topologia. 
  
> [!IMPORTANT]
> Quando si aggiunge un server Chat persistente o un pool di server Chat persistente alla topologia, Generatore di topologie deve essere in grado di configurare l'archivio file e configurare gli elenchi di controllo di accesso discrezionale (DACL) nella condivisione file da utilizzare per l'archivio file. Quando si esegue Generatore di topologie per pubblicare la nuova topologia, è quindi necessario essere connessi con un account dotato delle autorizzazioni di controllo completo (lettura/scrittura/modifica) per la condivisione file. 
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere un server Chat persistente alla topologia Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Nozioni di base sulla topologia Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
