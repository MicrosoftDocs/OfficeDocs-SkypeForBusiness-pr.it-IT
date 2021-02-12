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
description: La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota, è necessario passare dalla route di federazione dei server perimetrali delle versioni precedenti alla route di federazione dei server perimetrali di Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754036"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Configurare le route di federazione e il traffico multimediale

La federazione è una relazione di trust tra due o più domini SIP che consente a utenti di organizzazioni distinte di comunicare attraverso i confini della rete. Dopo aver eseguito la migrazione al pool pilota, è necessario passare dalla route di federazione dei server perimetrali della versione precedente alla route di federazione dei server perimetrali di Skype for Business Server 2019.
  
Utilizzare le procedure seguenti per eseguire la transizione della route di federazione e del traffico multimediale dal server perimetrale e dal Director della versione precedente al server perimetrale Skype for Business Server 2019, per una distribuzione a sito singolo.
  
> [!IMPORTANT]
> La modifica della route di federazione e del traffico multimediale richiede la pianificazione dei tempi di inattività di manutenzione per i server perimetrali di Skype for Business Server 2019 e versione precedente. Il processo di transizione completo implica anche che l'accesso federato non sarà disponibile per l'intera durata dell'interruzione dei servizi. È consigliabile pianificare l'interruzione dei servizi in un lasso di tempo in cui si prevede un'attività minima da parte degli utenti. È inoltre consigliabile inviare notifica agli utenti con sufficiente anticipo. Pianificare adeguatamente l'interruzione dei servizi e fare in modo che le aspettative dell'organizzazione siano appropriate. 
  
> [!IMPORTANT]
> Se il server perimetrale legacy è configurato per l'utilizzo dello stesso FQDN per il servizio Access Edge, il servizio Web Conferencing Edge e il servizio A/V Edge, le procedure descritte in questa sezione non sono supportate. Se i servizi Edge legacy sono configurati per l'utilizzo dello stesso FQDN, è necessario prima eseguire la migrazione di tutti gli utenti, quindi rimuovere le versioni precedenti del server perimetrale prima di abilitare la federazione nel server perimetrale Skype for Business Server 2019. 
  
> [!IMPORTANT]
> Se la federazione XMPP viene instradata tramite un server perimetrale Skype for Business Server 2019, gli utenti della versione precedente non saranno in grado di comunicare con il partner federato XMPP finché tutti gli utenti non saranno stati spostati in Skype for Business Server 2019, i criteri e i certificati XMPP non saranno stati configurati, il partner federato XMPP è stato configurato in Skype for Business Server 2019 e, infine, le voci DNS sono state aggiornate. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Per rimuovere l'associazione di federazione legacy dai siti di Skype for Business Server 2019

1. Nel Front End Server di Skype for Business Server 2019 aprire la topologia esistente in Generatore di topologie. 
    
2. Nel riquadro sinistro passare al nodo del sito, che si trova direttamente sotto **Skype for Business Server.**
    
3. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà**.
    
4. Nel riquadro sinistro, selezionare **Route di federazione**. 
    
5. In **Assegnazione route federazione sito** deselezionare la casella di controllo Abilita federazione **SIP** per disabilitare la route di federazione attraverso l'ambiente legacy. 
  
6. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
7. In **Generatore di topologie** selezionare il nodo principale Skype for Business **Server.**
    
8. Scegliere **Pubblica topologia** dal menu **Azione**.
    
9. Fare **clic su** Avanti per completare il processo di pubblicazione e quindi su **Fine** al termine del processo di pubblicazione. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Per configurare il server perimetrale legacy come server perimetrale non federato

1. Nel riquadro sinistro passare al nodo di installazione legacy e quindi al nodo **Pool di server perimetrali.** 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.
    
3. Selezionare **Generale** nel riquadro sinistro. 
    
4. Deselezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061)** e selezionare **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
6. Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata. 
    
7. Verificare che la federazione per il server perimetrale legacy sia disabilitata in Generatore di topologie.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Per configurare i certificati nel server perimetrale legacy

1. Esportare il certificato del proxy di accesso esterno, con la chiave privata, dal server perimetrale legacy. 
    
2. Nel server perimetrale Skype for Business Server 2019 e importare il certificato esterno del proxy di accesso dal passaggio precedente.
    
3. Assegnare il certificato esterno del proxy di accesso all'interfaccia esterna di Skype for Business Server 2019 del server perimetrale.
    
4. Il certificato dell'interfaccia interna del server perimetrale Skype for Business Server 2019 deve essere richiesto a un'autorità di certificazione attendibile e assegnato. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Per modificare la route di federazione della versione precedente per l'utilizzo di Skype for Business Server 2019 Edge Server

1. Nel riquadro sinistro di Generatore di topologie passare al nodo **Skype for Business Server 2019** e quindi al nodo Pool di server **perimetrali.** 
    
2. Fare clic con il pulsante destro del mouse sul server perimetrale e quindi scegliere **Modifica proprietà**.
    
3. Selezionare **Generale** nel riquadro sinistro. 
    
4. Selezionare la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061)** e quindi fare clic su **OK** per chiudere la pagina. 
  
5. Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.
    
6. Al termine della **Pubblicazione guidata** fare clic su **Fine** per chiudere la procedura guidata. 
    
