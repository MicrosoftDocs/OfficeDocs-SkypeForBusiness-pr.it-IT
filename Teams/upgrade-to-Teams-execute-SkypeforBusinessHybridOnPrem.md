---
title: Aggiornare Skype for Business locale a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Informazioni su come aggiornare l'organizzazione a Microsoft Teams da una distribuzione Skype for Business locale.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c45770258d452c3f84c707a51812d2e336ce48ee
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282173"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Eseguire l'Skype for Business locale a Teams

![Diagramma del percorso di aggiornamento, enfatizzando la distribuzione e l'implementazione](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

-   [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
-   [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
-   [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparare l'ambiente](./upgrade-prepare-environment.md)
-   [Preparare l'organizzazione](./upgrade-prepare-organization.md)
-   [Ha condotto un progetto pilota](./pilot-essentials.md)

Se è stato distribuito Skype for Business Server o Microsoft Lync locale e l'organizzazione vuole eseguire l'aggiornamento a Teams, seguire le istruzioni di questo articolo. È necessario configurare la connettività ibrida con l'organizzazione Microsoft 365 o Office 365 e determinare i requisiti di coesistenza se si spostano gli utenti in Teams in fasi.

Prima di iniziare, i professionisti IT e gli amministratori devono esaminare le considerazioni importanti [per](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) le organizzazioni con Skype for Business Server locali più avanti in questo articolo.

> [!IMPORTANT]
> Skype for Business Online verrà ritirato il 31 luglio 2021 e non sarà più accessibile o supportato. Per ottimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, è importante iniziare il viaggio verso Microsoft Teams oggi. Tenere presente che un aggiornamento riuscito allinea la preparazione tecnica e quella dell'utente, quindi assicurarsi di usare le indicazioni riportate di seguito mentre ci si sposta verso Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Passaggio 1: Configurare la connettività ibrida 

Il prerequisito fondamentale per l'aggiornamento degli utenti locali a Teams è la configurazione della connettività ibrida per la distribuzione Skype for Business Server locale. 

Per iniziare, leggere [Pianificare la connettività](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) ibrida e quindi seguire le attività descritte in [Configurare la connettività ibrida.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Passaggio 2: Impostare la modalità di coesistenza di transizione (facoltativo)

La coesistenza e l'interoperabilità tra Skype for Business e Teams client e utenti sono definiti dalle modalità Teams di aggiornamento.  Per impostazione predefinita, le organizzazioni sono in modalità Isole, che consente agli utenti di usare client Teams e Skype for Business client affiancati.

Per un'organizzazione che si sposta su Teams, la modalità TeamsOnly è la destinazione finale per ogni utente, anche se non è necessario assegnare a tutti gli utenti TeamsOnly (o qualsiasi altra modalità) contemporaneamente.

Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono facoltativamente usare una delle modalità di coesistenza di Skype for Business per garantire comunicazioni prevedibili tra gli utenti che sono in modalità TeamsOnly e gli utenti che non lo sono ancora.  Lo scopo delle modalità di coesistenza di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è fornire agli utenti finali un'esperienza semplice e prevedibile durante la transizione da Skype for Business a Teams. 

Quando un utente è in una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono instradati al client di Skype for Business dell'utente. Per evitare confusione tra gli utenti finali e garantire la corretta funzionalità di routing, chiamate e chat nel client Teams viene disabilitata quando un utente si trova in una delle modalità Skype for Business. Analogamente, la pianificazione delle riunioni in Teams viene disabilitata in modo esplicito quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata in modo esplicito quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere Indicazioni sulla migrazione e [l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams con Skype for Business e Impostazione delle impostazioni di [coesistenza e aggiornamento.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Passaggio 3: Spostare gli utenti da Skype for Business locale a Teams solo

In definitiva, è necessario spostare gli utenti in modalità TeamsOnly. Questa operazione può richiedere uno o due passaggi a seconda dell'ambiente locale.  

Per altre informazioni, vedere Spostare gli utenti tra l'ambiente locale e il [cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e Spostare gli utenti da locale a [Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Passaggio 4: Disabilitare l'ambiente ibrido per completare la migrazione nel cloud

Dopo aver spostato tutti gli utenti dall'ambiente locale al cloud, è possibile rimuovere la distribuzione locale Skype for Business locale. Per altre informazioni, vedere [Disabilitare la distribuzione ibrida per completare la migrazione nel cloud.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefonico di connettività PSTN e pstn

Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business. 

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), è possibile passare dalla modalità locale Skype for Business alla modalità TeamsOnly in due scenari:

- Un utente in Skype for Business locale con VoIP aziendale, che si trasferirà online e usa un piano Per chiamate Microsoft. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.  Per altre informazioni, vedere [Da Skype for Business Server locale, con VoIP aziendale, a Piano chiamate Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Un utente in Skype for Business locale con VoIP aziendale, che si trasferirà online e mantiene la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account di Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. Per altre informazioni, vedere [Da Skype for Business Server locale, con VoIP aziendale, a Routing diretto.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerazioni importanti per le organizzazioni con Skype for Business Server locali

- Gli articoli seguenti descrivono importanti concetti di aggiornamento e comportamenti di coesistenza:
    - [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
    - [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

- La configurazione Skype for Business ibrida è un prerequisito per la migrazione alla modalità TeamsOnly. Anche se è possibile usare Teams in modalità Isole senza configurazione ibrida, la transizione alla modalità TeamsOnly non può essere effettuata finché l'utente non viene spostato da Skype for Business locale a Skype for Business Online (con [Move-CsUser).](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Per altre informazioni, vedere [Configurare la connettività ibrida.](/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Se l'organizzazione ha Skype for Business Server e non è stata configurata la connettività ibrida, ma si vuole comunque usare Teams, per amministrare la funzionalità di Teams, è necessario usare un account amministrativo con un dominio onmicrosoft.com. 

- Teams gli utenti che hanno un account di Skype for Business locale, ovvero non sono ancora stati spostati nel cloud con Move-CsUser, non possono interagire con gli utenti di Skype for Business né possono eseguire la federazione con utenti esterni. Questa funzionalità è disponibile solo quando gli utenti vengono spostati nel cloud (in modalità Isole o come utenti TeamsOnly). 

- Se si hanno utenti con Skype for Business account locali, non è possibile assegnare la modalità TeamsOnly a livello di tenant. È prima di tutto necessario spostare tutti gli utenti con account Skype for Business locali nel cloud usando e quindi disabilitare la distribuzione ibrida per completare `Move-CsUser` [la migrazione al cloud.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`non funzionerà a livello di tenant se viene rilevato un record DNS lyncdiscover che punta a una posizione diversa da Office 365.

- È necessario assicurarsi che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi Skype for Business corretti. Questi attributi sono tutti prefissi con "msRTCSIP-". Se gli utenti non sono sincronizzati correttamente con Azure AD, gli strumenti di gestione in Teams non saranno in grado di gestire questi utenti. Ad esempio, non sarà possibile assegnare criteri di Teams agli utenti locali a meno che questi attributi non vengano sincronizzati correttamente. Per altre informazioni, vedere [Configurare azure AD Connessione per Teams e Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Per creare un nuovo utente teamsOnly o Skype for Business Online in un'organizzazione ibrida, è necessario prima abilitare l'utente *in Skype for Business Server* locale e quindi spostare l'utente dall'ambiente locale al cloud usando Move-CsUser.  La creazione dell'utente in locale garantisce prima di tutto che tutti gli altri utenti locali Skype for Business possano instradare l'utente appena creato. Dopo che tutti gli utenti sono stati spostati online, non è più necessario abilitare prima gli utenti in locale.

- Quando un utente viene spostato dall'ambiente locale al cloud, viene eseguita la migrazione delle riunioni organizzate da tale utente a Skype for Business Online o Teams, a seconda che sia o meno specificato l'opzione -MoveToTeams.

- Se si desidera visualizzare le notifiche nel client Skype for Business per gli utenti locali, è necessario usare TeamsUpgradePolicy nel set di strumenti locale. Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.  Gli utenti locali ricevono la loro modalità dalle istanze online di TeamsUpgradePolicy. Vedere le note in [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> I nuovi tenant creati dopo il 3 settembre 2019 vengono creati come tenant TeamsOnly a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server. Microsoft usa i record DNS per identificare le organizzazioni locali Skype for Business Server locali. Se l'organizzazione ha account locali Skype for Business Server senza voci DNS pubbliche, è necessario chiamare il supporto Microsoft per eseguire il downgrade del nuovo tenant. 

## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)