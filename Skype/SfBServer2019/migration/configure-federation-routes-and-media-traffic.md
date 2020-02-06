---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete. Dopo la migrazione al pool pilota, è necessario eseguire la transizione dalla Route federativo delle versioni precedenti dei server Edge alla route federativo dei server Edge di Skype for Business Server 2019.
ms.openlocfilehash: 71417307fd46c2c29535cea3a52f0286ad6dc951
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813814"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

Federation è una relazione di trust tra due o più domini SIP che consente agli utenti di organizzazioni separate di comunicare tra loro attraverso i confini della rete. Dopo la migrazione al pool pilota, è necessario eseguire la transizione dalla Route federativo della versione precedente di Edge Server alla route federativo di Skype for Business Server 2019 Edge Servers.
  
Usare le procedure seguenti per eseguire la transizione della route federativa e della route del traffico multimediale da Edge Server e Director della versione precedente al server Edge di Skype for Business Server 2019 per una distribuzione a sito singolo.
  
> [!IMPORTANT]
> Se si modifica la route della Federazione e il traffico multimediale, è necessario pianificare l'inattività di manutenzione per Skype for Business Server 2019 e i server Edge versione precedente. L'intero processo di transizione significa anche che l'accesso federato non sarà disponibile per la durata dell'interruzione. È consigliabile pianificare i tempi di inattività per un periodo di tempo in cui si prevede un'attività utente minima. Dovresti anche dare una notifica sufficiente agli utenti finali. Pianificare di conseguenza questa interruzione e impostare le aspettative appropriate all'interno dell'organizzazione. 
  
> [!IMPORTANT]
> Se il server perimetrale legacy è configurato per l'uso dello stesso nome di dominio completo per il servizio Access Edge, Web Conferencing Edge service e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate. Se i servizi Edge legacy sono configurati in modo da usare lo stesso nome di dominio completo, è necessario prima eseguire la migrazione di tutti gli utenti, quindi rimuovere il server Edge versioni precedenti prima di abilitare la Federazione in Skype for Business Server 2019 Edge Server. 
  
> [!IMPORTANT]
> Se la Federazione XMPP viene instradata tramite un server Edge di Skype for Business Server 2019, gli utenti della versione precedente non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Skype for Business Server 2019, i criteri XMPP e i certificati sono stati configurati, il partner federato XMPP è stato configurato in Skype for Business Server 2019 e, infine, le voci DNS sono state aggiornate. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Per rimuovere l'associazione di federazione legacy dai siti di Skype for Business Server 2019

1. Nel server front end di Skype for Business Server 2019 aprire la topologia esistente in Generatore di topologia. 
    
2. Nel riquadro sinistro passare al nodo del sito, che si trova direttamente sotto **Skype for Business Server**.
    
3. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.
    
4. Nel riquadro sinistro selezionare **Route federativo**. 
    
5. In **assegnazione della route federativo di sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route federativo nell'ambiente legacy. 
  
6. Fare clic su **OK** per chiudere la pagina Modifica proprietà. 
    
7. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**.
    
8. Nel menu **azione** fare clic su **Pubblica topologia**.
    
9. Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** quando il processo di pubblicazione è stato completato. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federativo

1. Nel riquadro sinistro passare al nodo di installazione legacy e quindi al nodo Pool di **bordi** . 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.
    
3. Selezionare **generale** nel riquadro sinistro. 
    
4. Deselezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e scegliere **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.
    
6. Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata. 
    
7. Verificare che la Federazione per il server perimetrale legacy sia disabilitata in Generatore di topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Per configurare i certificati nel server perimetrale legacy

1. Esportare il certificato del proxy di accesso esterno, con la chiave privata, dal server perimetrale legacy. 
    
2. In Skype for Business Server 2019 Edge Server e importare il certificato esterno del proxy di accesso dal passaggio precedente.
    
3. Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Skype for Business Server 2019 dell'Edge Server.
    
4. Il certificato di interfaccia interno di Skype for Business Server 2019 Edge Server deve essere richiesto da una CA attendibile e assegnato. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Per modificare la route federativo della versione precedente in uso di Skype for Business Server 2019 Edge Server

1. Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** . 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **modifica proprietà**.
    
3. Selezionare **generale** nel riquadro sinistro. 
    
