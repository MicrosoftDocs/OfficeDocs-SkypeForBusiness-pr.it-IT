---
title: Definire proprietà e opzioni per il pool Persistent Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'È possibile configurare le opzioni per il server Chat persistente o per il pool di server Chat persistente definendo le proprietà seguenti:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218547"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definire proprietà e opzioni per il pool Persistent Chat
 
È possibile configurare le opzioni per il server Chat persistente o per il pool di server Chat persistente definendo le proprietà seguenti:
  
 **Nome visualizzato del pool di chat persistente**: proprietà obbligatoria che definisce un nome descrittivo che verrà visualizzato per il server Chat persistente o per il pool di server Chat persistente.
  
 **Porta di chat persistente**: proprietà obbligatoria che definirà il numero di porta che questo server Chat persistente o il pool di server Chat persistente terrà in attesa.
  
 **Consenti conformità**: selezionare la casella di controllo se si prevede di distribuire e implementare la funzionalità e il database di conformità di Persistent Chat opzionali.
  
 **Utilizzare gli archivi SQL Server di backup per abilitare il ripristino di emergenza**: selezionare questa casella di controllo se si prevede di distribuire e implementare il ripristino di emergenza degli archivi SQL Server di chat persistente da un set di backup configurato di archivi in un altro SQL Server. Per ulteriori informazioni, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Questa opzione è disponibile solo per pool con più server. 
  
 **Utilizzare questo pool come predefinito per il sito \<site that this server or pool is being configured in\> **: selezionare questa casella di controllo se si tratta del server Chat persistente predefinito o del pool di server Chat persistente per il sito. È necessario disporre di un server di chat persistente predefinito o pol per sito.
  
> [!NOTE]
> Se la topologia include più siti, viene visualizzata una casella di controllo anche per **Usa questo pool come predefinito per tutti i siti**.
  
Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.
  
Fare clic su **Avanti** dopo aver immesso le opzioni per il pool per continuare con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
