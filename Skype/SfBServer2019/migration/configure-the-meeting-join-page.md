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
ms.localizationpriority: medium
description: Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita viene aperta l'app Web.
ms.openlocfilehash: 8cba2a6ea0bc54eae6c30265c21d33d01ec951c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617112"
---
# <a name="configure-the-meeting-join-page"></a>Configurare la pagina di partecipazione alle riunioni

Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva quale client è già installato nel computer dell'utente. In caso affermativo, il client viene aperto e accede alla riunione. Se un client non è installato, per impostazione predefinita viene aperta l'app Web.
  
È possibile modificare il comportamento della pagina di partecipazione alla riunione se si desidera consentire agli utenti di partecipare alle riunioni. Queste opzioni di configurazione sono state rimosse dal Pannello di controllo, ma è possibile configurarle utilizzando il cmdlet CsWebServiceConfiguration.
  
**Parametri di CsWebServiceConfiguration per la pagina di partecipazione alla riunione**

|**Parametro di CsWebServiceConfiguration**|**Descrizione**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |Se impostato su True, gli utenti che aderiscono a una riunione utilizzando un'applicazione client diversa da Lync avranno la possibilità di partecipare alla riunione. Il valore predefinito è False.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |Se impostato su True, le opzioni alternative per partecipare a una conferenza online verranno automaticamente espanse e visualizzate agli utenti. Se impostato su False (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni per se stesso.  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>Per configurare la pagina di partecipazione alla riunione tramite Skype for Business Server 2019 Management Shell

1. Avviare Skype for Business Server 2019 Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Eseguire il cmdlet seguente: 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    Questo cmdlet restituisce le impostazioni di configurazione del servizio Web.
    
3. Eseguire il comando seguente, con i parametri impostati su True o False, a seconda delle proprie preferenze (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di [Skype for Business Server Management Shell):](../../SfbServer/manage/management-shell.md)
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


