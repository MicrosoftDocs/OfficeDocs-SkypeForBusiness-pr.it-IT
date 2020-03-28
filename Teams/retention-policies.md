---
title: Criteri di conservazione in Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: Informazioni sui criteri di conservazione e su come crearli e gestirli in Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9097dfc43ca0f70d37b0051e6b0e10283da26c3
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033390"
---
# <a name="retention-policies-in-microsoft-teams"></a>Criteri di conservazione in Microsoft Teams

I criteri di conservazione consentono di gestire le informazioni nell'organizzazione in modo più efficiente. Usare i criteri di conservazione per mantenere i dati necessari a conformarsi ai criteri interni dell'organizzazione, alle normative di settore o alle esigenze legali e per eliminare i dati considerati una responsabilità che non è più necessario conservare o che non hanno alcun valore legale o aziendale.

Per impostazione predefinita, i dati delle chat di Teams, dei canali e dei file vengono conservati per sempre. Gli amministratori possono configurare i criteri di conservazione di Teams per i messaggi di chat e canali e decidere in modo proattivo se tenere i dati, eliminarli o conservarli per un periodo di tempo specifico e in seguito eliminarli.

È possibile creare e gestire i criteri di conservazione di Teams e altri carichi di lavoro nel [Centro sicurezza e conformità di Office 365](https://protection.office.com/) o tramite i cmdlet di PowerShell per il Centro sicurezza e conformità. È possibile applicare un criterio di conservazione di Teams a un'intera organizzazione o a specifici utenti e team.

> [!NOTE]
> Non è ancora supportata la configurazione per la conservazione dei messaggi del canale privato. La conservazione dei file condivisi in canali privati è supportata.

Per altre informazioni sui criteri di conservazione di Office 365, vedere [Panoramica dei criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).

## <a name="what-are-retention-policies-for-teams"></a>Cosa sono i criteri di conservazione di Teams?

Quando si configura un criterio di conservazione di Teams o qualsiasi altro carico di lavoro, è possibile configurarlo per:

- **Conservare i dati**: usare i criteri di conservazione per assicurarsi che i dati vengano conservati per un periodo di tempo specifico, indipendentemente dall'applicazione dell'utente. I dati vengono conservati per motivi di conformità e sono disponibili per eDiscovery fino alla scadenza del periodo di conservazione, in seguito al quale, in base ai relativi criteri, non verrà eseguita alcuna operazione o i dati verranno eliminati. Ad esempio, se si crea un criterio di conservazione di Teams per mantenere i messaggi dei canali per 7 anni, questi verranno conservati per eDiscovery per 7 anni, anche qualora gli utenti eliminassero i propri messaggi in Teams.
- **Eliminare i dati**: usare i criteri di conservazione per eliminare i dati affinché non siano responsabilità dell'organizzazione. Con i criteri di conservazione di Teams, quando si eliminano dei dati, questi vengono eliminati definitivamente da tutte le posizioni di archiviazione del servizio di Teams.

Con i criteri di conservazione di Teams è possibile:

- Conservare i messaggi di chat e/o canali per un periodo di tempo specifico e in seguito non eseguire alcuna operazione.
- Conservare i messaggi di chat e/o canali per un periodo di tempo specifico e in seguito eliminare i dati.
- Eliminare i messaggi di chat e/o canali dopo un periodo di tempo specifico.

> [!NOTE]
> Tenere presente che in Teams i file condivisi nelle chat private dagli utenti vengono archiviati nell'account di OneDrive for Business dell'utente che ha condiviso il file. Inoltre, i file che i membri del team caricano in una conversazione del canale vengono archiviati nel sito di SharePoint del team. Quindi, per mantenere o eliminare i file in Teams, creare criteri di conservazione applicabili a OneDrive for Business e SharePoint Online.

Se i dati sono soggetti a criteri di conservazione, gli utenti possono continuare a usarli in quanto non vengono spostati, ma conservati nella posizione originale. Se un utente modifica o elimina dati soggetti a criteri, viene salvata una copia in una posizione protetta che verrà conservata per l'intero periodo di applicazione dei criteri.

Il requisito minimo di licenza per i criteri di conservazione è avere Office 365 E3. Per altre informazioni sulle licenze, vedere [Licenze di Office 365 per Teams](Office-365-licensing.md).

## <a name="how-teams-retention-policies-work"></a>Come funzionano i criteri di conservazione di Teams

Le chat di Teams vengono archiviate in una cartella SubstrateHolds nascosta della cassetta postale di ogni utente della chat e i messaggi del canale di Teams vengono archiviati in una cartella SubstratesHolds nascosta della cassetta postale di gruppo di un team. Teams usa un servizio di chat con tecnologia Azure che archivia anche questi dati e che, per impostazione predefinita, li memorizza per sempre. Con i criteri di conservazione di Teams, quando si eliminano dei dati, questi vengono eliminati definitivamente sia nelle cassette postali di Exchange che nel servizio di chat sottostante.

Ecco cosa succede quando si applica un criterio di conservazione a messaggi di canali e chat di Teams:

- Se un messaggio della chat o del canale viene modificato o eliminato da un utente durante il periodo di conservazione, questo viene copiato (se è stato modificato) o spostato (se è stato eliminato) nella cartella SubstrateHolds e archiviato fino alla scadenza del periodo di conservazione. Se il criterio è configurato per l'eliminazione dei dati al termine del periodo di conservazione, i messaggi verranno eliminati definitivamente il giorno della scadenza di tale periodo.
- Se il messaggio di una chat o un canale non viene eliminato da un utente durante il periodo di conservazione, viene spostato nella cartella SubstrateHolds entro un giorno dalla scadenza del periodo di conservazione. Se il criterio è configurato per l'eliminazione dei dati al termine del periodo di conservazione, il messaggio verrà eliminato definitivamente un giorno dopo lo spostamento nella cartella.

> [!NOTE]
> La stessa procedura viene applicata alle chat di interoperabilità di Skype for Business Online e Teams. Quando una chat di Skype for Business Online viene spostata in Teams, diventa un messaggio in un thread di chat di Teams e viene inserita nella cassetta postale appropriata. I criteri di conservazione di Teams elimineranno questi messaggi dal thread di Teams. Tuttavia, se la cronologia delle conversazioni è abilitata per Skype for Business Online e dal lato client di Skype for Business Online i messaggi sono stati salvati in una cassetta postale, i dati della chat non vengono gestiti dai criteri di conservazione di Teams.

I criteri di conservazione di Teams si basano sulla data di creazione dei messaggi della chat o del canale e sono retroattivi. In altre parole, se si creano criteri di conservazione per l'eliminazione di dati precedenti a 90 giorni, i dati di Teams creati più di 90 giorni fa verranno eliminati.

È possibile che i criteri di conservazione applicati a SharePoint Online o OneDrive for Business eliminino un file a cui viene fatto riferimento nel messaggio di una chat o di un canale di Teams prima che tali messaggi vengano eliminati. In questo scenario, il file verrà comunque mostrato nel messaggio di Teams, ma se gli utenti fanno clic sul file visualizzeranno l'errore "File non trovato". Ciò può verificarsi anche in assenza di un criterio, se un utente elimina manualmente un file da SharePoint Online o OneDrive for Business.

### <a name="considerations-and-limitations"></a>Considerazioni e limitazioni

Ecco alcune considerazioni e limitazioni da tenere presenti quando si usano i criteri di conservazione di Teams:

- Teams necessita di un criterio di conservazione distinto dagli altri carichi di lavoro. In altre parole, è necessario creare criteri di conservazione specifici per i messaggi di chat e/o canali di Teams. Per questo motivo, non è possibile includere Teams nei criteri di conservazione a livello di organizzazione.

- I messaggi di canali privati non sono supportati. Al momento, i criteri di conservazione di Teams si applicano solo ai messaggi di canali standard.

- Teams non supporta impostazioni di conservazione avanzate, ad esempio la possibilità di applicare un criterio a contenuti che includono parole chiave o informazioni sensibili. Attualmente, i criteri di conservazione di Teams si applicano a tutti i contenuti di messaggi di chat e/o canali.

- Potrebbero essere necessari fino a tre giorni per pulire i messaggi scaduti in Teams. I criteri di conservazione di Teams elimineranno i messaggi di chat e canali al termine del periodo di conservazione. Tuttavia, potrebbero essere necessari fino a tre giorni per pulire i messaggi ed eliminarli definitivamente. Inoltre, i messaggi di chat e canali saranno disponibili per la ricerca tramite gli strumenti di eDiscovery tra il periodo successivo alla scadenza del periodo di conservazione e quello di eliminazione definitiva dei messaggi.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>Più criteri di conservazione e i principi di conservazione

Se si configurano più criteri di conservazione di Teams con durate variabili, vengono applicati i [principi dei criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence). Ecco una panoramica dell'ordine di priorità:

- La conservazione prevale sempre sull'eliminazione
- Prevale sempre il periodo di conservazione più lungo
- Per quanto riguarda le posizioni, l'inclusione implicita prevale su quella esplicita
- Prevale il periodo di eliminazione più breve

## <a name="when-to-use-retention-policies-for-teams"></a>Quando utilizzare i criteri di conservazione di Teams

In molti casi, le organizzazioni sentono maggiore responsabilità per i dati di chat private invece che per i messaggi dei canali, che in genere sono conversazioni relative a progetti.

È possibile configurare criteri di conservazione distinti per le chat private (chat individuali o di gruppo) e per i messaggi dei canali. È anche possibile configurare criteri univoci che si applicano a utenti o team specifici dell'organizzazione. Per le chat di Teams, è possibile selezionare gli utenti a cui applicare i criteri. Per i messaggi dei canali di Teams, è possibile selezionare i team a cui applicare i criteri.

Per i messaggi dei canali, ad esempio, è possibile applicare un criterio di eliminazione di un anno a team specifici dell'organizzazione e applicare un criterio di eliminazione triennale a tutti gli altri team.

## <a name="manage-retention-policies-for-teams"></a>Gestire i criteri di conservazione di Teams

### <a name="using-the-security--compliance-center"></a>Utilizzo del Centro sicurezza e conformità

#### <a name="create-a-retention-policy"></a>Creare un criterio di conservazione

Per creare criteri di conservazione per i messaggi di chat e canali di Teams, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro del Centro sicurezza e conformità, passare a **Governance delle informazioni** > **Conservazione**.
2. Selezionare **Crea**.
3. Nella pagina **Assegnare il nome al criterio**, immettere un nome e una descrizione per il criterio e quindi fare clic su **Avanti**.
4. Nella pagina **Impostazioni **, specificare se si desidera conservare i dati, eliminarli o entrambe le operazioni, insieme al periodo di conservazione; quindi fare clic su **Avanti**.
5. Nella pagina **Scegliere le posizioni**, eseguire le operazioni seguenti e quindi fare clic su **Avanti**:

    - Per applicare il criterio ai messaggi dei canali, abilitare **Messaggi dei canali di Teams**.  Se si desidera applicare il criterio a team specifici dell'organizzazione, selezionare **Scegli i team** e quindi selezionare i team desiderati.
    - Per applicare il criterio alle chat, abilitare **Chat di Teams**. Se si desidera applicare il criterio a utenti specifici dell'organizzazione, selezionare **Scegli gli utenti**, quindi selezionare gli utenti desiderati.
      > [!NOTE]
      > Quando si abilitano **Messaggi dei canali di Teams** e/o **Chat di Teams**, tutte le altre posizioni vengono automaticamente disabilitate. I criteri di conservazione di Teams possono includere solo posizioni di Teams.

        ![Screenshot delle opzioni per i messaggi dei canali e le chat di Teams nella pagina Scegliere le posizioni](media/retention-policies-create.png)

      > [!IMPORTANT]
      > I messaggi dei canali e le chat di Teams non sono interessati dai criteri di conservazione applicati alle cassette postali di utenti o gruppi nelle posizioni della **posta elettronica di Exchange** o dei **gruppi di Office 365**. Anche se i messaggi delle chat e i canali di Teams vengono archiviati in Exchange, sono interessati solo dai criteri di conservazione applicati alle posizioni di Teams.

6. Esaminare le impostazioni e quindi, una volta pronti, selezionare **Crea questo criterio**.

#### <a name="edit-a-retention-policy"></a>Modificare un criterio di conservazione

Per modificare un criterio di conservazione di Teams, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro del Centro sicurezza e conformità, passare a **Governance delle informazioni** > **Conservazione**.
2. Nell'elenco dei criteri di conservazione, selezionare la casella di controllo accanto al criterio di conservazione che si desidera modificare.
3. Selezionare **Modifica** accanto al criterio da modificare, apportare le modifiche desiderate, fare clic su **Salva** e quindi su **Chiudi**.

    ![Screenshot delle opzioni per i messaggi dei canali e le chat di Teams nella pagina Scegliere le posizioni](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>Eliminare un criterio di conservazione

Per eliminare un criterio di conservazione di Teams, eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro del Centro sicurezza e conformità, passare a **Governance delle informazioni** > **Conservazione**.
2. Nell'elenco dei criteri di conservazione, selezionare la casella di controllo accanto al criterio di conservazione che si desidera eliminare.
3. Selezionare **Elimina criterio**.

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per creare e gestire i criteri di conservazione dei team tramite [Office 365 Security & PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)per la conformità, usare i cmdlet seguenti:

|Criterio|Regola|
|---|---|
|[New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>Problemi noti

Di seguito sono elencati i problemi noti dei criteri di conservazione di Teams rilevati e in corso di analisi.

- In **Scegli i team** nella riga della posizione **Messaggi dei canali di Teams**, potrebbero venire mostrati gruppi di Office 365 non presenti in Teams. Questo problema verrà risolto in futuro.

- In **Scegli gli utenti** nella riga della posizione **Chat di Teams**, potrebbero venire mostrati utenti non della cassetta postale e guest. I criteri di conservazione non possono essere impostati per i guest e verranno presto rimossi dall'elenco.

- L'assistente per il ciclo di vita di Exchange viene eseguito quotidianamente, ma ha un contratto di servizio di 7 giorni. Di conseguenza, se si dispone di un criterio di conservazione di Teams per eliminare gli elementi precedenti a 60 giorni, è possibile che questi elementi vengano conservati fino a 67 giorni. Non si tratta di una nuova situazione, in quanto segue il modello di Exchange. Naturalmente, nella maggior parte dei casi, non si verifica alcun ritardo.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica dei criteri di conservazione](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
