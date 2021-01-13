---
title: Configurare la pagina di partecipazione alle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Riepilogo: informazioni su come configurare la pagina di partecipazione alle riunioni in Skype for Business Server.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828036"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurare la pagina di partecipazione alle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare la pagina di partecipazione alle riunioni in Skype for Business Server.
  
Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Skype for business è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita verrà aperto il client Skype for business. 
  
## <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni con altre versioni del client. Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Skype for Business Server, ma sono state configurate utilizzando il cmdlet Set-CsWebServiceConfiguration.
  
**Set-CsWebServiceConfiguration parametri della pagina di partecipazione alle riunioni**

|**Set-CsWebServiceConfiguration, parametro**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Questo parametro è stato deprecato per essere utilizzato con la versione locale di Skype for Business Server.  <br/> Se il valore è impostato su true, gli utenti che partecipano a una riunione utilizzando un'applicazione client diversa da Skype for business avranno la possibilità di partecipare alla riunione utilizzando l'applicazione client corrente. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Questo parametro è stato deprecato per essere utilizzato con la versione locale di Skype for Business Server.  <br/>  Se impostato su true, le opzioni alternative per partecipare a una conferenza online vengono espanse e mostrate automaticamente agli utenti. Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni per se stessi.  <br/> |
   

