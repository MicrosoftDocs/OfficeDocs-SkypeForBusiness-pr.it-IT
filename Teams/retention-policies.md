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
description: Usare i criteri di conservazione per Microsoft Teams per mantenere i messaggi necessari per rispettare i criteri interni, le normative di settore o i requisiti legali ed eliminare i messaggi considerati di responsabilità o che non hanno alcun valore commerciale legale.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 748106de5ed7e2f0147a182716ca8bce1571b82f
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418814"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gestire i criteri di conservazione per Microsoft Teams

> [!NOTE]
> Se in Teams viene visualizzato un messaggio che indica che le chat o i messaggi sono stati eliminati da un criterio di conservazione, vedere Messaggi [di Teams sui criteri di conservazione.](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)
> 
> Le informazioni in questa pagina sono per gli amministratori IT che gestiscono questi criteri di conservazione.

I criteri di conservazione e le etichette di conservazione di Microsoft 365 consentono di gestire in modo più efficace le informazioni nell'organizzazione. È possibile configurare le impostazioni di conservazione per mantenere i dati necessari per rispettare i criteri interni, le normative di settore o i requisiti legali dell'organizzazione. È anche possibile configurare le impostazioni di conservazione per eliminare i dati considerati di responsabilità, che non è più necessario conservare o che non hanno alcun valore legale o aziendale.

Teams supporta i criteri di conservazione per i messaggi di chat e di canale, in modo che gli amministratori possano decidere in modo proattivo se conservare questi dati, eliminarli o conservarli per un periodo di tempo specifico e quindi eliminarli. L'inizio del periodo di conservazione per queste azioni è sempre basato sulla data di creazione di un messaggio. È possibile applicare un criterio di conservazione di Teams a un'intera organizzazione o a specifici utenti e team. Le etichette di conservazione non sono supportate per Teams.

Per altre informazioni sulla conservazione e su come applicare le impostazioni di conservazione usando i criteri di conservazione o le etichette di conservazione per altri carichi di lavoro in Microsoft 365, vedere Informazioni sui criteri di conservazione e sulle etichette [di conservazione.](/microsoft-365/compliance/retention)

