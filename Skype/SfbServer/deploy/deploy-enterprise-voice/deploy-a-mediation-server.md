---
title: Distribuire un Mediation Server in Generatore di topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Riepilogo: informazioni su come definire e distribuire un Mediation Server in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 23d1567816c56408b276672fdd0330b0aa3d635c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245812"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Distribuire un Mediation Server in Generatore di topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire e distribuire un Mediation Server in Generatore di topologia in Skype for Business Server.
  
Il carico di lavoro VoIP aziendale, i servizi di conferenza telefonica con accesso esterno e le applicazioni vocali avanzate di Enterprise (Response Group Application, Call Park application, Call ammissioni Control (CAC) e così via) sono disponibili nei pool Front-end. La funzionalità di Mediation Server è integrata nel server front-end. Un server di mediazione autonomo separato non è necessario. 
  
L'unica eccezione è la configurazione di un trunk SIP per la connessione a un controller di bordo della sessione per un provider di servizi di telefonia Internet. Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un server di mediazione separato.
  
La connessione tra Skype for Business Server (un Mediation Server collocato in un pool Front-end o un Mediation Server autonomo) e un gateway viene definito come associazione logica denominata trunk. Gli argomenti di questa sezione descrivono come definire un trunk e come distribuire un Mediation Server autonomo, se ci si connette a un trunk SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Definire un Mediation Server in Generatore di topologie

È possibile aggiungere Mediation Server come ruolo collocato in un pool Front-end oppure definire un pool di Mediation Server autonomo distinto.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Per aggiungere un Mediation Server a un pool Front-End

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un pool Front-end.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse sul tipo di pool Front-end desiderato e quindi scegliere **nuovo pool Front-end.**..
    
4. Spostarsi tra la procedura guidata **Definisci nuovo pool di front end** fino a raggiungere la pagina **Selezione ruoli server collocati** .
    
5. In **Seleziona ruoli server collocati selezionare**l'opzione **collocazione Mediation Server**.
    
    > [!NOTE]
    > Se il tipo di pool Front-End selezionato è Enterprise Edition, il componente Mediation Server verrà installato in tutti i server front-end del pool Front-end. 
  
    > [!NOTE]
    > Il **pool di hop successivo** usato dal Mediation Server sarà il pool Front-end in cui è installato il Mediation Server.
  
    > [!NOTE]
    > Il **pool di Edge** usato da Mediation Server sarà lo stesso pool di Edge associato al pool Front-end in cui è installato il Mediation Server.
  
6. Fare clic su **Imposta predefinito** per usare questo pool Front-end per instradare le chiamate alla rete PSTN.
    
7. Al termine, fare clic su **fine** per associare uno o più peer al pool Front-end.
    
    > [!NOTE]
    > Prima di procedere con il passaggio successivo nel processo di distribuzione di VoIP aziendale, verificare che il pool di Mediation Server (ad esempio il pool Front end con il componente Mediation Server) usi i nomi di dominio completi specificati. 
  
8. Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Per aggiungere un Mediation Server autonomo

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. Nell'albero della console di generatore di topologia espandere il nome del sito per il quale si desidera definire un Mediation Server.
    
3. Nell'albero della console fare clic con il pulsante destro del mouse sul nodo **pool** di mediazione e quindi scegliere **pool di Mediation Server**.
    
4. In **Definisci nuovo pool**di mediazione digitare il nome di dominio completo (FQDN) del pool di Mediation Server.
    
5. Eseguire quindi una delle operazioni seguenti:
    
   - Se si vuole distribuire più server di mediazione nel pool per ottenere una disponibilità elevata, selezionare **più pool di computer**.
    
     > [!NOTE]
     > È necessario eseguire la [distribuzione](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) per supportare i pool di Mediation Server con più server di mediazione.
  
   - Se si vuole distribuire un solo Mediation Server nel pool perché non è necessaria una disponibilità elevata, selezionare **Single computer pool**. Ignorare il passaggio seguente.
    
6. Se nel passaggio precedente è stato selezionato **più pool di computer** , nell'elemento Definisci **i computer in questo pool** fare clic su **FQDN computer**, digitare il nome di dominio completo di ogni server nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti gli altri Mediation Server che si vuole aggiungere al pool. Dopo aver definito tutti i computer nel pool, fare clic su **Avanti**.
    
7. Nella pagina **selezionare l'hop successivo** fare clic su **pool hop successivo**, fare clic sul nome di dominio completo del pool Front-end che utilizzerà questo pool di Mediation Server e quindi fare clic su **Avanti**.
    
8. Nella pagina **selezionare un server perimetrale** eseguire una delle operazioni seguenti:
    
   - Se si vuole consentire la connettività PSTN agli utenti esterni abilitati per VoIP aziendale, in **selezionare pool Edge usato da questo Mediation Server**fare clic sul nome di dominio completo del pool di Edge Server che utilizzerà questo pool di Mediation Server per consentire la connettività PSTN Gli utenti esterni e quindi fare clic su **Avanti**.
    
   - Se non si prevede di abilitare gli utenti esterni per VoIP aziendale o se non si vuole concedere connettività PSTN agli utenti quando si trovano all'esterno della rete interna, fare clic su **Avanti**.
    
9. Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server 2015** e quindi scegliere **Pubblica topologia**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Definire le porte di ascolto di Mediation Server

Seguire i passaggi descritti in questo argomento per usare generatore di topologie per definire le porte in attesa un server di mediazione o un pool accetteranno le connessioni in ingresso da un peer del gateway.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Per modificare le porte di ascolto di Mediation Server

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. Nell'albero della console di generatore di topologia espandere il nodo **pool** di mediazione e fare clic con il pulsante destro del mouse sul server di mediazione creato in precedenza.
    
3. Per impostazione predefinita, le porte di ascolto SIP sul Mediation Server sono 5070 per il traffico TLS da Skype for Business Server e 5067 per il traffico TLS da peer (ad esempio gateway, sistemi PBX o SBCs). La porta TCP è disabilitata per impostazione predefinita. È necessario abilitare la porta TCP se sono presenti gateway che non supportano TLS.
    
4. Specificare l'intervallo di porte di ascolto TLS o TCP desiderato il server di mediazione accetterà le connessioni in ingresso dai gateway PSTN.
    
    > [!NOTE]
    > L'immissione di un intervallo di porte TCP non è necessaria se l'abilitazione della **porta TCP** non è selezionata. Questa impostazione è facoltativa.
  

