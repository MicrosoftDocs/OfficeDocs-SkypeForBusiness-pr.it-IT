---
title: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 10d9e2eb76873cedc82daea817a732b8feb379da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802136"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.
  
Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring del database. Per ulteriori informazioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.
  
Prima di configurare la distribuzione di chat persistente per la disponibilità elevata e il ripristino di emergenza, accertarsi di conoscere i concetti in [piano per la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La soluzione di ripristino di emergenza per il server Chat persistente descritta in questi argomenti è basata su un pool di server Chat persistente esteso. Il contenuto di pianificazione descrive i requisiti delle risorse e la topologia del pool esteso che consente la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, incluso l'utilizzo del mirroring di SQL Server per la disponibilità elevata e il log shipping di SQL Server per il ripristino di emergenza.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Utilizzo di generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza

All'interno di generatore di topologie, eseguire la procedura seguente per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.
  
1. Aggiungere i database mirror e gli archivi SQL Server del database secondario di log shipping.
    
2. Modificare le proprietà del servizio del server Chat persistente in:
    
    a. Abilitare il mirroring per il database primario.
    
    b. Aggiungere l'archivio SQL Server mirror primario.
    
    c. Abilitare il database di log shipping di SQL Server.
    
    d. Aggiungere l'archivio SQL Server secondario di log shipping di SQL Server.
    
    e. Aggiungere il mirror dell'archivio SQL Server per il database secondario.
    
    f. Pubblicare la topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurare il log shipping di SQL Server per il database primario del server Chat persistente

Se si utilizza SQL Server Management Studio, connettersi all'istanza del database secondario di log shipping del server di chat persistente e verificare che SQL Server Agent sia in esecuzione. Connettersi quindi all'istanza del database primario di Persistent Chat ed eseguire le operazioni seguenti:
  
1. Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.
    
2. In **Seleziona una pagina** fare clic su **log shipping delle transazioni**.
    
3. Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .
    
4. In **backup dei log delle transazioni** fare clic su **impostazioni di backup**.
    
5. Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
6. Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare un percorso locale per la cartella (ad esempio: c:\backup)** . Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.
    
    > [!IMPORTANT]
    > Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella. 
  
7. Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.
    
8. Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent in base alle esigenze.
    
9. In **compressione** selezionare **utilizza l'impostazione predefinita del server** e quindi fare clic su **OK**.
    
10. In **istanze e database secondari del server**, fare clic su **Aggiungi**.
    
11. Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.
    
12. Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.
    
13. Nella scheda **Inizializza database secondario** selezionare l'opzione **Sì, generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.
    
14. Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni. Questa cartella si trova spesso nel server secondario.
    
15. Tenere presente la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent in base alle esigenze. Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.
    
16. Nella scheda **Ripristina** , in **stato di database durante il ripristino dei backup**, scegliere l'opzione **modalità No Recovery** .
    
17. In **delay Restoring backups almeno:**, selezionare **0 minuti**.
    
18. Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.
    
19. Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**. Per personalizzare la pianificazione dell'installazione, fare clic su **pianificazione**, modificare la pianificazione di SQL Server Agent in base alle esigenze e quindi fare clic su **OK**. Questa pianificazione deve essere approssimativamente uguale alla pianificazione del backup.
    
20. Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurare il log shipping di SQL Server tra il mirror primario e il database secondario

Eseguire la procedura seguente per continuare il log shipping se il database di Persistent Chat primario non viene eseguito nel database mirror.
  
1. Eseguire manualmente il failover del database di Persistent Chat principale nel mirror. A tale scopo, è possibile utilizzare Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .
    
2. Se si utilizza SQL Server Management Studio, connettersi all'istanza del mirror del server di Persistent Chat principale.
    
3. Verificare che SQL Server Agent sia in esecuzione.
    
4. Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.
    
5. In **Seleziona una pagina** fare clic su **log shipping delle transazioni**.
    
6. Selezionare la casella **di controllo Abilita come database primario in una configurazione per il log shipping** .
    
7. In **backup dei log delle transazioni** fare clic su **impostazioni di backup**.
    
8. Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
9. Se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova sul server primario, digitare il percorso locale della cartella** . Se la cartella di backup non è presente nel server primario, è possibile lasciare vuota questa casella.
    
    > [!IMPORTANT]
    > Se l'account di servizio di SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella. 
  
10. Configurare i **file di eliminazione precedenti e di** **avviso se nessun backup viene eseguito all'interno** dei parametri.
    
11. Esaminare la pianificazione di backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione** e modificare la pianificazione di SQL Server Agent, in base alle esigenze.
    
    > [!IMPORTANT]
    > Utilizzare le stesse impostazioni utilizzate per il database primario. 
  
12. In **compressione** selezionare **utilizza l'impostazione predefinita del server** e fare clic su **OK**.
    
13. In **istanze e database secondari del server**, fare clic su **Aggiungi**.
    
14. Fare clic su **Connetti** e connettersi all'istanza di SQL Server configurata come server secondario.
    
15. Nella casella **database secondario** selezionare il database di **MGC** dall'elenco.
    
16. Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.
    
17. Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni e fare clic su **OK**. Questa cartella si trova spesso nel server secondario.
    
18. Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella nuova finestra di query**.
    
19. Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.
    
20. Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire su Primary: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > L'esecuzione manuale di questo script è necessaria perché SQL Server Management Studio non supporta più database primari in una configurazione di log shipping di SQL Server. 
  
21. Selezionare **Annulla** per chiudere il pannello di configurazione per la distribuzione dei file di registro e per stabilire una configurazione funzionante che implementi correttamente il file di log shipping sia per il database primario che per quello con mirroring (in caso di failover).
    
22. Non eseguire manualmente il backup del database primario di chat persistente sul primario. A tale scopo, è possibile utilizzare la shell di gestione di Skype for Business Server e il cmdlet **Invoke-CsDatabaseFailover** .
    

