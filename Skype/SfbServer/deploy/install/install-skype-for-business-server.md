---
title: Installare Skype for Business Server nei server della topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: "Riepilogo: informazioni su come installare i componenti di sistema di Skype for Business Server in ogni server della topologia. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: 35ad1914dced8d8937de0f56a19c2709551a2893
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245806"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installare Skype for Business Server nei server della topologia
 
**Riepilogo:** Informazioni su come installare i componenti di sistema di Skype for Business Server in ogni server della topologia. Scaricare una versione di valutazione gratuita di Skype for Business Server dal [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Dopo aver caricato la topologia in Central Management store e Active Directory sa quali server eseguiranno i ruoli, è necessario installare il sistema Skype for Business Server in ognuno dei server della topologia. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5 come indicato nel diagramma. L'installazione di Skype for Business Server System è il passaggio 7 di 8.
  
![Diagramma di panoramica.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installare Skype for Business Server System

Dopo aver pubblicato una topologia, è possibile installare i componenti di Skype for Business Server in ogni server della topologia. Questa sezione illustra l'installazione di Skype for Business Server e la configurazione dei ruoli del server per il pool Front-end e i ruoli del server che sono collocati con i server front-end. Per installare e configurare i ruoli del server, eseguire la distribuzione guidata di Skype for Business Server in ogni computer in cui si sta installando un ruolo del server. La distribuzione guidata viene usata per completare tutti e quattro i passaggi di distribuzione, incluso l'installazione dell'archivio di configurazione locale, l'installazione dei server front-end, la configurazione di certificati e l'avvio dei servizi.
  
> [!IMPORTANT]
> È necessario usare generatore di topologia per completare e pubblicare la topologia prima di poter installare Skype for Business Server su server. 
  
> [!NOTE]
> Questa procedura deve essere completata per tutti i server della topologia. 
  
> [!CAUTION]
> Dopo aver installato Skype for Business Server in un front end server, la prima volta che si avviano i servizi, è necessario verificare che il servizio Windows Firewall sia in esecuzione nel server. 
  
> [!CAUTION]
> Prima di eseguire questa procedura, verificare di aver effettuato l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Se non è ancora stata eseguita la configurazione di Skype for Business Server su questo server, verrà richiesto di eseguire un'unità e un percorso per l'installazione. In questo caso, è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o se si hanno problemi di spazio. È possibile modificare il percorso della posizione di installazione per i file di Skype for Business Server nella finestra di dialogo **imposta** in una nuova unità disponibile. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, verranno distribuiti anche gli altri file di Skype for Business Server.
  
> [!IMPORTANT]
> Prima di iniziare l'installazione, verificare che Windows Server sia aggiornato tramite Windows Update. 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installare Skype for Business Server System

1. Inserire il supporto di installazione di Skype for Business Server. Se l'installazione non viene avviata automaticamente, fare doppio clic su **configurazione**.
    
2. Il supporto di installazione richiede l'esecuzione di Microsoft Visual C++. Verrà visualizzata una finestra di dialogo che chiede se si vuole installarla. Fare clic su **Sì.**
    
3. Esaminare attentamente il contratto di licenza e, se si è d'accordo, selezionare **Accetto i termini del contratto di licenza**e fare clic su **OK**. 
    
4. La configurazione intelligente è una funzionalità di Skype for Business Server in cui è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti da Microsoft Update (MU) durante il processo di installazione, come illustrato nella figura. Questo offre un'esperienza migliore assicurandosi di avere gli aggiornamenti più recenti per il prodotto. Fare clic su **Installa** per avviare l'installazione.
    
    > [!NOTE]
    > Molte organizzazioni hanno implementato Windows Server Update Services (WSUS) negli ambienti aziendali. WSUS consente agli amministratori di gestire in modo completo la distribuzione degli aggiornamenti rilasciati tramite Microsoft Update ai computer della rete. Come parte della versione di aggiornamento cumulativo 1, Skype for Business Server ha introdotto il supporto per la configurazione intelligente per l'utilizzo con WSUS. I clienti con WSUS che distribuiscono Skype for Business Server per la prima volta o l'aggiornamento dall'ambiente Lync Server 2013 usando la funzionalità di aggiornamento sul posto avranno la configurazione intelligente per il recupero degli aggiornamenti di Skype for Windows da WSUS anziché per il recupero degli aggiornamenti da MU. I clienti che vogliono usare la configurazione intelligente devono eseguire SmartSetupWithWSUS. PSQ in tutti i computer prima di eseguire Setup. exe. 
  
     ![Schermata di configurazione intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Nella pagina distribuzione guidata fare clic su **Installa o Aggiorna sistema di Skype for Business Server**.
    
6. Eseguire le procedure descritte nelle procedure seguenti, dopo averle completate, fare clic su **Esci** per chiudere la distribuzione guidata. Ripetere le procedure per ogni server front-end nel pool.
    
### <a name="step-1-install-local-configuration-store"></a>Passaggio 1: installare lo Store di configurazione locale

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto al **passaggio 1: installare l'archivio di configurazione locale**.
    
    > [!NOTE]
    > L'archivio di configurazione locale è una copia di sola lettura dell'Central Management store. In una distribuzione Standard Edition, l'Central Management Store viene creato usando una copia locale di SQL Server Express Edition nel server front-end. Questo problema si verifica quando si esegue la procedura per preparare il server First Standard Edition. In una distribuzione di Enterprise Edition viene creato l'archivio di gestione centralizzato quando si pubblica la topologia che include un pool di front-end Enterprise Edition. 
  
2. Nella pagina **Installa configurazione locale Store** verificare che sia selezionata l'opzione **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.
    
    SQL Server Express Edition è installato nel server locale. SQL Server Express Edition è obbligatorio per l'archivio di configurazione locale.
    
3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Passaggio 2: configurare o rimuovere componenti di Skype for Business Server

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto al **passaggio 2: configurare o rimuovere i componenti di Skype for Business Server**.
    
2. Nella pagina **configurare i componenti di Skype for Business Server** fare clic su **Avanti** per configurare i componenti come definiti nella topologia pubblicata.
    
3. Nella pagina **comandi in esecuzione** viene visualizzato un riepilogo dei comandi e delle informazioni di installazione Man mano che viene eseguita la configurazione. Al termine, è possibile usare l'elenco per selezionare un log da visualizzare e quindi fare clic su **Visualizza log**.
    
4. Quando è stata eseguita la configurazione dei componenti di Skype for Business Server e i registri sono stati esaminati in base alle esigenze, fare clic su **fine** per completare questo passaggio nell'installazione.
    
    > [!NOTE]
    > Riavviare il server se richiesto (che potrebbe verificarsi se l'esperienza desktop di Windows dovesse essere installata). Quando il computer viene eseguito il backup e l'esecuzione, è necessario eseguire di nuovo questa procedura (passaggio 2: configurare o rimuovere i componenti di Skype for Business Server). 
  
    > [!NOTE]
    > Se il programma di installazione trova i prerequisiti che non sono stati soddisfatti, viene visualizzato un messaggio di "prerequisito non soddisfatto", come illustrato nella figura. Soddisfa il prerequisito richiesto e quindi avvia questa procedura (passaggio 2: configurare o rimuovere i componenti di Skype for Business Server). 
  
     ![Requisito necessario.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Verificare che i primi due passaggi siano stati completati come previsto. Verificare che sia presente un segno di spunta verde con la parola **completamento**, come illustrato nella figura.
    
     ![I primi due passaggi sono stati completati dall'installazione di componenti.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Eseguire di nuovo **Windows Update** per verificare la presenza di aggiornamenti dopo l'installazione dei componenti di Skype for Business Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Passaggio 3: richiedere, installare o assegnare certificati

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto al **passaggio 3: richiedere, installare o assegnare certificati**.
    
    > [!NOTE]
    > Skype for Business Server include il supporto per la famiglia SHA-2 (SHA-2 usa le lunghezze digest di 224, 256, 384 o 512 bit) dell'hash digest e degli algoritmi di firma per le connessioni da client che usano Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Sistemi operativi Server 2012 o Windows Server 2008 R2. Per supportare l'accesso esterno tramite la famiglia SHA-2, il certificato esterno viene emesso da un'autorità di certificazione pubblica che può anche emettere un certificato con lo stesso bit length digest. 
  
    > [!IMPORTANT]
    > La selezione dell'algoritmo di firma e del digest hash dipende dai client e dai server che utilizzeranno il certificato e da altri computer e dispositivi che i client e i server comunicheranno con chi deve anche sapere come usare gli algoritmi usati nella certificato. Per informazioni sulle lunghezze del digest supportate nel sistema operativo e in alcune applicazioni client, vedere [Blog di Windows PKI-SHA2 e Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Ogni Standard Edition o front end server richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web. È tuttavia possibile richiedere e assegnare un singolo certificato predefinito con le voci di nome alternativo oggetto appropriato e il certificato oAuthTokenIssuer. Per informazioni dettagliate sui requisiti per i certificati, vedere requisiti ambientali per i requisiti di [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o server [per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > La procedura seguente descrive come configurare i certificati da un'autorità di certificazione basata su Servizi certificati Active Directory interni. 
  
2. Nella pagina **creazione guidata certificato** fare clic su **Richiedi**.
    
3. Nella pagina **richiesta certificato** inserire i dati rilevanti, ad esempio selezionando il dominio SIP e quindi fare clic su **Avanti**.
    
4. Nella pagina **richieste immediate o posticipate** è possibile accettare l'impostazione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**. La CA interna con registrazione automatica online deve essere disponibile se si seleziona questa opzione. Se si sceglie l'opzione per rinviare la richiesta, verrà chiesto di specificare un nome e un percorso per salvare il file di richiesta del certificato. La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica. Sarà quindi necessario importare la risposta del certificato e assegnarla al ruolo di certificato corretto.
    
5. Nella pagina **scegliere una autorità di certificazione (CA)** selezionare l'opzione **Seleziona una CA dall'elenco rilevato nell'ambiente** e quindi selezionare una CA nota (tramite registrazione in servizi di dominio Active Directory) nell'elenco. In alternativa, selezionare l'opzione **specifica un'altra autorità di certificazione** , immettere il nome di un'altra CA nella casella e quindi fare clic su **Avanti**.
    
6. Nella pagina **account Authority Certificate** vengono chieste le credenziali per richiedere ed elaborare la richiesta di certificato presso la CA. Si sarebbe dovuto determinare se è necessario un nome utente e una password per richiedere un certificato in anticipo. L'amministratore della CA avrà le informazioni necessarie e potrebbe essere necessario per assisterti in questo passaggio. Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare un nome utente e una password nelle caselle di testo e quindi fare clic su **Avanti**.
    
7. Nella pagina **Specifica modello di certificato alternativo** , per usare il modello predefinito del server Web, fare clic su **Avanti**.
    
    > [!NOTE]
    > Se l'organizzazione ha creato un modello da usare come alternativa per il modello di CA del server Web predefinito, selezionare la casella di controllo e quindi immettere il nome del modello alternativo. Sarà necessario il nome del modello definito dall'amministratore della CA. 
  
8. Nella pagina **Impostazioni nome e sicurezza** specificare un **nome**descrittivo. Usando un nome descrittivo, puoi identificare rapidamente il certificato e lo scopo. Se si lascia vuoto, verrà generato automaticamente un nome. Impostare la **lunghezza del bit** della chiave o accettare l'impostazione predefinita di 2048 bit. Selezionare il **contrassegno della chiave privata del certificato come** esportabile se si determina che il certificato e la chiave privata devono essere spostati o copiati in altri sistemi e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Skype for Business Server offre requisiti minimi per una chiave privata esportabile. Una di queste posizioni si trova negli Edge Server in un pool, in cui il servizio di autenticazione dell'inoltro multimediale USA copie del certificato, invece dei singoli certificati per ogni istanza del pool. 
  
9. Nella pagina **informazioni organizzazione** facoltativamente specificare le informazioni sull'organizzazione e quindi fare clic su **Avanti**.
    
10. Nella pagina **informazioni geografiche** specificare facoltativamente informazioni geografiche e quindi fare clic su **Avanti**.
    
11. Nella pagina **nome oggetto/nomi oggetto alternativo** esaminare i nomi alternativi oggetto che verranno aggiunti e quindi fare clic su **Avanti**.
    
12. Nella pagina **Impostazioni dominio SIP** selezionare il **dominio SIP**e quindi fare clic su **Avanti**.
    
13. Nella pagina **Configura altri nomi alternativi oggetto** aggiungere eventuali nomi alternativi di altri soggetti necessari, inclusi quelli eventualmente necessari per altri domini SIP in futuro e quindi fare clic su **Avanti**.
    
14. Nella pagina **Riepilogo richiesta di certificato** esaminare le informazioni nel riepilogo. Se le informazioni sono corrette, fare clic su **Avanti**. Se è necessario correggere o modificare un'impostazione, fare clic su **Torna** alla pagina appropriata per apportare la correzione o la modifica.
    
15. Nella pagina **esecuzione dei comandi** fare clic su **Avanti**.
    
16. Nella pagina di **stato della richiesta di certificato online** verificare le informazioni restituite. Tenere presente che il certificato è stato emesso e installato nell'archivio certificati locale. Se viene segnalato come rilasciato e installato, ma non è valido, verificare che il certificato radice della CA sia stato installato nell'archivio della CA radice attendibile del server. Vedere la documentazione della CA su come recuperare un certificato CA radice attendibile. Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**. Per impostazione predefinita, la casella di controllo **assegna il certificato agli usi dei certificati Skype for Business Server** è selezionata. Se si vuole assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **fine**.
    
17. Se è stata deselezionata la casella di controllo **assegna il certificato agli usi dei certificati Skype for Business Server** nella pagina precedente, verrà visualizzata la pagina **assegnazione certificato** . Fare clic su **Avanti**.
    
18. Nella pagina **archivio certificati** selezionare il certificato richiesto. Se si vuole visualizzare il certificato, fare clic su **Visualizza dettagli certificato**e quindi su **Avanti** per continuare.
    
    > [!NOTE]
    > Se la pagina di **stato della richiesta di certificato online** ha segnalato un problema con il certificato, ad esempio il certificato non è valido, visualizzare il certificato effettivo per ottenere assistenza nella risoluzione del problema. Due problemi specifici che possono causare un certificato non valido sono il certificato della CA radice attendibile mancante menzionato in precedenza e una chiave privata mancante associata al certificato. Fare riferimento alla documentazione della CA per risolvere questi due problemi.
  
19. Nella pagina **Riepilogo assegnazione certificati** esaminare le informazioni presentate per verificare che si tratta del certificato da assegnare e quindi fare clic su **Avanti**.
    
20. Nella pagina **esecuzione dei comandi** esaminare l'output del comando. Fare clic su **Visualizza log** se si vuole rivedere il processo di assegnazione o se è stato emesso un errore o un avviso. Al termine della revisione, fare clic su **fine**.
    
21. Nella pagina **creazione guidata certificato** verificare che tutti i servizi abbiano un controllo verde per indicare che a tutti è stato assegnato un certificato, incluso OAuthTokenIssuer, come illustrato nella figura, quindi fare clic su **Chiudi**.
    
     ![Certificati installati e assegnati correttamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Se si sta eseguendo l'installazione in un ambiente lab e si è appena configurata l'autorità di certificazione tramite Servizi certificati Active Directory, sarà necessario riavviare sia il server che esegue i servizi certificati che il server front-end prima del certificato l'assegnazione può essere eseguita correttamente. 
  
    > [!TIP]
    >  Per altre informazioni sui certificati in Servizi certificati Active Directory, vedere [Servizi certificati Active Directory](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Passaggio 4: avviare i servizi

1. Esaminare i prerequisiti per il **passaggio 4: avviare i servizi**.
    
2. Se si tratta di un pool Enterprise Edition front-end con almeno tre server, viene usato il tessuto Windows ed è necessario usare il cmdlet **Start-CsPool** . Se si usa un singolo server, che è sempre il caso di Standard Edition, la musa usa il cmdlet **Start-CsWindowsService** . In questo esempio si usa Enterprise Edition con tre server front-end nel pool, aprire **Skype for Business Server Management Shell** ed eseguire il cmdlet **Start-CsPool** come illustrato nella figura. Per tutti gli altri ruoli, incluso il server Standard Edition, è necessario usare **Start-CsWindowsService**. Per distribuire ruoli diversi dal ruolo front-end, vedere la documentazione relativa a questi ruoli specifici.
    
     ![Avviare servizi Skype for business.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Nella pagina **esecuzione dei comandi** , dopo aver avviato tutti i servizi, fare clic su **fine**.
    
    > [!IMPORTANT]
    > Il comando per avviare i servizi sul server è un metodo di sforzo ottimale per segnalare che i servizi sono stati avviati. Potrebbe non corrispondere allo stato effettivo del servizio. È consigliabile usare lo stato del servizio di passaggio **(facoltativo)** per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente, come illustrato nella figura. Se il servizio Skype for Business Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse sul servizio in MMC e quindi scegliere **Avvia**. 
  
     ![Verificare che i servizi siano avviati.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

