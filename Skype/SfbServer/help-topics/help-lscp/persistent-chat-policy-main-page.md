---
title: Pagina principale Criteri Persistent Chat
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
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: È possibile utilizzare la pagina Criteri di Persistent Chat del gruppo di Persistent Chat per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione del criterio globale predefinito e la creazione di uno o più criteri utente e sito aggiuntivi per la distribuzione. Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente verrà visualizzato nel client.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819306"
---
# <a name="persistent-chat-policy-main-page"></a>Pagina principale dei criteri di Chat persistente
 
È possibile utilizzare la pagina Criteri di **Persistent Chat** del gruppo di **Persistent Chat** per gestire i criteri a livello globale, di pool, di sito o di utente, inclusa la configurazione del criterio globale predefinito e la creazione di uno o più criteri utente e sito aggiuntivi per la distribuzione. Se un utente è abilitato per il server Chat persistente in base ai criteri, l'ambiente del server Chat persistente verrà visualizzato nel client.
  
> [!NOTE]
> Nella topologia, i criteri del sito del server Chat persistente si applicano a livello globale, per pool di utenti, per sito dell'utente o per utente. 
  
Il criterio globale viene creato automaticamente quando si distribuisce il server Chat persistente e può essere configurato, ma non eliminato. Poiché il criterio globale si applica a tutti gli utenti, non è necessario impostarlo per utente.
  
È possibile creare e configurare più criteri sito e utente che, insieme al criterio globale, abilitano gli utenti per il server Chat persistente. I criteri del server Chat persistente del pool e del sito sostituiscono i criteri globali del server Chat persistente, ma solo per gli utenti del sito. I criteri utente hanno la priorità sia sul criterio globale che sui criteri pool e sito per gli utenti a cui viene assegnato il criterio utente.
  
> [!NOTE]
> Per configurare e utilizzare il server Chat persistente, è innanzitutto necessario utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere [Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md) 
  
## <a name="tasks-that-you-can-perform"></a>Attività eseguibili

Nella pagina Criteri chat **persistente** è possibile eseguire le attività seguenti: abilitare e gestire i criteri del server Chat persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Per configurare i criteri globali per Persistent Chat

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Nel Pannello di controllo di Skype for Business Server fare clic su **Chat persistente** e quindi su **Criteri chat persistente.**
    
4. Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.
    
   - In **Descrizione** specificare i dettagli relativi ai criteri utente, ad esempio Criteri globali per _centralSiteName._
    
   - Per controllare Persistent Chat per tutti i siti e gli utenti non controllati in modo specifico tramite criteri sito o utente, selezionare o deselezionare la casella di controllo Abilita **Persistent Chat.**
    
6. Fare clic su **Commit**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Per creare criteri di Persistent Chat per un sito

Per ogni sito distribuito, è possibile creare criteri di Persistent Chat specifici del sito.
  
La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.
    
6. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".
    
   - Per controllare Persistent Chat per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat**.
    
7. Fare clic su **Commit**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Per creare criteri utente per Persistent Chat

Nel Pannello di controllo di Skype for Business Server definisci i criteri utente che possono essere assegnati agli utenti in **Utenti.**
  
I criteri utente hanno la precedenza sui criteri globali e di sito, ma solo per gli utenti specifici a cui tali criteri utente sono assegnati.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo criterio utente.
    
   - In **Descrizione** fornire informazioni dettagliate sui criteri utente, ad esempio i criteri di Persistent Chat per un utente specifico.
    
   - Per controllare Persistent Chat per tutti gli utenti non controllati in modo specifico tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat.**
    
6. Fare clic su **Commit**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Per applicare un criterio utente di Persistent Chat a un account utente

Se un utente è stato abilitato per Skype for Business, è possibile applicare i criteri appropriati a utenti specifici per abilitarli o disabilitarli per il server Chat persistente.
  
Utilizzare la procedura descritta in questo argomento per applicare un criterio utente di Persistent Chat creato in precedenza a uno o più account utente o gruppi di utenti.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.
    
4. Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.
    
5. In **Modifica utente di Lync Server** in Criteri di Chat **persistente** selezionare il criterio utente di Persistent Chat che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano il criterio effettivo predefinito. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

