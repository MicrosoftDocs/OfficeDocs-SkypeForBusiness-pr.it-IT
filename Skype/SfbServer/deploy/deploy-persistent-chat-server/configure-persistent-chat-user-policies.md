---
title: Configurare i criteri utente di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Riepilogo: leggere questo argomento per informazioni su come creare criteri utente iniziali per il server di chat persistente in Skype for Business Server 2015. I criteri utente della chat persistente determinano se gli utenti sono autorizzati ad accedere alle chat room.'
ms.openlocfilehash: 3f2a55f3a411fc3020ebe9af57d456f00dd74ef4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195944"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurare i criteri utente di Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni su come creare criteri utente iniziali per il server di chat persistente in Skype for Business Server 2015. I criteri utente della chat persistente determinano se gli utenti sono autorizzati ad accedere alle chat room.
  
È possibile gestire i criteri degli utenti del server di chat persistente ai livelli seguenti: globale, sito o utente. Inizialmente, configuri il criterio globale per abilitare le impostazioni della chat persistente per tutti gli utenti della distribuzione e quindi crei altri criteri per l'utente e il sito per controllare se la chat persistente è attivata per utenti e siti specifici.
  
Questo argomento contiene le sezioni seguenti:
  
- Configurare il criterio globale
    
- Creare un criterio per il sito
    
- Creare un criterio utente
    
- Applicare un criterio a un utente o a un gruppo di utenti
    
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurare il criterio globale

Per configurare il criterio globale:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nel pannello di controllo di Skype for Business Server fare clic su **chat persistente**e quindi su **criteri di chat permanenti**.
    
4. Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri Chat persistente- Globale** eseguire le operazioni seguenti: 
    
   - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera utilizzare il nome predefinito Globale.
    
   - In **Descrizione**specificare i dettagli relativi al criterio utente (ad esempio, criteri globali per _centralSiteName_).
    
   - Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="create-a-site-policy"></a>Creare un criterio per il sito

Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito. La configurazione dei criteri sito ha la precedenza sui criteri globali, ma solo per il sito specifico a cui i criteri si riferiscono. Per creare un criterio per il sito:
  
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
    
## <a name="create-a-user-policy"></a>Creare un criterio utente

Puoi creare criteri specifici dell'utente che eseguono l'override dei criteri globali e di tutti i criteri del sito a cui appartiene l'utente. Per creare un criterio utente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Criteri di Chat persistente**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri Chat persistente** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo criterio utente.
    
   - In **Descrizione**, fornisci i dettagli sui criteri degli utenti, ad esempio i criteri di chat persistenti per un utente specifico.
    
   - Per controllare la chat persistente per tutti gli utenti che non sono specificamente controllati tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Applicare un criterio a un account utente

Dopo aver creato i criteri, è possibile applicarli a un account utente come indicato di seguito:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, eseguire l'accesso a qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.
    
4. Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **modifica utenti di Skype for Business Server** in **criteri di chat persistenti**Selezionare il criterio utente per la chat persistente che si vuole applicare.
    
    > [!NOTE]
    > Le ** \<impostazioni\> automatiche** applicano i criteri effettivi predefiniti. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

