---
title: Trasferimenti di file bloccati Point-to-
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: In Skype Business online, è necessario possibilità di controllare i trasferimenti di file da punto a punto (P2P) come parte di impostazioni di criteri di conferenza esistente. Tuttavia, in questo modo o blocchi file trasferimenti per gli utenti sono o meno sono trasferimento di file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguire la procedura riportata di seguito, è possibile bloccare i trasferimenti di file P2P con organizzazioni federate o partner.
ms.openlocfilehash: 8e3fd112d46a88752b0d6d19cf2e1fbb1787df32
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="block-point-to-point-file-transfers"></a>Trasferimenti di file bloccati Point-to-

In Skype Business online, è necessario possibilità di controllare i trasferimenti di file da punto a punto (P2P) come parte di impostazioni di criteri di conferenza esistente. Tuttavia, in questo modo o blocchi file trasferimenti per gli utenti sono o meno sono trasferimento di file a un utente che si trova all'interno della stessa organizzazione o a un utente federato di un'altra organizzazione. Seguire la procedura riportata di seguito, è possibile bloccare i trasferimenti di file P2P con organizzazioni federate o partner.
  
 Una situazione molto comune è quando si desidera consentire agli utenti interni per il trasferimento di file utilizzare P2P ma trasferimento di file bloccati con i partner federati. Per questo scenario, è necessario eseguire:
  
- Assegnare un criterio di conferenza con P2P trasferimento di file abilitato (_EnableP2PFileTransfer_ impostata su _True_) per gli utenti dell'organizzazione.
    
- Creare un criterio di comunicazione globale degli utenti esterni impostato per bloccare i trasferimenti di file esterni P2P (_EnableP2PFileTransfer_ impostato su _False_) e assegnarlo a un utente nell'organizzazione. 
    
È possibile trovare ulteriori informazioni su queste impostazioni [di seguito](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Se un utente federato all'esterno dell'organizzazione tenta di inviare un file a un utente di cui è stato applicato il criterio, ricevono un errore di **Trasferimento ha avuto esito negativo** . E se un utente tenta di inviare un file, verrà visualizzato un errore di **trasferimento di File è disattivato** .
  
Per ottenere questo risultato, l'utente deve utilizzare una versione supportata di un Skype Click-to-Run 2016 per applicazioni aziendali che supporta lo. La versione minima seguente di Skype per Business 2016 Click-to-Run client è necessaria:
  
|**Tipo**|**Data di rilascio**|**Versione**|**Build**|
|:-----|:-----|:-----|:-----|
|Prima versione per il canale corrente  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versione 1611 (Build 7571.2006)  <br/> |
|Canale corrente  <br/> |6/12/2016  <br/> |16.0.7571.2072  <br/> |Versione 1611 (Build 7571.2072)  <br/> |
|Canale differito  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versione 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Gli utenti che utilizzano le versioni precedenti di Skype per Mac client o app di Windows Business saranno ancora in grado di trasferire file. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificare e avviare Windows PowerShell

- **Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**
    
1. A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Verificare la versione digitando _Get-Host_ nella finestra di **Windows PowerShell** .
    
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

  Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [Connecting to Skype Business online tramite Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Disattivare i trasferimenti di file P2P per l'organizzazione

Per impostazione predefinita, _EnableP2PFileTransfer_ è abilitata sul criterio globale dell'organizzazione. Quando è stata creata, gli utenti sono stati assegnati i criteri _BposSAllModality_ .
  
Per consentire i trasferimenti P2P per interno i trasferimenti di file esterno organizzazione ma blocco a un'altra organizzazione, è necessario modificare a livello globale. A tale scopo, eseguire:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Disattivare i trasferimenti di file P2P per un utente

È possibile applicare a un utente crea un nuovo criterio e concedere a tale utente. A tale scopo, eseguire: 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Creare criteri di accesso esterno personalizzato](create-custom-external-access-policies.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 