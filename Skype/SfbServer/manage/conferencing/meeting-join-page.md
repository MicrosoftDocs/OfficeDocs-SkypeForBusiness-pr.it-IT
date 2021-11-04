---
title: Configurare la pagina di partecipazione alla riunione in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Riepilogo: informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.'
ms.openlocfilehash: 39a9fd42fd7d1017ece572856f6d85a09e1f55fe
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743562"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurare la pagina di partecipazione alla riunione in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.
  
Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Skype for Business è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita viene aperto Skype for Business client. 
  
## <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

È possibile modificare il comportamento della pagina di partecipazione alla riunione se si desidera consentire agli utenti di partecipare alle riunioni con altre versioni del client. Queste opzioni di configurazione sono state rimosse dal Pannello di controllo di Skype for Business Server, ma è possibile configurarle utilizzando il cmdlet Set-CsWebServiceConfiguration.
  
**Parametri Set-CsWebServiceConfiguration pagina di partecipazione alle riunioni**

|**Parametro Set-CsWebServiceConfiguration**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Questo parametro è stato deprecato per l'utilizzo con la versione locale di Skype for Business Server.  <br/> Se impostato su True, gli utenti che aderiscono a una riunione utilizzando un'applicazione client diversa da Skype for Business avranno la possibilità di partecipare alla riunione utilizzando l'applicazione client corrente. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Questo parametro è stato deprecato per l'utilizzo con la versione locale di Skype for Business Server.  <br/>  Se impostato su True, le opzioni alternative per partecipare a una conferenza online vengono automaticamente espanse e visualizzate agli utenti. Se impostato su False (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni per se stesso.  <br/> |
   

