---
title: Definire un gateway in Generatore di topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Riepilogo: informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 39e2bdf041055e392b88cc25594b45c2529161d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190406"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definire un gateway in Generatore di topologie in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.
  
Seguire questa procedura per usare generatore di topologia per definire un peer con cui è possibile associare un Mediation Server per consentire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale. Un peer per il Mediation Server può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP) a cui ci si connette configurando un trunk SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Per definire un peer per il Mediation Server

1. Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server 2015**e quindi su **Skype for Business Server 2015Topology Builder**.
    
2. In Skype for Business Server, il nome del sito, i componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **gateway PSTN** e quindi scegliere **nuovo gateway PSTN**.
3. In **Definisci nuovo gateway IP/PSTN**Digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e fare clic su **Avanti**.
    
    > [!NOTE]
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server. 
  
4. Definire la modalità di ascolto (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e fare clic su **Avanti**.

5. Definire un trunk radice per il gateway PSTN. Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.
    
    {Nome completo di Mediation Server, porta di attesa di Mediation Server (TLS o TCP): IP gateway e FQDN, porta di ascolto del gateway}
    
     - Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.
    
     - Il trunk radice non può essere rimosso finché non viene rimosso il gateway PSTN associato.
    
6. In **porta di ascolto per gateway IP/PSTN**Digitare la porta di attesa che il gateway, il PBX o il SBC utilizzerà per i messaggi SIP provenienti dal server di mediazione che verranno associati al trunk radice del gateway PSTN. Per impostazione predefinita, le porte sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS) in un gateway PSTN, un PBX o un SBC. In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.
    
7. In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer e quindi fare clic su **OK**.
    
    > [!NOTE]
    > Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS. 
  
8. In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo gateway PSTN.
    
9. In **porta Mediation Server associata**Digitare la porta di ascolto che il server di mediazione userà per i messaggi SIP dal gateway.
    
    > [!NOTE]
    > Con il supporto per più trunk in Skype for Business Server, puoi definire più porte di segnalazione SIP nel Mediation Server per la comunicazione con più gateway PSTN. Quando si definisce un trunk, la **porta del server di mediazione associata** deve essere compresa nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation. Questo intervallo di porte è definito in Skype for Business Server e nei pool di mediazione. Fare clic con il pulsante destro del mouse sul pool di Mediation Server di interesse e scegliere **modifica proprietà**. Specificare l'intervallo di porte nel campo **porte in attesa** .
  
10. Verificare che il peer definito sia in uso e che usi il nome di dominio completo o l'indirizzo IP specificato. Quindi fare clic su **fine**.
    
11. Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** e quindi scegliere **Pubblica topologia**.
    

