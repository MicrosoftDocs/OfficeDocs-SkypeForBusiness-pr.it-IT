---
title: Configurare Skype for Business Server per l'utilizzo Exchange Server archiviazione
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Riepilogo: configurare le trascrizioni di messaggistica istantanea Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: 44dbe1418176d7f0c33a6355480913a68baea0dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745292"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurare Skype for Business Server per l'utilizzo Exchange Server archiviazione

**Riepilogo:** Configurare le trascrizioni di messaggistica istantanea Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.

Skype for Business Server consente agli amministratori di disporre di trascrizioni di messaggistica istantanea e conferenze Web archiviate nella cassetta postale di Exchange Server 2016 o Exchange Server 2013 di un utente anziché in un database di SQL Server. Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella Eliminazioni della cassetta postale dell'utente. Questa cartella è nascosta e si trova nella cartella Elementi ripristinabili. Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere individuata utilizzando la ricerca nelle cassette postali di Exchange e/o Microsoft SharePoint Server 2013. Poiché le informazioni vengono archiviate nella stessa cartella utilizzata dalla funzionalità di archiviazione Exchange In-Place (responsabile dell'archiviazione della posta elettronica e di altre comunicazioni Exchange), gli amministratori possono utilizzare un singolo strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.

> [!IMPORTANT]
> Per disabilitare completamente l'archiviazione delle conversazioni, è inoltre necessario disabilitare la cronologia delle conversazioni. Per ulteriori informazioni, vedere i seguenti argomenti: [Managing the Archiving of internal and external communications in Skype for Business Server,](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications) [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)

Per archiviare le trascrizioni Exchange Server è necessario iniziare configurando l'autenticazione da server a server tra Skype for Business Server e Exchange Server. Dopo aver completato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Skype for Business Server (tenere presente che, a seconda dell'installazione e della configurazione, potrebbe non essere necessario completare tutte queste attività):

1. Abilitare Exchange archiviazione modificando le impostazioni di configurazione Skype for Business Server archiviazione. Questo passaggio è obbligatorio per tutte le distribuzioni.

2. Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti. Questo passaggio è obbligatorio per tutte le distribuzioni.

3. Configurare la proprietà ExchangeArchivingPolicy per ogni utente. Questo passaggio è necessario solo se Skype for Business Server e Exchange Server si trovano in foreste diverse.

## <a name="step-1-enabling-exchange-archiving"></a>Passaggio 1: abilitazione dell'Exchange archiviazione

L'archiviazione Skype for Business Server viene gestita principalmente utilizzando le impostazioni di configurazione dell'archiviazione. Quando si installa Skype for Business Server viene automaticamente data una singola raccolta globale di queste impostazioni. Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali né Exchange in queste impostazioni. Per utilizzare l'archiviazione Exchange, gli amministratori devono configurare entrambe le proprietà EnableArchiving e EnableExchangeArchiving in queste impostazioni di configurazione. La proprietà EnableArchiving può essere impostata su uno di tre possibili valori:

- **Nessuno**. L'archiviazione è disabilitata. Questo è il valore predefinito. Se EnableArchiving è impostato su None, non verrà archiviato nulla nel database di archiviazione Skype for Business Server o in Exchange Server.

- **ImOnly**. Vengono archiviate solo le trascrizioni dei messaggi istantanei. Se Exchange'archiviazione è abilitata, queste trascrizioni verranno archiviate in Exchange Server. Se Exchange'archiviazione è disabilitata, queste trascrizioni verranno archiviate Skype for Business Server.

- **ImAndWebConf**. Vengono archiviate sia le trascrizioni dei messaggi istantanei sia quelle di Web Conferencing. Se Exchange è abilitata l'archiviazione, queste trascrizioni verranno archiviate in Exchange Server. Se Exchange'archiviazione è disabilitata, queste trascrizioni verranno archiviate Skype for Business Server.

La proprietà EnableExchangeArchiving è un valore booleano: impostare EnableExchangeArchiving su True ($True) per abilitare l'archiviazione Exchange oppure impostare EnableExchangeArchiving su False ($False) per disabilitare l'archiviazione Exchange. Ad esempio, questo comando consente di abilitare l'archiviazione delle trascrizioni di messaggistica istantanea e di Exchange archiviazione:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Per disabilitare l'archiviazione Exchange, utilizzare un comando simile al seguente, che abilita l'archiviazione della messaggistica istantanea ma disabilita l'archiviazione Exchange (in altre parole, le trascrizioni verranno archiviate in Skype for Business Server):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se la proprietà EnableArchiving è impostata su None, Skype for Business Server le trascrizioni di messaggistica istantanea e conferenze Web non verranno archiviate affatto. In tal caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.

Exchange l'archiviazione può essere abilitata (o disabilitata) anche utilizzando il Skype for Business Server. A tale scopo, completare la procedura seguente:

1. Nel Pannello di controllo fare clic su **Monitoraggio e archiviazione** e quindi su **Configurazione archiviazione**.

2. Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta delle impostazioni di archiviazione da modificare (ad esempio la raccolta **Globale**).

3. Nel riquadro **Modifica impostazione di archiviazione** fare clic sull'elenco a discesa **Impostazione di archiviazione** e selezionare **Archivia sessioni di messaggistica istantanea** per archiviare solo le sessioni di messaggistica istantanea o su **Archivia sessioni di messaggistica istantanea e Web Conferencing** per archiviare sia le sessioni di messaggistica istantanea sia quelle di Web Conferencing.

4. Dopo aver scelto gli elementi da archiviare, selezionare la casella **Exchange Server di integrazione** per abilitare Exchange archiviazione. Per disabilitare Exchange archiviazione, deselezionare questa casella di controllo.

