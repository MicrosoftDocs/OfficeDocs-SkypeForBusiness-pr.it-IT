---
title: Configurare le route di federazione e il traffico multimediale
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali delle versioni precedenti alla route di Federazione dei server perimetrali di Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754036"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota, è necessario eseguire la transizione dalla route di Federazione dei server perimetrali della versione precedente alla route di Federazione dei server perimetrali di Skype for Business Server 2019.
  
Utilizzare le procedure seguenti per eseguire la transizione della route di Federazione e della route del traffico multimediale dal server perimetrale e dal Director della versione precedente al server perimetrale di Skype for Business Server 2019 per una distribuzione a sito singolo.
  
> [!IMPORTANT]
> La modifica della route di Federazione e della route del traffico multimediale richiede la pianificazione di tempi di inattività di manutenzione per i server Edge di Skype for Business Server 2019 e versioni precedenti. Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi. È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti. È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo. Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate. 
  
> [!IMPORTANT]
> Se il server perimetrale legacy è configurato in modo da utilizzare lo stesso nome di dominio completo per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate. Se i servizi perimetrali legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti, quindi rimuovere il server perimetrale versioni precedenti prima di abilitare la Federazione sul server perimetrale di Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se la Federazione XMPP viene instradata attraverso un server perimetrale di Skype for Business Server 2019, gli utenti della versione precedente non potranno comunicare con il partner federato XMPP finché tutti gli utenti non sono stati spostati in Skype for Business Server 2019, sono stati configurati i criteri e i certificati XMPP, il partner federato XMPP è stato configurato su Skype for Business Server 2019 e, infine, le voci DNS sono state aggiornate. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Per rimuovere l'associazione di federazione legacy dai siti di Skype for Business Server 2019

1. Nel server front end di Skype for Business Server 2019 aprire la topologia esistente in Generatore di topologie. 
    
2. Nel riquadro sinistro, passare al nodo del sito, che si trova direttamente sotto **Skype for Business Server**.
    
3. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà **.
    
4. Nel riquadro sinistro, selezionare **Route di federazione**. 
    
5. In **Assegnazione route federazione sito**deselezionare la casella di controllo **Abilita federazione SIP** per disabilitare la route di federazione tramite l'ambiente legacy. 
  
6. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
7. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**.
    
8. Scegliere **Pubblica topologia** dal menu **Azione**.
    
9. Fare clic su **Avanti** per completare il processo di pubblicazione e quindi fare clic su **fine** al termine del processo di pubblicazione. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federato

1. Nel riquadro sinistro passare al nodo installazione legacy e quindi al nodo **pool di server perimetrali** . 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.
    
3. Selezionare **Generale** nel riquadro sinistro. 
    
4. Deselezionare la casella di controllo **Abilita federazione per questo pool di server perimetrali (porta 5061)** e selezionare **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
6. Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata. 
    
7. Verificare che la Federazione per il server perimetrale legacy sia disabilitata in Generatore di topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Per configurare i certificati nel server perimetrale legacy

1. Esportare il certificato del proxy di accesso esterno con la chiave privata dal server perimetrale legacy. 
    
2. Sul server perimetrale di Skype for Business Server 2019 e importare il certificato esterno del proxy di accesso dal passaggio precedente.
    
3. Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Skype for Business Server 2019 del server perimetrale.
    
4. Il certificato dell'interfaccia interna del server perimetrale Skype for Business Server 2019 deve essere richiesto da un'autorità di certificazione attendibile e assegnato. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Per modificare la route di Federazione della versione precedente per l'utilizzo del server perimetrale di Skype for Business Server 2019

1. In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** . 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.
    
3. Selezionare **Generale** nel riquadro sinistro. 
    
4. Selezionare la casella di controllo **Abilita federazione per questo pool di server perimetrali (porta 5061)** e quindi fare clic su **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
6. Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata. 
    
7. Verificare che la **Federazione (porta 5061)** sia impostata su **attivata** in Generatore di topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Per aggiornare l'hop successivo di Federazione del server Edge di Skype for Business Server 2019

