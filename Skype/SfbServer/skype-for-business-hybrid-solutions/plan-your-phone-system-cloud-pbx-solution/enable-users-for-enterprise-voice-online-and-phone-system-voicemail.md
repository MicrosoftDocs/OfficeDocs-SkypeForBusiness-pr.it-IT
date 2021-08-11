---
title: Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica
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
description: Informazioni su come abilitare i Sistema telefonico vocali per gli Skype for Business utenti.
ms.openlocfilehash: fea5da3bb82281c05edd73ce8e69c7164440513080b7aa804b31abc5d4c65ba7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289074"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Abilitare gli utenti per VoIP aziendale online e Sistema telefonico nella segreteria telefonica
 
> [!Important]
> Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.  Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online non sarà più supportata.  Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

Informazioni su come abilitare i Sistema telefonico vocali per gli Skype for Business utenti.
  
Il passaggio finale per la Sistema telefonico con connettività PSTN locale consiste nell'abilitare gli utenti per Sistema telefonico e segreteria telefonica. Per abilitare queste funzionalità, è necessario essere un utente con il ruolo Amministratore globale ed essere in grado di eseguire PowerShell remoto. È necessario seguire i passaggi descritti in questo argomento per tutti gli account utente che non hanno VoIP aziendale abilitati per Skype for Business Online.
  
## <a name="enable-phone-system-voice-services"></a>Abilitare Sistema telefonico servizi vocali

Per abilitare un utente per Sistema telefonico Voice e segreteria telefonica, è necessario eseguire alcuni passaggi iniziali, ad esempio verificare se il connettore Skype for Business Online è distribuito sui server e abilitare gli utenti per la segreteria telefonica ospitata.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Per abilitare gli utenti per la Sistema telefonico vocale e la segreteria telefonica

> [!NOTE]
> Skype for Business Online Connector fa attualmente parte dell'Teams PowerShell più recente.
> Se si usa la versione pubblica più [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)non è necessario installare il connettore Skype for Business Online.

1. Prima di iniziare, verificare che il Teams PowerShell sia installato nei Front End Server. In caso contrario, eseguire l'installazione usando le istruzioni in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).
    
2. Avviare Windows PowerShell amministratore.
    
3. Digitare quanto segue e premere INVIO:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Utilizzare il cmdlet Set-CsUser per assegnare le proprietà $EnterpriseVoiceEnabled e $HostedVoiceMail all'utente nel modo seguente:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Ad esempio:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > È inoltre possibile specificare un utente in base all'indirizzo SIP, al nome dell'entità utente (UPN), al nome di dominio e al nome utente (dominio\nomeutente) e al nome visualizzato in Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Aggiornare l'URI linea e il dial plan per gli utenti abilitati per Sistema telefonico

In questa sezione viene descritto come aggiornare l'URI linea e il dial plan per gli utenti abilitati per Sistema telefonico. 
  
### <a name="to-update-the-line-uri"></a>Per aggiornare l'URI linea

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Usa il menu Start o il collegamento sul desktop per aprire il Skype for Business Server Pannello di controllo.
    
    > [!NOTE]
    > È inoltre possibile aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Skype for Business Server Di controllo. 
  
3. Sulla barra di spostamento sinistra fare clic su **Utenti**.
    
4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.
    
5. Nella tabella fare clic sull'Skype for Business utente che si desidera modificare l'URI di riga.
    
6. Fare **clic su URI** linea e digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200. Quindi fare clic su **Commit**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Aggiornare il dial plan utilizzando i cmdlet di Windows PowerShell locali

È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet [Grant-CsDialPlan.](/powershell/module/skype/grant-csdialplan?view=skype-ps) È possibile eseguire questo cmdlet dal Skype for Business Server 2015 o da una sessione remota di Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Per assegnare un dial plan per utente a un singolo utente

- Utilizzare il cmdlet [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) per assegnare il dial plan per utente RedmondDialPlan all'utente Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Per assegnare un dial plan per utente a più utenti

- Il comando seguente assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser:](/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> È possibile utilizzare dial plan globali o utente per gli utenti online. I dial plan del sito non possono essere utilizzati in quanto si applicano solo agli utenti ospitati in locale e assegnati a un sito locale. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Per annullare l'assegnazione di un dial plan per utente

- Utilizzare il cmdlet [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) per annullare l'assegnazione di qualsiasi dial plan per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione del dial plan per utente, Ken Myer verrà gestito automaticamente utilizzando il dial plan globale o il dial plan con ambito di servizio assegnato alla funzione di registrazione o al gateway PSTN. Un dial plan con ambito di servizio ha la precedenza sul dial plan globale:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Aggiornare i criteri di routing vocale utilizzando i cmdlet di Windows PowerShell locali

In questa sezione viene descritto come aggiornare i criteri di routing vocale per gli utenti abilitati per Sistema telefonico.
  
Sistema telefonico agli utenti deve essere assegnato un criterio di routing vocale per consentire il corretto instradamento delle chiamate. Questo comportamento è diverso dagli utenti di voIP aziendale locali che richiedono l'assegnazione di un criterio vocale per consentire il corretto routing delle chiamate. I criteri di routing vocale devono contenere utilizzi PSTN che definiscono le chiamate e le route autorizzate per Sistema telefonico utenti. È possibile copiare questi utilizzi PSTN dai criteri vocali esistenti ai nuovi criteri di routing vocale. Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy.](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)
  
> [!NOTE]
> A Sistema telefonico utenti viene assegnato lo stesso criterio vocale online denominato BusinessVoice che definisce le funzionalità di chiamata consentite; ad esempio, Consenti anello simultaneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Per assegnare un criterio di routing vocale per utente a un singolo utente

- Utilizzare il cmdlet [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) per assegnare il criterio di routing vocale per utente RedmondVoiceRoutingPolicy all'utente Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Per assegnare un criterio di routing vocale per utente a più utenti

- Il comando successivo assegna il criterio di routing vocale per utente RedmondVoiceRoutingPolicy a tutti gli utenti che lavorano nella città di Redmond. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > È possibile utilizzare criteri di routing vocale globali o utente per gli utenti online. I criteri di routing vocale del sito non possono essere utilizzati in quanto si applicano solo agli utenti ospitati in locale e assegnati a un sito locale. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Per annullare l'assegnazione di un criterio di routing vocale per utente

- Utilizzare il Grant-CsVoiceRoutingPolicy per annullare l'assegnazione di qualsiasi criterio di routing vocale per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione del criterio di routing vocale per utente, Ken Myer verrà gestito automaticamente utilizzando il criterio di routing vocale globale.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Per ulteriori informazioni, vedere [Grant-CsVoiceRoutingPolicy.](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)
