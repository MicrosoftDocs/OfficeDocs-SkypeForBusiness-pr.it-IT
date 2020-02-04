---
title: Espansione delle impostazioni generali di Mediation Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 364e76befd6d259428ea2ae8d580c774e06d210a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701911"
---
# <a name="mediation-server-general-settings-expander"></a>Espansione delle impostazioni generali di Mediation Server
 


## <a name="general-settings"></a>Impostazioni generali

Nome di dominio completo (FQDN) del pool di Mediation Server o Mediation Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.
  
Nella sezione **associazioni** selezionare un server perimetrale o un pool di Edge Server da associare al pool di Mediation Server o Mediation Server. Si seleziona il bordo che verrà usato dai componenti multimediali del Mediation Server per l'utente esterno VoIP aziendale.
  
Se non si dispone di un server perimetrale attualmente definito e si deve associare il Mediation Server a un server perimetrale, fare clic su **nuovo** e definire il nuovo pool di Edge Server o Edge Server nella procedura guidata Definisci nuovo pool di bordi.
  
## <a name="next-hop-settings"></a>Impostazioni dell'hop successivo

È possibile specificare il pool di Mediation Server o Mediation Server next hop selezionando il pool di front end Enterprise Edition definito o il server front-end Standard Edition nell'elenco a discesa. Un pool di Director o Director non è una selezione valida per un pool di Mediation Server o un Mediation Server next hop e non verrà visualizzato nell'elenco. Fare clic su **OK** per accettare e salvare le modifiche. Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.
  
## <a name="pstn-gateway-settings"></a>Impostazioni gateway PSTN

1. Puoi definire i gateway PSTN associati al pool di Mediation Server o Mediation Server. Se sono già stati definiti gateway, saranno disponibili per l'associazione con il Mediation Server. Se si abilita la collocazione del Mediation Server, definire l'intervallo di porte di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.
    
2. I trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server. 
    
3. Se si ha più di un trunk associato a un Mediation Server, è possibile specificare un trunk predefinito selezionando il trunk e quindi facendo clic su **Imposta come predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**. 
    

