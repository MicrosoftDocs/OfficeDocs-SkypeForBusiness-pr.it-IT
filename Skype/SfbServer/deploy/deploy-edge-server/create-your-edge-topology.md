---
title: Creare la topologia perimetrale per Skype for Business Server
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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Riepilogo: informazioni su come creare, pubblicare ed esportare la topologia di server perimetrali in Skype for Business Server.'
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804396"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Creare la topologia perimetrale per Skype for Business Server
 
**Riepilogo:** Informazioni su come creare, pubblicare ed esportare la topologia di server perimetrali in Skype for Business Server.
  
Generatore di topologie è lo strumento che è necessario utilizzare per creare la topologia dei server perimetrali, così come viene utilizzata per qualsiasi componente di topologia per Skype for Business Server. Prima di eseguire la procedura seguente, sarà necessario configurare almeno un pool Front end o un server Standard Edition.
  
In questo articolo vengono illustrati i seguenti argomenti:
  
- Creare la topologia del server perimetrale
    
- Pubblicare la topologia del server perimetrale
    
- Esportare la topologia del server perimetrale
    
  > [!NOTE]
  > Per eseguire la procedura seguente, è necessario eseguire l'accesso ai server di dominio descritti di seguito come utenti che sono membri dei seguenti gruppi di dominio: 
  
- RTCUniversalServerAdmins
    
- Domain Admins
    
## <a name="build-your-edge-server-topology"></a>Creare la topologia del server perimetrale

Il primo passaggio per la distribuzione consiste nella creazione della topologia del server perimetrale di Skype for Business Server, che è costituita da una delle tre opzioni seguenti:
  
- Un singolo server perimetrale
    
- Pool di Edge con bilanciamento del carico DNS (uno o più server)
    
- Un pool di Edge con bilanciamento del carico hardware (uno o più server)
    
Se non si è sicuri di cosa si ha bisogno, prima di iniziare a eseguire questa procedura è opportuno ripassare la documentazione relativa alla pianificazione. In caso contrario, iniziamo.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definizione della topologia per un singolo server perimetrale

1. Accedere al server di Skype for Business Server Standard Edition o a un pool Front End di Skype for Business Server.
    
2. Una volta lì, aprire **Generatore di topologie di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge** e quindi scegliere **nuovo pool di server perimetrali**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di server perimetrali** .
    
6. Nella schermata **definire l'FQDN del pool di server perimetrali** , digitare il nome di dominio completo (FQDN) interno che dovrà essere utilizzato dall'applicazione Edge e selezionare **pool di computer singolo**, quindi fare clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
   - È possibile che si desideri utilizzare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la **casella di controllo utilizza un singolo FQDN e indirizzo IP** (e tenere presente il passaggio 9 in basso).
    
   - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per il pool di server perimetrali (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni disponibili sono le seguenti:
    
   - Abilitare IPv4 sull'interfaccia interna
    
   - Abilitare IPv6 sull'interfaccia interna
    
   - Abilitare IPv4 sull'interfaccia esterna
    
   - Abilitare IPv6 sull'interfaccia esterna
    
   Tali indirizzi sono piuttosto evidenti, indipendentemente dal fatto che si utilizzino indirizzi IPv4 o IPv6 e si stiano applicando gli stessi all'interno o all'esterno del server perimetrale (è necessario tenerlo presente per il passaggio 10). È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. È possibile eseguire questa operazione scegliendo **l'indirizzo IP esterno del pool di server perimetrali viene convertito dalla casella di controllo NAT** . Quando pronto, fare clic su **Avanti** .
    
9. Nella schermata FQDN esterni, le scelte dipendono dalla selezione effettuata nel passaggio 7 sopra.
    
   - Se è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio **Access Edge SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere i tre FQDN esterni per il servizio **SIP Access** Edge, il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Al termine, fare clic su **Avanti**.
    
10. Si è ora nella schermata **definire l'indirizzo IP interno** . In questo articolo verrà digitato l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte riportate nel passaggio 8. Quando pronto, fare clic su **Avanti** .
    
11. Nella schermata **definire l'indirizzo IP esterno** , sono disponibili alcune opzioni in base alle scelte precedenti:
    
    - È possibile utilizzare un solo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quale si sta utilizzando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile scegliere di utilizzare tre nomi FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzamento IPv6, non verrà visualizzata la finestra di dialogo. Questo è normale, basta andare al passaggio successivo. 
  
12. Se si è scelto di utilizzare NAT nel passaggio 8, si otterrà una schermata con un controllo TextBox **indirizzo IP pubblico** . Sarà necessario immettere l'indirizzo IPv4 pubblico e/o IPv6 impostato per il servizio A/V Edge, che dovrà essere convertito da NAT. Scegliere il pulsante **Avanti**.
    
13. La schermata successiva è **definire l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front end o un pool autonomo. Se si dispone di un Director nell'ambiente in uso, è necessario scegliere il Director. Scegliere il pulsante **Avanti**.
    
14. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, compresi i pool Front end e i server Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare con questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È necessario tenere presente che, se i pool interni o i server autonomi utilizzano già un server perimetrale di Skype for Business Server diverso, non possono disporre di più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un messaggio di avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro server perimetrale si arresterà. 
  
15. Fare clic su **fine** nella schermata successiva.
    
16. A questo punto, è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni riportate in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) per la distribuzione al server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server perimetrali con bilanciamento del carico DNS

