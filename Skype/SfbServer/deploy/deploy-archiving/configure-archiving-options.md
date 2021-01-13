---
title: Configurare le opzioni di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: "Riepilogo: leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziale per Skype for Business Server. Inizialmente sono state configurate le configurazioni di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare le configurazioni dopo la distribuzione."
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815536"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a>Configurare le opzioni di archiviazione per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziale per Skype for Business Server. Inizialmente sono state configurate le configurazioni di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare le configurazioni dopo la distribuzione.
  
Per configurare le configurazioni di archiviazione iniziali, è possibile utilizzare il pannello di controllo di Skype for Business Server per specificare quanto segue:
  
- Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server
    
- Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico
    
- Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico
    
Sarà necessario configurare le opzioni per gli elementi seguenti:
  
- Se abilitare o disabilitare l'archiviazione
    
- Se archiviare le sessioni di messaggistica istantanea
    
- Se archiviare le sessioni di Web Conferencing
    
- Se bloccare l'attività quando l'archiviazione non è disponibile
    
- Se utilizzare l'integrazione di Exchange
    
- Informazioni su come configurare l'eliminazione e l'esportazione dei dati
    
> [!NOTE]
> Prima di abilitare l'archiviazione, è necessario specificare tutte le opzioni appropriate. 
  
Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione tramite il pannello di controllo o utilizzando Windows PowerShell, vedere [gestire le opzioni di archiviazione in Skype for Business Server](../../manage/archiving/options.md).
  
## <a name="configure-global-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello globale

Quando si aggiunge l'archiviazione alla topologia e si pubblica la topologia, in Skype for Business Server viene creata una configurazione globale per l'archiviazione. Per impostazione predefinita, nessuna opzione di archiviazione è abilitata nella configurazione globale. La configurazione globale controlla le opzioni abilitate per l'intera distribuzione, a meno che non si impostino configurazioni a livello di sito o di pool, le quali hanno la priorità sulla configurazione globale.
  
Per configurare le opzioni di archiviazione a livello globale:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **Globale**, su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica Impostazione di archiviazione - Globale** selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazione di archiviazione**:
    
   - **Disabilita archiviazione**
    
   - **Archivia sessioni di messaggistica istantanea**
    
   - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
6. Anche nella pagina **Modifica impostazione di archiviazione-globale** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
   - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
7. Fare clic su **Commit**.
    
## <a name="configure-site-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello di sito

È possibile specificare le opzioni di archiviazione per un sito specifico. Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per il sito specificato. 
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione sito**.
    
5. In **Seleziona un sito** selezionare il sito da configurare per l'archiviazione.
    
6. In **Nuova impostazione di archiviazione** eseguire una delle operazioni seguenti nella casella di riepilogo a discesa **Impostazione di archiviazione**:
    
   - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.
    
   - Per abilitare l'archiviazione per le conferenze e le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.
    
   - Per disabilitare l'archiviazione dei criteri, fare clic su **Disabilita archiviazione**.
    
7. Sempre in **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
   - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
8. Fare clic su **Commit**.
    
## <a name="configure-pool-level-archiving-options"></a>Configurare le opzioni di archiviazione a livello di pool

È possibile specificare le opzioni di archiviazione per un pool specifico. La configurazione di un pool ha la priorità sulla configurazione globale e sulla configurazione del sito, ma solo per il pool specificato nella relativa configurazione.
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione pool**.
    
5. In **Seleziona un servizio** selezionare il pool da configurare per l'archiviazione.
    
6. In **Nuova impostazione di archiviazione** selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazione di archiviazione**:
    
   - **Disabilita archiviazione**
    
   - **Archivia sessioni di messaggistica istantanea**
    
   - **Archivia sessioni di messaggistica istantanea e Web Conferencing**
    
7. Sempre nella pagina **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:
    
   - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
   - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
   - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
   - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
   - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
8. Fare clic su **Commit**.
    

