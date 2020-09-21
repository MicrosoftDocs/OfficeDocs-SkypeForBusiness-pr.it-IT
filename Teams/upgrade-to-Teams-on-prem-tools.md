---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Eseguire l'aggiornamento da Skype for business a teams-strumenti per l'aggiornamento
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b910a93435cedfc1dcc83c34b766d9121f93eea
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955953"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>Strumenti per l'aggiornamento ai team &mdash; per gli amministratori IT

In questo articolo vengono illustrati gli strumenti per l'aggiornamento ai team. Questo articolo è il terzo di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- **Strumenti per la gestione dell'aggiornamento**   (questo articolo)
- [Considerazioni aggiuntive per le organizzazioni con Skype for business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementare l'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni su PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>Strumenti per la gestione dell'aggiornamento

Qualunque sia il metodo di aggiornamento scelto, è possibile gestire la transizione a TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), che controlla la modalità di coesistenza di un utente. Per altre informazioni su ognuna delle modalità, vedere [modalità di coesistenza](migration-interop-guidance-for-teams-with-skype.md).

Sia che si esegua una transizione di selezione delle funzionalità usando le modalità Skype for business o semplicemente l'aggiornamento alla modalità TeamsOnly dalla configurazione predefinita Islands, TeamsUpgradePolicy è lo strumento principale. Come qualsiasi altro criterio in teams, puoi assegnare TeamsUpgradePolicy direttamente a un utente. È anche possibile impostare i criteri come predefiniti a livello di tenant. Qualsiasi assegnazione a un utente ha la precedenza sull'impostazione predefinita del tenant.  È possibile gestire i criteri nella console di amministrazione di teams e in PowerShell.

È possibile assegnare qualsiasi modalità di TeamsUpgradePolicy agli utenti se l'utente è ospitato in Skype for business online o in locale, **ad eccezione del fatto che la modalità TeamsOnly può essere assegnata solo a un utente già disponibile in Skype for business online**. Il motivo è che l'interoperabilità con gli utenti di Skype for business e la Federazione, oltre alle funzionalità del sistema telefonico Microsoft 365, è possibile solo se l'utente è ospitato in Skype for business online.

Gli utenti con account Skype for business ospitati in locale [devono essere spostati online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (Skype for business online o Direct to Teams) usando Move-CsUser nel set di strumenti locali di Skype for business. Questi utenti possono essere spostati in TeamsOnly in uno o due passaggi:

-   1 passaggio: specificare l'opzione-MoveToTeams in Move-CsUser. In questo articolo è necessario Skype for Business Server 2019 o Skype for Business Server 2015 con CU8 o versioni successive.

-   2 passaggi: dopo aver eseguito Move-CsUser, concedere la modalità TeamsOnly all'utente usando TeamsUpgradePolicy.

A differenza di altri criteri, non è possibile creare nuove istanze di TeamsUpgradePolicy in Microsoft 365 o Office 365. Tutte le istanze esistenti sono compilate nel servizio.  Tieni presente che la modalità è una proprietà all'interno di TeamsUpgradePolicy, piuttosto che il nome di un'istanza di criteri. In alcuni casi, ma non tutti, il nome dell'istanza di criterio corrisponde alla modalità. In particolare, per assegnare la modalità TeamsOnly a un utente, l'istanza "UpgradeToTeams" di TeamsUpgradePolicy viene assegnata all'utente. Per visualizzare un elenco di tutte le istanze, è possibile eseguire il comando seguente:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Per aggiornare un utente online alla modalità TeamsOnly, assegna l'istanza "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Per aggiornare un utente locale di Skype for business alla modalità TeamsOnly, USA Move-CsUser nel set di strumenti locale:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Per modificare la modalità per tutti gli utenti del tenant, ad eccezione di quelli che hanno una concessione esplicita per utente (che ha la precedenza), eseguire il comando seguente:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se si hanno utenti con account Skype for business in locale, non è necessario assegnare la modalità TeamsOnly a livello di tenant, a meno che non si assegni esplicitamente un'altra modalità a tutti gli utenti con account Skype for business locale.


## <a name="using-notifications-in-skype-for-business-clients"></a>Uso delle notifiche nei client Skype for business

Gli amministratori hanno la possibilità di fornire notifiche degli utenti finali nel client Skype for business per informare gli utenti che presto verranno aggiornati ai team, come illustrato nel diagramma seguente. Ad esempio, una settimana prima che l'amministratore abbia intenzione di aggiornare un gruppo di utenti alla modalità TeamsOnly, l'amministratore potrebbe voler attivare queste notifiche per il gruppo di utenti. Queste notifiche sono abilitate usando un'istanza di TeamsUpgradePolicy con NotifySfbUsers = true.  Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers.  Per tutte le modalità diverse da TeamsOnly, esistono in realtà due istanze per modalità, che corrispondono ai due valori di NotifySfbUsers. 

![Diagramma che mostra le notifiche](media/teams-upgrade-sfb-with-notifications.png)

Se gli utenti sono ospitati in Skype for business online, è sufficiente assegnare l'istanza di criteri con la stessa modalità dell'utente, ma con NotifySfbUsers = true. 

Se gli utenti sono ospitati in Skype for Business Server locale, sarà necessario usare il set di strumenti locale e sarà necessario Skype for Business Server 2019 o CU8 per Skype for Business Server 2015. Per gli utenti ospitati in Skype for Business Server locale, la proprietà Mode dell'istanza online di TeamsUpgradePolicy è onorata, ma la proprietà NotifySfbUsers non è. Se si desidera ricevere le notifiche, è necessario creare un'istanza locale di TeamsUpgradePolicy per controllare il comportamento del client. 

Nella finestra di PowerShell locale creare una nuova istanza di TeamsUpgradePolicy con NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Quindi, usando la stessa finestra di PowerShell locale, assegna il nuovo criterio agli utenti desiderati:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>Migrazione delle riunioni

Quando un utente viene migrato in modalità TeamsOnly, per impostazione predefinita le riunioni Skype for business esistenti che hanno organizzato verranno convertite in teams. Puoi facoltativamente disabilitare il comportamento predefinito quando assegni la modalità TeamsOnly a un utente. Quando si spostano utenti da locale, le riunioni devono essere migrate nel cloud per funzionare con l'account utente online, ma se non si specifica-MoveToTeams, le riunioni verranno migrate come riunioni Skype for business, anziché convertite in teams. 

Quando si assegna la modalità TeamsOnly a livello di tenant, la migrazione delle riunioni non viene attivata per gli utenti. Se si vuole assegnare la modalità TeamsOnly a livello di tenant e eseguire la migrazione delle riunioni, è possibile usare PowerShell per ottenere un elenco di utenti nel tenant (ad esempio, usando Get-CsOnlineUser con tutti i filtri necessari) e quindi scorrere ogni utente per attivare la migrazione delle riunioni usando Start-CsExMeetingMigration. Per informazioni dettagliate, vedere [uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).



## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

