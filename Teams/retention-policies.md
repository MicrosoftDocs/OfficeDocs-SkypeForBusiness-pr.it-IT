---
title: Criteri di conservazione in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Informazioni sui criteri di conservazione e su come crearli e gestirli in teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160750"
---
# <a name="retention-policies-in-microsoft-teams"></a>Criteri di conservazione in Microsoft Teams

I criteri di conservazione consentono di gestire in modo più efficace le informazioni dell'organizzazione. Usare i criteri di conservazione per mantenere i dati necessari per conformarsi ai criteri interni dell'organizzazione, alle normative del settore o alle esigenze legali e per eliminare i dati considerati responsabili, che non è più necessario mantenere o che non hanno alcun valore legale o aziendale.

Per impostazione predefinita, i dati di chat, canale e file di team vengono mantenuti per sempre. Gli amministratori possono configurare i criteri di conservazione dei team per i messaggi di chat e canali e decidere in modo proattivo se mantenere i dati, eliminarli o conservarli per un determinato periodo di tempo e quindi eliminarli.

È possibile creare e gestire i criteri di conservazione per team e altri carichi di lavoro nel [centro conformità & sicurezza di Office 365](https://protection.office.com/) o tramite i cmdlet di PowerShell di Security & Compliance Center. È possibile applicare criteri di conservazione dei team a un'intera organizzazione o a utenti e team specifici.

> [!NOTE]
> Non è ancora supportata la configurazione per la conservazione dei messaggi del canale privato. È supportata la conservazione dei file condivisi nei canali privati.

Per altre informazioni sui criteri di conservazione per Office 365, vedere [Panoramica dei criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>Quali sono i criteri di conservazione per i team?

Quando si configurano criteri di conservazione per team o altri carichi di lavoro, è possibile configurarli in:

- **Mantieni i dati**: usa un criterio di conservazione per assicurarti che i dati vengano conservati per un periodo di tempo specificato, indipendentemente da ciò che accade nell'app utente. I dati vengono mantenuti per motivi di conformità ed è disponibile per eDiscovery fino alla scadenza del periodo di conservazione, dopo il quale i criteri indicano se non eseguire alcuna operazione o eliminare i dati. Se ad esempio si creano criteri di conservazione di teams per mantenere i messaggi di canale per 7 anni, i messaggi vengono conservati per eDiscovery per 7 anni, anche se gli utenti eliminano i messaggi in teams.
- **Eliminare dati**: usare i criteri di conservazione per eliminare i dati per evitare che non sia una responsabilità per l'organizzazione. Con i criteri di conservazione di teams, quando si eliminano i dati, questa viene eliminata definitivamente da tutti i percorsi di archiviazione nel servizio teams.

Con i criteri di conservazione per i team è possibile:

- Mantenere le chat di team e/o i messaggi di canale per una durata specifica e quindi non eseguire alcuna operazione.
- Mantieni le chat di team e/o i messaggi di canale per una durata specifica e quindi Elimina i dati.
- Eliminare le chat di team e/o i messaggi di canale dopo una durata specificata.

> [!NOTE]
> Tenere presente che in teams i file che gli utenti condividono in chat private sono archiviati nell'account di OneDrive for business dell'utente che ha condiviso il file. E i file che i membri del team caricano in una conversazione sul canale vengono archiviati nel sito di SharePoint del team. Di conseguenza, per mantenere o eliminare i file in teams, creare criteri di conservazione che si applicano a OneDrive for business e SharePoint Online.

Quando i dati sono soggetti a criteri di conservazione, gli utenti possono continuare a lavorarci perché i dati vengono mantenuti al suo posto, nella posizione originale. Se un utente modifica o Elimina i dati soggetti al criterio, una copia viene salvata in un percorso sicuro in cui viene mantenuta mentre il criterio è attivo.

Il requisito minimo di licenze per i criteri di conservazione è Office 365 E3. Per ulteriori informazioni sulle licenze, vedere [licenze di Office 365 per Team](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Funzionamento dei criteri di conservazione dei team

Le chat di teams sono archiviate in una cartella di SubstrateHolds nascosta nella cassetta postale di ogni utente nella chat e i messaggi del canale di teams vengono archiviati in una cartella SubstratesHolds nascosta nella cassetta postale del gruppo per un team. Teams usa un servizio di chat basato su Azure che archivia anche questi dati e, per impostazione predefinita, questo servizio archivia i dati per sempre. Con i criteri di conservazione di teams, quando si eliminano i dati, i dati vengono eliminati definitivamente dalle cassette postali di Exchange e dal servizio chat sottostante.

Ecco cosa succede quando si applicano i criteri di conservazione a teams chat e Channel messages:

- Se una chat o un messaggio di canale viene modificato o eliminato da un utente durante il periodo di conservazione, il messaggio viene copiato (se è stato modificato) o spostato (se è stato eliminato) nella cartella SubstrateHolds e archiviato fino alla scadenza del periodo di conservazione. Se il criterio è configurato per eliminare i dati quando scade il periodo di conservazione, i messaggi vengono eliminati definitivamente il giorno in cui scade il periodo di conservazione.
- Se una chat o un messaggio di canale non viene eliminato da un utente durante il periodo di conservazione, il messaggio viene spostato nella cartella SubstrateHolds entro un giorno dopo la scadenza del periodo di conservazione. Se il criterio è configurato per eliminare i dati quando scade il periodo di conservazione, il messaggio viene eliminato definitivamente un giorno dopo lo spostamento nella cartella.

> [!NOTE]
> Lo stesso flusso funziona per le chat di interoperabilità di Skype for business online e teams. Quando una chat di Skype for business online entra in teams, diventa un messaggio in un thread di chat di teams e viene ingerito nella cassetta postale appropriata. I criteri di conservazione dei team elimineranno questi messaggi dal thread teams. Tuttavia, se la cronologia delle conversazioni è attivata per Skype for business online e dal lato client Skype for business online questi vengono salvati in una cassetta postale, i dati della chat non vengono gestiti da criteri di conservazione dei team.

I criteri di conservazione in teams sono basati sulla data in cui sono stati creati i messaggi della chat o del canale e sono retroattivi. In altre parole, se si creano criteri di conservazione per eliminare i dati antecedenti a 90 giorni, i dati del team creati più di 90 giorni fa vengono eliminati.

È possibile che i criteri di conservazione applicati a SharePoint Online o OneDrive for business possano eliminare un file a cui si fa riferimento in una chat o un messaggio di canale di teams prima che i messaggi vengano eliminati. In questo scenario, il file verrà ancora visualizzato nel messaggio teams, ma quando gli utenti fanno clic sul file, viene visualizzato un errore "file non trovato". Questo problema può verificarsi anche in assenza di un criterio, se un utente elimina manualmente un file da SharePoint Online o OneDrive for business.

### <a name="considerations-and-limitations"></a>Considerazioni e limitazioni

Ecco alcune considerazioni e limitazioni da tenere presenti quando si utilizzano i criteri di conservazione dei team:

- I team richiedono criteri di conservazione separati da altri carichi di lavoro. In altre parole, è necessario creare criteri di conservazione specifici per i messaggi chat e/o canali del team. Per questo motivo, non puoi includere team in criteri di conservazione a livello di organizzazione.

- I messaggi del canale privato non sono supportati. In questo momento, i criteri di conservazione per i team si applicano solo ai messaggi di canale standard.

- Teams non supporta le impostazioni di conservazione avanzate, ad esempio la possibilità di applicare un criterio al contenuto che contiene parole chiave o informazioni riservate. Attualmente i criteri di conservazione in teams si applicano a tutti i contenuti di chat e/o canali.

- I team possono richiedere fino a tre giorni per la pulizia dei messaggi scaduti. I criteri di conservazione dei team elimineranno i messaggi di chat e canali quando scade il periodo di conservazione. Tuttavia, potrebbero essere necessarie fino a tre giorni per pulire questi messaggi e eliminarli definitivamente. Anche i messaggi di chat e canali saranno ricercabili con gli strumenti di eDiscovery tra il momento in cui scade il periodo di conservazione e quando i messaggi vengono eliminati definitivamente.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Più criteri di conservazione e i principi di conservazione

Se si configurano più criteri di conservazione di teams con durata variabile, si applicano i [principi dei criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) . Ecco una panoramica delle caratteristiche che hanno la precedenza:

- La conservazione prevale sempre sull'eliminazione
- Il periodo di conservazione più lungo vince sempre
- L'inclusione esplicita prevale sull'inclusione implicita in termini di posizioni
- Vittorie del periodo di eliminazione più breve

## <a name="when-to-use-retention-policies-for-teams"></a>Quando usare i criteri di conservazione per i team

In molti casi, le organizzazioni considerano i dati della chat privata come un numero maggiore di passività rispetto ai messaggi del canale, che in genere sono più conversazioni correlate al progetto.

È possibile configurare criteri di conservazione separati per le chat private (1:1 o 1: molte chat) e i messaggi del canale. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di teams, puoi selezionare a quali utenti si applica il criterio. Per i messaggi del canale teams, è possibile selezionare a quali team si applica il criterio.

Per i messaggi di canale, ad esempio, è possibile applicare un criterio di eliminazione di un anno a team specifici dell'organizzazione e applicare criteri di eliminazione di tre anni a tutti gli altri team.

## <a name="manage-retention-policies-for-teams"></a>Gestire i criteri di conservazione per i team

### <a name="using-the-security--compliance-center"></a>Uso del centro conformità & sicurezza

#### <a name="create-a-retention-policy"></a>Creare criteri di conservazione

Per creare criteri di conservazione per le chat di team e i messaggi di canale, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra del centro conformità & sicurezza, accedere alla**conservazione**delle **informazioni sulla governance** > .
2. Selezionare **Crea**.
3. Nella pagina **Name Your Policy** immettere un nome e una descrizione per il criterio e quindi fare clic su **Avanti**.
4. Nella pagina **Impostazioni** specificare se si vuole mantenere i dati, eliminarli o entrambi, il periodo di conservazione e quindi fare clic su **Avanti**.
5. Nella pagina **Choose locations** eseguire le operazioni seguenti e quindi fare clic su **Avanti**:

    - Per applicare il criterio ai messaggi del canale, attivare i **messaggi del canale teams**.  Se si vuole applicare il criterio a team specifici dell'organizzazione, selezionare **Scegli teams**e quindi selezionare i team desiderati.
    - Per applicare il criterio alle chat, attivare le **chat di teams**. Se si vuole applicare il criterio a utenti specifici dell'organizzazione, selezionare Seleziona **utenti**e quindi selezionare gli utenti desiderati.
      > [!NOTE]
      > Quando si attivano **i messaggi del canale di teams** e/o le **chat in teams**, tutte le altre posizioni vengono disattivate automaticamente. I criteri di conservazione dei team possono includere solo le posizioni dei team.

        ![Screenshot delle opzioni per i messaggi del canale teams e per le chat team nella pagina Scegli percorsi](media/retention-policies-create.png)

      > [!IMPORTANT]
      > I criteri di conservazione applicati alle cassette postali di un utente o di gruppo nei percorsi di **posta elettronica di Exchange** o di **gruppi di Office 365** non influenzano i messaggi di chat e i canali Anche se le chat di team e i messaggi di canale sono archiviati in Exchange, i criteri di conservazione applicati alle posizioni dei team sono influenzati solo dalle condizioni di mantenimento.

6. Esaminare le impostazioni e quindi quando si è pronti selezionare **crea questo criterio**.

#### <a name="edit-a-retention-policy"></a>Modificare i criteri di conservazione

Per modificare i criteri di conservazione di un team, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra del centro conformità & sicurezza, accedere alla**conservazione**delle **informazioni sulla governance** > .
2. Nell'elenco dei criteri di conservazione Selezionare la casella di controllo accanto ai criteri di conservazione che si desidera modificare.
3. Selezionare **modifica** accanto a ciò che si vuole modificare, apportare le modifiche, fare clic su **Salva**e quindi su **Chiudi**.

    ![Screenshot delle opzioni per i messaggi del canale teams e per le chat team nella pagina Scegli percorsi](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Eliminare i criteri di conservazione

Per eliminare i criteri di conservazione di un team, eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra del centro conformità & sicurezza, accedere alla**conservazione**delle **informazioni sulla governance** > .
2. Nell'elenco dei criteri di conservazione Selezionare la casella di controllo accanto ai criteri di conservazione che si desidera eliminare.
3. Selezionare **Elimina criteri**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per creare e gestire i criteri di conservazione dei team tramite PowerShell, usare i cmdlet seguenti.

|Criteri|Regola|
|---|---|
|[New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [New-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problemi noti

Di seguito sono riportati i problemi noti per i criteri di conservazione in team che vengono rilevati e analizzati.

- In **Scegli teams** nella riga location **messages Channel teams** puoi vedere i gruppi di Office 365 che non sono anche teams. Questa operazione verrà affrontata in futuro.

- In **Scegli utenti** nella riga posizione **chat teams** è possibile che vengano visualizzati utenti guest e non-Mailbox. I criteri di conservazione non sono pensati per essere impostati per gli utenti e stiamo lavorando per rimuoverli dall'elenco.

- Il programma ELC (Exchange Life Cycle Assistant) viene eseguito giornalmente, ma ha uno SLA di 7 giorni. Di conseguenza, è possibile che, se si dispone di un criterio di conservazione di teams per eliminare gli elementi precedenti a 60 giorni, questi elementi potrebbero essere mantenuti per un massimo di 67 giorni. Non si tratta di una nuova situazione: segue il modello Exchange. Naturalmente, nella maggior parte dei casi, non ci sono ritardi.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica dei criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
