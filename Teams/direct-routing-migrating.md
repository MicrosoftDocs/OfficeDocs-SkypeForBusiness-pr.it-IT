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
description: Informazioni su cosa è necessario per eseguire la migrazione a routing diretto da una prospettiva di configurazione di Skype for business online e teams.
ms.openlocfilehash: 85b53bf33cd8f9015ea9294876a06da3532ad085
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836056"
---
# <a name="migrate-to-direct-routing"></a>Eseguire la migrazione a Instradamento diretto

Questo articolo descrive le informazioni necessarie per eseguire la migrazione a routing diretto da una prospettiva di configurazione di Skype for business online e Microsoft teams. Questo articolo illustra la migrazione da quanto segue: 
 
- Sistema telefonico Office 365 con piani di chiamata (per team e Skype for business online) 
- Sistema telefonico Office 365 con connettività PSTN locale in Skype for Business Server (per Skype for business online)  
- Sistema telefonico Office 365 con connettività PSTN locale tramite Cloud Connector Edition (per Skype for business online)

  
Oltre a questi passaggi di configurazione, la configurazione è necessaria anche per il controller Border Session (SBC) per instradare le chiamate alla nuova route. Che esula dall'ambito di questo documento. Per altre informazioni, vedere la documentazione del fornitore SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Stato finale di provisioning degli utenti per varie opzioni di connettività PSTN 

La tabella seguente mostra lo stato di fine di un utente con provisioning per le opzioni di connettività PSTN selezionate con il sistema telefonico di Office 365. Vengono visualizzati solo gli attributi rilevanti per la voce.

|Attributi degli oggetti utente |Sistema telefonico con piani di chiamata|Sistema telefonico con connettività PSTN locale tramite Skype for Business Server|Sistema telefonico con connettività PSTN locale tramite connettore Cloud|Sistema telefonico con connettività PSTN locale tramite routing diretto|
|---|---|---|---|---|
|Client|Skype for business o Teams |Skype for business |Skype for business |Teams|
|Licenze|Skype business online</br>Piano 2</br></br>MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)</br></br></br>Piani di chiamata</br>Teams|Skype business online Plan 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)|Skype business online Plan 2 (MCOProfessional o MCOSTANDARD)</br></br></br>Sistema telefonico (MCOEV)|Skype business online Plan 2 (MCOProfessional o MCOSTANDARD</br></br></br>Sistema telefonico (MCOEV)</br></br>Teams|
OnPremLineURI |N/D|Il numero di telefono deve essere sincronizzato dall'annuncio locale. |Il numero di telefono può essere gestito sia in Active Directory locale che in Azure Active Directory.|Il numero di telefono può essere gestito sia in Active Directory locale che in Azure Active Directory. Tuttavia, se l'organizzazione ha Skype for business locale, il numero deve essere sincronizzato dall'Active Directory locale.|
|LineURI|Numero di telefono chiamante PSTN|Imposta automaticamente dal parametro OnPremLineURI|Imposta automaticamente dal parametro OnPremLineURI|Imposta automaticamente dal parametro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Ha un valore|Ha un valore|Ha un valore|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Ha un valore|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/D|N/D|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/D|N/D|True|
||||||

<sup>1</sup> La scelta della modalità corretta di TeamsUpgradePolicy dipende dallo scenario. Leggere l'esperienza vocale in diverse modalità nelle [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md).

Come parte di questo sforzo, Microsoft ha recentemente aggiornato l'"interfaccia di amministrazione di Microsoft Teams" (noto anche come Modern Portal) per riflettere il nuovo modello di gestione basato sulle modalità di coesistenza. In Modern Portal la configurazione di TeamsUpgradePolicy ora imposta automaticamente anche TeamsInteropPolicy su un valore uniforme, quindi TeamsInteropPolicy non viene più esposto nell'interfaccia utente. Tuttavia, gli amministratori che usano PowerShell devono comunque impostare sia TeamsUpgradePolicy che TeamsInteropPolicy insieme per garantire il routing corretto. Una volta completata la transizione a TeamsUpgradePolicy, non sarà più necessario impostare anche TeamsInteropPolicy.

Per altre informazioni, fare riferimento alle [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrazione da piani di chiamata

Per altre informazioni sulla migrazione dai piani di chiamata, vedere:

- [Configurare i piani per chiamate](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice utente](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
È consigliabile rimuovere le informazioni del piano di licenza configurate in precedenza nel modo seguente:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrazione da Office 365 Phone System con connettività PSTN locale in Skype for Business Server

Per altre informazioni sulla migrazione da un sistema telefonico a una connettività PSTN locale in Skype for Business Server, vedere quanto segue:

- [Pianificazione](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Distribuzione](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

È consigliabile rimuovere le informazioni di routing vocale configurate in precedenza come indicato di seguito:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> Se è configurato un CsVoiceRoutingPolicy globale, è consigliabile rimuovere qualsiasi utilizzo PSTN associato a questo criterio globale. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrazione da Office 365 Phone System con connettività PSTN locale tramite Cloud Connector Edition 

Per altre informazioni sulla migrazione da un sistema telefonico a una connettività PSTN locale tramite connettore Cloud, vedere quanto segue:

- [Pianificazione](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Distribuzione](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configurazione utente](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

È consigliabile rimuovere le informazioni di routing vocale configurate in precedenza come indicato di seguito:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>COLLEGAMENTI CORRELATI

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

