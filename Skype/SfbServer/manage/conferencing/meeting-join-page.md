---
title: Configurare la pagina di partecipazione alla riunione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Riepilogo: informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189647"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Configurare la pagina di partecipazione alla riunione in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.
  
Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Skype for business è già installato nel computer dell'utente. Se un client è già installato, il client si apre e si unisce alla riunione. Se un client non è installato, per impostazione predefinita viene aperto il client Skype for business. 
  
## <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alla riunione

È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare a riunioni con altre versioni del client. Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Skype for Business Server, ma le configuri usando il cmdlet Set-CsWebServiceConfiguration.
  
**Set di pagine di join di riunione-parametri di CsWebServiceConfiguration**

|**Parametro Set-CsWebServiceConfiguration**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Questo parametro è stato deprecato per l'uso con la versione locale di Skype for Business Server.  <br/> Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Skype for business avranno la possibilità di partecipare alla riunione usando l'applicazione client corrente. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Questo parametro è stato deprecato per l'uso con la versione locale di Skype for Business Server.  <br/>  Se impostato su true, le opzioni alternative per partecipare a una conferenza online vengono espanse e visualizzate automaticamente agli utenti. Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.  <br/> |
   

