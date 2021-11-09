---
title: Definire un gateway in Generatore di topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Riepilogo: informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.'
ms.openlocfilehash: 2e8a69fb1a884597f4e6ecde1a3811a88982d13e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857953"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definire un gateway in Generatore di topologie in Skype for Business Server
 
**Riepilogo:** Informazioni su come definire un gateway PSTN in Generatore di topologie in Skype for Business Server.
  
Seguire questa procedura per utilizzare Generatore di topologie per definire un peer a cui è possibile associare un Mediation Server per fornire la connettività alla rete PSTN (Public Switched Telephone Network) per gli utenti abilitati per VoIP aziendale. Un peer per Mediation Server può essere un gateway PSTN, un IP-PBX o un session border controller (SBC) per un provider di servizi di telefonia Internet (ITSP) a cui ci si connette configurando un trunk SIP.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>Per definire un peer per il Mediation Server

1. Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server 2015** e quindi Skype for Business Server Generatore di topologie **2015**.
    
2. In Skype for Business Server, il nome del sito, Componenti condivisi, fare clic con il pulsante destro del mouse sul nodo **Gateway PSTN** e quindi scegliere **Nuovo gateway PSTN.**
3. Nella finestra **Definisci nuovo gateway IP/PSTN** digitare il nome di dominio completo (FQDN) o l'indirizzo IP del peer e quindi fare clic su **Avanti**.
    
    > [!NOTE]
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server. 
  
4. Definire la modalità di attesa (IPv4 o IPv6) dell'indirizzo IP del nuovo gateway PSTN e quindi fare clic su **Avanti**.

5. Definire un trunk radice per il gateway PSTN. Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla.
    
    {FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP gateway e FQDN, porta di attesa gateway}
    
     - Quando si definisce un gateway PSTN in Generatore di topologie, è necessario definire un trunk radice per aggiungere correttamente il gateway PSTN alla topologia.
    
     - Il trunk radice non può essere rimosso se non si rimuove prima il gateway PSTN associato.
    
6. In Porta di attesa per gateway **IP/PSTN** digitare la porta di attesa che verrà utilizzata dal gateway, dal PBX o dal servizio SBC per i messaggi SIP provenienti dal Mediation Server che verranno associati al trunk radice del gateway PSTN. Per impostazione predefinita, vengono utilizzate la porta 5066 per TCP (Transmission Control Protocol) e la porta 5067 per TLS (Transport Layer Security) in un gateway PSTN, un PBX o un sistema SBC. In un Survivable Branch Appliance in un sito di succursale, le porte predefinite sono 5081 per TCP e 5082 per TLS.
    
7. In **Protocollo trasporto SIP** fare clic sul tipo di trasporto utilizzato dal peer e quindi su **OK**.
    
    > [!NOTE]
    > Per motivi di sicurezza, è consigliabile distribuire un peer nel Mediation Server in grado di utilizzare TLS. 
  
8. In **Mediation Server associato** selezionare il pool Mediation Server da associare al trunk radice del gateway PSTN.
    
9. In **Porta Mediation Server associata** digitare la porta di attesa che verrà utilizzata dal Mediation Server per i messaggi SIP provenienti dal gateway.
    
    > [!NOTE]
    > Con il supporto di più trunk Skype for Business Server, è possibile definire più porte di segnalazione SIP nel Mediation Server per le comunicazioni con più gateway PSTN. Quando si definisce un trunk, la porta **Mediation Server** associata deve essere all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server. Questo intervallo di porte è definito in pool Skype for Business Server mediation pool. Fare clic con il pulsante destro del mouse sul pool Mediation Server di interesse e **scegliere Modifica proprietà**. Specificare l'intervallo di porte nel campo **Porte di attesa**.
  
10. Verificare che il peer definito sia in esecuzione e che utilizzi l'FQDN o l'indirizzo IP specificato. Quindi fare clic **su Fine.**
    
11. Fare clic con il pulsante **destro del Skype for Business Server** e quindi scegliere Pubblica **topologia**.
    

