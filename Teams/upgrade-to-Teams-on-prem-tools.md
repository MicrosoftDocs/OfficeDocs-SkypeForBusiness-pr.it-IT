---
title: Strumenti per l'aggiornamento a Teams da una Skype for Business locale
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Strumenti per l'aggiornamento da Skype for Business a Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d98257e9a29564d22b57c5cc537d703bbb1fe842
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729305"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Strumenti per l'aggiornamento a Teams &mdash; per gli amministratori IT

Questo articolo descrive gli strumenti per l'aggiornamento a Teams da Skype for Business. 

Prima di iniziare l'aggiornamento, Microsoft consiglia gli articoli seguenti che descrivono i concetti importanti per l'aggiornamento e i comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>Strumenti per la gestione dell'aggiornamento

Indipendentemente dal metodo di aggiornamento scelto, per gli utenti che hanno già Skype for Business Online, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy,](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)che controlla la modalità di coesistenza di un utente. Per gli utenti con un account locale in Skype for Business Server, è anche possibile `Move-CsUser` [spostarli nel cloud.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  Per altre informazioni su ognuna delle modalità, vedere [Modalità di coesistenza.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> Se attualmente si usa Skype for Business Online Connector per gestire i servizi, è necessario passare al modulo di PowerShell di Teams e aggiornare gli script di PowerShell esistenti. Per altre informazioni, vedere Passare [da Skype for Business Online Connector al Teams di PowerShell.](teams-powershell-move-from-sfbo.md)

TeamsUpgradePolicy è lo strumento principale per eseguire una transizione delle funzionalità selezionate usando le modalità di Skype for Business o semplicemente eseguire l'aggiornamento alla modalità TeamsOnly dalla configurazione predefinita isole. Come qualsiasi altro criterio in Teams, è possibile assegnare TeamsUpgradePolicy direttamente a un utente. È anche possibile impostare il criterio come predefinito a livello di tenant. Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.  È possibile gestire i criteri nella console di amministrazione Teams e in PowerShell.

È possibile assegnare qualsiasi modalità di TeamsUpgradePolicy, ad eccezione della modalità TeamsOnly, agli utenti ospitati Skype for Business locale. Al contrario, agli utenti ospitati nel cloud può essere assegnata solo la modalità TeamsOnly. La modalità **TeamsOnly** può essere assegnata solo a un utente che si trova già nel cloud perché l'interoperabilità e la federazione con gli utenti di Skype for Business e le funzionalità di Microsoft 365 Sistema telefonico sono possibili solo se l'utente si trova in Skype for Business Online.  Inoltre, non è possibile assegnare la modalità TeamsOnly come impostazione predefinita a livello di tenant se si ha una distribuzione locale di **Skype for Business,** rilevata dalla presenza di un record DNS di lyncdiscover che punta a una posizione diversa da Office 365. Per informazioni dettagliate, [vedere Disabilitare la configurazione ibrida per completare la migrazione a Teams solo](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).

Gli utenti Skype for Business account locali devono essere spostati [online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) in modalità solo Teams usando Move-CsUser nel set di strumenti Skype for Business locale. 

A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365. Tutte le istanze esistenti sono incorporate nel servizio.  Si noti che la modalità è una proprietà all'interno di TeamsUpgradePolicy, anziché il nome di un'istanza dei criteri. In alcuni casi, ma non in tutti, il nome dell'istanza dei criteri corrisponde alla modalità. In particolare, per assegnare la modalità TeamsOnly a un utente, si concede l'istanza "UpgradeToTeams" di TeamsUpgradePolicy a tale utente. Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Per aggiornare un utente online alla modalità TeamsOnly, assegnare l'istanza "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Per aggiornare un utente locale Skype for Business alla modalità TeamsOnly, usare Move-CsUser nel set di strumenti locale:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

Per cambiare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se si hanno utenti con Skype for Business account locali, non è possibile assegnare la modalità TeamsOnly a livello di tenant. È necessario spostare questi utenti singolarmente in Teams modalità Solo con Move-CsUser.


## <a name="using-notifications-in-skype-for-business-clients"></a>Uso delle notifiche nei Skype for Business client

Gli amministratori hanno la possibilità di fornire notifiche agli utenti finali nel client Skype for Business per informare gli utenti che presto verranno aggiornati a Teams, come illustrato nel diagramma seguente. Ad esempio, una settimana prima che l'amministratore pianichi di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per quel gruppo di utenti. Queste notifiche vengono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers=true.  Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers.  Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, corrispondenti ai due valori di NotifySfbUsers. 

![Diagramma che mostra le notifiche.](media/teams-upgrade-sfb-with-notifications.png)

Se gli utenti sono ospitati in Skype for Business Online, è sufficiente assegnare l'istanza dei criteri che ha la stessa modalità dell'utente, ma con NotifySfbUsers=true. 

Se gli utenti sono ospitati in Skype for Business Server locale, è necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015. Per gli utenti ospitati in Skype for Business Server locale, viene rispettata la proprietà mode dell'istanza online di TeamsUpgradePolicy, ma non la proprietà NotifySfbUsers. Se si desidera ricevere notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client. 

Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers=true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Quindi, usando la stessa finestra di PowerShell locale, assegnare il nuovo criterio agli utenti desiderati:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migrazione delle riunioni

Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for Business che hanno organizzato verranno convertite in Teams. Facoltativamente, è possibile disabilitare il comportamento predefinito quando si assegna la modalità TeamsOnly a un utente. Quando si spostano utenti dall'ambiente locale, è necessario eseguire la migrazione delle riunioni nel cloud per funzionare con l'account utente online, ma se non si specifica -MoveToTeams, le riunioni verranno migrate come riunioni Skype for Business anziché convertite in Teams. 

Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti. Se si vuole assegnare la modalità TeamsOnly a livello di tenant ed eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant , ad esempio usando Get-CsOnlineUser con tutti i filtri necessari, e quindi scorrere ognuno di questi utenti per avviare la migrazione delle riunioni con Start-CsExMeetingMigration. Per informazioni dettagliate, vedere [Uso del servizio di migrazione delle riunioni (MMS).](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>Collegamenti correlati

[Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