1. Accedere al server di Skype for Business Server Standard Edition o a un server front-end di Skype for Business Server.
    
2. Una volta lì, aprire **Generatore di topologie di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge** e quindi scegliere **nuovo pool di server perimetrali**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di server perimetrali** .
    
6. Nella schermata **definire l'FQDN del pool di server perimetrali** , digitare il nome di dominio completo (FQDN) interno che il pool di server perimetrali utilizzerà e selezionare **pool di più computer**, facendo clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
    - È possibile che si desideri utilizzare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la **casella di controllo utilizza un singolo FQDN e indirizzo IP** (e tenere presente il passaggio 9 in basso).
    
    - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per il pool di server perimetrali (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni disponibili sono le seguenti:
    
    - Abilitare IPv4 sull'interfaccia interna
    
   - Abilitare IPv6 sull'interfaccia interna
    
   - Abilitare IPv4 sull'interfaccia esterna
    
   - Abilitare IPv6 sull'interfaccia esterna
    
     Tali indirizzi sono piuttosto evidenti, indipendentemente dal fatto che si utilizzino indirizzi IPv4 o IPv6 e si stiano applicando gli stessi all'interno o all'esterno del server perimetrale (è necessario tenerlo presente per il passaggio 11). È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. È possibile eseguire questa operazione scegliendo **l'indirizzo IP esterno del pool di server perimetrali viene convertito dalla casella di controllo NAT** . Quando pronto, fare clic su **Avanti** .
    
9. Nella schermata FQDN esterni, le scelte dipendono dalla selezione effettuata nel passaggio 7 sopra.
    
   - Se è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio **Access Edge SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere i tre FQDN esterni per il servizio **SIP Access** Edge, il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Al termine, fare clic su **Avanti**.
    
10. A questo punto è stata raggiunta la schermata **define the computers in this pool** . Fare clic su **Aggiungi**.
    
11. Si è ora nella schermata **definire l'indirizzo IP interno** . In questo articolo verrà digitato l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte riportate nel passaggio 8. Quando pronto, fare clic su **Avanti** .
    
12. Nella schermata **definire l'indirizzo IP esterno** , sono disponibili alcune opzioni in base alle scelte precedenti:
    
    - È possibile utilizzare un solo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quale si sta utilizzando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile scegliere di utilizzare tre nomi FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzamento IPv6, non verrà visualizzata la finestra di dialogo. Questo è normale, basta andare al passaggio successivo. 
  
13. Fare clic su **Fine**. Il server perimetrale appena creato dovrebbe essere ora elencato nella finestra di dialogo **definire i computer in questo pool** .
    
14. Se si è ancora nella schermata **Definisci i computer in questo pool** , fare clic sul pulsante **Aggiungi** di nuovo e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si intende avere in questo pool. Al termine, fare clic su **Avanti**.
    
15. Se si è scelto di utilizzare NAT nel passaggio 8, si otterrà una schermata con un controllo TextBox **indirizzo IP pubblico** . Sarà necessario immettere l'indirizzo IPv4 pubblico e/o IPv6 impostato per il servizio A/V Edge, che dovrà essere convertito da NAT. Scegliere il pulsante **Avanti**.
    
16. La schermata successiva è **definire l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front end o un pool autonomo. Se si dispone di un Director nell'ambiente in uso, è necessario scegliere il Director. Scegliere il pulsante **Avanti**.
    
17. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, compresi i pool Front end e i pool Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare con questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È necessario tenere presente che, se i pool interni o i server autonomi utilizzano già un server perimetrale di Skype for Business Server diverso, non possono disporre di più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un messaggio di avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro server perimetrale si arresterà. 
  
18. Fare clic su **fine** nella schermata successiva.
    
19. A questo punto, è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni riportate in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) per la distribuzione al server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server perimetrali con bilanciamento del carico hardware

