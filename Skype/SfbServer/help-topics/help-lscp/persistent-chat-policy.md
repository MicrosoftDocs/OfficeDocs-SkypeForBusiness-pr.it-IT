---
title: Criteri di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: È possibile usare la pagina Criteri di Chat persistente del gruppo Chat persistente per gestire criteri a livello globale, di pool, sito o utente, incluse la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri di sito e utente aggiuntivi per la distribuzione. Se il server di chat persistente è abilitato per un utente in base ai criteri, l'ambiente del server di chat persistente viene visualizzato nel client.
ms.openlocfilehash: f08f0af3c2f553f1acc980c64be1602519ffa898
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191813"
---
# <a name="persistent-chat-policy"></a>Criteri di Chat persistente
 
È possibile usare la pagina **Criteri di Chat persistente** del gruppo **Chat persistente** per gestire criteri a livello globale, di pool, sito o utente, incluse la configurazione dei criteri globali predefiniti e la creazione di uno o più criteri di sito e utente aggiuntivi per la distribuzione. Se il server di chat persistente è abilitato per un utente in base ai criteri, l'ambiente del server di chat persistente viene visualizzato nel client.
  
Il criterio globale viene creato automaticamente quando si distribuisce il server di chat persistente e può essere configurato, ma non eliminato. Poiché il criterio globale si applica a tutti gli utenti, non deve essere impostato per ogni utente.
  
È possibile creare e configurare più criteri per il sito e gli utenti che, insieme al criterio globale, consentono agli utenti di usare il server di chat persistente. I criteri per i server di chat persistenti per pool e siti eseguono l'override del criterio server globale di chat persistente, ma solo per gli utenti del sito. I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.
  
> [!NOTE]
> Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere [aggiungere il server di chat persistente alla topologia di Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Criteri di Chat persistente** è possibile eseguire le attività seguenti: abilitare i criteri del server Chat persistente e gestire i criteri del server Chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Per configurare il criterio globale per la chat persistente

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nel pannello di controllo di Skype for Business Server fare clic su **chat persistente**e quindi su **criteri di chat permanenti**.
    
4. Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri Chat persistente- Globale** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera utilizzare il nome predefinito Globale.
    
   - In **Descrizione**specificare i dettagli relativi al criterio utente (ad esempio, criteri globali per _centralSiteName_).
    
   - Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Per creare criteri di chat persistenti per un sito

Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito.
  
La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.
    
6. In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".
    
   - Per controllare Chat persistente per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente**.
    
7. Fare clic su **Commit**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Per creare un criterio utente per la chat persistente

Nel pannello di controllo di Skype for Business Server Definisci i criteri utente che possono essere assegnati agli utenti negli **utenti**.
  
Il criterio utente ha la priorità sul criterio globale e sui criteri sito, ma solo per gli utenti specifici a cui viene assegnato il criterio utente.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo criterio utente.
    
   - In **Descrizione**, fornisci i dettagli sui criteri degli utenti, ad esempio i criteri di chat persistenti per un utente specifico.
    
   - Per controllare la chat persistente per tutti gli utenti che non sono specificamente controllati tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Per applicare un criterio utente di chat persistente a un account utente

Se un utente è stato abilitato per Skype for Business Server, è possibile applicare criteri appropriati a utenti specifici per abilitarli o disabilitarli per il server di chat persistente.
  
Usare la procedura descritta in questo argomento per applicare un criterio utente di chat persistente creato in precedenza a uno o più account utente o gruppi di utenti.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.
    
4. Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **modifica utenti di Lync Server** in **criteri di chat persistenti**Selezionare i criteri utente per la chat persistente che si desidera applicare.
    
    > [!NOTE]
    > Le ** \<impostazioni\> automatiche** applicano i criteri effettivi predefiniti. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

