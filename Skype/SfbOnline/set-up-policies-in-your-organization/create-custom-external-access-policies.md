---
title: Creare criteri di accesso esterno personalizzato
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: Skype for business online consente di creare altri criteri di accesso esterno. A differenza dei criteri per i client o i servizi di conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti in grado di coprire la maggior parte degli scenari.
ms.openlocfilehash: 02fba48a6b8acf2a2b66078624ab36eb7453df0c
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164645"
---
# <a name="create-custom-external-access-policies"></a>Creare criteri di accesso esterno personalizzato

Skype for business online consente di creare altri criteri di accesso esterno. A differenza dei criteri per i client o i servizi di conferenza, in cui è possibile avere più combinazioni, esistono tre criteri di accesso esterno predefiniti in grado di coprire la maggior parte degli scenari. Questi sono:
  
- Nessun accesso dei consumatori federati o Skype (_Tag: NoFederationAndPIC_ )
    
- Solo accesso federativo (_Tag: FederationOnly_ )
    
- Accesso federativo e consumer (_FederationAndPICDefault_)
    
I criteri esterni personalizzati consentono di creare altre forze di polizia che non sono coperte dalle impostazioni descritte sopra. Quando il criterio è stato creato, è necessario impostare tutti i parametri obbligatori e non è possibile modificarli in un secondo momento. La creazione di nuovi criteri personalizzati consente di controllare funzionalità come l'accesso dei consumatori Skype o un criterio per disabilitare l'audio/video del cloud pubblico, un aspetto che non è stato incluso nelle impostazioni predefinite. I criteri di accesso esterno personalizzati seguono la stessa sintassi dei criteri client, mobilità e conferenza. Per altre informazioni su queste impostazioni, vedere [qui](https://technet.microsoft.com/library/mt228132.aspx).
  
Per fare questo lavoro, l'utente deve usare una versione supportata di 2016 a portata di clic di Skype for business app che lo supporta. È necessaria la versione minima seguente di Skype for business 2016 a portata di clic:
  
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
    
2. Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Vedere [Windows Management Framework 4,0](https://www.microsoft.com/download/details.aspx?id=40855) per scaricare e aggiornare Windows PowerShell alla versione 4,0. Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
    Per saperne di più, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Avviare una sessione di Windows PowerShell**
    
1. Fare clic sul pulsante **Start** > **Windows PowerShell**.
    
2. Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:
    
    > [!NOTE]
    > Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Per altre informazioni sull'avvio di Windows PowerShell, vedere [connettersi a tutti i servizi Microsoft 365 o Office 365 in una singola finestra di Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Creare un criterio di accesso esterno personalizzato per un utente

Per farlo, eseguire quanto segue:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
[Bloccare i trasferimenti di file Point-to-Point](block-point-to-point-file-transfers.md)

[Impostazione dei criteri client per la propria organizzazione](set-up-client-policies-for-your-organization.md)

[Configurare i criteri di conferenza nell'organizzazione](set-up-conferencing-policies-for-your-organization.md)

  
 
