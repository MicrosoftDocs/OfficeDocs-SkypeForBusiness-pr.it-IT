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
  
Generatore di topologie è lo strumento che è necessario utilizzare per creare la topologia di server perimetrali, proprio come viene usato per qualsiasi componente della topologia per Skype for Business Server. Prima di eseguire la procedura seguente, è necessario configurare almeno un pool Front End o un server Standard Edition.
  
In questo articolo vengono trattati i seguenti argomenti:
  
- Creare la topologia dei server perimetrali
    
- Pubblicare la topologia dei server perimetrali
    
- Esportare la topologia dei server perimetrali
    
  > [!NOTE]
  > Per eseguire la procedura seguente, è necessario accedere ai server di dominio indicati di seguito come utente membro dei gruppi di dominio seguenti: 
  
- RTCUniversalServerAdmins
    
- Domain Admins
    
## <a name="build-your-edge-server-topology"></a>Creare la topologia dei server perimetrali

Il primo passaggio di distribuzione consiste nella creazione della topologia di Server perimetrale di Skype for Business Server, costituita da una delle tre opzioni seguenti:
  
- Un singolo server perimetrale
    
- Un pool di server perimetrali con bilanciamento del carico DNS (uno o più server)
    
- Un pool di server perimetrali con bilanciamento del carico hardware (uno o più server)
    
Se non si è sicuri di cosa è necessario, prima di iniziare a eseguire questa procedura, è il momento di consultare la documentazione relativa alla pianificazione. In caso contrario, iniziamo.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definizione della topologia per un singolo server perimetrale

1. Accedere al server Skype for Business Server Standard Edition o a un pool Front End di Skype for Business Server.
    
2. Una volta lì, aprire Generatore di topologie **di Skype for Business Server.**
    
3. Nell'albero della console espandere il sito in cui si desidera distribuire il server perimetrale.
    
4. Fare clic con il **pulsante destro del** mouse su Pool di server perimetrali e quindi scegliere Nuovo pool di server **perimetrali.**
    
5. Nella schermata **Definisci** nuovo pool di server perimetrali fare clic su **Avanti.**
    
6. Nella schermata Definire l'FQDN del **pool** di server perimetrali digitare il nome di dominio completo  (FQDN) interno che verrà utilizzato dal server perimetrale e selezionare Pool **di computer** singolo facendo clic su Avanti al termine dell'operazione.
    
7. Nella schermata **Selezione funzionalità** è possibile scegliere tra le opzioni seguenti:
    
   - È possibile che si intenda utilizzare lo stesso FQDN e lo stesso indirizzo IP per il servizio accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la casella di controllo Usa un singolo FQDN e indirizzo **IP** (e tenere presente questo passaggio per il passaggio 9 di seguito)
    
   - Se si prevede di abilitare la federazione, selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061).**
    
8. Dopo aver fatto clic su **Avanti,** ti troverai nella schermata **Opzioni IP.** Le opzioni disponibili sono le seguenti:
    
   - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
   Questi indirizzi sono piuttosto auto-esplicativi, sia che si utilizzino indirizzi IPv4 o IPv6 e che si applicino tali indirizzi al server perimetrale internamente o esternamente (è necessario tenere presente questo passaggio per il passaggio 10). È inoltre possibile configurare il server perimetrale o il pool di server perimetrali per l'utilizzo di un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. A tale scopo, selezionare la casella di controllo L'indirizzo IP esterno di questo pool di server perimetrali viene **convertito da NAT.** Quando **si è** pronti, fare clic su Avanti.
    
9. Nella schermata FQDN esterni, le scelte effettuate dipendono dalla selezione effettuata nel passaggio 7 precedente.
    
   - Se è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** è necessario immettere il singolo FQDN esterno nella **casella Accesso SIP.** Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile utilizzare 5061 per il servizio Access Edge **SIP,** 444 per il servizio **Web Conferencing** Edge e 443 per il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** sarà necessario immettere i tre FQDN esterni per il servizio Access Edge **SIP,** il servizio **Web Conferencing** Edge e il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
10. You're now on the **Define the Internal IP address** screen. Qui si digita l'indirizzo IP del server perimetrale nelle caselle di testo Indirizzo **IPv4** interno e Indirizzo **IPv6** interno, a seconda delle scelte effettuate nel passaggio 8. Quando **si è** pronti, fare clic su Avanti.
    
11. Nella schermata **Definire l'indirizzo IP** esterno sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - È possibile utilizzare un singolo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quello in uso) nella casella di testo Accesso **SIP** e quindi fare clic su **Avanti.**
    
    - È possibile che si sia scelto di utilizzare tre FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio Access Edge **SIP,** il **servizio Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti.**
    
    > [!NOTE]
    > Se in precedenza non è stato scelto di abilitare e assegnare l'indirizzamento IPv6, questa finestra di dialogo non verrà visualizzata. È normale, basta andare al passaggio successivo. 
  
