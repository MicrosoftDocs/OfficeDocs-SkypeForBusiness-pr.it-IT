---
title: Creare la topologia di Edge per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Riepilogo: informazioni su come creare, pubblicare ed esportare la topologia di Edge Server in Skype for Business Server.'
ms.openlocfilehash: c625656f1686b6e72be2f0223d6560464bb9e7bc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001476"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Creare la topologia di Edge per Skype for Business Server
 
**Riepilogo:** Informazioni su come creare, pubblicare ed esportare la topologia di Edge Server in Skype for Business Server.
  
Generatore di topologia è lo strumento che devi usare per creare la topologia di Edge Server, così come viene usata per qualsiasi componente di topologia per Skype for Business Server. Prima di eseguire la procedura seguente, è necessario configurare almeno un pool Front-end o un server Standard Edition.
  
In questo articolo vengono illustrati gli argomenti seguenti:
  
- Creare la topologia di Edge Server
    
- Pubblicare la topologia di Edge Server
    
- Esportare la topologia di Edge Server
    
  > [!NOTE]
  > Per eseguire la procedura seguente, è necessario accedere ai server di dominio menzionati di seguito come utenti che fanno parte dei seguenti gruppi di domini: 
  
- RTCUniversalServerAdmins
    
- Amministratori di dominio
    
## <a name="build-your-edge-server-topology"></a>Creare la topologia di Edge Server

Il primo passaggio di distribuzione consiste nel creare la topologia di Skype for Business Server Edge Server, costituita da una delle tre opzioni seguenti:
  
- Un singolo Edge Server
    
- Pool di Edge con bilanciamento del carico DNS (uno o più server)
    
- Un pool di Edge con bilanciamento del carico hardware (uno o più server)
    
Se non si è sicuri di cosa si ha bisogno, prima di iniziare a seguire questa procedura è consigliabile passare alla documentazione relativa alla pianificazione. In caso contrario, iniziamo.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definizione della topologia per un singolo Edge Server

1. Accedere al server Skype for Business Server Standard Edition o a un pool Front-End di Skype for Business Server.
    
2. Una volta lì, Apri il **Generatore di topologia di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di bordi** .
    
6. Nella schermata **Definisci il** nome di dominio completo del pool di Edge digitare l'FQDN (Fully Qualified Domain Name) interno che verrà usato dall'Edge Server e selezionare **Single computer pool**, quindi fare clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
   - Potresti voler usare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio di Web Conferencing per Skype for Business Server e il servizio A/V Edge. In questo caso, è necessario scegliere la **casella di controllo Usa un singolo nome di dominio completo e indirizzo IP** (tenendo presente il passaggio 9 seguente)
    
   - Se si prevede di abilitare la Federazione, selezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni sono le seguenti:
    
   - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
   Queste informazioni sono abbastanza comprensibili, sia che si stiano usando indirizzi IPv4 o IPv6, sia che si stiano applicando tali indirizzi nel server perimetrale internamente o esternamente (è necessario tenerlo presente per il passaggio 10). Hai anche la possibilità di configurare il tuo Edge Server o il tuo pool di Edge per usare un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. A tale scopo, selezionare la casella di controllo **indirizzo IP esterno di questo pool di Edge tradotto da NAT** . Quando si è pronti, fare clic su **Avanti** .
    
9. Nella schermata FQDN esterni le opzioni dipendono dalla selezione effettuata nel passaggio 7.
    
   - Se è stata selezionata la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio Edge per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio Edge **Access SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
   - Se non è stata visualizzata la casella di controllo **Usa un solo nome FQDN e indirizzo IP** , sarà necessario immettere i tre nomi di dominio completi esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
10. Si è ora nella schermata **Definisci l'indirizzo IP interno** . Qui digitate l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte effettuate nel passaggio 8. Quando si è pronti, fare clic su **Avanti** .
    
11. Nella schermata **Definisci indirizzo IP esterno** sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - Potresti usare un singolo FQDN per tutti i servizi. In questo caso, digitare l'indirizzo IPv4 o IPv6 esterno (in base a quale si sta usando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile che tu abbia scelto di usare tre nomi FQDN e indirizzi IP distinti per i servizi. In questo caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata. Questo è normale, basta passare al passaggio successivo. 
  
12. Se si è scelto di usare NAT nel passaggio 8, si otterrà una schermata con una casella di testo **Pubblica indirizzo IP** . È necessario immettere l'indirizzo IPv4 e/o IPv6 pubblico impostato per il servizio A/V Edge, per essere tradotto da NAT. Quindi fare clic su **Avanti**.
    
13. La schermata successiva è **Definisci l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front-end o un pool autonomo. Se si ha un amministratore nell'ambiente, è consigliabile scegliere il Director. Quindi fare clic su **Avanti**.
    
14. Nella schermata **Associa pool Front-End** è necessario specificare uno o più pool interni, inclusi i pool Front-end e i server Standard Edition, da associare a questo server perimetrale. Basta scegliere i nomi dei pool interni che si vuole usare con questo Edge Server per comunicare con utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > Tieni presente che se i tuoi pool interni o i server autonomi usano già un server Edge Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in quella situazione, viene visualizzato un avviso che indica l'altro Edge Server e si può decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro Edge Server si arresta. 
  