7. Verificare che **la federazione (porta 5061)** sia impostata su **Abilitato** in Generatore di topologie.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Per aggiornare l'hop successivo di federazione del server perimetrale di Skype for Business Server 2019

1. Nel riquadro sinistro di Generatore di topologie passare al nodo **Skype for Business Server 2019** e quindi al nodo Pool di server **perimetrali.** 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà**. 
    
3. On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.
  
4. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
5. In **Generatore di topologie** selezionare il nodo principale Skype for Business **Server.** 
    
6. Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Per configurare il percorso multimediale in uscita del server perimetrale di Skype for Business Server 2019

1. Nel riquadro sinistro di Generatore di topologie passare al nodo **Skype for Business Server 2019** e quindi al pool sotto Standard Edition Front End **Server** o Pool Enterprise Edition **Front End.**
    
2. Fare clic con il pulsante destro del mouse sul pool e quindi scegliere  **Modifica proprietà**.
    
3. Nella sezione  **Associazioni** selezionare la casella di controllo  **Associa pool di server perimetrali (per componenti multimediali)**. 
  
4. Dalla casella di riepilogo a discesa, selezionare il server perimetrale Skype for Business Server 2019.
    
5. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Per attivare la federazione dei server perimetrali di Skype for Business Server 2019

1. Nel riquadro sinistro di Generatore di topologie passare al nodo **Skype for Business Server 2019** e quindi al nodo Pool di server **perimetrali.** 
    
2. Espandere il nodo, fare clic con il pulsante destro del mouse sul server perimetrale elencato e quindi scegliere  **Modifica proprietà**. 
    
    > [!NOTE]
    > La federazione può essere abilitata solo per un singolo pool di server perimetrali. In presenza di più pool di server perimetrali, selezionarne uno da utilizzare come pool di server perimetrali federati. 
  
3. Nella pagina **Generale** verificare che la casella di controllo Abilita federazione per il pool di server perimetrali **(porta 5061)** sia selezionata. 
  
4. Fare clic su  **OK** per chiudere la pagina Modifica proprietà. 
    
5. Passare al nodo del sito. 
    
6. Fare clic con il pulsante destro del mouse sul sito e quindi scegliere  **Modifica proprietà**.
    
7. Nel riquadro sinistro fare clic su  **Route di federazione**.
    
8. In **Assegnazione route federazione sito** selezionare Abilita federazione **SIP** e quindi nell'elenco selezionare il server perimetrale Skype for Business Server 2019 elencato. 
  
9. Fare clic su  **OK** per chiudere la pagina  **Modifica proprietà**. 
    
     Nel caso di distribuzioni multisito, eseguire questa procedura in ogni sito. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Per pubblicare le modifiche di configurazione del server perimetrale

1. In **Generatore di topologie** selezionare il nodo principale Skype for Business **Server.** 
    
2. Scegliere **Pubblica topologia** dal menu **Azione** e completare la procedura guidata. 
    
3. Attendere il completamento della replica di Active Directory in tutti i pool della distribuzione.
    
    > [!NOTE]
    > È possibile che venga visualizzato il messaggio seguente: Avviso: La topologia contiene più di **un server perimetrale federato. Ciò può verificarsi durante la migrazione a una versione più recente del prodotto. In tal caso, per la federazione verrà utilizzato attivamente un solo server perimetrale. Verificare che il record DNS SRV esterno punti al server perimetrale corretto. Se si desidera distribuire più server perimetrali federativi per essere attivi contemporaneamente (ovvero non uno scenario di migrazione), verificare che tutti i partner federati utilizzino Skype for Business Server. Verificare che il record DNS SRV esterno elenchi tutti i server perimetrali abilitati per la federazione.** Si tratta di un avviso previsto che può essere tranquillamente ignorato. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Per configurare il server perimetrale di Skype for Business Server 2019

1. Portare online tutti i server perimetrali di Skype for Business Server 2019. 
    
2. Aggiornare le regole di routing del firewall esterno o le impostazioni del servizio di bilanciamento del carico hardware per inviare il traffico SIP per l'accesso esterno (in genere la porta 443) e la federazione (in genere la porta 5061) al server perimetrale Skype for Business Server 2019, anziché al server perimetrale legacy.
    
    > [!NOTE]
    > Se non si dispone di un servizio di bilanciamento del carico hardware, è necessario aggiornare il record A DNS per la federazione per risolvere il nuovo server Access Edge di Skype for Business Server. Per ottenere questo risultato con un'interruzione minima, ridurre il valore TLL per l'FQDN Access Edge di Skype for Business Server esterno in modo che, quando IL DNS viene aggiornato per puntare al nuovo Skype for Business Server Access Edge, la federazione e l'accesso remoto verranno aggiornati rapidamente. 
  
3. Arrestare **l'Access Edge di Skype for Business Server** da ogni computer Edge Server. 
    
4. Da ogni computer server perimetrale legacy aprire l'applet **Servizi** da **Strumenti di amministrazione.**
    
5. Nell'elenco dei servizi, trovare **Skype for Business Server Access Edge.**
    
6. Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Arresta** per arrestarlo. 
    
7. Impostare il tipo di avvio su **Disabilitato**. 
    
8. Fare clic su  **OK** per chiudere la finestra **Proprietà**. 
    