1. Accedere al server di Skype for Business Server Standard Edition o a un server front-end di Skype for Business Server.
    
2. Una volta lì, aprire **Generatore di topologie di Skype for Business Server**.
    
3. Nell'albero della console espandere il sito in cui si intende distribuire il server perimetrale.
    
4. Fare clic con il pulsante destro del mouse su pool **Edge** e quindi scegliere **nuovo pool di server perimetrali**.
    
5. Fare clic su **Avanti** nella schermata **Definisci nuovo pool di server perimetrali** .
    
6. Nella schermata **definire l'FQDN del pool di server perimetrali** , digitare il nome di dominio completo (FQDN) interno che il pool di server perimetrali utilizzerà e selezionare **pool di più computer**, facendo clic su **Avanti** al termine.
    
7. Nella schermata **Seleziona funzionalità** è possibile scegliere:
    
   - È possibile che si desideri utilizzare lo stesso FQDN e l'indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la **casella di controllo utilizza un singolo FQDN e indirizzo IP** (e tenere presente il passaggio 9 in basso).
    
   - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per il pool di server perimetrali (porta 5061)** .
    
8. Dopo aver fatto clic su **Avanti**, ti troverai nella schermata **opzioni IP** . Le opzioni disponibili sono le seguenti:
    
   - Abilitare IPv4 sull'interfaccia interna
    
   - Abilitare IPv6 sull'interfaccia interna
    
   - Abilitare IPv4 sull'interfaccia esterna
    
   - Abilitare IPv6 sull'interfaccia esterna
    
     Tali indirizzi sono piuttosto evidenti, indipendentemente dal fatto che si utilizzino indirizzi IPv4 o IPv6 e si stiano applicando gli stessi all'interno o all'esterno del server perimetrale (è necessario tenerlo presente per il passaggio 11).
    
     > [!NOTE]
     > A differenza delle altre due opzioni di topologia, quando si utilizza un dispositivo di bilanciamento del carico hardware, **non è necessario** selezionare l'opzione che **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**. Questo **non è supportato**.
  
9. Nella schermata FQDN esterni, le scelte dipendono dalla selezione effettuata nel passaggio 7 sopra.
    
   - Se è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere il nome di dominio completo esterno singolo nella casella **accesso SIP** . Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile 5061 per il servizio **Access Edge SIP** , 444 per il servizio **Web Conferencing** Edge e 443 per il servizio **A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo **utilizza un singolo FQDN e indirizzo IP** , è necessario immettere i tre FQDN esterni per il servizio **SIP Access** Edge, il servizio **Web Conferencing** Edge e il servizio **a/V** Edge. Al termine, fare clic su **Avanti**.
    
10. A questo punto è stata raggiunta la schermata **define the computers in this pool** . Fare clic su **Aggiungi**.
    
