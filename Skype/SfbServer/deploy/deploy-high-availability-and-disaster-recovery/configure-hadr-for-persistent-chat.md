---
title: 'Business Server 2015: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente'
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
description: Informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.
ms.openlocfilehash: 6579d9b6dfa8a2c9bed237cf98685137f229860a7fe4f338f3d994230516d353
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298586"
---
# <a name="business-server-2015-configure-high-availability-and-disaster-recovery-for-persistent-chat-server"></a>Business Server 2015: Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015.
  
Skype for Business Server supporta più modalità di disponibilità elevata per i server back-end, incluso il mirroring del database. Per ulteriori informazioni, vedere [Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
> [!NOTE]
> I gruppi di disponibilità AlwaysOn non sono supportati con i server Chat persistente. 
  
Prima di configurare la distribuzione di Persistent Chat per la disponibilità elevata e il ripristino di emergenza, assicurarsi di avere familiarità con i concetti descritti in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) La soluzione di ripristino di emergenza per il server Chat persistente descritta in questi argomenti si basa su un pool di server Chat persistente estesa. Il contenuto della pianificazione descrive i requisiti delle risorse e la topologia di pool estesa che consente la disponibilità elevata e il ripristino di emergenza per il server Chat persistente, incluso l'utilizzo del mirroring SQL Server per la disponibilità elevata e il log shipping di SQL Server per il ripristino di emergenza.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Utilizzare Generatore di topologie per configurare la disponibilità elevata e il ripristino di emergenza

In Generatore di topologie eseguire la procedura seguente per configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente.
  
1. Aggiungere i database mirror e il database secondario di log shipping SQL Server archivi.
    
2. Modificare le proprietà del servizio del server Chat persistente in:
    
    a. Abilitare il mirroring per il database primario.
    
    b. Aggiungere l'archivio SQL Server mirror primario.
    
    c. Abilitare il SQL Server log shipping.
    
    d. Aggiungere il SQL Server log shipping secondario SQL Server archivio.
    
    e. Aggiungere il SQL Server mirror dell'archivio per il database secondario.
    
    f. Pubblicare la topologia.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurare il SQL Server log shipping per il database primario del server Chat persistente

Utilizzando SQL Server Management Studio, connettersi all'istanza del database di log shipping secondario del server Chat persistente e verificare che SQL Server Agent sia in esecuzione. Connettersi quindi all'istanza del database principale di Persistent Chat ed eseguire la procedura seguente:
  
1. Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.
    
2. In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**
    
3. Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**
    
4. In **Backup del log delle transazioni** fare clic su Backup **Impostazioni**.
    
5. Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
6. Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel server principale, digitare un percorso locale della cartella **(ad esempio: c:\backup).** Se la cartella di backup non si trova nel server principale, è possibile lasciare vuota questa casella.
    
    > [!IMPORTANT]
    > Se l SQL Server account di servizio del server principale viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella. 
  
7. Configurare i **parametri Delete files older than e** Alert if no backup occurs **within** parameters.
    
8. Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.** Per personalizzare la pianificazione per l'installazione, fare clic **su Pianificazione** e modificare la pianificazione SQL Server agent in base alle esigenze.
    
9. In **Compressione** selezionare **Usa l'impostazione predefinita del server** e quindi fare clic su **OK.**
    
10. In **Istanze e database del server secondario** fare clic su **Aggiungi.**
    
11. Fare **Connessione** e connettersi all'istanza di SQL Server che è stato configurato come server secondario.
    
12. Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.
    
13. Nella scheda **Inizializza database** secondario scegliere **l'opzione Sì,** generare un backup completo del database primario e ripristinarlo nel database secondario (e creare il database secondario se non esiste) .
    
14. Nella casella **Cartella** di  destinazione per i file copiati della scheda Copia file digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni. Questa cartella si trova spesso nel server secondario.
    
15. Si noti la pianificazione della copia elencata nella **casella Pianificazione** in **Copia processo.** Per personalizzare la pianificazione per l'installazione, fare clic **su Pianificazione** e modificare la pianificazione SQL Server agent in base alle esigenze. Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.
    
16. Nella scheda **Ripristino,** in **Stato database durante il ripristino dei backup,** scegliere l'opzione Nessuna modalità **di** ripristino.
    
17. In **Ritardare il ripristino dei backup almeno:** selezionare **0 minuti.**
    