1. In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** . 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà **. 
    
3. In **selezione hop successivo**nella pagina **generale** selezionare dall'elenco a discesa il pool di Skype for Business Server 2019.
  
4. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
5. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**. 
    
6. Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Per configurare il percorso multimediale in uscita di Skype for Business Server 2019 Edge Server

1. In Generatore di topologie, nel riquadro sinistro, passare al nodo **Skype for Business Server 2019** e quindi al pool al di sotto di **Standard Edition Front End Server** o **pool Enterprise Edition front end**.
    
2. Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà **.
    
3. Nella sezione  **Associazioni ** selezionare la casella di controllo  **Associa pool di server perimetrali (per componenti multimediali) **. 
  
4. Nella casella a discesa selezionare il server perimetrale di Skype for Business Server 2019.
    
5. Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Per abilitare la Federazione del server perimetrale di Skype for Business Server 2019

1. In Generatore di topologie, nel riquadro sinistro, passare al nodo di **Skype for Business Server 2019** e quindi al nodo **pool di Edge** . 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà **. 
    
    > [!NOTE]
    > La Federazione può essere abilitata solo per un singolo pool di server perimetrali. In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati. 
  
3. Nella pagina **generale** verificare che sia selezionata la casella **di controllo Abilita federazione per il pool di server perimetrali (porta 5061)** . 
  
4. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
5. Passare al nodo del sito. 
    
6. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà **.
    
7. Nel riquadro sinistro fare clic su  **Route di federazione **.
    
8. In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il server perimetrale di Skype for Business Server 2019 nell'elenco. 
  
9. Fare clic su  **OK ** per chiudere la pagina  **Modifica proprietà **. 
    
     Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche di configurazione del server perimetrale

1. In **Generatore di topologie**selezionare il nodo principale **di Skype for Business Server**. 
    
2. Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata. 
    
3. Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.
    
    > [!NOTE]
    > È possibile che venga visualizzato il messaggio seguente: **Avviso: la topologia contiene più server perimetrali federati. Ciò può verificarsi durante la migrazione a una versione più recente del prodotto. In tal caso, solo un server perimetrale verrebbe utilizzato attivamente per la Federazione. Verificare che il record SRV DNS esterno punti al server perimetrale corretto. Se si desidera distribuire più server perimetrale federativo affinché siano attivi contemporaneamente, ovvero non uno scenario di migrazione, verificare che tutti i partner federati utilizzino Skype for Business Server. Verificare che il record SRV DNS esterno elenchi tutti i server perimetrali abilitati per la Federazione.** Si tratta di un avviso previsto che può essere tranquillamente ignorato. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Per configurare il server perimetrale di Skype for Business Server 2019

1. Portare online tutti i server Edge di Skype for Business Server 2019. 
    
2. Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware in modo da inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la Federazione (in genere la porta 5061) al server perimetrale di Skype for Business Server 2019, anziché al server perimetrale legacy.
    
    > [!NOTE]
    > Se non si dispone di un dispositivo di bilanciamento del carico hardware, è necessario aggiornare il record DNS a per la Federazione per risolvere il nuovo server Access Edge di Skype for Business Server. Per ottenere questo risultato con interruzioni minime, ridurre il valore TLL per l'FQDN del server di accesso esterno di Skype for business, in modo che quando DNS viene aggiornato per puntare al nuovo Edge di accesso di Skype for Business Server, la Federazione e l'accesso remoto vengano aggiornati rapidamente. 
  
3. Arrestare il **server perimetrale di accesso di Skype for business** da ogni computer server perimetrale. 
    
4. Da ogni computer server perimetrale legacy, aprire l'applet **Servizi** dagli **strumenti di amministrazione**.
    
5. Nell'elenco dei servizi, trova **Access Edge di Skype for Business Server**.
    
6. Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestarlo. 
    
7. Impostare il tipo di avvio su **Disabilitato**. 
    
8. Fare clic su  **OK ** per chiudere la finestra **Proprietà **. 
    

