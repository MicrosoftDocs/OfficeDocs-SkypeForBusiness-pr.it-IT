---
title: Configurare i criteri utente di chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Riepilogo: leggere questo argomento per informazioni su come creare criteri utente iniziali per il server Chat persistente in Skype for Business Server 2015. I criteri utente di chat persistente determinano se gli utenti possono accedere alle chat room o meno.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802116"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurare i criteri utente di chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come creare criteri utente iniziali per il server Chat persistente in Skype for Business Server 2015. I criteri utente di chat persistente determinano se gli utenti possono accedere alle chat room o meno.
  
È possibile gestire i criteri utente del server Chat persistente ai livelli seguenti: globale, sito o utente. Inizialmente, è possibile configurare i criteri globali per abilitare le impostazioni della chat persistente per tutti gli utenti nella distribuzione e quindi creare criteri di utente e sito aggiuntivi per controllare se la chat persistente è attivata per utenti e siti specifici.
  
In questa sezione sono contenute le seguenti sezioni:
  
- Configurare il criterio globale
    
- Creare un criterio sito
    
- Creare un criterio utente
    
- Applicare un criterio a un utente o a un gruppo di utenti
    
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurare il criterio globale

Per configurare i criteri globali:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Nel pannello di controllo di Skype for Business Server, fare clic su **Persistent Chat** e quindi su **criteri di chat persistente**.
    
4. Fare clic su **Globale** nell'elenco di criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Criteri Persistent Chat - Globale** eseguire le operazioni seguenti: 
    
   - In **Nome** specificare un nuovo nome per i criteri globali, se non si desidera usare il nome predefinito Globale.
    
   - In **Descrizione** fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri globali per  _NomeSitoCentrale "_.
    
   - Per controllare la chat persistente per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="create-a-site-policy"></a>Creare un criterio sito

Per ogni sito distribuito, è possibile creare un criterio di chat persistente specifico del sito. La configurazione nel criterio sito ha la priorità sul criterio globale, ma solo per il sito specifico a cui si applica il criterio sito. Per creare un criterio sito:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri sito**.
    
5. In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.
    
6. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per i nuovi criteri di sito, ad esempio Redmond.
    
   - In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri di sito, ad esempio "Criteri chat room per Redmond".
    
   - Per controllare Persistent Chat per tutti i siti non controllati in modo specifico tramite criteri di sito, selezionare o deselezionare la casella di controllo **Abilita Persistent Chat**.
    
7. Fare clic su **Commit**.
    
## <a name="create-a-user-policy"></a>Creare un criterio utente

È possibile creare criteri specifici dell'utente che eseguono l'override dei criteri globali e di tutti i criteri di sito a cui appartiene l'utente. Per creare un criterio utente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Criteri Persistent Chat**.
    
4. Fare clic su **Nuovo** e quindi su **Criteri utente**.
    
5. In **Nuovi criteri Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo criterio utente.
    
   - In **Descrizione** fornire informazioni dettagliate sugli elementi del criterio utente, ad esempio criteri di chat persistente per utenti specifici.
    
   - Per controllare la chat persistente per tutti gli utenti non controllati in modo specifico tramite criteri utente, selezionare o deselezionare la casella di controllo **Abilita Chat persistente** .
    
6. Fare clic su **Commit**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Applicare un criterio a un account utente

Dopo aver creato i criteri, è possibile applicarli a un account utente come indicato di seguito:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.
    
4. Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.
    
5. In **modifica utente di Skype for Business Server** in **criteri di Persistent Chat** Selezionare il criterio utente di chat persistente che si desidera applicare.
    
    > [!NOTE]
    > Le **\<Automatic\>** impostazioni applicano il criterio effettivo predefinito. Queste impostazioni vengono applicate automaticamente dal server.
  
6. Fare clic su **Commit**.
    

