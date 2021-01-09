---
title: Criteri di conservazione in Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Usare i criteri di conservazione per Microsoft teams per mantenere i messaggi necessari per rispettare i criteri interni, le normative del settore o le esigenze legali e per eliminare i messaggi considerati come passività o che non hanno un valore aziendale legale.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786828"
---
# <a name="retention-policies-in-microsoft-teams"></a>Criteri di conservazione in Microsoft Teams

I criteri di conservazione e le etichette di conservazione di Microsoft 365 consentono di gestire in modo più efficace le informazioni dell'organizzazione. Puoi configurare le impostazioni di conservazione per mantenere i dati necessari per conformarsi ai criteri interni dell'organizzazione, alle normative del settore o alle esigenze legali. È anche possibile configurare le impostazioni di conservazione per eliminare i dati considerati come passività, che non è più necessario mantenere o che non hanno alcun valore legale o aziendale.

Teams supporta i criteri di conservazione per la chat e i messaggi di canale in modo che, come amministratore, sia possibile decidere se mantenere questi dati, eliminarli o conservarli per un determinato periodo di tempo e quindi eliminarli. È possibile applicare un criterio di conservazione di Teams a un'intera organizzazione o a specifici utenti e team. Le etichette di conservazione non sono supportate per i team.

Per altre informazioni sulla conservazione e su come applicare le impostazioni di conservazione usando i criteri di conservazione o le etichette di conservazione per altri carichi di lavoro in Microsoft 365, vedere informazioni [sui criteri di conservazione e sulle etichette di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention).

I requisiti minimi di licenza per i criteri di conservazione per i team sono Microsoft 365 E3. Per ulteriori informazioni sulle licenze, vedere [Descrizione del servizio Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-work"></a>Come funzionano i criteri di conservazione di Teams

I messaggi di chat in teams vengono archiviati in una cartella nascosta nella cassetta postale di ogni utente incluso nella chat e i messaggi del canale teams vengono archiviati in una cartella nascosta simile nella cassetta postale del gruppo per il team. Per mantenere i messaggi soggetti a criteri di conservazione, una copia del contenuto viene mantenuta automaticamente in una cartella nascosta denominata **SubstrateHolds** come sottocartella nella cartella **elementi ripristinabili** di Exchange. Finché questi messaggi non vengono eliminati definitivamente dalla cartella SubstrateHolds, rimangono ricercabili dagli strumenti di eDiscovery.

Per informazioni dettagliate sugli elementi inclusi ed esclusi per i criteri di conservazione dei team e sul funzionamento di questi criteri a seconda della configurazione dei criteri, vedere informazioni [sulla conservazione per Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).

> [!NOTE]
> Questa pagina spiega perché a volte potrebbe essere visualizzato un ritardo quando i criteri di conservazione eliminano i messaggi. Ad esempio, i messaggi possono essere visibili fino a 7 giorni dopo il periodo di scadenza configurato nei criteri di conservazione.

Se si configurano più criteri di conservazione dei team con impostazioni di conservazione diverse, i principi di conservazione consentono di risolvere eventuali conflitti. Ad esempio:
- Se c'è un conflitto tra il mantenimento o l'eliminazione dello stesso contenuto, il contenuto viene sempre mantenuto.
- Se c'è un conflitto in quanto tempo per mantenere lo stesso contenuto, viene mantenuto per il periodo di conservazione più lungo.

Questi due principi di conservazione affrontano la maggior parte dei conflitti che potrebbero verificarsi quando si hanno più criteri di conservazione per i team, ma per altre informazioni, vedere [i principi di conservazione o cosa ha la precedenza?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quando utilizzare i criteri di conservazione di Teams

In molti casi, le organizzazioni sentono maggiore responsabilità per i dati di chat private invece che per i messaggi dei canali, che in genere sono conversazioni relative a progetti.

È possibile configurare criteri di conservazione distinti per le chat private (chat individuali o di gruppo) e per i messaggi dei canali. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di Teams, è possibile selezionare gli utenti a cui applicare i criteri. Per i messaggi dei canali di Teams, è possibile selezionare i team a cui applicare i criteri.

Per i messaggi dei canali, ad esempio, è possibile applicare un criterio di eliminazione di un anno a team specifici dell'organizzazione e applicare un criterio di eliminazione triennale a tutti gli altri team.

## <a name="create-and-manage-retention-policies-for-teams"></a>Creare e gestire i criteri di conservazione per i team

Per creare criteri di conservazione per le chat di team e i messaggi di canale, usare le istruzioni dei [criteri di conservazione per i percorsi dei team](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).

Questa pagina contiene altre informazioni sulla creazione e la gestione dei criteri di conservazione per altri carichi di lavoro in Microsoft 365. Ad esempio, potresti voler anche creare criteri di conservazione per i gruppi di Microsoft 365 per mantenere ed eliminare i file a cui si accede in teams e archiviati in OneDrive o SharePoint.  

## <a name="end-user-experience"></a>Esperienza utente finale

Per le chat private (chat di 1:1) o le chat di gruppo, gli utenti finali vedranno che le chat precedenti alla configurazione dei criteri di conservazione vengono eliminate e un messaggio di controllo che indica che "abbiamo eliminato i messaggi meno recenti a causa dei criteri di conservazione dell'organizzazione" viene visualizzato sopra i messaggi ancora non eliminati.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Utente informato in teams il messaggio di chat viene eliminato a causa di un criterio di conservazione di Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="L'utente in teams che spiega i messaggi viene eliminato come risultato di un criterio di conservazione di Teams":::

Per i messaggi di canale, gli utenti finali (membri del canale) vedranno scomparire i messaggi eliminati dalla visualizzazione dopo la scadenza dei messaggi. Se il messaggio eliminato è un messaggio padre di una conversazione in thread, al posto del messaggio padre viene visualizzato un messaggio che indica che "questo messaggio è stato eliminato a causa di un criterio di conservazione".

:::image type="content" source="media/retention-policies-image3.png" alt-text="Screenshot del canale prima della conservazione":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Screenshot del canale dopo la conservazione":::

> [!NOTE]
> I messaggi visualizzati che gli utenti finali vedono come risultato della messaggistica eliminata non sono configurabili in questo momento.


## <a name="related-topics"></a>Argomenti correlati

- [Introduzione ai criteri di conservazione e alle etichette di conservazione](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [Informazioni sulla conservazione per Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Creare e configurare criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)