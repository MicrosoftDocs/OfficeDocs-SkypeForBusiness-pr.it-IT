---
title: Distribuire un Mediation Server in Generatore di topologie in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Riepilogo: informazioni su come definire e distribuire un Mediation Server in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 852571234b531fddfbd55cce6444f4f00abc95fe97567a58fb7829f29c5a0701
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323508"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Distribuire un Mediation Server in Generatore di topologie in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire e distribuire un Mediation Server in Generatore di topologie in Skype for Business Server.
  
Il carico di lavoro VoIP aziendale, le conferenze telefoniche con accesso esterno e le applicazioni VoIP aziendale avanzate (applicazione Response Group, applicazione Parcheggio di chiamata, controllo di ammissione di chiamata e così via) sono disponibili nei pool Front End. La funzionalità del Mediation Server è incorporata nel Front End Server. Non è necessario un Mediation Server autonomo separato. 
  
L'unica eccezione è rappresentata dalla configurazione di un trunk SIP per la connessione a un Session Border Controller per un provider di servizi di telefonia Internet (ITSP). Per connettere l'VoIP aziendale di rete al provider trunk SIP, è necessario distribuire un Mediation Server separato.
  
La connessione tra Skype for Business Server (un Mediation Server collocato in un pool Front End o un Mediation Server autonomo) e un gateway è definito come un'associazione logica denominata trunk. Negli argomenti di questa sezione viene illustrato come definire un trunk e come distribuire un Mediation Server autonomo se si effettua la connessione a un trunk SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definire un Mediation Server in Generatore di topologie

È possibile aggiungere Mediation Server come ruolo collocato in un pool Front End o definire un pool Mediation Server autonomo separato.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Per aggiungere un Mediation Server a un pool Front End

1. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Skype for Business Server Generatore di topologie **2015**.
    
2. Nell'albero della console di Generatore di topologie espandere il nome del sito per cui si desidera definire un pool Front End.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front End desiderato e quindi scegliere **Nuovo pool Front End.**.
    
4. Scorrere i vari passaggi della procedura guidata **Definisci nuovo pool Front End** fino a raggiungere la pagina **Selezionare ruoli server collocati**.
    
5. In **Seleziona ruoli server collocati** selezionare l'opzione Colloca Mediation **Server**.
    
    > [!NOTE]
    > Se il tipo di pool Front End selezionato è il edizione Enterprise, il componente Mediation Server verrà installato in tutti i Front End Server del pool Front End. 
  
    > [!NOTE]
    > Il **pool hop successivo** utilizzato dal Mediation Server sarà il pool Front End in cui è collocato il Mediation Server.
  
    > [!NOTE]
    > Il **pool di server** perimetrali utilizzato dal Mediation Server sarà lo stesso pool di server perimetrali associato al pool Front End in cui è collocato il Mediation Server.
  
6. Fare **clic su Rendi** predefinito per utilizzare questo pool Front End per instradare le chiamate alla rete PSTN.
    
7. Al **termine** dell'associazione di uno o più peer al pool Front End, fare clic su Fine.
    
    > [!NOTE]
    > Prima di procedere con il passaggio successivo del processo di distribuzione di VoIP aziendale, verificare che il pool Mediation Server (ad esempio, il pool Front End con il componente Mediation Server collocato) utilizzi gli FQDN specificati. 
  
8. Fare clic con il pulsante **destro del Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Per aggiungere un Mediation Server autonomo

1. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Skype for Business Server Generatore di topologie **2015**.
    
2. Nell'albero della console di Generatore di topologie espandere il nome del sito per cui si desidera definire un Mediation Server.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **Pool Mediation** Server e quindi scegliere Pool **Mediation Server**.
    
4. In **Definisci nuovo pool Mediation Server** digitare il nome di dominio completo (FQDN) del pool Mediation Server.
    
5. Eseguire quindi una delle operazioni seguenti:
    
   - Se si desidera distribuire più Mediation Server nel pool per garantire la disponibilità elevata, selezionare **Pool di più computer.**
    
     > [!NOTE]
     > È necessario [eseguire la](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) distribuzione per supportare pool Mediation Server con più Mediation Server.
  
   - Se si desidera distribuire un solo Mediation Server nel pool perché non è necessaria la disponibilità elevata, selezionare **Pool a computer singolo**. Ignorare il passaggio seguente.
    
6. Se si seleziona **Pool di più computer** nel passaggio precedente , in **Definire i computer nel pool corrente** fare clic su **FQDN computer**, digitare l'FQDN di ogni server nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti gli altri Mediation Server che si desidera aggiungere al pool. Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.
    
7. Nella pagina **Selezionare l'hop** successivo fare clic su Pool **hop** successivo, fare clic sul nome di dominio completo del pool Front End che utilizzerà il pool Mediation Server e quindi fare clic su **Avanti.**
    
8. Nella pagina **Selezionare un server perimetrale** eseguire una delle operazioni seguenti:
    
   - Se si desidera fornire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in Selezionare il pool di server perimetrali utilizzato da **questo Mediation Server** fare clic sul nome di dominio completo del pool di server perimetrali che utilizzerà il pool Mediation Server per fornire la connettività PSTN a tali utenti esterni e quindi fare clic su **Avanti.**
    
   - Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si desidera fornire la connettività PSTN agli utenti quando si trova all'esterno della rete interna, fare clic su **Avanti.**
    
9. Fare clic con il pulsante **destro del Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definire le porte di attesa di Mediation Server

Seguire i passaggi descritti in questo argomento per utilizzare Generatore di topologie per definire le porte di attesa che un Mediation Server o un pool accetteranno le connessioni in ingresso da un peer gateway.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Per modificare le porte di attesa di Mediation Server

1. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Skype for Business Server Generatore di topologie **2015**.
    
2. Nell'albero della console di Generatore di topologie espandere il nodo **Pool Mediation** Server e fare clic con il pulsante destro del mouse sul Mediation Server creato in precedenza.
    
3. Per impostazione predefinita, le porte di attesa SIP nel Mediation Server sono 5070 per il traffico TLS da Skype for Business Server e 5067 per il traffico TLS da peer (ad esempio gateway, PCX o SBC). La porta TCP è disabilitata per impostazione predefinita. È necessario abilitare la porta TCP in presenza di gateway che non supportano TLS.
    
4. Specificare l'intervallo di porte di attesa TLS o TCP desiderato che il Mediation Server accetterà le connessioni in ingresso dai gateway PSTN.
    
    > [!NOTE]
    > Non è necessario immettere un intervallo di porte TCP se l'opzione **Abilita la porta TCP** non è selezionata. Questa impostazione è facoltativa.
  

