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
description: In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814635"
---
# <a name="block-point-to-point-file-transfers"></a>Bloccare i trasferimenti di file “punto a punto”

In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
  
 Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P, ma bloccare il trasferimento di file con partner federati. Per questo scenario, è necessario eseguire le operazioni seguenti:
  
- Assegnare un criterio di conferenza con il trasferimento di file P2P abilitato (_EnableP2PFileTransfer_ impostato su _true_) agli utenti dell'organizzazione.
    
- Creare un criterio di comunicazione utente esterno globale impostato per bloccare i trasferimenti di file P2P esterni (_EnableP2PFileTransfer_ impostato su _false_) e assegnarlo a un utente dell'organizzazione. 
    
Per altre informazioni su queste impostazioni, vedere [qui](https://technet.microsoft.com/library/mt228132.aspx).
  
Se un utente federato all'esterno dell'organizzazione prova a inviare un file a un utente in cui è stato applicato il criterio, riceverà un errore di **trasferimento non riuscito** . E se un utente tenta di inviare un file, riceverà un **trasferimento di file disattivato** .
  
Per ottenere questo lavoro, l'utente deve usare una versione supportata di un'app Skype for business a portata di clic di 2016 che la supporta. È necessaria la versione minima seguente di Skype for business 2016 a portata di clic:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release per il canale corrente  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (Build 7571,2006)  <br/> |
|Canale corrente  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (Build 7571,2072)  <br/> |
|Deferred Channel  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (Build 7369,2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che usano versioni precedenti di Skype for business per le app di Windows o i client Mac saranno comunque in grado di trasferire file. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
    1. A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Controlla la versione digitando _Get-host_ nella finestra di **Windows PowerShell** .
        
    3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Quando richiesto, riavviare il computer.
        
    4. Sarà inoltre necessario installare il modulo di Windows PowerShell per Teams che consente di creare una sessione remota di Windows PowerShell che si connette a Skype for business online. 
    
    Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
    1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
        
    2. Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:
    
        > [!NOTE]
        > Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.
        >
        > Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Disabilitare i trasferimenti di file P2P per l'organizzazione

Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitato nel criterio globale dell'organizzazione. Al momento della creazione, agli utenti è stato assegnato il criterio _BposSAllModality_ .
  
Per consentire i trasferimenti P2P per l'interno dell'organizzazione, ma bloccare i trasferimenti di file esterni a un'altra organizzazione, è sufficiente modificarla a livello globale. Per farlo, Esegui:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Disabilitare i trasferimenti di file P2P per un utente

Puoi applicarlo a un utente creando un nuovo criterio e conferendolo a tale utente. Per farlo, Esegui: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 e Skype for business online con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Perché è necessario usare Microsoft 365 o Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo usando l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
