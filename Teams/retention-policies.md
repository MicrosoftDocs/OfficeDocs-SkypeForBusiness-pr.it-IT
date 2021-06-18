---
title: Gestire i criteri di conservazione per Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Usare i criteri di conservazione per Microsoft Teams per mantenere i messaggi che l’organizzazione deve archiviare per conformarsi ai criteri interni, alle normative di settore o alle esigenze legali e per eliminare i messaggi considerati una responsabilità o che non hanno alcun valore legale aziendale.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617758"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gestire i criteri di conservazione per Microsoft Teams

> [!NOTE]
> Se viene visualizzato un messaggio in Teams che indica che le chat o i messaggi sono stati eliminati da un criterio di conservazione, vedere [Messaggi di Teams sui criteri di conservazione](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Le informazioni fornite in questa pagina sono riservate agli amministratori IT che gestiscono questi criteri di conservazione.

I criteri di conservazione e le etichette di conservazione di Microsoft 365 consentono di gestire le informazioni nell'organizzazione in modo più efficiente. È possibile configurare le impostazioni di conservazione per mantenere i dati che devono essere archiviati per conformità ai criteri interni, alle normative di settore o alle esigenze legali dell'organizzazione. È anche possibile configurare le impostazioni di conservazione per eliminare i dati considerati di responsabilità, che non è più necessario mantenere o che non hanno alcun valore legale o aziendale.

Teams supporta i criteri di conservazione di Teams per i messaggi di chat e canali n modo che un amministratore possa decidere modo proattivo se tenere questi dati, eliminarli o conservarli per un periodo di tempo specifico e in seguito eliminarli. L'inizio del periodo di conservazione per queste azioni è sempre basato su quando viene creato un messaggio. È possibile applicare un criterio di conservazione di Teams a un'intera organizzazione o a specifici utenti e team. Le etichette di conservazione non sono supportate per Teams.

Per altre informazioni sulle soluzioni di conservazione in Microsoft 365, vedere [Informazioni sui criteri e le etichette di conservazione](/microsoft-365/compliance/retention).

Gli utenti soggetti a criteri di conservazione per Teams devono avere una licenza appropriata, ad esempio Office 365 E3 o Office 365 A3. Per altre opzioni di licenza per questi criteri di conservazione, vedere la sezione [Governance delle informazioni](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) da [Linee guida sulle licenze per la sicurezza e la conformità di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Per altre informazioni sulle licenze per Teams, vedere [Descrizione del servizio Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Come si criteri di conservazione di Teams conservano ed eliminano azioni

Se si configurano criteri di conservazione di Teams per conservare le chat o i messaggi del canale, gli utenti possono comunque modificare ed eliminare i messaggi nell'app Teams. Anche se gli utenti non visualizzano più i messaggi pre-modificati o eliminati in Teams, i dati di questi messaggi vengono archiviati in una posizione protetta progettata per le ricerche di eDiscovery da parte degli amministratori di conformità. L'eliminazione definitiva di questi dati non avviene prima della fine del periodo di conservazione configurato o se un altro criterio di conservazione è configurato per conservare questi dati oppure è soggetto a un [blocco di eDiscovery ](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

Quando un criterio di conservazione è configurato per eliminare le chat e i messaggi del canale, questi messaggi diventano idonei per l'eliminazione automatica. Se i messaggi vengono ancora visualizzati nell'app Teams, scompariranno da lì e [gli utenti vengono informati che un criterio di conservazione ha eliminato questi messaggi](#end-user-experience). Se i messaggi sono stati precedentemente soggetti a un'azione di conservazione e sono stati modificati o eliminati dagli utenti, questi messaggi verranno eliminati dalla posizione protetta e non verranno più restituiti nelle ricerche di eDiscovery.

Per informazioni dettagliate sul funzionamento di questi criteri a seconda della configurazione dei criteri e delle azioni degli utenti e dei dati dei messaggi inclusi ed esclusi per i criteri di conservazione di Teams, vedere [Informazioni sulla conservazione per Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). Questa pagina spiega anche perché talvolta si verificano ritardi quando i criteri di conservazione eliminano i messaggi. Ad esempio, i messaggi possono essere visibili agli utenti nell'app Teams fino a 7 giorni dopo il periodo di scadenza configurato nei criteri di conservazione.

Se si configurano più criteri di conservazione di Teams con impostazioni di conservazione diverse, i principi di conservazione risolvono eventuali conflitti. Ad esempio:

- Se si verifica un conflitto tra la conservazione o l'eliminazione dello stesso contenuto, il contenuto viene sempre conservato nella posizione protetta in modo che rimanga ricercabile con eDiscovery per gli amministratori di conformità.
    
    Questo principio si applica anche ai messaggi soggetti a blocchi di eDiscovery per motivi legali o di indagine.

- Se si verifica un conflitto a proposito del periodo di conservazione dello stesso contenuto, esso viene conservato nella posizione protetta per il periodo di conservazione più lungo.

Questi due principi di conservazione risolvono la maggior parte dei conflitti che possono verificarsi quando si hanno più criteri di conservazione per Teams, ma per altre informazioni, vedere [Principi di conservazione o cosa ha la precedenza?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando utilizzare i criteri di conservazione di Teams

In molti casi, le organizzazioni sentono maggiore responsabilità per i dati di chat private invece che per i messaggi dei canali, che in genere sono conversazioni relative a progetti.

È possibile configurare criteri di conservazione distinti per le chat private (chat individuali o di gruppo) e per i messaggi dei canali. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di Teams, è possibile selezionare gli utenti a cui applicare i criteri. Per i messaggi dei canali di Teams, è possibile selezionare i team a cui applicare i criteri.

Per i messaggi dei canali, ad esempio, è possibile applicare un criterio di conservazione a team specifici dell'organizzazione e tale criterio è configurato con un'azione di eliminazione dopo 1 anno. Applicare quindi un altro criterio di conservazione a tutti gli altri team e tale criterio viene configurato con un'azione di eliminazione dopo 3 anni.

## <a name="create-and-manage-retention-policies-for-teams"></a>Creare e gestire i criteri di conservazione per Teams

Per creare o modificare un criterio di conservazione per le chat di Teams e i messaggi del canale, usare le istruzioni di [Criteri di conservazione per le posizioni di Teams](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).

Questa pagina contiene informazioni aggiuntive sulla creazione e sulla gestione dei criteri di conservazione per altri carichi di lavoro in Microsoft 365. Ad esempio, è possibile creare anche un criterio di conservazione per Gruppi di Microsoft 365 per conservare ed eliminare i file a cui si accede in Teams e archiviati in OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Esperienza dell'utente finale

Per le chat private (chat 1:1) o le chat di gruppo, gli utenti vedranno che le chat precedenti alla configurazione dei criteri di conservazione vengono eliminate e un messaggio generato automaticamente che indica che i messaggi meno recenti sono stati eliminati a causa dei criteri di conservazione dell'organizzazione viene visualizzato sopra i messaggi non eliminati. Ad esempio:

:::image type="content" source="media/retention-policies-image1.png" alt-text="L'utente viene informato in Teams che il messaggio di chat viene eliminato a causa di un criterio di conservazione di Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="All'utente in Teams viene spiegato che i messaggi vengono eliminati in seguito ai criteri di conservazione di Teams":::

Per i messaggi del canale, gli utenti (membri del canale) vedranno i messaggi eliminati scomparire dalla visualizzazione dopo la scadenza dei messaggi. Se il messaggio eliminato è un messaggio padre di una conversazione in thread, al posto del messaggio padre verrà visualizzato un messaggio che indica che il messaggio è stato eliminato a causa di un criterio di conservazione. Ad esempio:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot del canale prima della conservazione":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot del canale dopo la conservazione":::

> [!NOTE]
> I messaggi visualizzati dagli utenti come risultato dei messaggi eliminati non sono configurabili in questo momento.

I collegamenti in questi messaggi visualizzati vanno a [Messaggi di Teams sui criteri di conservazione](https://support.microsoft.com/it-IT/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Questa documentazione per gli utenti finali consente di rispondere alle domande di base sul motivo per cui i messaggi sono stati eliminati. Tuttavia, come parte della distribuzione dei criteri di conservazione, assicurarsi di comunicare agli utenti e all’help desk l'impatto delle impostazioni configurate.

## <a name="related-topics"></a>Argomenti correlati

- [Informazioni sui criteri e sulle etichette di conservazione](/microsoft-365/compliance/get-started-with-retention)
- [Informazioni sulla conservazione per Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Creare e configurare criteri di conservazione](/microsoft-365/compliance/create-retention-policies)
