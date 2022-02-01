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
ms.localizationpriority: medium
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299061"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Eseguire l'Skype for Business locale a Teams

![Diagramma del percorso di aggiornamento, enfatizzando la distribuzione e l'implementazione.](media/upgrade-banner-deployment.png "Fasi del percorso di aggiornamento, con particolare attenzione alla fase di distribuzione e implementazione")

Questo articolo fa parte della fase di distribuzione e implementazione del percorso di aggiornamento. Prima di procedere, verificare di aver completato le attività seguenti:

-   [Coinvolgimento degli stakeholder del progetto](upgrade-enlist-stakeholders.md)
-   [Definizione dell'ambito del progetto](./upgrade-define-project-scope.md)
-   [Comprensione della coesistenza e dell'interoperabilità di Skype for Business e Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Hai scelto il percorso di aggiornamento](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparare l'ambiente](./upgrade-prepare-environment.md)
-   [Preparare l'organizzazione](./upgrade-prepare-organization.md)
-   [Ha condotto un progetto pilota](./pilot-essentials.md)

Se è stato distribuito Skype for Business Server o Microsoft Lync Server locale e l'organizzazione vuole eseguire l'aggiornamento a Teams, seguire le istruzioni di questo articolo. È necessario configurare la connettività ibrida con l'organizzazione Microsoft 365 come descritto in Pianificare la connettività ibrida tra Skype for Business Server [e Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Prima di iniziare, è consigliabile esaminare anche considerazioni importanti per le organizzazioni con Skype for Business Server locali [più avanti in](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) questo articolo.

> [!IMPORTANT]
> Skype for Business Online è stato ritirato il 31 luglio 2021. Per massimizzare la realizzazione dei vantaggi e garantire che l'organizzazione abbia il tempo necessario per implementare l'aggiornamento, ti consigliamo di iniziare il tuo viaggio verso Microsoft Teams oggi. Tenere presente che un aggiornamento riuscito allinea la conformità tecnica e quella dell'utente, quindi assicurarsi di usare queste indicazioni mentre si esplora il percorso verso Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Passaggio 1: Configurare la connettività ibrida 

Il prerequisito fondamentale per l'aggiornamento degli utenti locali a Teams è la configurazione della connettività ibrida per la distribuzione Skype for Business Server locale. 

Per iniziare,  [leggerePianificare](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) la connettività ibrida e quindi seguire le attività descritte in [Configurare la connettività ibrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Passaggio 2: Impostare la modalità di coesistenza di transizione (facoltativo)

La coesistenza e l'interoperabilità tra Skype for Business e Teams client e utenti sono definiti dalle [modalità di coesistenza](migration-interop-guidance-for-teams-with-skype.md). Le organizzazioni ibride sono per impostazione predefinita in modalità Isole. La modalità Isole consente agli utenti di usare sia Teams che Skype for Business client affiancati. Le organizzazioni possono usare facoltativamente altre modalità di coesistenza per offrire agli utenti finali un'esperienza prevedibile durante la transizione da Skype for Business a Teams. Indipendentemente dalla modalità utilizzata da un'organizzazione per gli utenti locali, quando questi vengono spostati dall'ambiente locale al cloud, diventano TeamsOnly (e non possono avere altre modalità).  Finché gli utenti usano ancora Skype for Business Server, è possibile assegnare loro una modalità diversa da TeamsOnly. Se necessario, gli utenti di TeamsOnly possono essere spostati di nuovo in locale, in modo che ricevano i criteri globali del tenant di TeamsUpgradePolicy.

Quando un utente è in una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono instradati al client Skype for Business'utente. Per evitare confusione tra gli utenti finali e garantire la corretta funzionalità di routing, chiamate e chat nel client Teams è disabilitata per un utente a cui è assegnata una delle modalità Skype for Business *messaggi*. La pianificazione delle riunioni in Teams è disabilitata quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata  quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

A seconda dei requisiti, è possibile assegnare la modalità di coesistenza appropriata in base al percorso di aggiornamento scelto dall'organizzazione. Per altre informazioni, vedere Indicazioni sulla migrazione e [l'interoperabilità](migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams con Skype for Business e Impostazione delle impostazioni di [coesistenza e aggiornamento](./setting-your-coexistence-and-upgrade-settings.md).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Passaggio 3: Spostare gli utenti da Skype for Business locale a Teams solo

Microsoft ha di recente semplificato il processo di spostamento degli utenti in TeamsOnly. Questo processo è ora un singolo passaggio, indipendentemente dalla versione di Skype for Business Server o Lync Server 2013 in uso. Per altre informazioni, vedere Spostare gli utenti tra l'ambiente locale e il cloud e Spostare gli utenti da locale a Teams.For more information, see  [Move users between on-premises and the cloud and](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) [Move users from on-premises to Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Passaggio 4: Completare la migrazione al cloud disabilitando la distribuzione ibrida e la rimozione delle autorizzazioni locali Skype for Business

Dopo aver spostato tutti gli utenti dall'ambiente locale al cloud, è possibile rimuovere la distribuzione locale Skype for Business locale. Per altre informazioni, vedere [Rimuovere](/skypeforbusiness/hybrid/decommission-on-prem-overview) l'ambiente Skype for Business locale.


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefonico di connettività PSTN e pstn

Sistema telefonico con Teams è supportato dopo che l'utente è in modalità TeamsOnly. Se l'utente è in modalità Isole, Sistema telefonico è supportato solo con Skype for Business. 

### <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Quando si valutano le opzioni di connettività PSTN (Public Switched Telephone Network), ci sono due scenari possibili quando si passa dalla Skype for Business locale alla modalità TeamsOnly:

- Un utente in Skype for Business locale con VoIP aziendale, che si trasferirà online e usa un piano Per chiamate Microsoft. La migrazione di questo utente a Teams richiede lo spostamento dell'account Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con A) la porta del numero di telefono dell'utente a un piano per chiamate Microsoft o B) assegnando un nuovo numero di abbonato dalle aree geografiche disponibili.  Per altre informazioni, vedere [Da Skype for Business Server locale, con VoIP aziendale, al piano per chiamate Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Un utente in Skype for Business locale con VoIP aziendale, che si trasferirà online e mantiene la connettività PSTN locale. La migrazione di questo utente a Teams richiede lo spostamento dell'account di Skype for Business locale dell'utente nel cloud e il coordinamento dello spostamento con la migrazione dell'utente al routing diretto. Per altre informazioni, vedere [Da Skype for Business Server locale, con VoIP aziendale, a Routing diretto](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerazioni importanti per le organizzazioni con Skype for Business Server locali

- La configurazione Skype for Business ibrida è un prerequisito per la migrazione alla modalità TeamsOnly. È possibile che gli utenti locali Skype for Business Server utenti usino Teams in modalità Isole senza configurazione ibrida. Tuttavia, la transizione alla modalità TeamsOnly non può essere effettuata senza spostare l'utente nel cloud usando [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), per cui è necessaria la connettività ibrida. Per altre informazioni, vedere [Configurare la connettività ibrida](/skypeforbusiness/hybrid/configure-hybrid-connectivity). L'imminente ritiro Skype for Business online non modificherà questo requisito. Perché le organizzazioni si spostino da Skype for Business Server a Teams, devono comunque configurare l'ambiente ibrido usando lo stesso set di strumenti, esattamente come prima del *ritiro*.

- Per spostare un utente locale nel cloud, usare `Move-CsUser` gli strumenti di amministrazione locali. Non è più necessario specificare l'opzione per `-MoveToTeams` spostare gli utenti direttamente da locale a TeamsOnly. Agli utenti viene assegnata automaticamente la modalità TeamsOnly e le riunioni locali vengono convertite automaticamente in riunioni Teams, indipendentemente `-MoveToTeams` dal fatto che l'opzione sia specificata.

- Se l'organizzazione ha Skype for Business Server e non è stata configurata la connettività ibrida, ma si vuole comunque usare Teams, per amministrare le funzionalità di Teams è necessario usare un account amministrativo con un dominio onmicrosoft.com. Senza connettività ibrida, gli strumenti di amministrazione non riconosceranno i domini locali. 

- Teams gli utenti che hanno un account Skype for Business locale, ovvero non sono ancora stati spostati nel cloud con Move-CsUser, non possono interagire con gli utenti di Skype for Business né possono eseguire la federazione con utenti esterni. Questa funzionalità è disponibile solo dopo che gli utenti sono stati spostati nel cloud e sono utenti di TeamsOnly. 

- Se si hanno utenti con account Skype for Business locali o se si ha ancora un record DNS di lyncdiscover per una distribuzione locale, non è possibile assegnare la modalità TeamsOnly a livello di tenant. È prima di tutto necessario spostare tutti gli utenti con account Skype for Business locali nel cloud usando `Move-CsUser`. Seguire quindi i passaggi descritti in [Disabilitare la distribuzione ibrida](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid) per completare la migrazione al cloud, che include la rimozione delle voci DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`non funziona a livello di tenant se viene rilevato un record DNS lyncdiscover che punta a una posizione diversa da Office 365.

- È necessario assicurarsi che gli utenti siano sincronizzati correttamente in Azure AD con gli attributi Skype for Business corretti. Questi attributi sono tutti prefissi con "msRTCSIP-". Se gli utenti non vengono sincronizzati correttamente con Azure AD, gli strumenti di gestione in Teams non saranno in grado di gestire questi utenti. Ad esempio, non sarà possibile assegnare Teams criteri di protezione agli utenti locali a meno che questi attributi non vengano sincronizzati correttamente. Per altre informazioni, vedere [Configurare Azure AD Connessione per Teams e Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Per creare un nuovo TeamsOnly in un'organizzazione ibrida, è necessario prima abilitare l'utente *in Skype for Business Server* locale e quindi spostare l'utente dall'ambiente locale al cloud usando Move-CsUser.  La creazione dell'utente in locale garantisce prima di tutto che tutti gli altri utenti locali Skype for Business possano instradare l'utente appena creato. Dopo *che* tutti gli utenti sono stati spostati online, non è più necessario abilitare prima gli utenti in locale.

- Se si desidera visualizzare le notifiche nel client Skype for Business per gli utenti locali, è necessario usare TeamsUpgradePolicy nel set di strumenti locale. Solo il parametro NotifySfbUsers è pertinente per gli utenti locali.  Gli utenti locali ricevono la propria modalità dalle istanze online di TeamsUpgradePolicy. Vedere le note in [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> I nuovi tenant creati dopo il 3 settembre 2019 vengono creati come tenant TeamsOnly a meno che l'organizzazione non abbia già una distribuzione locale di Skype for Business Server. Microsoft usa i record DNS per identificare le organizzazioni locali Skype for Business Server locali. Per altre informazioni, vedere [Implicazioni dns per le organizzazioni locali che diventano ibride](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid). 

- Gli articoli seguenti descrivono importanti concetti di aggiornamento e comportamenti di coesistenza:
    - [Coesistenza di Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
    - [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
