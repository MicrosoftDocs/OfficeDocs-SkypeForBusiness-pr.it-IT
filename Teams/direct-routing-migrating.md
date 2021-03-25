---
title: Eseguire la migrazione a Instradamento diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri cosa è necessario per eseguire la migrazione a Direct Routing dal punto di vista della configurazione di Skype for Business Online e Teams.
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122200"
---
# <a name="migrate-to-direct-routing"></a>Eseguire la migrazione a Instradamento diretto

Questo articolo descrive cosa è necessario per eseguire la migrazione a Routing diretto dal punto di vista della configurazione di Skype for Business Online e Microsoft Teams. Questo articolo illustra la migrazione da quanto segue: 
 
- Sistema telefonico con piani per chiamate (per Teams e Skype for Business online) 
- Sistema telefonico con connettività PSTN locale in Skype for Business Server (per Skype for Business online)  
- Sistema telefonico con connettività PSTN locale tramite Cloud Connector Edition (per Skype for Business online)


Oltre a questi passaggi di configurazione, è necessaria anche la configurazione nel Session Border Controller (SBC) per instradare le chiamate al nuovo percorso. Questo non rientra nell'ambito di questo documento. Per altre informazioni, vedere la documentazione del fornitore SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Stato finale del provisioning degli utenti per varie opzioni di connettività PSTN 

La tabella seguente mostra lo stato finale per un utente di cui è stato eseguito il provisioning per le opzioni di connettività PSTN selezionate con Sistema telefonico. Vengono visualizzati solo gli attributi pertinenti per la voce.

|Attributi degli oggetti utente |Phone System e Piani di Chiamata|Sistema telefonico con connettività PSTN locale tramite Skype for Business Server|Sistema telefonico con connettività PSTN locale tramite Cloud Connector|Sistema telefonico con connettività PSTN locale tramite routing diretto|
|---|---|---|---|---|
|Client|Skype for Business o Teams |Skype for Business |Skype for Business |Teams|
|Licenze|Skype Business Online</br>Piano 2</br></br>MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)</br></br></br>Piani di chiamata</br>Teams|Skype Business Online Piano 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)|Skype Business Online Piano 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)|Skype Business Online Piano 2 (MCOProfessional o MCOSTANDARD</br></br></br>Sistema telefonico (MCOEV)</br></br>Teams|
OnPremLineURI |N/D|Il numero di telefono deve essere sincronizzato da Active Directory locale. |Il numero di telefono può essere gestito in Active Directory locale o in Azure Active Directory.|Il numero di telefono può essere gestito in Active Directory locale o in Azure Active Directory. Tuttavia, se l'organizzazione ha Skype for Business locale, il numero deve essere sincronizzato da Active Directory locale.|
|LineURI|Numero di telefono per chiamate PSTN|Imposta automaticamente dal parametro OnPremLineURI|Imposta automaticamente dal parametro OnPremLineURI|Imposta automaticamente dal parametro OnPremLineURI|
|EnterpriseVoiceEnabled|Vero|Vero|Vero|Vero|
|HostedVoiceMail |Vero|Vero|Vero|Vero|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Ha un valore|Ha un valore|Ha un valore|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Ha un valore|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|Vero|N/D|N/D|Vero|
|TeamsCallingPolicy</br>AllowGroupCalling|Vero|N/D|N/D|Vero|
||||||

<sup>1</sup> La scelta della modalità giusta di TeamsUpgradePolicy dipende dallo scenario. Per informazioni sull'esperienza vocale in diverse modalità, vedere Guida alla migrazione e [all'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)per le organizzazioni che usano Teams insieme a Skype for Business.

Nell'ambito di questo lavoro, Microsoft ha aggiornato di recente l'"interfaccia di amministrazione di Microsoft Teams" (nota anche come portale moderno) per riflettere il nuovo modello di gestione basato sulle modalità di coesistenza. Nel portale moderno, la configurazione di TeamsUpgradePolicy ora imposta automaticamente anche TeamsInteropPolicy su un valore coerente, quindi TeamsInteropPolicy non viene più esposto nell'interfaccia utente. Tuttavia, gli amministratori che usano PowerShell devono comunque impostare sia TeamsUpgradePolicy che TeamsInteropPolicy insieme per garantire il routing corretto. Al termine della transizione a TeamsUpgradePolicy, non sarà più necessario impostare anche TeamsInteropPolicy.

Per altre informazioni, vedere Guida alla migrazione e [all'interoperabilità](migration-interop-guidance-for-teams-with-skype.md)per le organizzazioni che usano Teams insieme a Skype for Business.

## <a name="migrating-from-calling-plans"></a>Migrazione da piani per chiamate

Per altre informazioni sulla migrazione da Piani per chiamate, vedere:

- [Configurare i piani per chiamate](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Utente Set-CsOnlineVoice](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
È consigliabile rimuovere le informazioni del piano di licenza configurate in precedenza nel modo seguente:
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrazione dal sistema telefonico di Office 365 con connettività PSTN locale in Skype for Business Server

Per altre informazioni sulla migrazione da Sistema telefonico con connettività PSTN locale in Skype for Business Server, vedere quanto segue:

- [Pianificazione](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Distribuzione](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

È consigliabile rimuovere le informazioni di routing vocale configurate in precedenza nel modo seguente:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Se è configurato un CsVoiceRoutingPolicy globale, è consigliabile rimuovere gli eventuali utilizzi PSTN associati a questo criterio globale. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrazione dal sistema telefonico di Office 365 con connettività PSTN locale tramite Cloud Connector Edition 

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](direct-routing-landing-page.md)

Per altre informazioni sulla migrazione da Sistema telefonico con connettività PSTN locale tramite Cloud Connector, vedere quanto segue:

- [Pianificazione](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Distribuzione](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configurazione utente](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

È consigliabile rimuovere le informazioni di routing vocale configurate in precedenza nel modo seguente:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Collegamenti correlati

[Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)