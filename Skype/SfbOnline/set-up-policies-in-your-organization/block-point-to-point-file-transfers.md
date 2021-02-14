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
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814635"
---
# <a name="block-point-to-point-file-transfers"></a>Bloccare i trasferimenti di file “punto a punto”

In Skype for Business online è possibile controllare i trasferimenti di file P2P (Point-to-Point) come parte delle impostazioni dei criteri di conferenza esistenti. Ciò consente o blocca i trasferimenti di file per gli utenti, indipendentemente dal fatto che trasferiscono o meno file a un utente interno alla stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo la procedura seguente, è possibile bloccare i trasferimenti di file P2P con le organizzazioni federate o i partner.
  
 Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P ma bloccare il trasferimento di file con partner federati. Per questo scenario, è necessario eseguire le seguenti operazione:
  
- Assegnare un criterio di conferenza con il trasferimento di file P2P abilitato _(EnableP2PFileTransfer_ impostato su _True)_ agli utenti dell'organizzazione.
    
- Creare un set di criteri di comunicazione utente esterno globale per bloccare i trasferimenti di file P2P esterni _(EnableP2PFileTransfer_ impostato su _False)_ e assegnarlo a un utente dell'organizzazione. 
    
Altre informazioni su queste impostazioni sono [disponibili qui.](https://technet.microsoft.com/library/mt228132.aspx)
  
Se un utente federato esterno all'organizzazione tenta di inviare un file a un utente a cui è stato applicato il criterio, riceverà un errore di trasferimento non **riuscito.** Inoltre, se un utente prova a inviare un file, riceverà un errore di trasferimento **file disattivato.**
  
A tale scopo, l'utente deve utilizzare una versione supportata di un'app Skype for Business 2016 A scelta che la supporta. È richiesta la seguente versione minima del client A scelta di Skype for Business 2016:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per Current Channel  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (build 7571.2006)  <br/> |
|Current Channel  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (build 7571.2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (build 7369.2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che utilizzano versioni precedenti delle app Windows o dei client Mac di Skype for Business potranno comunque trasferire i file. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
    1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Controllare la versione _digitando Get-Host_ nella finestra **Windows PowerShell** lavoro.
        
    3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0. Quando richiesto, riavviare il computer.
        
    4. Dovrai inoltre installare il modulo Windows PowerShell per Teams che ti consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online. 
    
    Per altre informazioni, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in un'unica Windows PowerShell singola.](https://technet.microsoft.com/library/dn568015.aspx)
    
- **Avviare una sessione di Windows PowerShell**
    
    1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:
    
        > [!NOTE]
        > Skype for Business Online Connector fa attualmente parte del più recente modulo PowerShell di Teams.
        >
        > Se si usa la versione pubblica più recente di [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare Skype for Business Online Connector.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere Connettersi a tutti i servizi di [Microsoft 365 o Office 365 in](https://technet.microsoft.com/library/dn568015.aspx) un'unica finestra di Windows PowerShell oppure Configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
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

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell puoi gestire Microsoft 365 o Office 365 e Skype for Business online tramite un unico punto di amministrazione, che ti semplifica il lavoro quotidiano, quando hai più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