11. Si è ora nella schermata **definire l'indirizzo IP interno** . In questo articolo verrà digitato l'indirizzo IP del server perimetrale nelle caselle di testo **indirizzo IPv4 interno** e **indirizzo IPv6 interno** , a seconda delle scelte riportate nel passaggio 8. Quando pronto, fare clic su **Avanti** .
    
12. Nella schermata **definire l'indirizzo IP esterno** , sono disponibili alcune opzioni in base alle scelte precedenti:
    
    - È possibile utilizzare un solo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quale si sta utilizzando) nella casella di testo **accesso SIP** e quindi fare clic su **Avanti**.
    
    - È possibile scegliere di utilizzare tre nomi FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio **Access Edge SIP** , il servizio **Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se in precedenza non si è scelto di abilitare e assegnare l'indirizzamento IPv6, non verrà visualizzata la finestra di dialogo. Questo è normale, basta andare al passaggio successivo. 
  
13. Fare clic su **Fine**. Il server perimetrale appena creato dovrebbe essere ora elencato nella finestra di dialogo **definire i computer in questo pool** .
    
14. Se si è ancora nella schermata **Definisci i computer in questo pool** , fare clic sul pulsante **Aggiungi** di nuovo e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si intende avere in questo pool. Al termine, fare clic su **Avanti**.
    
15. La schermata successiva è **definire l'hop successivo**. Nella casella **pool hop successivo** selezionare il nome del pool interno, che potrebbe essere un pool Front end o un pool autonomo. Se si dispone di un Director nell'ambiente in uso, è necessario scegliere il Director. Scegliere il pulsante **Avanti**.
    
16. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, compresi i pool Front end e i pool Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare con questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È necessario tenere presente che, se i pool interni o i server autonomi utilizzano già un server perimetrale di Skype for Business Server diverso, non possono disporre di più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un messaggio di avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si procede con questa nuova associazione, la connessione all'altro server perimetrale si arresterà. 
  
17. Fare clic su **fine** nella schermata successiva.
    
18. A questo punto, è possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni riportate in [Deploy Edge Servers in Skype for Business Server](deploy-edge-servers.md) per la distribuzione al server perimetrale da qui.
    
## <a name="publish-your-edge-server-topology"></a>Pubblicare la topologia del server perimetrale

Dopo aver completato la procedura descritta in alto, è il momento di pubblicare la nuova topologia, che consentirà anche di esportarla nel server perimetrale o nel pool di server Edge di Skype for business. attenersi alla seguente procedura:
  
1. Avviare **Generatore di topologie** (se non è già stato avviato dalla procedura precedente).
    
2. In **Generatore di topologie**, nell'albero della console, fare clic con il pulsante destro del mouse su **Skype for Business Server** e quindi scegliere **Generatore di topologie di Skype for Business Server**.
    
3. Nella pagina iniziale della procedura guidata fare clic su **Avanti**.
    
4. Nella pagina **Crea database** fare clic su **Avanti**.
    
5. Quando lo stato indica che la creazione del database ha avuto esito positivo, eseguire le operazioni seguenti:
    
    - Per visualizzare il registro, fare clic su **Visualizza registro**.
    
    - Per chiudere la procedura guidata, fare clic su **Fine**.
    
## <a name="export-your-edge-server-topology"></a>Esportare la topologia del server perimetrale

Per eseguire correttamente la distribuzione, è necessario che l'installazione guidata di Skype for Business Server abbia accesso ai dati dell'archivio di gestione centrale. Per i server interni nel dominio o nella foresta, questo è in genere semplice. I server perimetrali si trovano all'esterno del dominio e pertanto è necessario esportare manualmente il file di topologia nel percorso del server perimetrale, in genere su un supporto fisico. Questa esportazione viene fatta tramite PowerShell:
  
1. Avviare la **Shell di gestione di Skype for Business Server**.
    
2. In **Skype for Business Server Management Shell**, eseguire le operazioni seguenti:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiare il file esportato in un supporto esterno, ad esempio un'unità USB o una condivisione di rete che è possibile raggiungere dalla posizione del server perimetrale.
    

