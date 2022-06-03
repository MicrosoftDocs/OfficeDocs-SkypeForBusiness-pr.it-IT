---
title: Installare Skype for Business Server nei server nella topologia
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Riepilogo: informazioni su come installare i componenti di sistema Skype for Business Server in ogni server della topologia.'
ms.openlocfilehash: 7aea6d25edcd28ba611b81d33eceed4172019bee
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860617"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installare Skype for Business Server nei server nella topologia
 
**Riepilogo:** Informazioni su come installare i componenti di sistema Skype for Business Server in ogni server nella topologia.
  
Dopo che la topologia è stata caricata nell'archivio di gestione centrale e Active Directory sa quali server eseguiranno i ruoli, è necessario installare il sistema Skype for Business Server in ognuno dei server nella topologia. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5 come descritto nel diagramma. L'installazione del sistema Skype for Business Server è il passaggio 7 dell'8.
  
![Diagramma di panoramica.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installare Skype for Business Server sistema

Dopo aver pubblicato una topologia, è possibile installare i componenti Skype for Business Server in ogni server della topologia. Questa sezione illustra come installare Skype for Business Server e configurare i ruoli del server per il pool Front End e tutti i ruoli del server collocati con i server Front End. Per installare e configurare i ruoli del server, eseguire la Distribuzione guidata Skype for Business Server in ogni computer in cui si sta installando un ruolo del server. La Distribuzione guidata consente di completare tutti e quattro i passaggi di distribuzione, tra cui l'installazione dell'archivio di configurazione locale, l'installazione dei Front End Server, la configurazione dei certificati e l'avvio dei servizi.
  
> [!IMPORTANT]
> È necessario usare Generatore di topologie per completare e pubblicare la topologia prima di poter installare Skype for Business Server nei server. 
  
> [!NOTE]
> Questa procedura deve essere completata per tutti i server nella topologia. 
  
> [!CAUTION]
> Dopo aver installato Skype for Business Server in un Front End Server, la prima volta che si avviano i servizi, è necessario assicurarsi che il servizio firewall Windows sia in esecuzione nel server. 
  
> [!CAUTION]
> Prima di seguire questa procedura, assicurarsi di essere connessi al server con un account utente di dominio sia un amministratore locale che un membro del gruppo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Se non è già stato eseguito Skype for Business Server installazione in questo server, verranno richiesti un'unità e un percorso per l'installazione. In questo modo è possibile eseguire l'installazione in un'unità diversa dall'unità di sistema, se l'organizzazione lo richiede o in caso di problemi di spazio. È possibile modificare il percorso di installazione per i file Skype for Business Server nella finestra di dialogo **Installazione** in una nuova unità disponibile. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, verranno distribuiti anche gli altri file di Skype for Business Server.
  
> [!IMPORTANT]
> Prima di iniziare l'installazione, assicurarsi che Windows Server sia aggiornato usando Windows Update. 
  
![Windows Server aggiornato.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installare Skype for Business Server sistema

1. Inserire il supporto di installazione Skype for Business Server. Se l'installazione non viene avviata automaticamente, fare doppio clic su **Imposta**.
    
2. Il supporto di installazione richiede Microsoft Visual C++ per l'esecuzione. Verrà visualizzata una finestra di dialogo che chiede se si vuole installarla. Fare clic su **Sì.**
    
3. Esaminare attentamente il Contratto di licenza e, se si accetta, selezionare **Accetto le condizioni nel contratto di licenza** e fare clic su **OK**. 
    
4. La configurazione intelligente è una funzionalità in Skype for Business Server in cui è possibile connettersi a Internet per verificare la disponibilità di aggiornamenti da Microsoft Update (MU) durante il processo di installazione, come illustrato nella figura. Ciò offre un'esperienza migliore assicurandosi di avere gli aggiornamenti più recenti per il prodotto. Fare clic su **Installa** per avviare l'installazione.
    
    > [!NOTE]
    > Molte organizzazioni hanno distribuito Windows Server Update Services (WSUS) negli ambienti aziendali. WSUS consente agli amministratori di gestire completamente la distribuzione degli aggiornamenti rilasciati tramite Microsoft Update ai computer della rete. Nell'ambito dell'aggiornamento cumulativo 1 Skype for Business Server introdotto il supporto per l'uso di Smart Setup con WSUS. I clienti con WSUS che distribuiscono Skype for Business Server per la prima volta o che eseguono l'aggiornamento dall'ambiente Lync Server 2013 usando la funzionalità di aggiornamento In-Place avranno Skype di recupero delle impostazioni intelligenti per gli aggiornamenti Windows da WSUS anziché recuperare gli aggiornamenti da MU. I clienti che vogliono usare l'installazione intelligente devono eseguire SmartSetupWithWSUS.psq in tutti i computer prima di eseguire Setup.exe. 
  
     ![Screenshot dell'installazione intelligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Nella pagina Distribuzione guidata fare clic su **Installa o aggiorna Skype for Business Server sistema**.
    
6. Eseguire le procedure nelle procedure seguenti, dopo averle completate, fare clic su **Esci** per chiudere la Distribuzione guidata. Ripetere le procedure per ogni server Front End nel pool.
    
### <a name="step-1-install-local-configuration-store"></a>Passaggio 1: Installare l'archivio di configurazione locale

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto a **Passaggio 1: Installare l'archivio di configurazione locale**.
    
    > [!NOTE]
    > L'archivio di configurazione locale è una copia di sola lettura dell'archivio di gestione centrale. In una distribuzione edizione Standard, l'archivio di gestione centrale viene creato usando una copia locale di SQL Server Express Edition nel server Front End. Ciò si verifica quando si esegue la routine Prepare First edizione Standard Server. In una distribuzione edizione Enterprise, l'archivio di gestione centrale viene creato quando si pubblica la topologia che include un pool front-end edizione Enterprise. 
  
2. Nella pagina **Installa archivio configurazione locale** verificare che sia selezionata l'opzione **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.
    
    SQL Server Express Edition è installato nel server locale. SQL Server Express Edition è necessaria per l'archivio di configurazione locale.
    
3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.
    
### <a name="step-2-set-up-or-remove-skype-for-business-server-components"></a>Passaggio 2: Configurare o rimuovere componenti Skype for Business Server

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto a **Passaggio 2: Installazione o Rimozione dei componenti Skype for Business Server**.
    
2. Nella pagina **Configura componenti Skype for Business Server** fare clic su **Avanti** per configurare i componenti come definito nella topologia pubblicata.
    
3. Nella pagina **Comandi in esecuzione** viene visualizzato un riepilogo dei comandi e delle informazioni di installazione durante la configurazione. Al termine, è possibile usare l'elenco per selezionare un log da visualizzare e quindi fare clic su **Visualizza log**.
    
4. Al termine dell'installazione di Skype for Business Server componenti ed aver esaminato i log in base alle esigenze, fare clic su **Fine** per completare questo passaggio nell'installazione.
    
    > [!NOTE]
    > Riavviare il server se richiesto (cosa che potrebbe verificarsi se Windows'esperienza desktop doveva essere installata). Quando il computer è di backup ed è in esecuzione, è necessario eseguire di nuovo questa procedura (Passaggio 2: Installazione o Rimozione dei componenti Skype for Business Server). 
  
    > [!NOTE]
    > Se il programma di installazione trova tutti i prerequisiti che non sono stati soddisfatti, verrà visualizzato un messaggio "Prerequisito non soddisfatto", come illustrato nella figura. Soddisfare i prerequisiti necessari e quindi avviare di nuovo la procedura (passaggio 2: installazione o rimozione dei componenti Skype for Business Server). 
  
     ![Prerequisiti necessari.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Verificare che i primi due passaggi sono stati completati come previsto. Verificare che sia presente un segno di spunta verde con la parola **Complete**, come illustrato nella figura.
    
     ![I primi due passaggi sono stati completati dall'installazione dei componenti.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Eseguire **di nuovo Windows Update** per verificare se sono presenti aggiornamenti dopo l'installazione dei componenti Skype for Business Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Passaggio 3: Richiedere, installare o assegnare certificati

1. Esaminare i prerequisiti e quindi fare clic su **Esegui** accanto a **Passaggio 3: Richiedere, installare o assegnare certificati**.
    
    > [!NOTE]
    > Skype for Business Server include il supporto per la suite SHA-2 (SHA-2 usa lunghezze di digest di 224, 256, 384 o 512 bit) di hash digest e di firma degli algoritmi per le connessioni dai client che eseguono Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 o sistemi operativi Windows Server 2008 R2. Per supportare l'accesso esterno tramite la suite SHA-2, il certificato esterno viene emesso da una CA pubblica che può anche emettere un certificato con lo stesso digest di lunghezza in bit. 
  
    > [!IMPORTANT]
    > La selezione dell'algoritmo di digest hash e firma dipende dai client e dai server che useranno il certificato e da altri computer e dispositivi con cui i client e i server comunicheranno, che devono anche sapere come usare gli algoritmi usati nel certificato. Per informazioni sulle lunghezze di digest supportate nel sistema operativo e in alcune applicazioni client, vedere [Windows blog PKI - SHA2 e Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Ogni edizione Standard o server Front End richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web. È tuttavia possibile richiedere e assegnare un singolo certificato predefinito con le voci del nome alternativo del soggetto appropriate e il certificato oAuthTokenIssuer. Per informazioni dettagliate sui requisiti del certificato, vedere [Requisiti ambientali per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Requisiti del server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > La procedura seguente descrive come configurare i certificati da un'autorità di certificazione interna basata su Servizi certificati Active Directory. 
  
2. Nella pagina **Configurazione guidata certificati** fare clic su **Richiesta**.
    
3. Nella pagina **Richiesta di certificato** immettere i dati pertinenti, inclusa la selezione del dominio SIP e fare clic su **Avanti**.
    
4. Nella pagina **Richieste immediate o ritardate** è possibile accettare l'opzione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**. Se si seleziona questa opzione, deve essere disponibile la CA interna con registrazione automatica online. Se si sceglie l'opzione di ritardare la richiesta, sarà necessario specificare un nome e un percorso in cui salvare il file di richiesta di certificato. La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica. Sarà quindi necessario importare il certificato di risposta e assegnarlo al ruolo appropriato.
    
5. Nella pagina **Scegliere un'autorità di certificazione (CA)** selezionare l'opzione **Selezionare una CA dall'elenco rilevato nell'ambiente** e quindi selezionare una CA nota (tramite registrazione in Active Directory Domain Services) dall'elenco. In alternativa, selezionare l'opzione **Specifica un'altra autorità di certificazione**, immettere il nome di un'altra CA e quindi fare clic su **Avanti**.
    
6. Nella pagina **Account autorità di certificazione** viene richiesto di immettere le credenziali per richiedere ed elaborare la richiesta di certificato per la CA. Stabilire se è necessario specificare un nome utente e una password per richiedere un certificato in anticipo. L'amministratore della CA avrà le informazioni necessarie e potrebbe essere necessario assistere l'utente in questo passaggio. Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare il nome utente e la password nelle caselle di testo, quindi fare clic su **Avanti**.
    
7. Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti** per utilizzare il modello Server Web predefinito.
    
    > [!NOTE]
    > Se l'organizzazione ha creato un modello da utilizzare come alternativa al modello Server Web predefinito della CA, selezionare la casella di controllo, quindi immettere il nome del modello alternativo. È necessario specificare il nome del modello come definito dall'amministratore della CA. 
  
8. Nella pagina **Nome e sicurezza Impostazioni** specificare un **nome descrittivo**. Usando un nome descrittivo, è possibile identificare rapidamente il certificato e lo scopo. Se questo campo viene lasciato vuoto, verrà generato automaticamente un nome. Impostare il valore **Lunghezza in bit** della chiave o accettare il valore predefinito di 2048 bit. Selezionare la **chiave privata del certificato come esportabile** se si determina che il certificato e la chiave privata devono essere spostati o copiati in altri sistemi e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Skype for Business Server ha requisiti minimi per una chiave privata esportabile. La chiave viene esportata nei server perimetrali di un pool, dove il servizio di autenticazione del Media Relay utilizza copie del certificato anziché i singoli certificati per ogni istanza nel pool. 
  
9. Nella pagina **Informazioni sull'organizzazione** immettere facoltativamente le informazioni sull'organizzazione e quindi fare clic su **Avanti**.
    
10. Nella pagina **Dati geografici** specificare facoltativamente i dati geografici e quindi fare clic su **Avanti**.
    
11. Nella pagina **Nome soggetto / Nomi soggetto alternativi** verificare i nomi soggetto alternativi che verranno aggiunti e quindi fare clic su **Avanti**.
    
12. Nella pagina **Impostazione del dominio SIP** selezionare la casella di controllo **Dominio SIP** e quindi fare clic su **Avanti**.
    
13. Nella pagina **Configura nomi soggetto alternativi aggiuntivi** aggiungere eventuali nomi soggetto alternativi aggiuntivi necessari, inclusi quelli potranno essere richiesti in futuro per i domini SIP aggiuntivi, quindi fare clic su **Avanti**.
    
14. Nella pagina **Riepilogo richiesta certificato** esaminare le informazioni. Se sono corrette, fare clic su **Avanti**. Se è necessario correggere o modificare un'impostazione, fare clic su **Indietro** fino alla pagina appropriata.
    
15. Nella pagina **Esecuzione comandi in corso** fare clic su **Avanti**.
    
16. Nella pagina On the **Stato richiesta di certificato online** esaminare le informazioni restituite. Verificare che il certificato sia stato emesso e installato nell'archivio certificati locale. Se viene segnalato come emesso e installato, ma non è valido, assicurarsi che il certificato radice ca sia stato installato nell'archivio CA radice attendibile del server. Per informazioni su come recuperare un certificato di CA radice attendibile, consultare la documentazione sulla CA. Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**. Per impostazione predefinita, è selezionata la casella di controllo **Assegna il certificato a Skype for Business Server utilizzi del certificato**. Se si desidera assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **Fine**.
    
17. Se nella pagina precedente è stata deselezionata la casella di controllo **Assegna il certificato a Skype for Business Server utilizzi del certificato**, verrà visualizzata la pagina **Assegnazione certificato**. Fare clic su **Avanti**.
    
18. Nella pagina **Archivio certificati** selezionare il certificato richiesto. Se si desidera visualizzarlo, fare clic su **Visualizza dettagli certificato** e quindi su **Avanti** per continuare.
    
    > [!NOTE]
    > Se nella pagina **Stato richiesta certificato online** è stato segnalato un problema con il certificato, ad esempio il certificato non è valido, visualizzare il certificato effettivo per la risoluzione del problema. In particolare, il certificato può non essere valido perché non è stato emesso da una CA radice attendibile, come accennato in precedenza, oppure perché non è associato a una chiave privata. Per risolvere questi due problemi, consultare la documentazione della CA.
  
19. Nella pagina **Riepilogo assegnazione certificati** esaminare le informazioni presentate per assicurarsi che si tratta del certificato che deve essere assegnato e quindi fare clic su **Avanti**.
    
20. Nella pagina **Esecuzione comandi in corso** esaminare l'output del comando. Fare clic su **Visualizza registro** se si desidera rivedere il processo di assegnazione oppure se è stato generato un messaggio di errore o di avviso. Al termine, fare clic su **Fine**.
    
21. Nella pagina **Creazione guidata certificato** verificare che tutti i servizi abbiano un controllo verde per indicare che a tutti è stato assegnato un certificato, incluso OAuthTokenIssuer , come illustrato nella figura, e quindi fare clic su **Chiudi**.
    
     ![Certificati installati e assegnati correttamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Se si esegue l'installazione in un ambiente lab e si è appena configurata l'autorità di certificazione usando Servizi certificati Active Directory, è necessario riavviare sia il server che esegue Servizi certificati che il server Front End prima che l'assegnazione del certificato possa essere completata correttamente. 
  
    > [!TIP]
    >  Per altre informazioni sui certificati in Servizi certificati Active Directory, vedere [Servizi certificati Active Directory](/windows/deployment/deploy-whats-new). 
  
### <a name="step-4-start-services"></a>Passaggio 4: Avviare i servizi

1. Esaminare i prerequisiti per **Passaggio 4: Avviare i servizi**.
    
2. Se si tratta di un pool front-end edizione Enterprise con almeno tre server, viene usato Windows Fabric ed è necessario usare il cmdlet **Start-CsPool**. Se viene usato un singolo server, come sempre avviene con edizione Standard, usare il cmdlet **Start-CsWindowsService**. In questo esempio viene usato edizione Enterprise con tre server Front End nel pool, aprire **Skype for Business Server Management Shell** ed eseguire il cmdlet **Start-CsPool** come illustrato nella figura. Per tutti gli altri ruoli, incluso edizione Standard server, è necessario usare **Start-CsWindowsService**. Per distribuire ruoli diversi dal ruolo Front End, vedere la documentazione per questi ruoli specifici.
    
     ![Avviare Skype for Business servizi.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Nella pagina **Esecuzione comandi in corso**, dopo l'avvio di tutti i servizi, fare clic su **Fine**.
    
    > [!IMPORTANT]
    > Il comando per avviare i servizi nel server è un metodo ottimale per segnalare che i servizi sono stati effettivamente avviati. Potrebbe non riflettere lo stato effettivo del servizio. È consigliabile usare il passaggio **Stato servizio (facoltativo)** per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente, come illustrato nella figura. Se un servizio Skype for Business Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse su tale servizio in MMC e quindi scegliere **Avvia**. 
  
     ![Verificare che i servizi siano stati avviati.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
