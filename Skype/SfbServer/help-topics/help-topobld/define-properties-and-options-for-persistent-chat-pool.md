---
title: Definire proprietà e opzioni per il pool Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'È possibile configurare le opzioni per il server Chat persistente o il pool di server Chat persistente definendo le proprietà seguenti:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818426"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definire le proprietà e le opzioni per il pool di Chat persistente
 
È possibile configurare le opzioni per il server Chat persistente o il pool di server Chat persistente definendo le proprietà seguenti:
  
 **Nome visualizzato del pool di Chat** persistente: proprietà obbligatoria che definisce un nome descrittivo che verrà visualizzato per il server Chat persistente o il pool di server Chat persistente.
  
 **Porta di Chat persistente:** proprietà obbligatoria che definisce il numero di porta su cui il server Chat persistente o il pool di server Chat persistente sarà in ascolto.
  
 **Abilita conformità:** selezionare la casella di controllo se si prevede di distribuire e implementare la funzionalità e il database di conformità di Persistent Chat facoltativi.
  
 Utilizzare **gli archivi SQL Server** di backup per abilitare il ripristino di emergenza: selezionare questa casella di controllo se si prevede di distribuire e implementare il ripristino di emergenza degli archivi SQL Server di Persistent Chat da un set di backup configurato di archivi in un altro SQL Server. Per informazioni dettagliate, vedere Configurare la disponibilità elevata e il ripristino di emergenza per il [server Chat persistente in Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
  
> [!NOTE]
> Questa opzione è disponibile solo per pool con più server. 
  
 **Utilizzare questo pool come \<site that this server or pool is being configured in\> predefinito per** il sito: selezionare questa casella di controllo se si tratta del server Chat persistente o del pool di server Chat persistente predefinito per il sito. È necessario disporre di un server Chat persistente predefinito o di un server per sito.
  
> [!NOTE]
> Se la topologia include più siti, viene visualizzata una casella di controllo anche per **Usa questo pool come predefinito per tutti i siti**.
  
Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.
  
Fare **clic** su Avanti dopo aver immesso le opzioni per il pool per continuare con la definizione del pool del server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