12. Se si è scelto di utilizzare NAT nel passaggio 8, verrà visualizzata una schermata con una casella di testo Indirizzo **IP** pubblico. Sarà necessario immettere l'indirizzo IPv4 pubblico e/o IPv6 impostato per il servizio A/V Edge, da convertire tramite NAT. Scegliere il pulsante **Avanti**.
    
13. La schermata successiva è **Definire l'hop successivo.** Nella casella **Pool hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool autonomo. Se si dispone di un Director nell'ambiente, è consigliabile scegliere il Director. Scegliere il pulsante **Avanti**.
    
14. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, inclusi pool Front End e server Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È importante tenere presente che se i pool interni o i server autonomi usano già un server perimetrale Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si continua con questa nuova associazione, la connessione all'altro server perimetrale verrà interrotta. 
  
15. Fare **clic** su Fine nella schermata successiva.
    
16. Ora sarà possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni in Distribuire server perimetrali [in Skype for Business Server](deploy-edge-servers.md) per la distribuzione nel server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server perimetrali con bilanciamento del carico DNS

1. Accedere al server Skype for Business Server Standard Edition o a un Front End Server di Skype for Business Server.
    
2. Una volta lì, aprire Generatore di topologie **di Skype for Business Server.**
    
3. Nell'albero della console espandere il sito in cui si desidera distribuire il server perimetrale.
    
4. Fare clic con il **pulsante destro del** mouse su Pool di server perimetrali e quindi scegliere Nuovo pool di server **perimetrali.**
    
5. Nella schermata **Definisci** nuovo pool di server perimetrali fare clic su **Avanti.**
    
6. Nella schermata Definire l'FQDN del **pool** di server perimetrali digitare il nome di dominio completo  (FQDN) interno che verrà utilizzato dal pool di server perimetrali e selezionare Pool di **più computer** e fare clic su Avanti al termine.
    
7. Nella schermata **Selezione funzionalità** è possibile scegliere tra le opzioni seguenti:
    
    - È possibile che si intenda utilizzare lo stesso FQDN e lo stesso indirizzo IP per il servizio Accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la casella di controllo Usa un singolo FQDN e indirizzo **IP** (e tenere presente questo passaggio per il passaggio 9 di seguito)
    
    - Se si prevede di abilitare la federazione, selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061).**
    
8. Dopo aver fatto clic su **Avanti,** ti troverai nella schermata **Opzioni IP.** Le opzioni disponibili sono le seguenti:
    
    - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
     Questi indirizzi sono piuttosto auto-esplicativi, sia che si utilizzino indirizzi IPv4 o IPv6 e che si applicino tali indirizzi al server perimetrale internamente o esternamente (è necessario tenere presente questo passaggio per il passaggio 11). È inoltre possibile configurare il server perimetrale o il pool di server perimetrali per l'utilizzo di un indirizzo NAT (Network Address Translation) per l'indirizzo IP esterno. A tale scopo, selezionare la casella di controllo L'indirizzo IP esterno di questo pool di server perimetrali viene **convertito da NAT.** Quando **si è** pronti, fare clic su Avanti.
    
9. Nella schermata FQDN esterni, le scelte effettuate dipendono dalla selezione effettuata nel passaggio 7 precedente.
    
   - Se è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** è necessario immettere il singolo FQDN esterno nella **casella Accesso SIP.** Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile utilizzare 5061 per il servizio Access Edge **SIP,** 444 per il servizio **Web Conferencing** Edge e 443 per il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** sarà necessario immettere i tre FQDN esterni per il servizio Access Edge **SIP,** il servizio **Web Conferencing** Edge e il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
10. Ora hai raggiunto la schermata **Definisci i computer in questo pool.** Fare clic su **Aggiungi**.
    
11. You're now on the **Define the Internal IP address** screen. Qui si digita l'indirizzo IP del server perimetrale nelle caselle di testo Indirizzo **IPv4** interno e Indirizzo **IPv6** interno, a seconda delle scelte effettuate nel passaggio 8. Quando **si è** pronti, fare clic su Avanti.
    
12. Nella schermata **Definire l'indirizzo IP** esterno sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - È possibile utilizzare un singolo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quello in uso) nella casella di testo Accesso **SIP** e quindi fare clic su **Avanti.**
    
    - È possibile che si sia scelto di utilizzare tre FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio Access Edge **SIP,** il **servizio Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti.**
    
    > [!NOTE]
    > Se in precedenza non è stato scelto di abilitare e assegnare l'indirizzamento IPv6, questa finestra di dialogo non verrà visualizzata. È normale, basta andare al passaggio successivo. 
  
13. Fare clic su **Fine**. Il server perimetrale appena creato dovrebbe essere elencato nella finestra di dialogo **Definisci i computer nel pool.**
    