15. Nella schermata successiva fare clic su **fine** .
    
16. A questo punto è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni fornite in [distribuire Edge Server in Skype for Business Server](deploy-edge-servers.md) per la distribuzione in un server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server Edge con bilanciamento del carico DNS

1. Accedere al server Skype for Business Server Standard Edition o a un server front-end di Skype for Business Server.
    
2. Una volta lì, Apri il **Generatore di topologia di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di bordi** .
    
6. Nella schermata **Definisci il** nome di dominio completo del pool di Edge digitare l'FQDN (Fully Qualified Domain Name) interno che verrà usato dal pool di Edge e selezionare **più pool di computer**, quindi fare clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
    - Potresti voler usare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio di Web Conferencing per Skype for Business Server e il servizio A/V Edge. In questo caso, è necessario scegliere la **casella di controllo Usa un singolo nome di dominio completo e indirizzo IP** (tenendo presente il passaggio 9 seguente)
    
    - Se si prevede di abilitare la Federazione, selezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni sono le seguenti:
    
    - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
     Queste informazioni sono abbastanza comprensibili, sia che si stiano usando indirizzi IPv4 o IPv6, sia che si stiano applicando tali indirizzi nel server perimetrale internamente o esternamente (è necessario tenerlo presente per il passaggio 11). Hai anche la possibilità di configurare il tuo Edge Server o il tuo pool di Edge per usare un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. A tale scopo, selezionare la casella di controllo **indirizzo IP esterno di questo pool di Edge tradotto da NAT** . Quando si è pronti, fare clic su **Avanti** .
    
9. Nella schermata FQDN esterni le opzioni dipendono dalla selezione effettuata nel passaggio 7.
    
   - Se è stata selezionata la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio Edge per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio Edge **Access SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
   - Se non è stata visualizzata la casella di controllo **Usa un solo nome FQDN e indirizzo IP** , sarà necessario immettere i tre nomi di dominio completi esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
10. A questo punto è stata raggiunta la schermata **Definisci i computer in questo pool** . Fare clic sul pulsante **Aggiungi** .
    
11. Si è ora nella schermata **Definisci l'indirizzo IP interno** . Qui digitate l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte effettuate nel passaggio 8. Quando si è pronti, fare clic su **Avanti** .
    
12. Nella schermata **Definisci indirizzo IP esterno** sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - Potresti usare un singolo FQDN per tutti i servizi. In questo caso, digitare l'indirizzo IPv4 o IPv6 esterno (in base a quale si sta usando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile che tu abbia scelto di usare tre nomi FQDN e indirizzi IP distinti per i servizi. In questo caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata. Questo è normale, basta passare al passaggio successivo. 
  
13. Fare clic su **fine**. Il server perimetrale appena creato dovrebbe essere elencato nella finestra di dialogo **Definisci i computer in questo pool** .
    
14. Ancora nella schermata **Definisci i computer in questo pool** , fare di nuovo clic sul pulsante Aggiungi e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si vuole **inserire** nel pool. Al termine, fare clic su **Avanti**.
    
15. Se si è scelto di usare NAT nel passaggio 8, si otterrà una schermata con una casella di testo **Pubblica indirizzo IP** . È necessario immettere l'indirizzo IPv4 e/o IPv6 pubblico impostato per il servizio A/V Edge, per essere tradotto da NAT. Quindi fare clic su **Avanti**.
    
16. La schermata successiva è **Definisci l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front-end o un pool autonomo. Se si ha un amministratore nell'ambiente, è consigliabile scegliere il Director. Quindi fare clic su **Avanti**.
    
17. Nella schermata **Associa pool Front-End** è necessario specificare uno o più pool interni, inclusi i pool Front-end e i pool Standard Edition, da associare a questo Edge Server. Basta scegliere i nomi dei pool interni che si vuole usare con questo Edge Server per comunicare con utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > Tieni presente che se i tuoi pool interni o i server autonomi usano già un server Edge Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in quella situazione, viene visualizzato un avviso che indica l'altro Edge Server e si può decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro Edge Server si arresta. 
  
18. Nella schermata successiva fare clic su **fine** .
    
19. A questo punto è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni fornite in [distribuire Edge Server in Skype for Business Server](deploy-edge-servers.md) per la distribuzione in un server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server Edge con bilanciamento del carico hardware

1. Accedere al server Skype for Business Server Standard Edition o a un server front-end di Skype for Business Server.
    
2. Una volta lì, Apri il **Generatore di topologia di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di bordi** .
    
