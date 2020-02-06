---
title: Definire proprietà e opzioni per il pool Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Si configurano le opzioni per il server di chat persistente o per il pool di server di chat persistente definendo le proprietà seguenti:'
ms.openlocfilehash: 39816bcc4c76a5be07e90c63dfa9064c4a0670d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820188"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definire proprietà e opzioni per il pool Chat persistente
 
Si configurano le opzioni per il server di chat persistente o per il pool di server di chat persistente definendo le proprietà seguenti:
  
 **Nome visualizzato del pool di chat persistente**: una proprietà obbligatoria che definisce un nome descrittivo dell'utente che verrà visualizzato per questo server di chat persistente o per il pool di server di chat persistente.
  
 **Porta della chat persistente**: una proprietà obbligatoria che definirà il numero di porta che verrà ascoltato da questo server di chat persistente o dal pool di server di chat persistente.
  
 **Abilitare la conformità**: selezionare la casella di controllo se si prevede di distribuire e implementare la funzionalità e il database di conformità delle chat persistenti facoltative.
  
 **Usare gli archivi di SQL Server di backup per abilitare il ripristino di emergenza**: selezionare questa casella di controllo se si prevede di distribuire e implementare il ripristino di emergenza degli archivi di SQL Server di chat persistenti da un set di backup configurato di archivi in un altro server SQL. Per informazioni dettagliate, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Questa opzione è disponibile solo per pool con più server. 
  
 **Usare questo pool come predefinito per il sito \<del sito in\>cui è configurato questo server o pool**: selezionare questa casella di controllo se si tratta del server di chat persistente predefinito o del pool di server di chat persistente per il sito. È necessario disporre di un server di chat persistente predefinito o pol per sito.
  
> [!NOTE]
> Se la topologia include più siti, viene visualizzata una casella di controllo anche per **Usa questo pool come predefinito per tutti i siti**.
  
Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.
  
Fare clic su **Avanti** dopo aver completato l'immissione delle opzioni per il pool per procedere con la definizione del pool del server di chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool di Chat persistente**.
  
Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype per Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
