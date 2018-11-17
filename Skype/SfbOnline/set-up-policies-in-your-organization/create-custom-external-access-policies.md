---
title: Creare criteri di accesso esterno personalizzato
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype per Business Online consente di creare i criteri di accesso esterno aggiuntivi. A differenza dei criteri client o di conferenza, dove è possibile avere più combinazioni, sono disponibili tre criteri predefiniti l'accesso esterno che possono soddisfare la maggior parte degli scenari.
ms.openlocfilehash: a822e09875bbef1fcd1472ac988a32cadfaf5850
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561697"
---
# <a name="create-custom-external-access-policies"></a>Creare criteri di accesso esterno personalizzato

Skype per Business Online consente di creare i criteri di accesso esterno aggiuntivi. A differenza dei criteri client o di conferenza, dove è possibile avere più combinazioni, sono disponibili tre criteri predefiniti l'accesso esterno che possono soddisfare la maggior parte degli scenari. Di seguito sono:
  
- No federato o Access Consumer Skype (_Tag: NoFederationAndPIC_ )
    
- Accesso federato (_Tag: FederationOnly_ )
    
- Federati e Consumer accedere (_FederationAndPICDefault_)
    
Criteri personalizzati esterni consentono di creare ulteriori criteri che non sono inclusi le impostazioni precedenti. Quando è stato creato il criterio, potrebbe essere necessario impostare tutti i parametri obbligatori e non modificare in seguito. Creazione di nuovi criteri personalizzati consentono alle funzionalità di controllo, ad esempio access consumer Skype o un criterio per disabilitare pubblica cloud audio/video, ovvero un'attività non è stato trattati con impostazioni predefinite. Criteri di accesso esterno personalizzati seguono la stessa sintassi di criteri client, conferenze e dispositivi mobili. È possibile trovare ulteriori informazioni su queste impostazioni [di seguito](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Per ottenere questo risultato, l'utente deve utilizzando una versione supportata di 2016 Skype a portata di clic per applicazioni aziendali che supporta lo. La versione minima seguente di Skype per Business 2016 Click-to-Run client è necessaria:
  
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
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Quando richiesto, riavviare il computer.
    
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

   Se si desiderano ulteriori informazioni sull'avvio di Windows PowerShell, vedere [Connect a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [impostare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Creare un criterio di accesso esterno personalizzati per un utente

Per farlo, eseguire quanto segue:
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Trasferimenti di file bloccati punto-punto](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Impostare i criteri relativi alle conferenze nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 