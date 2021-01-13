---
title: Configurare Skype for Business Server per l'utilizzo dell'archiviazione di Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Riepilogo: configurare le trascrizioni di messaggistica istantanea per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: f051e5f3798b76b5e3943893d2a18e113ae8ab16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833896"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurare Skype for Business Server per l'utilizzo dell'archiviazione di Exchange Server

**Riepilogo:** Configurare le trascrizioni di messaggistica istantanea per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.

Skype for Business Server fornisce agli amministratori la possibilità di archiviare la messaggistica istantanea e le trascrizioni di Web Conferencing in una cassetta postale di Exchange Server 2016 o Exchange Server 2013 anziché in un database di SQL Server. Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella Eliminazioni della cassetta postale dell'utente. Questa cartella è nascosta e si trova nella cartella Elementi ripristinabili. Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere individuata utilizzando la ricerca di cassette postali di Exchange e/o Microsoft SharePoint Server 2013. Poiché le informazioni vengono memorizzate nella stessa cartella utilizzata dalla funzionalità di archiviazione In-Place di Exchange (responsabile della posta elettronica e di altre comunicazioni di Exchange), gli amministratori possono utilizzare un unico strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.

> [!IMPORTANT]
> Per disabilitare completamente l'archiviazione delle conversazioni, è inoltre necessario disabilitare la cronologia delle conversazioni. Per ulteriori informazioni, vedere i seguenti argomenti: [gestione dell'archiviazione delle comunicazioni interne ed esterne in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Per archiviare le trascrizioni in Exchange Server, è necessario iniziare con la configurazione dell'autenticazione da server a server tra Skype for Business Server e Exchange Server. Dopo aver effettuato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Skype for Business Server (si noti che, a seconda dell'installazione e della configurazione, potrebbe non essere necessario completare tutte queste attività):

1. Abilitare l'archiviazione di Exchange modificando le impostazioni di configurazione dell'archiviazione di Skype for Business Server. Questo passaggio è obbligatorio per tutte le distribuzioni.

2. Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti. Questo passaggio è obbligatorio per tutte le distribuzioni.

3. Configurare la proprietà ExchangeArchivingPolicy per ogni utente. Questo passaggio è necessario solo se Skype for Business Server e Exchange Server si trovano in foreste diverse.

## <a name="step-1-enabling-exchange-archiving"></a>Passaggio 1: abilitazione dell'archiviazione di Exchange

L'archiviazione in Skype for Business Server viene gestita principalmente utilizzando le impostazioni di configurazione dell'archiviazione. Quando si installa Skype for Business Server, viene automaticamente assegnata una singola raccolta globale di queste impostazioni. Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali e non è abilitata per l'archiviazione di Exchange in queste impostazioni. Per utilizzare l'archiviazione di Exchange, gli amministratori devono configurare le proprietà EnableArchiving e EnableExchangeArchiving nelle impostazioni di configurazione. La proprietà EnableArchiving può essere impostata su uno di tre possibili valori:

- **Nessuna**. L'archiviazione è disabilitata. Questo è il valore predefinito. Se EnableArchiving è impostato su nessuno, il database di archiviazione di Skype for Business Server o di Exchange Server non verrà archiviato.

- **Imsolo**. Vengono archiviate solo le trascrizioni dei messaggi istantanei. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange Server. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Skype for Business Server.

- **ImAndWebConf**. Vengono archiviate sia le trascrizioni dei messaggi istantanei sia quelle di Web Conferencing. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange Server. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Skype for Business Server.

La proprietà EnableExchangeArchiving è un valore booleano: impostare EnableExchangeArchiving su true ($True) per abilitare l'archiviazione di Exchange o impostare EnableExchangeArchiving su false ($False) per disabilitare l'archiviazione di Exchange. Ad esempio, questo comando consente di abilitare l'archiviazione delle trascrizioni di messaggistica istantanea e di abilitare anche l'archiviazione di Exchange:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Per disabilitare l'archiviazione di Exchange, utilizzare un comando simile al seguente, che consente l'archiviazione di messaggistica istantanea ma disabilita l'archiviazione in Exchange (in altre parole, le trascrizioni verranno archiviate in Skype for Business Server):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se la proprietà EnableArchiving è impostata su None, Skype for Business Server non archivierà affatto la messaggistica istantanea e le trascrizioni di Web Conferencing. In tal caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.

L'archiviazione di Exchange può anche essere abilitata (o disattivata) utilizzando Skype for Business Server. A tale scopo, completare la procedura seguente:

1. Nel Pannello di controllo fare clic su **Monitoraggio e archiviazione** e quindi su **Configurazione archiviazione**.

2. Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta delle impostazioni di archiviazione da modificare (ad esempio la raccolta **Globale**).

3. Nel riquadro **Modifica impostazione di archiviazione** fare clic sull'elenco a discesa **Impostazione di archiviazione** e selezionare **Archivia sessioni di messaggistica istantanea** per archiviare solo le sessioni di messaggistica istantanea o su **Archivia sessioni di messaggistica istantanea e Web Conferencing** per archiviare sia le sessioni di messaggistica istantanea sia quelle di Web Conferencing.

