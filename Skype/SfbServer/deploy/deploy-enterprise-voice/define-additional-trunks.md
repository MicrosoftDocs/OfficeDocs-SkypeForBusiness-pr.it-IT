---
title: Definire ulteriori trunk in Generatore di topologie in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Riepilogo: informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836996"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definire ulteriori trunk in Generatore di topologie in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire un ulteriore Trunk tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.
  
Eseguire la procedura seguente per definire un trunk aggiuntivo a cui è possibile associare un peer a un Mediation Server. Un peer fornisce gli utenti abilitati per VoIP aziendale con connettività alla rete PSTN (Public Switched Telephone Network). Un peer può essere un gateway PSTN, un IP-PBX, o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP).
  
Un trunk è una connessione logica tra un Mediation Server e un gateway.
  
> [!NOTE]
> In questo argomento si presuppone che sia installato un gateway PSTN e un trunk radice con almeno un Mediation Server collocato o autonomo, come descritto in [definire un gateway in Generatore di topologie in Skype for Business Server](define-a-gateway.md) nella documentazione relativa alla distribuzione.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Per definire un ulteriore Trunk tra un Mediation Server e un peer gateway

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015** e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. In Skype for Business Server, nome del sito, **componenti condivisi**, fare clic con il pulsante destro del mouse sul nodo **Trunks** e quindi scegliere **nuovo trunk**.
   1. In **Definisci nuovo trunk**, specificare un nome descrittivo per identificare in modo univoco il trunk. Non è possibile definire due trunk con lo stesso nome.
    
      > [!NOTE]
      > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server. 
  
3. In **Gateway PSTN associato** selezionare il peer gateway PSTN da associare al trunk.
    5. In **porta di attesa per gateway PSTN** Digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceverà i messaggi SIP dal Mediation Server che deve essere associato a questo trunk. Le porte predefinite per il peer sono 5066 per TCP (Transmission Control Protocol) e 5067 per TLS (Transport Layer Security). Le porte di Survivable Branch Appliance predefinite sono 5081 per TCP e 5082 per TLS.
    
4. In **Protocollo trasporto SIP** fare clic sul tipo di di trasporto utilizzato dal peer.
    
    > [!NOTE]
    > Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS. 
  
5. In **Mediation Server associato** selezionare il pool di Mediation Server da associare al trunk radice di questo peer
    
6. In **porta Mediation Server associato** Digitare la porta di attesa che il Mediation Server riceverà messaggi SIP dal peer.
    
    > [!NOTE]
    > Con il supporto per più trunk in Skype for Business Server, due trunk con nomi trunk diversi non possono essere configurati con la stessa **porta di Mediation Server associata** e la **porta di attesa per gateway IP/PSTN**
  
    > [!NOTE]
    > Con il supporto per più trunk in Skype for Business Server, è possibile definire più porte di segnalazione SIP sul Mediation Server per la comunicazione con più peer. Quando si definisce un trunk, il numero di **porta del Mediation Server associato** deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server. Questo intervallo di porte è definito in pool di server Skype for business e Mediation Server. Fare clic con il pulsante destro del mouse sul pool di Mediation Server pertinente e scegliere **modifica proprietà**. Specificare l'intervallo di porte nel campo **Porte di attesa**.
  
7. Fare clic su **OK**. 
    

