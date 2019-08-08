---
title: Definire trunk aggiuntivi in Generatore di topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Riepilogo: informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: eeaddf6b5b150298e7a77b819464b3c0ef653b70
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245861"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definire trunk aggiuntivi in Generatore di topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.
  
Seguire questa procedura per definire un trunk aggiuntivo a cui è possibile associare un peer a un Mediation Server. Un peer fornisce agli utenti abilitati per VoIP aziendale la connettività alla rete PSTN (Public Switched Telephone Network). Un peer può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP).
  
Un trunk è una connessione logica tra un Mediation Server e un gateway.
  
> [!NOTE]
> In questo argomento si presuppone che sia stato configurato un gateway PSTN e un trunk radice con almeno un server o un pool di mediazione autonomo o indipendente, come descritto in [definire un gateway in Generatore di topologie in Skype for Business Server](define-a-gateway.md) nella documentazione relativa alla distribuzione.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Per definire un trunk aggiuntivo tra un Mediation Server e un peer gateway

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. In Skype for Business Server, il nome del sito, i **componenti condivisi**, fare clic **** con il pulsante destro del mouse sul nodo Trunks e quindi scegliere **nuovo trunk**.
   1. In **Definisci nuovo trunk**specificare un nome descrittivo per identificare in modo univoco il trunk. Non è possibile avere due trunk con lo stesso nome.
    
      > [!NOTE]
      > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server. 
  
3. In **gateway PSTN associato**selezionare il peer del gateway PSTN da associare al trunk.
    5. In **porta di attesa per gateway PSTN**Digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceva i messaggi SIP dal Mediation Server che deve essere associato a questo trunk. Le porte peer predefinite sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS). Le porte predefinite Survivable Branch Appliance sono 5081 per TCP e 5082 per TLS.
    
4. In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer.
    
    > [!NOTE]
    > Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS. 
  
5. In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo peer
    
6. In **porta Mediation Server associata**Digitare la porta di attesa in cui il Mediation Server riceverà i messaggi SIP dal peer.
    
    > [!NOTE]
    > Con il supporto per più trunk in Skype for Business Server, due trunk con nomi trunk diversi non possono essere configurati con la stessa **porta del server di mediazione associata** e la **porta di ascolto per gateway IP/PSTN**
  
    > [!NOTE]
    > Con il supporto per più trunk in Skype for Business Server, è possibile definire più porte di segnalazione SIP nel Mediation Server per la comunicazione con più peer. Quando si definisce un trunk, il numero di **porta del server di mediazione associato** deve essere compreso nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation. Questo intervallo di porte è definito in pool di Skype for Business Server e Mediation Server. Fare clic con il pulsante destro del mouse sul pool di Mediation Server e scegliere **modifica proprietà**. Specificare l'intervallo di porte nel campo **porte in attesa** .
  
7. Fare clic su **OK**. 
    

