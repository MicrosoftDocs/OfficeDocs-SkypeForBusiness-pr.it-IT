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
f1keywords: None
ms.custom:
- Setup
description: In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
ms.openlocfilehash: 8b45067cf0c717fdcda144fc44750b7cf3d0f7f7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297817"
---
# <a name="block-point-to-point-file-transfers"></a>Bloccare i trasferimenti di file “punto a punto”

In Skype for business online hai la possibilità di controllare i trasferimenti di file Point-to-Point (P2P) come parte delle impostazioni dei criteri di conferenza esistenti. Tuttavia, questo consente o blocca i trasferimenti di file per gli utenti che trasferiscono o meno i file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguendo i passaggi seguenti, è possibile bloccare i trasferimenti di file P2P con organizzazioni o partner federati.
  
 Uno scenario molto comune è quando si vuole consentire agli utenti interni di usare il trasferimento di file P2P, ma bloccare il trasferimento di file con partner federati. Per questo scenario, è necessario eseguire le operazioni seguenti:
  
- Assegnare un criterio di conferenza con il trasferimento di file P2P abilitato (_EnableP2PFileTransfer_ impostato su _true_) agli utenti dell'organizzazione.
    
- Creare un criterio di comunicazione utente esterno globale impostato per bloccare i trasferimenti di file P2P esterni (_EnableP2PFileTransfer_ impostato su _false_) e assegnarlo a un utente dell'organizzazione. 
    
Per altre informazioni su queste impostazioni, vedere [qui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
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
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
    Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi di Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Disabilitare i trasferimenti di file P2P per l'organizzazione

Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitato nel criterio globale dell'organizzazione. Al momento della creazione, agli utenti è stato assegnato il criterio _BposSAllModality_ .
  
Per consentire i trasferimenti P2P per l'interno dell'organizzazione, ma bloccare i trasferimenti di file esterni a un'altra organizzazione, è sufficiente modificarla a livello globale. Per farlo, Esegui:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Disabilitare i trasferimenti di file P2P per un utente

Puoi applicarlo a un utente creando un nuovo criterio e conferendolo a tale utente. Per farlo, Esegui: 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Argomenti correlati
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