> [!NOTE]
> La casella di controllo **Integrazione Exchange Server** non sarà disponibile se **Impostazione di archiviazione** è impostata su **Disabilita archiviazione**. È necessario abilitare prima l'archiviazione e quindi Exchange archiviazione.

Se Skype for Business Server e Exchange Server si trovano nella stessa foresta, l'archiviazione per i singoli utenti (o almeno per gli utenti che dispongono di account di posta elettronica su Exchange Server) viene gestita utilizzando i criteri di conservazione Exchange In-Place. Se si dispone di utenti ospitati in una versione precedente di Exchange l'archiviazione per tali utenti verrà gestita utilizzando i criteri di Skype for Business Server archiviazione. Si noti che solo gli utenti con account in Exchange Server 2016 o Exchange Server 2013 possono avere le trascrizioni Skype for Business archiviate in Exchange.

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, l'archiviazione per i singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente. Per ulteriori informazioni, vedere il passaggio 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Passaggio 2: Abilitazione dell'archiviazione delle comunicazioni interne e/o esterne

Dopo aver abilitato l'archiviazione (e Exchange archiviazione), è necessario modificare i criteri di archiviazione appropriati per assicurarsi che le sessioni utente siano effettivamente archiviate. Tenere presente che la semplice abilitazione dell'archiviazione (passaggio 1) non Skype for Business Server l'archiviazione delle trascrizioni di messaggistica istantanea e conferenze Web. È invece necessario utilizzare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna. Quando si installa Skype for Business Server si installa anche un singolo criterio di archiviazione globale contenente due proprietà:

- **ArchiveInternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione interna che interessano solo gli utenti con account Active Directory attivi nell'organizzazione.

- **ArchiveExternal**. Se impostata su True ($True), indica che verranno archiviate le sessioni di comunicazione esterna (sessioni che interessano almeno un utente che non ha un account Active Directory attivo nell'organizzazione.

Per impostazione predefinita, i valori di entrambe queste proprietà sono impostati su False, pertanto non vengono archiviate le sessioni di comunicazione né interna né esterna. Per modificare il criterio globale, è possibile utilizzare Skype for Business Server Management Shell e il cmdlet Set-CsArchivingPolicy. Questo comando abilita l'archiviazione delle sessioni di comunicazione sia interna sia esterna:

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

In alternativa, è possibile utilizzare New-CsArchivingPolicy per creare un nuovo criterio nell'ambito del sito o per utente. Ad esempio, questo comando crea un nuovo criterio di archiviazione per utente denominato RedmondArchivingPolicy:

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Se si crea un criterio per utente, sarà quindi necessario assegnarlo agli utenti appropriati. Ad esempio:

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

I criteri di archiviazione possono essere gestiti anche tramite il Skype for Business Server di controllo. Nel Pannello di controllo, fare clic su **Monitoraggio e archiviazione**, quindi su **Criteri di archiviazione**. Per modificare criteri esistenti, fare doppio clic sui criteri (ad esempio Globale), quindi nel riquadro **Modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** secondo le esigenze. Per creare un nuovo criterio di archiviazione, fare clic su **Nuovo** e quindi selezionare **Criteri sito** o **Criteri utente.** Se si creano nuovi criteri utente, è quindi necessario accedere agli account utente appropriati (dalla scheda **Utenti**) e assegnare a tali utenti i nuovi criteri.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Passaggio 3: Configurazione della proprietà ExchangeArchivingPolicy

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione Exchange nelle impostazioni di configurazione dell'archiviazione. ciò non comporta l'archiviazione delle trascrizioni di messaggistica istantanea e conferenze Web in Exchange. È invece necessario configurare anche la proprietà ExchangeArchivingPolicy in ognuno degli account utente Skype for Business Server pertinenti. Questa proprietà può essere impostata su uno di quattro possibili valori:

1. **Non inizializzato**. Indica che l'archiviazione sarà basata sulle impostazioni di In-Place di archiviazione configurate per la cassetta postale Exchange'utente. se In-Place il blocco non è stato abilitato nella cassetta postale dell'utente, l'utente avrà le trascrizioni di messaggistica e conferenze Web archiviate in Skype for Business Server.

2. **UseLyncArchivingPolicy**. Indica che le trascrizioni di messaggistica istantanea e web conferencing dell'utente devono essere archiviate in Skype for Business Server anziché in Exchange.

3. **NoArchiving**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing non devono essere archiviate. Si noti che questa impostazione ha la priorità su Skype for Business Server criteri di archiviazione assegnati all'utente.

4. **ArchivingToExchange**. Indica che le trascrizioni di messaggistica istantanea e conferenze Web dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni di blocco In-Place assegnate o meno alla cassetta postale dell'utente.

Ad esempio, per configurare un account utente in modo che la messaggistica istantanea e le trascrizioni delle conferenze Web siano sempre archiviate in Exchange è possibile utilizzare un comando simile al seguente da Skype for Business Server Management Shell:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Per impostare gli stessi criteri di archiviazione per un gruppo di utenti (ad esempio tutti gli utenti ospitati in un pool di registrazione specificato), è possibile utilizzare un comando simile al seguente:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Si noti che è necessario utilizzare Skype for Business Server Management Shell (e Windows PowerShell) per configurare il valore della proprietà ExchangeArchivingPolicy. Questa proprietà non viene esposta agli amministratori nel Skype for Business Server.

Per visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile utilizzare un comando simile al seguente che restituisce il nome visualizzato di Active Directory di tutti gli utenti la cui proprietà ExchangeArchivingPolicy è impostata su Uninitialized:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

In modo analogo, questo comando restituisce il nome visualizzato degli utenti la cui proprietà ExchangeArchivingPolicy non è impostata su UseLyncArchivingPolicy:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```