---
title: Configurare la pagina di partecipazione alle riunioni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva il client già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita verrà aperta l'app Web.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754026"
---
# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva il client già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita verrà aperta l'app Web.
  
È possibile modificare il comportamento della pagina di partecipazione alle riunioni se si desidera consentire agli utenti di partecipare alle riunioni. Queste opzioni di configurazione sono state rimosse dal pannello di controllo, ma è possibile configurarle utilizzando il cmdlet CsWebServiceConfiguration.
  
**Parametri di CsWebServiceConfiguration per la pagina di partecipazione alla riunione**

|**Parametro di CsWebServiceConfiguration**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se il valore è impostato su true, gli utenti che partecipano a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Se impostato su true, le opzioni alternative per partecipare a una conferenza online verranno espanse e mostrate automaticamente agli utenti. Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni per se stessi.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Per configurare la pagina di partecipazione alle riunioni utilizzando Skype for Business Server 2019 Management Shell

1. Avviare la shell di gestione di Skype for Business Server 2019: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire il cmdlet seguente: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.
    
3. Eseguire il seguente comando, con i parametri impostati su true o false, a seconda della preferenza (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) ):
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


