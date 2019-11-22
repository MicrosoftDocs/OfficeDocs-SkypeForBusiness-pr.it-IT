---
title: Domande frequenti sui criteri di conservazione di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: prvijay
audience: admin
description: Domande frequenti sui criteri di conservazione in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa8e71d167bbb5f5381c66a1a8545a6f94f74e62
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793502"
---
# <a name="microsoft-teams-retention-policies-faq"></a>Domande frequenti sui criteri di conservazione di Microsoft Teams

> [!NOTE]
> Non è ancora supportata la configurazione per la conservazione dei messaggi del canale privato. È supportata la conservazione dei file condivisi nei canali privati.

### <a name="what-types-of-policies-can-i-set-up-in-retention-policies-and-how-do-they-work"></a>Quali tipi di criteri è possibile configurare nei criteri di conservazione e come funzionano?

Quando si configurano criteri di conservazione, per i team o per qualsiasi altro carico di lavoro nel centro sicurezza & conformità, è possibile impostare due tipi di criteri principali: 
- Conservazione: questi criteri assicurano che i dati vengano mantenuti per un determinato periodo di tempo, indipendentemente da ciò che accade negli strumenti per gli utenti finali. Assicurano che i dati vengano mantenuti per motivi di conformità e disponibili in eDiscovery fino alla scadenza di questo periodo. Dopo la scadenza, il criterio può indicare se non fare nulla o eliminare i dati. In teams se si creano criteri di conservazione per 7 anni, anche se gli utenti finali eliminano i messaggi del team, questi messaggi vengono conservati per eDiscovery per 7 anni.
- Eliminazione: questi criteri assicurano che i dati non siano una passività per l'organizzazione. Dopo la durata specificata, i dati vengono eliminati da tutto lo spazio di archiviazione pertinente in teams. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>È possibile includere team in criteri a livello di organizzazione? 

No, al momento no. È necessario creare criteri specifici per la chat dei team e i messaggi di canale usando la riga posizione teams o i cmdlet teams: [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Questi cmdlet hanno anche le versioni Get e set.

### <a name="are-these-retention-policies-retroactive"></a>Questi criteri di conservazione sono retroattivi? 

Sì, lo sono. Se si creano criteri di conservazione per eliminare dati antecedenti a 60 giorni, verranno eliminati i dati di teams creati più di 60 giorni fa. 

### <a name="what-is-the-default-retention-policy"></a>Qual è il criterio di conservazione predefinito? 

Per impostazione predefinita, i dati di chat, canale e file di team vengono mantenuti per sempre.

### <a name="what-licensing-is-required-for-retention-policies"></a>Quali licenze sono necessarie per i criteri di conservazione?

Il requisito minimo di licenze per i criteri di conservazione è Office 365 E3. Per altre informazioni sulle licenze, leggere [licenze di Office 365 per i team](office-365-licensing.md).

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>È possibile impostare come destinazione set di utenti o team in un criterio? 

Sì, è così. Nel passaggio percorsi della creazione guidata criteri è possibile includere o escludere Team (**messaggi del canale teams**) o utenti (**Chat Team**) e creare criteri mirati per l'organizzazione. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Qual è la differenza principale tra l'uso della riga posizione della cassetta postale del gruppo e i messaggi del canale dei team nei criteri di conservazione? 

Se si usano le righe della cassetta postale del gruppo e della posizione della cassetta postale utente per Exchange Online, i dati del team verranno eliminati dalle cassette postali specificate. Tuttavia, questo rimuove solo i dati dalla cassetta postale. Non elimina i dati di altri team, ad esempio il servizio chat. Ti consigliamo di usare i criteri di conservazione dei team per gestire correttamente tutti i dati del team. I criteri di conservazione dei team rimuovono i dati di team da tutte le posizioni di archiviazione: cassette postali, servizio chat, client teams. 

Nota: il lancio della caratteristica criteri di conservazione per i team assicura che solo i criteri Team eliminino gli elementi del team archiviati all'interno delle posizioni delle cassette postali di Exchange (utente o gruppo). La configurazione di altri criteri nelle cassette postali non può influenzare gli elementi teams. Questo era vero in passato, ma è stato risolto con l'avvio della funzionalità criteri di conservazione. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Cosa succede a Skype for business online e alle chat di interoperabilità in teams: i criteri di conservazione sono influenzati?

Sì, Skype for business online e le chat di interoperabilità dei team funzionano allo stesso modo. Una volta che la chat di Skype for business online entra in teams, diventa un messaggio in un thread di chat di teams e viene ingerito nella cassetta postale appropriata. In questo modo, lo stesso flusso di lavoro: i criteri di eliminazione dei team elimineranno questi messaggi dal thread teams. Tuttavia, se la cronologia delle conversazioni è attivata per Skype for business online e il lato client Skype for business online viene salvato in una cassetta postale, i dati della chat non vengono gestiti da criteri di conservazione dei team.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>È possibile eseguire queste operazioni tramite i cmdlet Security & Compliance Center? Cosa si deve usare? 

Assolutamente. È possibile creare criteri di conservazione dei team usando i [cmdlet di PowerShell Security & Compliance Center]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). Tenere presente che non si tratta di cmdlet di Exchange Online. Ecco i cmdlet creati per i team. Seguono le nomenclature e lo stile esistenti dai cmdlet di conservazione oggi disponibili nel centro conformità & sicurezza.

|Criteri|Regola|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Se sono presenti più criteri di conservazione per i team con durata variabile, quale vince?

Seguiamo [i principi dei criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)e ti consigliamo di farlo anche tu. La risposta breve è: 
-   La conservazione prevale sempre sull'eliminazione
-   Il periodo di conservazione più lungo vince sempre
-   L'inclusione esplicita prevale sull'inclusione implicita in termini di posizioni
-   Vittorie del periodo di eliminazione più breve
