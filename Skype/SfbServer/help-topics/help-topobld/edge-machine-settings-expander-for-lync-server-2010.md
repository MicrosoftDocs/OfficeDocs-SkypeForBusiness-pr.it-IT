---
title: Espansione delle impostazioni del computer perimetrale per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: "Per modificare le proprietà dei computer Edge Server come un singolo Edge Server o come computer membri in un pool di Edge, è possibile configurare le impostazioni di configurazione del nome del server e dell'indirizzo IP:"
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684779"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Espansione delle impostazioni del computer perimetrale per Lync Server 2010
 
Per modificare le proprietà dei computer Edge Server come un singolo Edge Server o come computer membri in un pool di Edge, è possibile configurare le impostazioni di **configurazione del nome del server e dell'indirizzo IP** :
  
- **Nome interno o FQDN**: digitare il nome del computer a cui viene fatto riferimento nel DNS (Domain Name System). 
    
- **Indirizzo IPv4 interno**: digitare l'indirizzo IPv4 della scheda di interfaccia di rete interna (NIC) per il computer.
    
- Si configura l' **indirizzo IPv4 esterno** del **servizio Access Edge** associato al computer
    
    > [!IMPORTANT]
    > Se si è scelto di usare un singolo indirizzo IP per la configurazione di Edge Server, sarà possibile modificare solo l'indirizzo IPv4 esterno per il servizio Access Edge. Gli altri servizi Edge condividono lo stesso indirizzo IPv4 del servizio Access Edge. 
  
- Se disponibile per la modifica, configurare l' **indirizzo IPv4 esterno** del **servizio di conferenza Web** associato al computer
    
- Se disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 esterno** del **servizio a/V** associato al computer
    
- Se disponibile per la modifica, è possibile configurare l' **indirizzo IPv4 pubblico abilitato per NAT** associato al computer.
    
    > [!IMPORTANT]
    > La proprietà di configurazione per l' **indirizzo IPv4 pubblico abilitato per NAT** sarà disponibile solo per la modifica se si è scelto di specificare la NAT (Network Address Translation) per il servizio a/V Edge
  
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  

