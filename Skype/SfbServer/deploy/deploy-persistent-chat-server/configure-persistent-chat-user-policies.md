---
title: Configurare i criteri utente di Persistent Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: "Riepilogo: leggere questo argomento per informazioni su come creare criteri utente iniziali per il server Chat persistente in Skype for Business Server 2015. I criteri utente di Persistent Chat determinano se agli utenti è consentito o meno l'accesso alle chat room."
ms.openlocfilehash: c77782ed1aeef1b7696ab7b00b5bbfcc9c00f421
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778896"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurare i criteri utente di Persistent Chat in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come creare criteri utente iniziali per il server Chat persistente in Skype for Business Server 2015. I criteri utente di Persistent Chat determinano se agli utenti è consentito o meno l'accesso alle chat room.
  
È possibile gestire i criteri utente del server Chat persistente ai livelli seguenti: globale, sito o utente. Inizialmente, si configura il criterio globale per abilitare le impostazioni di Persistent Chat per tutti gli utenti della distribuzione e quindi si creano criteri utente e sito aggiuntivi per controllare se Persistent Chat è attivata per utenti e siti specifici.
  
In questa sezione sono contenute le seguenti sezioni:
  
- Configurare il criterio globale
    
- Creare criteri sito
    
- Creare criteri utente
    
- Applicare un criterio a un utente o a un gruppo di utenti
    
> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurare il criterio globale

Per configurare il criterio globale:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Nel Skype for Business Server di controllo fare clic su **Persistent Chat** e quindi su Criteri **chat persistente.**
    
4. Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti: 
    
   - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.
    
   - In **Descrizione** fornire informazioni dettagliate sui criteri utente, ad esempio Criteri globali per _centralSiteName._
    
   - Per controllare Persistent Chat per tutti i siti e gli utenti non controllati in modo specifico tramite un criterio sito o un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat.**
    
6. Fare clic su **Commit**.
    
## <a name="create-a-site-policy"></a>Creare criteri sito

Per ogni sito distribuito, è possibile creare criteri di Persistent Chat specifici del sito. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Per creare un criterio sito:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.
    
6. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".
    
   - Per controllare Persistent Chat per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat**.
    
7. Fare clic su **Commit**.
    
## <a name="create-a-user-policy"></a>Creare criteri utente

È possibile creare criteri specifici dell'utente che sostituiscono i criteri globali e gli eventuali criteri del sito a cui appartiene l'utente. Per creare un criterio utente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo criterio utente.
    
   - In **Descrizione** fornire informazioni dettagliate sul criterio utente, ad esempio criteri di Persistent Chat per un utente specifico.
    
   - Per controllare Persistent Chat per tutti gli utenti non controllati in modo specifico tramite un criterio utente, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat.**
    
6. Fare clic su **Commit**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Applicare un criterio a un account utente

Dopo aver creato i criteri, è possibile applicarli a un account utente nel modo seguente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.
    
4. Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.
    
5. In **Modifica Skype for Business Server utente** in Criteri chat **persistente** selezionare il criterio utente di Persistent Chat che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano il criterio effettivo predefinito. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