4. Dopo aver scelto gli elementi da archiviare, selezionare la casella di controllo **integrazione di Exchange Server** per abilitare l'archiviazione di Exchange. Per disabilitare l'archiviazione di Exchange, deselezionare questa casella di controllo.

> [!NOTE]
> La casella di controllo **Integrazione Exchange Server** non sarà disponibile se **Impostazione di archiviazione** è impostata su **Disabilita archiviazione**. È innanzitutto necessario abilitare l'archiviazione e quindi abilitare l'archiviazione di Exchange.

Se Skype for Business Server e Exchange Server si trovano nella stessa foresta, l'archiviazione per singoli utenti (o almeno per gli utenti che dispongono di account di posta elettronica su Exchange Server) viene gestita utilizzando i criteri di conservazione In-Place di Exchange. Se si dispone di utenti ospitati in una versione precedente di Exchange, l'archiviazione per tali utenti verrà gestita utilizzando i criteri di archiviazione di Skype for Business Server. Si noti che solo gli utenti con account su Exchange Server 2016 o Exchange Server 2013 possono fare in modo che le trascrizioni Skype for business vengano archiviate in Exchange.

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, l'archiviazione per singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente. Per ulteriori informazioni, vedere il passaggio 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Passaggio 2: Abilitazione dell'archiviazione delle comunicazioni interne e/o esterne

Dopo aver abilitato l'archiviazione (e l'archiviazione di Exchange), è necessario modificare i criteri di archiviazione corretti per garantire che le sessioni degli utenti vengano effettivamente archiviate. Si noti che l'abilitazione dell'archiviazione (passaggio 1) non consente a Skype for Business Server di avviare l'archiviazione delle trascrizioni di messaggistica istantanea e Web Conferencing. È invece necessario utilizzare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna. Quando si installa Skype for Business Server, viene installato anche un singolo criterio di archiviazione globale contenente due proprietà:

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

I criteri di archiviazione possono essere gestiti anche utilizzando il pannello di controllo di Skype for Business Server. Nel Pannello di controllo, fare clic su **Monitoraggio e archiviazione**, quindi su **Criteri di archiviazione**. Per modificare criteri esistenti, fare doppio clic sui criteri (ad esempio Globale), quindi nel riquadro **Modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** secondo le esigenze. Per creare un nuovo criterio di archiviazione, fare clic su **nuovo** e quindi selezionare criteri **sito** o criteri **utente**. Se si creano nuovi criteri utente, è quindi necessario accedere agli account utente appropriati (dalla scheda **Utenti**) e assegnare a tali utenti i nuovi criteri.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Passaggio 3: Configurazione della proprietà ExchangeArchivingPolicy

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione di Exchange nelle impostazioni di configurazione dell'archiviazione; Questo non provocherà la messaggistica istantanea e le trascrizioni di Web Conferencing che vengono archiviate in Exchange. Al contrario, è necessario configurare anche la proprietà ExchangeArchivingPolicy su ciascuno degli account utente di Skype for Business Server rilevanti. Questa proprietà può essere impostata su uno di quattro possibili valori:

1. Non **inizializzato**. Indica che l'archiviazione si baserà sulle impostazioni di blocco In-Place configurate per la cassetta postale di Exchange dell'utente. Se In-Place blocco non è stato abilitato nella cassetta postale dell'utente, l'utente dovrà archiviare la propria trascrizione di messaggistica e Web Conferencing in Skype for Business Server.

2. **UseLyncArchivingPolicy**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Skype for Business Server piuttosto che in Exchange.

3. **Noarchiving**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing non devono essere archiviate. Si noti che questa impostazione sostituisce tutti i criteri di archiviazione di Skype for Business Server assegnati all'utente.

4. **ArchivingToExchange**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni di blocco In-Place che sono state assegnate (o meno) alla cassetta postale dell'utente.

Ad esempio, per configurare un account utente in modo che le trascrizioni di messaggistica istantanea e Web Conferencing vengano sempre archiviate in Exchange, è possibile utilizzare un comando simile al seguente da Skype for Business Server Management Shell:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Per impostare gli stessi criteri di archiviazione per un gruppo di utenti (ad esempio tutti gli utenti ospitati in un pool di registrazione specificato), è possibile utilizzare un comando simile al seguente:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tenere presente che è necessario utilizzare Skype for Business Server Management Shell (e Windows PowerShell) per configurare il valore della proprietà ExchangeArchivingPolicy. Questa proprietà non è esposta agli amministratori di Skype for Business Server.

Per visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile utilizzare un comando simile al seguente che restituisce il nome visualizzato di Active Directory di tutti gli utenti la cui proprietà ExchangeArchivingPolicy è impostata su Uninitialized:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

In modo analogo, questo comando restituisce il nome visualizzato degli utenti la cui proprietà ExchangeArchivingPolicy non è impostata su UseLyncArchivingPolicy:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


