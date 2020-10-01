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
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c359b39707b57a653f35e75497672d306209ccd
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328215"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Considerazioni sull'aggiornamento per le organizzazioni con Skype for Business Server locale &mdash; per gli amministratori IT

In questo articolo vengono illustrate altre considerazioni per le organizzazioni con Skype for Business Server locale. Questo articolo è il quarto di diversi che descrivono i concetti di aggiornamento e l'implementazione per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- **Considerazioni aggiuntive per le organizzazioni con Skype for business locale** (questo articolo)
- [Implementazione dell'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni su PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerazioni per le organizzazioni con Skype for Business Server locale

- La configurazione di Skype for business Hybrid è un prerequisito per la migrazione alla modalità TeamsOnly. Anche se è possibile usare le squadre in modalità isole senza ibrida, la transizione alla modalità TeamsOnly non può essere eseguita finché l'utente non viene spostato da Skype for business locale a Skype for business online (usando [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Per altre informazioni, vedere [configurare la connettività ibrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Se l'organizzazione ha Skype for Business Server e non è stata configurata la connettività ibrida, ma si vuole comunque usare teams, per amministrare la funzionalità teams, è necessario usare un account di amministrazione che disponga di un dominio con estensione onmicrosoft.com. 

- Gli utenti di team che hanno un account Skype for business locale (ovvero non sono ancora stati spostati nel cloud usando Move-CsUser) non possono interagire con gli utenti di Skype for business, né possono essere federati con utenti esterni. Questa funzionalità è disponibile solo quando gli utenti vengono spostati nel cloud (in modalità isole o come utenti di TeamsOnly). 

- Se si hanno utenti con account Skype for business in locale, non è possibile assegnare la modalità TeamsOnly a livello di tenant. Devi prima di tutto trasferire tutti gli utenti con gli account Skype for business locali nel cloud usando `Move-CsUser` e quindi [disabilitare Hybrid per completare la migrazione al cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` non funziona a livello di tenant se viene rilevato un record DNS di Lyncdiscover che punta a una posizione diversa da Office 365.

- Devi assicurarti che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi Skype for business corretti. Questi attributi sono tutti prefissi con "msRTCSIP-". Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in teams non saranno in grado di gestire questi utenti. Ad esempio, non sarà possibile assegnare criteri di teams agli utenti locali, a meno che non si stiano sincronizzando correttamente questi attributi. Per altre informazioni, vedere [configurare Azure ad Connect per Teams e Skype for business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Per creare un nuovo utente di TeamsOnly o Skype for business online in un'organizzazione ibrida, *è prima di tutto necessario abilitare l'utente in Skype for Business Server locale*e quindi trasferire l'utente dal locale al cloud usando Move-CsUser.  La creazione dell'utente in locale garantisce innanzitutto che tutti gli altri utenti di Skype for business rimanenti saranno in grado di instradare l'utente appena creato. Una volta che tutti gli utenti sono stati spostati online, non è più necessario abilitare prima gli utenti in locale.

- Quando un utente viene spostato dal locale al cloud, le riunioni organizzate dall'utente vengono migrate in Skype for business online o in teams, a seconda che venga specificato o meno l'opzione-MoveToTeams.

- Se si vogliono visualizzare le notifiche nel client Skype for business per gli utenti locali, è necessario usare TeamsUpgradePolicy nel set di strumenti locale. Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.  Gli utenti locali ricevono la modalità dalle istanze online di TeamsUpgradePolicy. Vedere le note in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Qualsiasi nuovo tenant creato dopo il 3 settembre 2019 viene creato come tenant di TeamsOnly, a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server. Microsoft usa i record DNS per identificare le organizzazioni di Skype for Business Server locale. Se l'organizzazione ha un server Skype for business locale senza voci DNS pubbliche, è necessario chiamare il supporto Microsoft per declassare il nuovo tenant. 













## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

