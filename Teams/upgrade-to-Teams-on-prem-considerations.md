---
title: Eseguire l'aggiornamento a Teams da una distribuzione locale di Skype for Business - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533593"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Considerazioni sull'aggiornamento per le organizzazioni con Skype for Business Server locale &mdash; per amministratori IT

Questo articolo descrive altre considerazioni da tenere in considerazione per le organizzazioni con Skype for Business Server locale. Questo articolo è il quarto di diversi articoli che descrivono i concetti e l'implementazione dell'aggiornamento per gli amministratori IT.  

- [Panoramica](upgrade-to-teams-on-prem-overview.md)
- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- **Considerazioni aggiuntive per le organizzazioni con Skype for Business locale** (questo articolo)
- [Implementazione dell'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni sulla rete PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerazioni per le organizzazioni con Skype for Business Server locale

- La configurazione ibrida di Skype for Business è un prerequisito per la migrazione alla modalità TeamsOnly. Anche se è possibile usare Teams in modalità isole senza distribuzione ibrida, la transizione alla modalità TeamsOnly non può essere effettuata finché l'utente non viene spostato da Skype for Business locale a Skype for Business online (con [Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Per altre informazioni, vedere [Configurare la connettività ibrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Se l'organizzazione dispone di Skype for Business Server e la connettività ibrida non è stata configurata, ma si vuole comunque usare Teams per amministrare le funzionalità di Teams, è necessario usare un account amministrativo con un dominio onmicrosoft.com. 

- Gli utenti di Teams che dispongono di un account Skype for Business locale (ovvero non sono ancora stati spostati nel cloud con Move-CsUser) non possono interagire con gli utenti di Skype for Business né possono federatire con utenti esterni. Questa funzionalità è disponibile solo dopo lo spostamento degli utenti nel cloud (in modalità Isole o in modalità TeamsOnly). 

- Se hai utenti con account Skype for Business in locale, non puoi assegnare la modalità TeamsOnly a livello di tenant. Devi prima spostare nel cloud tutti gli utenti con account Skype for Business locali e quindi disabilitare la migrazione ibrida per completare `Move-CsUser` [la migrazione al cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` non funzionerà a livello di tenant se è stato rilevato un record DNS lyncdiscover che punta a una posizione diversa da Office 365.

- È necessario assicurarsi che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi corretti di Skype for Business. Questi attributi sono tutti prefissi con "msRTCSIP-". Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in Teams non saranno in grado di gestire questi utenti. Ad esempio, non sarà possibile assegnare criteri di Teams agli utenti locali a meno che questi attributi non vengano sincronizzati correttamente. Per altre informazioni, vedere [Configurare Azure AD Connect per Teams e Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Per creare un nuovo utente TeamsOnly o Skype for Business online in un'organizzazione ibrida, devi prima abilitare l'utente *in Skype for Business Server* locale, quindi spostarlo dalla distribuzione locale al cloud con Move-CsUser.  La creazione dell'utente in locale assicura prima che tutti gli altri utenti skype for Business locali rimanenti saranno instraderanno all'utente appena creato. Dopo aver spostato tutti gli utenti online, non è più necessario abilitare prima gli utenti in locale.

- Quando un utente viene spostato dalla distribuzione locale al cloud, le riunioni organizzate da quell'utente vengono migrate a Skype for Business Online o Teams, a seconda che sia o meno specificato il parametro -MoveToTeams.

- Se desideri visualizzare le notifiche nel client Skype for Business per gli utenti locali, devi utilizzare TeamsUpgradePolicy nel set di strumenti locale. Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.  Gli utenti locali ricevono la modalità dalle istanze online di TeamsUpgradePolicy. Vedere le note in [Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> I nuovi tenant creati dopo il 3 settembre 2019 vengono creati come tenant TeamsOnly, a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server. Microsoft usa i record DNS per identificare le organizzazioni Skype for Business Server locali. Se l'organizzazione dispone di Skype for Business Server locale senza voci DNS pubbliche, sarà necessario chiamare il supporto Tecnico Microsoft per eseguire il downgrade del nuovo tenant. 













## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