4. Selezionare la casella di controllo **Abilita federazione per questo pool di bordi (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia**dal menu **azione** e quindi fare clic su **Avanti**.
    
6. Al termine della **pubblicazione guidata** , fare clic su **fine** per chiudere la procedura guidata. 
    
7. Verificare che **Federation (porta 5061)** sia impostato su **Enabled** in Generatore di topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Per aggiornare l'hop successivo della Federazione di Skype for Business Server 2019 Edge Server

1. Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** . 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**. 
    
3. Nella pagina **generale** , in **selezione hop successivo**, selezionare nell'elenco a discesa il pool di Skype for Business Server 2019.
  
4. Fare clic su **OK** per chiudere la pagina Modifica proprietà. 
    
5. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**. 
    
6. Nel menu **azione** fare clic su **Pubblica topologia** e completare la procedura guidata. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Per configurare il percorso multimediale in uscita di Skype for Business Server 2019 Edge Server

1. In Generatore di topologie, nel riquadro sinistro, passare al nodo **Skype for Business Server 2019** e quindi al pool sotto i **server front end Standard Edition** o i **pool Front-End di Enterprise Edition**.
    
2. Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.
    
3. Nella sezione **associazioni** selezionare la casella **di controllo Associa pool Edge (per componenti multimediali)** . 
  
4. Nella casella a discesa selezionare il server Edge di Skype for Business Server 2019.
    
5. Fare clic su **OK** per chiudere la pagina **modifica proprietà** . 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Per attivare la Federazione di Skype for Business Server 2019 Edge Server

1. Nel riquadro sinistro di generatore di topologia passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di bordi** . 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere **modifica proprietà**. 
    
    > [!NOTE]
    > La Federazione può essere abilitata solo per un singolo pool di Edge. Se si hanno più pool di bordi, selezionarne uno da usare come pool di bordi federativi. 
  
3. Nella pagina **generale** verificare che la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** sia selezionata. 
  
4. Fare clic su **OK** per chiudere la pagina Modifica proprietà. 
    
5. Passare al nodo del sito. 
    
6. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere **modifica proprietà**.
    
7. Nel riquadro sinistro fare clic su **Route federativo**.
    
8. In **assegnazione della route federativo di sito**selezionare **Abilita federazione SIP**e quindi nell'elenco selezionare il server Edge di Skype for Business Server 2019 elencato. 
  
9. Fare clic su **OK** per chiudere la pagina **modifica proprietà** . 
    
     Per le distribuzioni multisito, completare questa procedura in ogni sito. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche alla configurazione di Edge Server

1. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**. 
    
2. Nel menu **azione** selezionare **Pubblica topologia** e completare la procedura guidata. 
    
3. Attendere che la replica di Active Directory si verifichi in tutti i pool della distribuzione.
    
    > [!NOTE]
    > Potrebbe essere visualizzato il messaggio seguente: **Avviso: la topologia contiene più di un server perimetrale federato. Questo problema può verificarsi durante la migrazione a una versione più recente del prodotto. In questo caso, un solo server perimetrale verrebbe usato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si vuole distribuire più Edge Server federativo in modo che sia attivo contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Skype for Business Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati alla Federazione.** Questo avviso è previsto e può essere ignorato in modo sicuro. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Per configurare Skype for Business Server 2019 Edge Server

1. Porta tutti i server Edge di Skype for Business Server 2019 online. 
    
2. Aggiornare le regole di routing del firewall esterno o le impostazioni di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) a Skype for Business Server 2019 Edge Server, invece del server perimetrale legacy.
    
    > [!NOTE]
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record DNS per la Federazione per risolverlo nel nuovo server di Access Edge di Skype for Business Server. Per eseguire questa operazione con interruzioni minime, ridurre il valore di TLL per l'FQDN di Access Edge di Skype for Business Server esterno, in modo che quando il DNS viene aggiornato per puntare al nuovo Edge di Access di Skype for Business Server, la Federazione e l'accesso remoto verranno aggiornati rapidamente. 
  
3. Arrestare il **bordo di accesso di Skype for Business Server** da ogni computer Edge Server. 
    
4. Da ogni computer legacy Edge Server aprire l'applet **Servizi** dagli strumenti di **Amministrazione**.
    
5. Nell'elenco servizi individuare **Edge Access per Skype for Business Server**.
    
6. Fare clic con il pulsante destro del mouse sul nome dei servizi e quindi scegliere **Interrompi** per arrestare il servizio. 
    
7. Impostare il tipo di avvio su **disabled**. 
    
8. Fare clic su **OK** per chiudere la finestra **Proprietà** . 
    