14. Ancora nella schermata Definisci i computer in  questo **pool,** fare di nuovo clic sul pulsante Aggiungi e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si intende avere nel pool. Al termine, fare clic su **Avanti.**
    
15. Se si è scelto di utilizzare NAT nel passaggio 8, verrà visualizzata una schermata con una casella di testo Indirizzo **IP** pubblico. Sarà necessario immettere l'indirizzo IPv4 pubblico e/o IPv6 impostato per il servizio A/V Edge, da convertire tramite NAT. Scegliere il pulsante **Avanti**.
    
16. La schermata successiva è **Definire l'hop successivo.** Nella casella **Pool hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool autonomo. Se si dispone di un Director nell'ambiente, è consigliabile scegliere il Director. Scegliere il pulsante **Avanti**.
    
17. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, inclusi i pool Front End e i pool Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È importante tenere presente che se i pool interni o i server autonomi usano già un server perimetrale Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si continua con questa nuova associazione, la connessione all'altro server perimetrale verrà interrotta. 
  
18. Fare **clic** su Fine nella schermata successiva.
    
19. Ora sarà possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni in Distribuire server perimetrali [in Skype for Business Server](deploy-edge-servers.md) per la distribuzione nel server perimetrale da qui.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definizione della topologia per un pool di server perimetrali con bilanciamento del carico hardware

1. Accedere al server Skype for Business Server Standard Edition o a un Front End Server di Skype for Business Server.
    
2. Una volta lì, aprire Generatore di topologie **di Skype for Business Server.**
    
3. Nell'albero della console espandere il sito in cui si desidera distribuire il server perimetrale.
    
4. Fare clic con il **pulsante destro del** mouse su Pool di server perimetrali e quindi scegliere Nuovo pool di server **perimetrali.**
    
5. Nella schermata **Definisci** nuovo pool di server perimetrali fare clic su **Avanti.**
    
6. Nella schermata Definire l'FQDN del **pool** di server perimetrali digitare il nome di dominio completo  (FQDN) interno che verrà utilizzato dal pool di server perimetrali e selezionare Pool di **più computer** e fare clic su Avanti al termine.
    
7. Nella schermata **Selezione funzionalità** è possibile scegliere tra le opzioni seguenti:
    
   - È possibile che si intenda utilizzare lo stesso FQDN e lo stesso indirizzo IP per il servizio Accesso SIP, il servizio Web Conferencing di Skype for Business Server e il servizio A/V Edge. In tal caso, è necessario scegliere la casella di controllo Usa un singolo FQDN e indirizzo **IP** (e tenere presente questo passaggio per il passaggio 9 di seguito)
    
   - Se si prevede di abilitare la federazione, selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061).**
    
8. Dopo aver fatto clic su **Avanti,** ti troverai nella schermata **Opzioni IP.** Le opzioni disponibili sono le seguenti:
    
   - Abilitare IPv4 nell'interfaccia interna
    
   - Abilitare IPv6 nell'interfaccia interna
    
   - Abilitare IPv4 nell'interfaccia esterna
    
   - Abilitare IPv6 nell'interfaccia esterna
    
     Questi indirizzi sono piuttosto auto-esplicativi, sia che si utilizzino indirizzi IPv4 o IPv6 e che si applicino tali indirizzi al server perimetrale internamente o esternamente (è necessario tenere presente questo passaggio per il passaggio 11).
    
     > [!NOTE]
     > A differenza delle altre due opzioni di topologia,  quando si utilizza un servizio di bilanciamento del carico hardware, NON è necessario selezionare l'opzione L'indirizzo IP esterno del pool di server perimetrali viene **convertito da NAT.** Questa opzione **non è supportata.**
  
9. Nella schermata FQDN esterni, le scelte effettuate dipendono dalla selezione effettuata nel passaggio 7 precedente.
    
   - Se è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** è necessario immettere il singolo FQDN esterno nella **casella Accesso SIP.** Sarà quindi necessario immettere numeri di porta diversi per ogni servizio perimetrale per consentire a tutti di connettersi in modo indipendente. È consigliabile utilizzare 5061 per il servizio Access Edge **SIP,** 444 per il servizio **Web Conferencing** Edge e 443 per il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
   - Se non è stata selezionata la casella di controllo Usa un singolo FQDN e indirizzo **IP,** sarà necessario immettere i tre FQDN esterni per il servizio Access Edge **SIP,** il servizio **Web Conferencing** Edge e il **servizio A/V** Edge. Al termine, fare clic su **Avanti**.
    
10. Ora hai raggiunto la schermata **Definisci i computer in questo pool.** Fare clic su **Aggiungi**.
    