18. Scegliere una soglia di avviso in **Avviso se non viene eseguito alcun ripristino all'interno di**.
    
19. Esaminare la pianificazione del ripristino elencata nella **casella Pianificazione** in Processo **di ripristino**. Per personalizzare la pianificazione per l'installazione, fare clic su **Pianificazione,** modificare la pianificazione SQL Server Agent in base alle esigenze e fare clic su **OK.** Questa pianificazione deve essere approssimativamente la stessa della pianificazione di backup.
    
20. Nella finestra **di dialogo Proprietà** database fare clic su **OK** per avviare il processo di configurazione.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurare il SQL Server log shipping tra il mirror primario e il database secondario

Eseguire la procedura seguente per continuare il log shipping se viene eseguito il backup del database di Persistent Chat primario nel relativo database mirror.
  
1. Eseguire manualmente il failover del database principale di Persistent Chat nel mirror. Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**
    
2. Utilizzando il SQL Server Management Studio, connettersi all'istanza mirror del server Chat persistente principale.
    
3. Verificare che l'SQL Server agent sia in esecuzione.
    
4. Fare clic con il pulsante destro del mouse sul database mgc e quindi scegliere **Proprietà**.
    
5. In **Selezionare una pagina fare** clic su Log shipping delle **transazioni.**
    
6. Selezionare la **casella di controllo Abilita come database primario in una configurazione di log shipping.**
    
7. In **Backup del log delle transazioni** fare clic su Backup **Impostazioni**.
    
8. Nella casella **Percorso di rete della cartella di backup** digitare il percorso di rete della condivisione creata per la cartella di backup del log delle transazioni.
    
9. Se la cartella di backup si trova nel server primario, digitare il percorso locale della cartella di backup nella casella Se la cartella di backup si trova nel **server principale,** digitare un percorso locale per la cartella. Se la cartella di backup non si trova nel server principale, è possibile lasciare vuota questa casella.
    
    > [!IMPORTANT]
    > Se l SQL Server account di servizio del server principale viene eseguito con l'account di sistema locale, è necessario creare la cartella di backup nel server primario e specificare un percorso locale per tale cartella. 
  
10. Configurare i **parametri Delete files older than e** Alert if no backup occurs **within** parameters.
    
11. Esaminare la pianificazione del backup elencata nella casella **Pianificazione** in **Processo di backup.** Per personalizzare la pianificazione per l'installazione, fare clic **su Pianificazione** e modificare la pianificazione SQL Server Agent, in base alle esigenze.
    
    > [!IMPORTANT]
    > Utilizzare le stesse impostazioni utilizzate per il database primario. 
  
12. In **Compressione** selezionare **Usa l'impostazione predefinita del server** e fare clic su **OK.**
    
13. In **Istanze e database del server secondario** fare clic su **Aggiungi.**
    
14. Fare **Connessione** e connettersi all'istanza di SQL Server configurata come server secondario.
    
15. Nella casella **Database secondario** selezionare il database **mgc** dall'elenco.
    
16. Nella scheda **Inizializza database secondario** selezionare l'opzione **No, il database secondario viene inizializzato.**
    
17. Nella scheda **Copia file,** in **Cartella** di destinazione per i file copiati, digitare il percorso della cartella in cui devono essere copiati i backup dei registri delle transazioni e fare clic su **OK.** Questa cartella si trova spesso nel server secondario.
    
18. Aprire **l'elenco a** discesa Configurazione script e selezionare **Configurazione script in Nuova finestra query.**
    
19. Nella finestra della nuova query, in **Proprietà database,** fare clic su **OK** per avviare il processo di configurazione.
    
20. Selezionare ed eseguire la prima metà della query (vedere il passaggio 18) fino alla riga: -- \* \* \* \* \* \* End: Script da eseguire in Primary: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > L'esecuzione manuale di questo script è necessaria perché SQL Server Management Studio non supporta più database primari in una SQL Server log shipping. 
  
21. Selezionare **Annulla** per chiudere il pannello di configurazione Log File shipping e stabilire un'installazione funzionante che implementi correttamente il file shipping di log sia per il database primario che per il database con mirroring (in caso di failover).
    
22. Eseguire manualmente il fail back del database di Persistent Chat primario nel database primario. Questa operazione viene eseguita utilizzando Skype for Business Server Management Shell e il cmdlet **Invoke-CsDatabaseFailover.**
    

