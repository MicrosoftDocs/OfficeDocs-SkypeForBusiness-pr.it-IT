---
title: Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server
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
ms.openlocfilehash: 5c6863b93de0e8cf96ae2fa521da8dcd4b75c836d70d1d22d734ef25a21d6568
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283828"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definire trunk aggiuntivi in Generatore di topologie in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire un trunk aggiuntivo tra un Mediation Server e un peer gateway in Generatore di topologie in Skype for Business Server.
  
Seguire questa procedura per definire un trunk aggiuntivo a cui è possibile associare un peer a un Mediation Server. Un peer fornisce agli utenti abilitati VoIP aziendale la connettività alla rete PSTN (Public Switched Telephone Network). Un peer può essere un gateway PSTN, un IP-PBX, o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP).
  
Un trunk è una connessione logica tra un Mediation Server e un gateway.
  
> [!NOTE]
> In questo argomento si presuppone che sia stato configurato un gateway PSTN e un trunk radice con almeno un Mediation Server o un pool autonomo o collocato, come descritto [in Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) nella documentazione relativa alla distribuzione.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Per definire un trunk aggiuntivo tra un Mediation Server e un peer gateway

1. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Skype for Business Server Generatore di topologie **2015**.
    
2. In Skype for Business Server, il nome del sito, **Componenti condivisi**, fare clic con il pulsante destro del mouse sul nodo **Trunk e** quindi scegliere Nuovo **trunk**.
   1. In **Definisci nuovo trunk**, specificare un nome descrittivo per identificare in modo univoco il trunk. Non è possibile definire due trunk con lo stesso nome.
    
      > [!NOTE]
      > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server. 
  
3. In **Gateway PSTN associato** selezionare il peer gateway PSTN da associare al trunk.
    5. In Porta di attesa per **gateway PSTN** digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceverà i messaggi SIP dal Mediation Server da associare al trunk. Le porte predefinite per il peer sono 5066 per TCP (Transmission Control Protocol) e 5067 per TLS (Transport Layer Security). Le porte predefinite di Survivable Branch Appliance sono 5081 per TCP e 5082 per TLS.
    
4. In **Protocollo trasporto SIP** fare clic sul tipo di di trasporto utilizzato dal peer.
    
    > [!NOTE]
    > Per motivi di sicurezza, è consigliabile distribuire un peer nel Mediation Server in grado di utilizzare TLS. 
  
5. In **Mediation Server associato** selezionare il pool Mediation Server da associare al trunk radice del peer
    
6. In **Porta Mediation Server associata** digitare la porta di attesa che il Mediation Server riceverà i messaggi SIP dal peer.
    
    > [!NOTE]
    > Con il supporto di più trunk in Skype for Business Server, non è possibile configurare due trunk con nomi trunk diversi con la stessa porta **Mediation Server** associata e la stessa porta di attesa per il **gateway IP/PSTN**
  
    > [!NOTE]
    > Con il supporto di più trunk Skype for Business Server, è possibile definire più porte di segnalazione SIP nel Mediation Server per le comunicazioni con più peer. Quando si definisce un trunk, il numero di porta **del Mediation Server** associato deve essere compreso nell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server. Questo intervallo di porte è definito in pool Skype for Business Server Mediation Server. Fare clic con il pulsante destro del mouse sul pool Mediation Server pertinente e **scegliere Modifica proprietà**. Specificare l'intervallo di porte nel campo **Porte di attesa**.
  
7. Fare clic su **OK**. 
    