11. You're now on the **Define the Internal IP address** screen. Qui si digita l'indirizzo IP del server perimetrale nelle caselle di testo Indirizzo **IPv4** interno e Indirizzo **IPv6** interno, a seconda delle scelte effettuate nel passaggio 8. Quando **si è** pronti, fare clic su Avanti.
    
12. Nella schermata **Definire l'indirizzo IP** esterno sono disponibili alcune opzioni a seconda delle scelte precedenti:
    
    - È possibile utilizzare un singolo FQDN per tutti i servizi. In tal caso, digitare l'indirizzo IPv4 o IPv6 esterno (a seconda di quello in uso) nella casella di testo Accesso **SIP** e quindi fare clic su **Avanti.**
    
    - È possibile che si sia scelto di utilizzare tre FQDN e indirizzi IP distinti per i servizi. In tal caso, immettere gli indirizzi IPv4 o IPv6 esterni per il servizio Access Edge **SIP,** il **servizio Web Conferencing** Edge e il servizio **A/V** Edge e quindi fare clic su **Avanti.**
    
    > [!NOTE]
    > Se in precedenza non è stato scelto di abilitare e assegnare l'indirizzamento IPv6, questa finestra di dialogo non verrà visualizzata. È normale, basta andare al passaggio successivo. 
  
13. Fare clic su **Fine**. Il server perimetrale appena creato dovrebbe essere elencato nella finestra di dialogo **Definisci i computer nel pool.**
    
14. Ancora nella schermata Definisci i computer in  questo **pool,** fare di nuovo clic sul pulsante Aggiungi e ripetere i passaggi da 11 a 13 fino a quando non sono stati aggiunti tutti i server perimetrali che si intende avere nel pool. Al termine, fare clic su **Avanti.**
    
15. La schermata successiva è **Definire l'hop successivo.** Nella casella **Pool hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool autonomo. Se si dispone di un Director nell'ambiente, è consigliabile scegliere il Director. Scegliere il pulsante **Avanti**.
    
16. Nella schermata **Associa pool Front End** è necessario specificare uno o più pool interni, inclusi i pool Front End e i pool Standard Edition, da associare a questo server perimetrale. È sufficiente scegliere i nomi dei pool interni che si desidera utilizzare questo server perimetrale per comunicare con gli utenti esterni supportati. Fare clic su **Avanti**.
    
    > [!NOTE]
    > È importante tenere presente che se i pool interni o i server autonomi usano già un server perimetrale Skype for Business Server diverso, non possono avere più associazioni. Se si sceglie un pool interno o un server autonomo in tale situazione, verrà visualizzato un avviso che indica l'altro server perimetrale ed è possibile decidere se continuare o meno. Se si continua con questa nuova associazione, la connessione all'altro server perimetrale verrà interrotta. 
  
17. Fare **clic** su Fine nella schermata successiva.
    
18. Ora sarà possibile pubblicare questa tecnologia aggiornata e seguire le istruzioni in Distribuire server perimetrali [in Skype for Business Server](deploy-edge-servers.md) per la distribuzione nel server perimetrale da qui.
    
## <a name="publish-your-edge-server-topology"></a>Pubblicare la topologia dei server perimetrali

Dopo aver completato i passaggi precedenti, è il momento di pubblicare questa nuova topologia, che consentirà anche di esportarla nel server perimetrale o nel pool di server perimetrali di Skype for Business Server. attenersi alla seguente procedura:
  
1. Avviare **Generatore di topologie** (se non è già stato avviato dalla procedura precedente).
    
2. In **Generatore di topologie,** nell'albero della console, fare clic con il pulsante destro del mouse su **Skype for Business Server** e quindi scegliere Generatore di topologie di Skype for **Business Server.**
    
3. Nella pagina iniziale della procedura guidata fare clic su **Avanti**.
    
4. Nella pagina **Crea database** fare clic su **Avanti**.
    
5. Quando lo stato indica che la creazione del database ha avuto esito positivo, eseguire le operazioni seguenti:
    
    - Per visualizzare il registro, fare clic su **Visualizza registro**.
    
    - Per chiudere la procedura guidata, fare clic su **Fine**.
    
## <a name="export-your-edge-server-topology"></a>Esportare la topologia dei server perimetrali

Per la distribuzione corretta, la Distribuzione guidata di Skype for Business Server deve accedere ai dati dell'archivio di gestione centrale. Per i server interni nel dominio o nella foresta, questo in genere è semplice. I server perimetrali sono esterni al dominio e pertanto è necessario esportare manualmente il file della topologia nel percorso del server perimetrale, in genere su un supporto fisico. Questa esportazione viene eseguita tramite PowerShell:
  
1. Avviare **Skype for Business Server Management Shell.**
    
2. In **Skype for Business Server Management Shell,** eseguire le operazioni seguenti:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiare il file esportato in un supporto esterno(ad esempio, un'unità USB o una condivisione di rete raggiungibile dalla posizione del server perimetrale).
    

