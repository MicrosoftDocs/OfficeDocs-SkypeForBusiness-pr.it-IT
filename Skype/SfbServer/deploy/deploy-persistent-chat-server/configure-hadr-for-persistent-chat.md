---
title: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 81fcc37ecbdf513decd89481c8a651404d91294a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795527"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015.
  
Skype for Business Server supporta più modalità di elevata disponibilità per i server back-end, incluso il mirroring del database. Per altre informazioni, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> I gruppi di disponibilità AlwaysOn non sono supportati con i server di chat permanenti. 

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.
  
Prima di configurare la distribuzione della chat persistente per l'elevata disponibilità e il ripristino di emergenza, assicurarsi di avere familiarità con i concetti in [piano per l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La soluzione di ripristino di emergenza per il server di chat persistente descritta in questi argomenti si basa su un pool di server di chat persistente allungato. Il contenuto della pianificazione descrive i requisiti delle risorse e la topologia del pool allungata che consente la disponibilità elevata e il ripristino di emergenza per il server di chat persistente, incluso l'uso del mirroring di SQL Server per l'elevata disponibilità e la distribuzione del log ripristino di emergenza.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usare generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza

In Generatore di topologie eseguire la procedura seguente per configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente.
  
1. Aggiungere i database mirror e il database secondario del log shipping di SQL Server Store.
    
2. Modificare le proprietà del servizio server di chat persistente in:
    
    un. Abilitare il mirroring per il database primario.
    
    b. Aggiungere il mirror principale di SQL Server Store.
    
    c. Abilitare il database di log shipping di SQL Server.
    
    3D. Aggiungere l'archivio SQL Server log shipping secondario di SQL Server.
    
    e. Aggiungere il mirror di SQL Server Store per il database secondario.
    
    f. Pubblicare la topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurare la distribuzione del log di SQL Server per il database primario del server Chat persistente

In SQL Server Management Studio connettersi all'istanza del database di log shipping secondario del server di chat persistente e verificare che SQL Server Agent sia in uso. Quindi Connetti all'istanza del database primario della chat persistente ed Esegui i passaggi seguenti:
  
1. Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.
    
2. In **selezionare una pagina**fare clic su **distribuzione log transazioni**.
    
3. Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .
    
4. In **backup del log delle transazioni**fare clic su **impostazioni di backup**.
    
5. Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
6. Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella casella **se la cartella di backup si trova nel server principale, digitare un percorso locale alla cartella (esempio: c:\backup)** . Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.
    
    > [!IMPORTANT]
    > Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella. 
  
7. Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.
    
8. Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio.
    
9. In **compressione**selezionare **Usa l'impostazione predefinita del server**e quindi fare clic su **OK**.
    
10. In **istanze server secondarie e database**fare clic su **Aggiungi**.
    
11. Fare clic su **Connetti** e Connetti all'istanza di SQL Server configurata come server secondario.
    
12. Nella casella **database secondario** selezionare il database **MGC** dall'elenco.
    
13. Nella scheda **Inizializza database secondario** scegliere l'opzione **Sì, generare un backup completo del database principale e ripristinarlo nel database secondario (e creare il database secondario se non esiste)**.
    
14. Nella casella **cartella di destinazione per i file copiati** della scheda **copia file** Digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni. Questa cartella si trova spesso nel server secondario.
    
15. Nota la pianificazione della copia elencata nella casella **pianificazione** in **copia processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent in modo obbligatorio. Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.
    
16. Nella scheda **Ripristina** , in **stato del database durante il ripristino dei backup**, scegliere l'opzione **Nessuna modalità di recupero** .
    
17. In **delay Restoring backups almeno:** selezionare **0 minuti**.
    
18. Scegliere una soglia di avviso in **avviso se non si verifica alcun ripristino all'interno**.
    
19. Esaminare la pianificazione di ripristino elencata nella casella **pianificazione** in **Ripristina processo**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**, regolare la pianificazione di SQL Server Agent come richiesto e fare clic su **OK**. Questa programmazione deve essere approssimativamente uguale alla programmazione di backup.
    
20. Nella finestra di dialogo **Proprietà database** fare clic su **OK** per avviare il processo di configurazione.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurare la distribuzione del log di SQL Server tra lo specchio principale e il database secondario

Eseguire la procedura seguente per continuare il log shipping se il database principale della chat persistente non viene superato nel database mirror.
  
1. Eseguire manualmente il failover del database principale della chat persistente in mirror. Questa operazione viene eseguita usando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .
    
2. In SQL Server Management Studio connettersi all'istanza del mirror del server di chat persistente principale.
    
3. Verificare che l'agente SQL Server sia in uso.
    
4. Fare clic con il pulsante destro del mouse sul database di MGC e quindi scegliere **Proprietà**.
    
5. In **selezionare una pagina**fare clic su **distribuzione log transazioni**.
    
6. Selezionare la casella **di controllo Abilita come database primario in una configurazione di distribuzione del log** .
    
7. In **backup del log delle transazioni**fare clic su **impostazioni di backup**.
    
8. Nella casella **percorso di rete della cartella di backup** Digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
9. Se la cartella di backup si trova nel server principale, digitare il percorso locale della cartella di backup nella finestra di dialogo **se la cartella di backup si trova nel server principale, digitare un percorso locale nella casella della cartella** . Se la cartella di backup non si trova nel server principale, è possibile lasciarla vuota.
    
    > [!IMPORTANT]
    > Se l'account del servizio SQL Server nel server primario viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server principale e specificare un percorso locale per la cartella. 
  
10. Configurare i **file di eliminazione più vecchi e di** **avviso se non si verifica alcun backup all'interno** dei parametri.
    
11. Esaminare la pianificazione del backup elencata nella casella **pianificazione** in **processo di backup**. Per personalizzare la pianificazione per l'installazione, fare clic su **pianificazione**e regolare la pianificazione di SQL Server Agent, se necessario.
    
    > [!IMPORTANT]
    > Usa le stesse impostazioni usate per il database primario. 
  
12. In **compressione**selezionare **Usa l'impostazione predefinita del server**e fare clic su **OK**.
    
13. In **istanze server secondarie e database**fare clic su **Aggiungi**.
    
14. Fare clic su **Connetti**e connettersi all'istanza di SQL Server configurata come server secondario.
    
15. Nella casella **database secondario** selezionare il database **MGC** dall'elenco.
    
16. Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato**.
    
17. Nella scheda **copia file** , nella **cartella di destinazione per i file copiati**, digitare il percorso della cartella in cui devono essere copiati i backup dei log delle transazioni e fare clic su **OK**. Questa cartella si trova spesso nel server secondario.
    
18. Aprire l'elenco a discesa **configurazione script** e selezionare **configurazione script nella finestra nuova query**.
    
19. Nella finestra nuova query, in **Proprietà database**, fare clic su **OK** per avviare il processo di configurazione.
    
20. Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga:-- \* \* \* \* \* \* end: script da eseguire \* \* \* \* \* \*in primo piano:.
    
    > [!IMPORTANT]
    > L'esecuzione manuale di questo script è necessaria perché in SQL Server Management Studio non è supportato più database primari in una configurazione di log shipping di SQL Server. 
  
21. Selezionare **Annulla** per chiudere il pannello di configurazione del file di log shipping e stabilire una configurazione di lavoro che implementi correttamente la spedizione del file di log sia per il database primario che per il mirroring (in caso di failover).
    
22. Non eseguire manualmente il backup del database principale della chat persistente. Questa operazione viene eseguita usando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover** .
    