6. Nella schermata **Definisci il** nome di dominio completo del pool di Edge digitare l'FQDN (Fully Qualified Domain Name) interno che verrà usato dal pool di Edge e selezionare **più pool di computer**, quindi fare clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
   - Potresti voler usare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio di Web Conferencing per Skype for Business Server e il servizio A/V Edge. In questo caso, è necessario scegliere la **casella di controllo Usa un singolo nome di dominio completo e indirizzo IP** (tenendo presente il passaggio 9 seguente)
    
   - Se si prevede di abilitare la Federazione, selezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni sono le seguenti:
    
   - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
     Queste informazioni sono abbastanza comprensibili, sia che si stiano usando indirizzi IPv4 o IPv6, sia che si stiano applicando tali indirizzi nel server perimetrale internamente o esternamente (è necessario tenerlo presente per il passaggio 11).
    
     > [!NOTE]
     > A differenza delle altre due opzioni della topologia, quando si usa un bilanciamento del carico hardware, **non è necessario** selezionare l'opzione che **l'indirizzo IP esterno del pool di Edge viene tradotto da NAT**. Questa operazione **non è supportata**.
  
9. Nella schermata FQDN esterni le opzioni dipendono dalla selezione effettuata nel passaggio 7.
    
   - Se è stata selezionata la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio Edge per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio Edge **Access SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
   - Se non è stata visualizzata la casella di controllo **Usa un solo nome FQDN e indirizzo IP** , sarà necessario immettere i tre nomi di dominio completi esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Fare clic su **Avanti** al termine.
    
10. A questo punto è stata raggiunta la schermata **Definisci i computer in questo pool** . Fare clic sul pulsante **Aggiungi** .
    
11. Si è ora nella schermata **Definisci l'indirizzo IP interno** . Qui digitate l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte effettuate nel passaggio 8. Quando si è pronti, fare clic su **Avanti** .
    
12. Nella schermata **Definisci indirizzo IP esterno** sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - Potresti usare un singolo FQDN per tutti i servizi. In questo caso, digitare l'indirizzo IPv4 o IPv6 esterno (in base a quale si sta usando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile che tu abbia scelto di usare tre nomi FQDN e indirizzi IP distinti per i servizi. In questo caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata. Questo è normale, basta passare al passaggio successivo. 
  
13. Fare clic su **fine**. Il server perimetrale appena creato dovrebbe essere elencato nella finestra di dialogo **Definisci i computer in questo pool** .
    
14. Ancora nella schermata **Definisci i computer in questo pool** , fare di nuovo clic sul pulsante Aggiungi e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si vuole **inserire** nel pool. Al termine, fare clic su **Avanti**.
    
15. La schermata successiva è **Definisci l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front-end o un pool autonomo. Se si ha un amministratore nell'ambiente, è consigliabile scegliere il Director. Quindi fare clic su **Avanti**.
    
16. Nella schermata **Associa pool Front-End** è necessario specificare uno o più pool interni, inclusi i pool Front-end e i pool Standard Edition, da associare a questo Edge Server. Basta scegliere i nomi dei pool interni che si vuole usare con questo Edge Server per comunicare con utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > Tieni presente che se i tuoi pool interni o i server autonomi usano già un server Edge Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in quella situazione, viene visualizzato un avviso che indica l'altro Edge Server e si può decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro Edge Server si arresta. 
  
17. Nella schermata successiva fare clic su **fine** .
    
18. A questo punto è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni fornite in [distribuire Edge Server in Skype for Business Server](deploy-edge-servers.md) per la distribuzione in un server perimetrale da qui.
    
## <a name="publish-your-edge-server-topology"></a>Pubblicare la topologia di Edge Server

Dopo aver completato la procedura descritta sopra, è il momento di pubblicare questa nuova topologia, che consentirà anche di esportarla in Skype for Business Server Edge Server o Edge pool. Seguire questa procedura:
  
1. Avviare **Generatore di topologie** (se non è già stato avviato dalla procedura precedente).
    
2. In **Generatore di topologie**, nell'albero della console, fare clic con il pulsante destro del mouse su **Skype for Business Server** e quindi scegliere **Generatore di topologia di Skype for Business Server**.
    
3. Nella pagina di **benvenuto** della procedura guidata fare clic su **Avanti**.
    
4. Nella pagina **crea altri database** fare clic su **Avanti**.
    
5. Quando lo stato indica che la creazione del database è riuscita, eseguire le operazioni seguenti:
    
    - Per visualizzare il log, fare clic su **Visualizza log**.
    
    - Per chiudere la procedura guidata, fare clic su **fine**.
    
## <a name="export-your-edge-server-topology"></a>Esportare la topologia di Edge Server

Per distribuire correttamente, la distribuzione guidata di Skype for Business Server richiede l'accesso ai dati dell'archivio di gestione centrale. Per i server interni nel dominio o nella foresta, in genere è semplice. I server perimetrali si trovano all'esterno del dominio e quindi è necessario esportare manualmente il file della topologia nel percorso del server perimetrale, in genere su un supporto fisico. Questa esportazione viene eseguita tramite PowerShell:
  
1. Avviare **Skype for Business Server Management Shell**.
    
2. In **Skype for Business Server Management Shell**eseguire le operazioni seguenti:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiare il file esportato in elementi multimediali esterni, ad esempio un'unità USB o una condivisione di rete raggiungibile dalla posizione del server perimetrale.
    

