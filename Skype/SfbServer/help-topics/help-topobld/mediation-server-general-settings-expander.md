---
title: Espansione delle impostazioni generali di Mediation Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: de4d09db10610bee5f498b07cca6a052b6a79a38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852100"
---
# <a name="mediation-server-general-settings-expander"></a>Espansione delle impostazioni generali di Mediation Server
 


## <a name="general-settings"></a>Generale

Nome di dominio completo (FQDN) del pool Mediation Server o del Mediation Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.
  
Nella sezione **Associazioni** è possibile selezionare un server perimetrale o un pool di server perimetrali da associare al pool Mediation Server o al Mediation Server. È possibile selezionare il server perimetrale che verrà utilizzato dai componenti multimediali del Mediation Server per l'VoIP aziendale.
  
Se attualmente non è definito un server perimetrale ed è necessario associare il Mediation Server a un server di questo tipo, fare clic su **Nuovo** e definire il nuovo server perimetrale o il nuovo pool di server perimetrali nella procedura guidata Definisci pool di server perimetrali.
  
## <a name="next-hop-settings"></a>Hop successivo

È possibile specificare l'hop successivo del pool Mediation Server o del Mediation Server selezionando nell'elenco a discesa il pool Enterprise Edition Front End o il server Standard Edition Front End Server definito. Un server Director o un pool di server Director non è una selezione valida per l'hop successivo di un pool Mediation Server o di un Mediation Server e non verrà visualizzato nell'elenco. Fare **clic su OK** per accettare e salvare le modifiche. Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.
  
## <a name="pstn-gateway-settings"></a>Gateway PSTN

1. Definire gateway PSTN associati al pool Mediation Server o al Mediation Server. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server. Se si abilita la collocazione del Mediation Server, definire l'intervallo di porte di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.
    
2. Trunk associati al Mediation Server nella stessa posizione. Se i trunk sono già stati definiti, saranno disponibili per l'associazione a Mediation Server. 
    
3. Se a Mediation Server sono associati più trunk, sarà possibile specificare un trunk predefinito, selezionando il trunk e quindi facendo clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**. 
    