Il requisito minimo di licenza per i criteri di conservazione per Teams è Microsoft 365 E3. Per altre informazioni sulle licenze, vedere Descrizione [del servizio Microsoft Teams.](/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retentiondeletion-policies-work"></a>Funzionamento dei criteri di conservazione/eliminazione di Teams

I messaggi di chat di Teams sono archiviati in due posizioni. La copia principale viene archiviata in Azure, una copia secondaria usata per i criteri di conformità viene archiviata in una cartella nascosta nella cassetta postale di Exchange Online di ogni utente incluso nella chat e i messaggi del canale teams vengono archiviati in una cartella nascosta simile nella cassetta postale del gruppo per il team. Quando un criterio di eliminazione dei messaggi di chat viene applicato a un utente o a un team, la copia secondaria viene eliminata per prima, seguita dalla copia principale. La ricerca di eDiscovery o Teams si basa sui messaggi archiviati nella copia secondaria e quindi i messaggi diventano non individuabili quando la copia secondaria viene eliminata. 

Quando un criterio di conservazione dei messaggi di chat viene applicato a un utente o a un team e se i messaggi vengono eliminati (a causa di un altro criterio di eliminazione o dall'utente stesso), la copia principale viene eliminata, quindi il client Teams vede il messaggio scomparire, ma la copia secondaria viene spostata automaticamente in una cartella nascosta denominata **SubstrateHolds** , che è una sottocartella nella cartella Elementi ripristinabili di **Exchange.** Finché questi messaggi non vengono eliminati definitivamente dalla cartella SubstrateHolds, rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.

Per informazioni dettagliate sugli elementi inclusi ed esclusi per i criteri di conservazione di Teams e sul funzionamento di questi criteri in base alla configurazione dei criteri, vedere Informazioni sulla conservazione [per Microsoft Teams.](/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Questa pagina spiega perché a volte possono verificarsi ritardi durante l'eliminazione dei messaggi da parte dei criteri di conservazione. Ad esempio, i messaggi possono essere visibili fino a 7 giorni dopo il periodo di scadenza configurato nei criteri di conservazione.

Se si configurano più criteri di conservazione di Teams con impostazioni di conservazione diverse, i principi di conservazione risolvono eventuali conflitti. Ad esempio:
- In caso di conflitto tra la conservazione o l'eliminazione dello stesso contenuto, il contenuto viene sempre mantenuto.
- Se si verifica un conflitto per quanto tempo conservare lo stesso contenuto, viene mantenuto per il periodo di conservazione più lungo.

Questi due principi di conservazione affrontano la maggior parte dei conflitti che possono verificarsi quando si hanno più criteri di conservazione per Teams, ma per altre informazioni, vedere Principi di conservazione o cosa [ha la precedenza?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando utilizzare i criteri di conservazione di Teams

In molti casi, le organizzazioni sentono maggiore responsabilità per i dati di chat private invece che per i messaggi dei canali, che in genere sono conversazioni relative a progetti.

È possibile configurare criteri di conservazione distinti per le chat private (chat individuali o di gruppo) e per i messaggi dei canali. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di Teams, è possibile selezionare gli utenti a cui applicare i criteri. Per i messaggi dei canali di Teams, è possibile selezionare i team a cui applicare i criteri.

Per i messaggi dei canali, ad esempio, è possibile applicare un criterio di eliminazione di un anno a team specifici dell'organizzazione e applicare un criterio di eliminazione triennale a tutti gli altri team.

## <a name="create-and-manage-retention-policies-for-teams"></a>Creare e gestire criteri di conservazione per Teams

Per creare criteri di conservazione per le chat e i messaggi del canale di Teams, seguire le istruzioni fornite da [Criteri di conservazione per le posizioni di Teams.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

In questa pagina sono disponibili altre informazioni sulla creazione e la gestione dei criteri di conservazione per altri carichi di lavoro in Microsoft 365. Ad esempio, può essere necessario creare anche criteri di conservazione per i gruppi di Microsoft 365 per conservare ed eliminare i file a cui si accede in Teams e archiviati in OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Esperienza utente finale

Per le chat private (chat 1:1) o chat di gruppo, gli utenti vedranno che le chat precedenti alla configurazione dei criteri di conservazione vengono eliminate e un messaggio generato automaticamente che indica "Sono stati eliminati i messaggi meno recenti a causa dei criteri di conservazione dell'organizzazione" viene visualizzato sopra i messaggi ancora non eliminati. Ad esempio:

:::image type="content" source="media/retention-policies-image1.png" alt-text="Utente informato in Teams che il messaggio di chat viene eliminato a causa di un criterio di conservazione di Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Gli utenti di Teams che spiegano i messaggi vengono eliminati in seguito a un criterio di conservazione di Teams":::

Per i messaggi del canale, gli utenti (membri del canale) vedono i messaggi eliminati scomparire dalla visualizzazione dopo la scadenza dei messaggi. Se il messaggio eliminato era un messaggio padre di una conversazione in thread, al posto del messaggio padre verrà visualizzato un messaggio che indica "Questo messaggio è stato eliminato a causa di criteri di conservazione". Ad esempio:

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot del canale prima della conservazione":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot del canale dopo la conservazione":::

> [!NOTE]
> Al momento, i messaggi visualizzati dagli utenti come risultato dei messaggi eliminati non sono configurabili.

I collegamenti in questi messaggi visualizzati passano ai messaggi [di Teams relativi ai criteri di conservazione.](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b) Questa documentazione per gli utenti finali consente di rispondere a domande di base sui motivi per cui i messaggi sono stati eliminati. Tuttavia, nell'ambito della distribuzione dei criteri di conservazione, assicurarsi di comunicare agli utenti e all'help desk l'impatto delle impostazioni configurate.

## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai criteri di conservazione e alle etichette di conservazione](/microsoft-365/compliance/get-started-with-retention)
- [Informazioni sulla conservazione per Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Creare e configurare criteri di conservazione](/microsoft-365/compliance/create-retention-policies)
