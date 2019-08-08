---
title: Configurare le opzioni di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: "Riepilogo: leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziali per Skype for Business Server. È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione."
ms.openlocfilehash: 76611d5b475c66bc6546bfe1c340f729f281a4fb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234562"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurare le opzioni di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziali per Skype for Business Server. È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.
  
Per configurare le configurazioni di archiviazione iniziali, usare il pannello di controllo di Skype for Business Server per specificare quanto segue:
  
- Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico
    
Sarà necessario configurare le opzioni seguenti:
  
- Se abilitare o disabilitare l'archiviazione
    
- Se archiviare le sessioni di messaggistica istantanea
    
- Se archiviare le sessioni di Web Conferencing
    
- Se bloccare l'attività quando l'archiviazione non è disponibile
    
- Se usare l'integrazione di Exchange
    
- Come configurare l'eliminazione e l'esportazione dei dati
    
> [!NOTE]
> Devi specificare tutte le opzioni appropriate prima di abilitare l'archiviazione. 
  
Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione tramite il pannello di controllo o tramite Windows PowerShell, vedere [gestire le opzioni di archiviazione in Skype for Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello globale

Quando si aggiunge l'archiviazione alla topologia e si pubblica la topologia, Skype for Business Server crea una configurazione globale per l'archiviazione. Per impostazione predefinita, le opzioni di archiviazione non sono abilitate nella configurazione globale. La configurazione globale Controlla quali opzioni sono abilitate per l'intera distribuzione, a meno che non vengano configurate configurazioni del sito o del pool, che eseguono l'override della configurazione globale.
  
Per configurare le opzioni di archiviazione a livello globale:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **Modifica impostazioni di archiviazione-globale**, nell'elenco a discesa **Impostazioni archiviazione** Selezionare una delle opzioni di archiviazione seguenti:
    
   - **Disabilita archiviazione**
    
   - **Archivia sessioni di messaggistica istantanea**
    
   - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
6. Anche nell' **impostazione modifica archiviazione-pagina globale** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
   - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione**esportati.
    
7. Fare clic su **Commit**.
    
## <a name="configure-site-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello di sito

È possibile specificare le opzioni di archiviazione per un sito specifico. Una configurazione del sito sostituisce la configurazione globale, ma solo per il sito specificato nella configurazione del sito. 
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **configurazione sito**.
    
5. In **Seleziona un sito**selezionare il sito da configurare per l'archiviazione.
    
6. In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.
    
   - Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.
    
   - Per disabilitare l'archiviazione per il criterio, fare clic su **Disattiva archiviazione**.
    
7. Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
   - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione**esportati.
    
8. Fare clic su **Commit**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello di pool

È possibile specificare le opzioni di archiviazione per un pool specifico. La configurazione del pool sostituisce la configurazione globale e la configurazione del sito, ma solo per il pool specificato nella configurazione del pool.
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **Configurazione pool**.
    
5. In **Seleziona un servizio**selezionare il pool da configurare per l'archiviazione.
    
6. In **nuova impostazione archiviazione**selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazioni archiviazione** :
    
   - **Disabilita archiviazione**
    
   - **Archivia sessioni di messaggistica istantanea**
    
   - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
7. Anche nella pagina **nuova impostazione archiviazione** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .
    
   - Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione**esportati.
    
8. Fare clic su **Commit**.
    

