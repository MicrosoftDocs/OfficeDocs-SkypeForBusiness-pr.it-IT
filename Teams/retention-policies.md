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
description: Usare i criteri di conservazione Microsoft Teams per mantenere i messaggi che l'organizzazione deve rispettare i criteri interni, le normative di settore o i requisiti legali ed eliminare i messaggi considerati di responsabilità o che non hanno alcun valore commerciale legale.
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
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617758"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gestire i criteri di conservazione per Microsoft Teams

> [!NOTE]
> Se viene visualizzato un messaggio in Teams che le chat o i messaggi sono stati eliminati da un criterio di conservazione, vedere Teams sui criteri [di conservazione.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> Le informazioni in questa pagina sono per gli amministratori IT che gestiscono questi criteri di conservazione.

I criteri di conservazione e le etichette di conservazione Microsoft 365 consentono di gestire in modo più efficace le informazioni nell'organizzazione. È possibile configurare le impostazioni di conservazione per mantenere i dati necessari per rispettare i criteri interni, le normative di settore o i requisiti legali dell'organizzazione. È anche possibile configurare le impostazioni di conservazione per eliminare i dati considerati di responsabilità, che non è più necessario conservare o che non hanno alcun valore legale o aziendale.

Teams supporta i criteri di conservazione per i messaggi della chat e del canale, in modo che l'amministratore possa decidere in modo proattivo se conservare questi dati, eliminarli o conservarli per un periodo di tempo specifico e quindi eliminarli. L'inizio del periodo di conservazione per queste azioni è sempre basato sulla data di creazione di un messaggio. È possibile applicare un criterio di conservazione di Teams a un'intera organizzazione o a specifici utenti e team. Le etichette di conservazione non sono supportate per Teams.

Per altre informazioni sulle soluzioni di conservazione in Microsoft 365, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](/microsoft-365/compliance/retention)

