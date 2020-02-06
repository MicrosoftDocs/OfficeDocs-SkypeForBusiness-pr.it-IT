---
title: Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica di Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Informazioni su come abilitare il sistema telefonico in Office 365 Voice Services per gli utenti di Skype for business.
ms.openlocfilehash: f4fdd2a9a3da58f6804fa65acf96ba2b8fac682e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802206"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica di Office 365
 
Informazioni su come abilitare il sistema telefonico in Office 365 Voice Services per gli utenti di Skype for business.
  
Il passaggio finale nella distribuzione di sistemi telefonici in Office 365 con connettività PSTN locale consiste nell'abilitare gli utenti per il sistema telefonico in Office 365 e la segreteria telefonica. Per abilitare queste funzionalità, è necessario essere un utente con il ruolo di amministratore globale di Office 365 ed essere in grado di eseguire Remote PowerShell. È necessario seguire la procedura descritta in questo argomento per tutti gli account utente che non dispongono già di VoIP aziendale abilitato per Skype for business online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Abilitare il sistema telefonico in Office 365 Voice Services

Per abilitare un utente per il sistema telefonico in Office 365 Voice and voicemail, è necessario eseguire alcuni passaggi iniziali, ad esempio verificare se il connettore di Skype for business online è distribuito nei server e abilitare gli utenti per la segreteria telefonica ospitata.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Per abilitare gli utenti per il sistema telefonico in Office 365 Voice and voicemail

1. Prima di iniziare, verificare che il connettore Skype for business online (modulo Windows PowerShell) sia distribuito nei server front-end. In caso contrario, è possibile scaricarlo dall' [area download](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Per altre informazioni sull'uso di questo modulo, vedere [configurare il computer per la gestione di Skype for business online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Avviare Windows PowerShell come amministratore.
    
3. Digitare il codice seguente e premere INVIO:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Digitare il codice seguente e premere INVIO:
    
   ```powershell
   $cred = Get-Credential
   ```

    Dopo aver premuto INVIO, dovrebbe essere visualizzata la finestra di dialogo credenziali di Windows PowerShell.
    
5. Digitare il nome utente e la password dell'amministratore del tenant e fare clic su **OK**.
    
6. Nella finestra di PowerShell digitare il codice seguente e premere INVIO:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Importare la sessione digitando il cmdlet seguente:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Quando si esegue PowerShell in un server Skype for business, i cmdlet di Skype for business locali sono già caricati quando si apre PowerShell. Devi specificare il parametro-AllowClobber per consentire ai cmdlet online di sovrascrivere i cmdlet locali con lo stesso nome.
    
8. Usa il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente come indicato di seguito:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Ad esempio:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > È anche possibile specificare un utente per l'indirizzo SIP, il nome dell'entità utente (UPN), il nome di dominio e il nomeutente (dominio\nomeutente) e il nome visualizzato in Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico in Office 365

Questa sezione descrive come aggiornare l'URI di linea e il dial plan per gli utenti abilitati per il sistema telefonico in Office 365. 
  
### <a name="to-update-the-line-uri"></a>Per aggiornare l'URI di linea

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Usare il menu Start o il collegamento sul desktop per aprire il pannello di controllo di Skype for Business Server.
    
    > [!NOTE]
    > È anche possibile aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il pannello di controllo di Skype for Business Server. 
  
3. Sulla barra di spostamento sinistra fare clic su **utenti**.
    
4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.
    
5. Nella tabella fare clic sull'account utente di Skype for business che si desidera modificare URI di linea.
    
6. Fare clic su **URI linea**e digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200. Quindi fare clic su **commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aggiornare il dial plan con i cmdlet di Windows PowerShell locali

È possibile assegnare piani di dial per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Questo cmdlet può essere eseguito da Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Per assegnare un dial plan per utente a un singolo utente

- Usare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente "RedmondDialPlan" all'utente Ken REQUESTO:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Per assegnare un dial plan per utente a più utenti

- Con il comando seguente viene assegnato il dial plan per utente "RedmondDialPlan" a tutti gli utenti che lavorano nella città di Redmond. Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Per gli utenti online è possibile usare piani di Dial globale o utenti. I piani di accesso al sito non possono essere usati perché si applicano solo agli utenti ospitati in locale e assegnati a un sito locale. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Per annullare l'assegnazione di un dial plan per utente

- Usare il cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di un dial plan per utente assegnato in precedenza a Ken. Dopo che il dial plan per utente non è stato assegnato, Ken è gestito automaticamente tramite il dial plan globale o con il dial plan per l'ambito dei servizi assegnato al proprio registrar o gateway PSTN. Un dial plan per l'ambito dei servizi ha la precedenza sul dial plan globale:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aggiornare i criteri di routing vocale usando i cmdlet di Windows PowerShell locali

Questa sezione descrive come aggiornare i criteri di routing vocale per gli utenti abilitati per il sistema telefonico in Office 365.
  
Sistema telefonico in Office 365 gli utenti devono disporre di un criterio di routing vocale assegnato alle chiamate per l'instradamento corretto. Ciò si differenzia dagli utenti di VoIP aziendale locali che richiedono l'assegnazione di un criterio vocale per consentire alle chiamate di instradarsi correttamente. Il criterio di routing vocale deve contenere gli usi PSTN che definiscono le chiamate e le route autorizzate per il sistema telefonico negli utenti di Office 365. È possibile copiare questi usi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale. Per altre informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Tutti i sistemi telefonici in Office 365 agli utenti viene assegnato lo stesso criterio vocale online denominato BusinessVoice, che definisce le funzionalità di chiamata consentite; ad esempio, Consenti squillo simultaneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Per assegnare un criterio di routing vocale per utente a un singolo utente

- Usare il cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken request:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Per assegnare criteri di routing vocale per utente a più utenti

- Il comando successivo assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond. Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > È possibile usare i criteri di routing vocale globale o utente per gli utenti online. I criteri di routing vocale del sito non possono essere usati perché si applicano solo agli utenti ospitati in locale e assegnati a un sito locale. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Per annullare l'assegnazione di un criterio di routing vocale per utente

- Usare Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di criteri di routing vocale per utente assegnati in precedenza a Ken. Dopo che i criteri di routing vocale per utente non sono assegnati, Ken è gestito automaticamente tramite il criterio di routing vocale globale.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Per altre informazioni, vedere [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

