---
title: Bloccare i trasferimenti di file “punto a punto”
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: In Skype for Business online è possibile controllare i trasferimenti di file P2P (Point-to-Point) come parte delle impostazioni dei criteri di conferenza esistenti. Ciò consente o blocca i trasferimenti di file per gli utenti, indipendentemente dal fatto che trasferiscono o meno file a un utente interno alla stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo la procedura seguente, è possibile bloccare i trasferimenti di file P2P con le organizzazioni federate o i partner.
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569102"
---
# <a name="block-point-to-point-file-transfers"></a>Bloccare i trasferimenti di file “punto a punto”

In Skype for Business online è possibile controllare i trasferimenti di file P2P (Point-to-Point) come parte delle impostazioni dei criteri di conferenza esistenti. Ciò consente o blocca i trasferimenti di file per gli utenti, indipendentemente dal fatto che trasferiscono o meno file a un utente interno alla stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo la procedura seguente, è possibile bloccare i trasferimenti di file P2P con le organizzazioni federate o i partner.
  
 Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P ma bloccare il trasferimento di file con partner federati. Per questo scenario, è necessario eseguire le seguenti operazione:
  
- Assegnare un criterio di conferenza con il trasferimento di file _P2P abilitato (EnableP2PFileTransfer_ impostato su _True)_ agli utenti dell'organizzazione.
    
- Creare un set di criteri di comunicazione utente esterno globale per bloccare i trasferimenti di file P2P esterni _(EnableP2PFileTransfer_ impostato su _False)_ e assegnarlo a un utente dell'organizzazione. 
    
Altre informazioni su queste impostazioni sono [disponibili qui.](https://technet.microsoft.com/library/mt228132.aspx)
  
Se un utente federato esterno all'organizzazione tenta di inviare un file a un utente a cui è stato applicato il criterio, riceverà un errore di trasferimento non **riuscito.** Inoltre, se un utente prova a inviare un file, riceverà un **errore di** trasferimento file disattivato.
  
A tale scopo, l'utente deve utilizzare una versione supportata di un'app Skype for Business 2016 A scelta che la supporta. È richiesta la seguente versione minima del client Skype for Business 2016 A scelta:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (build 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (build 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che utilizzano versioni precedenti delle app Windows o dei client Mac di Skype for Business potranno comunque trasferire i file. 
  
## <a name="start-windows-powershell"></a>Iniziare Windows PowerShell

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams. Se si usa la versione pubblica più recente di Teams PowerShell, non è necessario installare Skype for Business Online Connector.
1. Installare il [modulo Teams di PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Aprire un Windows PowerShell comando ed eseguire i comandi seguenti: 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Disabilitare i trasferimenti di file P2P per l'organizzazione

Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitato nei criteri globali dell'organizzazione. Quando è stata creata, agli utenti è stato assegnato il _criterio BposSAllModality._
  
Per consentire i trasferimenti P2P all'interno dell'organizzazione ma bloccare i trasferimenti di file esterni a un'altra organizzazione, è sufficiente cambiarlo a livello globale. A tale scopo, eseguire:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Disabilitare i trasferimenti di file P2P per un utente

È possibile applicarlo a un utente creando un nuovo criterio e concedendo il criterio a tale utente. A tale scopo, eseguire: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell?

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 e Skype for Business online con un unico punto di amministrazione che consente di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