Gli utenti soggetti a criteri di conservazione per Teams devono avere una licenza appropriata, ad esempio Office 365 E3 o Office 365 A3. Per altre opzioni di licenza per questi criteri di conservazione, vedere la sezione [Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) delle informazioni di Microsoft 365 sulle licenze per la sicurezza [& conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Per altre informazioni sulle licenze per Teams, vedere Microsoft Teams [descrizione del servizio.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Come Teams criteri di conservazione supportano le azioni di conservazione ed eliminazione

Se si configurano criteri Teams di conservazione per conservare chat o messaggi di canale, gli utenti possono comunque modificare ed eliminare i messaggi nell'app Teams. Anche se gli utenti non vedono più i messaggi pre-modificati o eliminati in Teams, i dati di questi messaggi vengono archiviati in una posizione protetta progettata per le ricerche eDiscovery da parte degli amministratori della conformità. L'eliminazione definitiva di questi dati non avviene prima della fine del periodo di conservazione configurato o se un altro criterio di conservazione è configurato per conservare questi dati o se è soggetto a un blocco [di eDiscovery.](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)

Quando un criterio di conservazione è configurato per eliminare chat e messaggi del canale, questi messaggi diventano idonei per l'eliminazione automatica. Se i messaggi sono ancora visualizzati nell'app Teams, scompariranno da lì e gli utenti vengono informati che i criteri di conservazione hanno eliminato [questi messaggi.](#end-user-experience) Se in precedenza i messaggi erano soggetti a un'azione di conservazione e sono stati modificati o eliminati dagli utenti, questi messaggi verranno eliminati dalla posizione protetta e non verranno più restituiti nelle ricerche di eDiscovery.

[Per](/microsoft-365/compliance/retention-policies-teams)informazioni dettagliate sul funzionamento di questi criteri in base alla configurazione dei criteri e alle azioni degli utenti e sui dati dei messaggi inclusi ed esclusi per i criteri di conservazione di Teams, vedere Informazioni sulla conservazione per Microsoft Teams . Questa pagina spiega anche perché a volte possono verificarsi ritardi durante l'eliminazione dei messaggi da parte dei criteri di conservazione. Ad esempio, i messaggi possono essere visibili agli utenti nell'app Teams fino a 7 giorni dopo il periodo di scadenza configurato nei criteri di conservazione.

Se si configurano più criteri Teams di conservazione con impostazioni di conservazione diverse, i principi di conservazione risolvono eventuali conflitti. Ad esempio:

- Se si verifica un conflitto tra la conservazione o l'eliminazione dello stesso contenuto, il contenuto viene sempre mantenuto nella posizione protetta in modo che rimanga disponibile per la ricerca con eDiscovery per gli amministratori della conformità.
    
    Questo principio si applica anche ai messaggi che sono oggetto di blocchi di eDiscovery per motivi legali o investigativi.

- Se si verifica un conflitto per quanto tempo conservare lo stesso contenuto, viene mantenuto nella posizione protetta per il periodo di conservazione più lungo.

Questi due principi di conservazione affrontano la maggior parte dei conflitti che possono verificarsi quando si hanno più criteri di conservazione per Teams, ma per altre informazioni, vedere Principi di conservazione o cosa ha [la precedenza?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando utilizzare i criteri di conservazione di Teams

In molti casi, le organizzazioni sentono maggiore responsabilità per i dati di chat private invece che per i messaggi dei canali, che in genere sono conversazioni relative a progetti.

È possibile configurare criteri di conservazione distinti per le chat private (chat individuali o di gruppo) e per i messaggi dei canali. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di Teams, è possibile selezionare gli utenti a cui applicare i criteri. Per i messaggi dei canali di Teams, è possibile selezionare i team a cui applicare i criteri.

Ad esempio, per i messaggi del canale, è possibile applicare un criterio di conservazione a team specifici dell'organizzazione e tale criterio è configurato con un'azione di eliminazione dopo 1 anno. Applicare quindi un altro criterio di conservazione a tutti gli altri team e tale criterio viene configurato con un'azione di eliminazione dopo 3 anni.

## <a name="create-and-manage-retention-policies-for-teams"></a>Creare e gestire criteri di conservazione per Teams

Per creare o modificare criteri di conservazione per Teams chat e messaggi del canale, seguire le istruzioni fornite da Criteri di conservazione per Teams [posizioni.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

In questa pagina sono disponibili altre informazioni sulla creazione e la gestione dei criteri di conservazione per altri carichi di lavoro in Microsoft 365. Ad esempio, può essere necessario creare anche criteri di conservazione per Microsoft 365 Groups per conservare ed eliminare i file a cui si accede in Teams e archiviati in OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Esperienza utente finale

Per le chat private (chat 1:1) o chat di gruppo, gli utenti vedranno che le chat precedenti alla configurazione dei criteri di conservazione vengono eliminate e un messaggio generato automaticamente che indica "Sono stati eliminati i messaggi meno recenti a causa dei criteri di conservazione dell'organizzazione" viene visualizzato sopra i messaggi ancora non eliminati. Ad esempio:

:::image type="content" source="media/retention-policies-image1.png" alt-text="L'utente informato in Teams che il messaggio di chat viene eliminato a causa di un criterio Teams di conservazione":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Gli utenti Teams che spiegano i messaggi vengono eliminati in seguito a un criterio Teams di conservazione":::

Per i messaggi del canale, gli utenti (membri del canale) vedono i messaggi eliminati scomparire dalla visualizzazione dopo la scadenza dei messaggi. Se il messaggio eliminato era un messaggio padre di una conversazione in thread, al posto del messaggio padre verrà visualizzato un messaggio che indica "Questo messaggio è stato eliminato a causa di criteri di conservazione". Ad esempio:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot del canale prima della conservazione":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot del canale dopo la conservazione":::

> [!NOTE]
> Al momento, i messaggi visualizzati dagli utenti come risultato dei messaggi eliminati non sono configurabili.

I collegamenti in questi messaggi visualizzati vengono Teams [sui criteri di conservazione.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) Questa documentazione per gli utenti finali consente di rispondere a domande di base sui motivi per cui i messaggi sono stati eliminati. Tuttavia, nell'ambito della distribuzione dei criteri di conservazione, assicurarsi di comunicare agli utenti e all'help desk l'impatto delle impostazioni configurate.

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai criteri di conservazione e alle etichette di conservazione](/microsoft-365/compliance/get-started-with-retention)
- [Informazioni sulla conservazione per Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Creare e configurare criteri di conservazione](/microsoft-365/compliance/create-retention-policies)
