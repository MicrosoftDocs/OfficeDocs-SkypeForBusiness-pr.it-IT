---
title: Configurare la pagina di partecipazione alla riunione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. Se un client è già installato, tale client si apre e si unisce alla riunione. Se un client non è installato, per impostazione predefinita viene aperto l'app Web.
ms.openlocfilehash: 1bab2dff25db94b36c41e5824401777006760bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239561"
---
# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alla riunione

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. Se un client è già installato, tale client si apre e si unisce alla riunione. Se un client non è installato, per impostazione predefinita viene aperto l'app Web.
  
È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare alle riunioni. Queste opzioni di configurazione sono state rimosse dal pannello di controllo, ma le configuri usando il cmdlet CsWebServiceConfiguration.
  
**Parametri di CsWebServiceConfiguration pagina di join della riunione**

|**Parametro CsWebServiceConfiguration**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Quando è impostato su true, le opzioni alternative per partecipare a una conferenza online verranno espanse e visualizzate automaticamente agli utenti. Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Per configurare la pagina di partecipazione alla riunione usando Skype for Business Server 2019 Management Shell

1. Avviare Skype for Business Server 2019 Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Skype for Business Server 2019**e quindi su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente: 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.
    
3. Eseguire il comando seguente, con i parametri impostati su true o false, a seconda delle preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


