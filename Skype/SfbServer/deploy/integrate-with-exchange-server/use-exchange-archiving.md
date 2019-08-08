---
title: Configurare Skype for Business Server in uso per l'archiviazione di Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Riepilogo: configurare le trascrizioni di messaggistica istantanea per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: 89aaf4d931bb3aa33358e314a4dd714fd58e8e7a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244152"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurare Skype for Business Server in uso per l'archiviazione di Exchange Server

**Riepilogo:** Configurare le trascrizioni di messaggistica istantanea per Exchange Server 2016 o Exchange Server 2013 e Skype for Business Server.

Skype for Business Server offre agli amministratori la possibilità di archiviare le trascrizioni di messaggistica istantanea e Web Conferencing in una cassetta postale di Exchange Server 2016 o Exchange Server 2013 anziché in un database di SQL Server. Se si abilita questa opzione, le trascrizioni vengono scritte nella cartella eliminazioni nella cassetta postale dell'utente. La cartella Purges è una cartella nascosta trovata nella cartella elementi ripristinabili. Anche se questa cartella non è visibile agli utenti finali, la cartella viene indicizzata dal motore di ricerca di Exchange e può essere scoperta usando la ricerca delle cassette postali di Exchange e/o Microsoft SharePoint Server 2013. Poiché le informazioni sono archiviate nella stessa cartella usata dalla funzionalità di blocco sul posto di Exchange (responsabile dell'archiviazione della posta elettronica e di altre comunicazioni di Exchange), gli amministratori possono usare un singolo strumento per cercare tutte le comunicazioni elettroniche archiviate per un utente.

> [!IMPORTANT]
> Per disabilitare completamente l'archiviazione delle conversazioni, è anche necessario disabilitare la cronologia delle conversazioni. Per altre informazioni, vedere gli argomenti seguenti: [gestione dell'archiviazione delle comunicazioni interne ed esterne in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Per archiviare le trascrizioni in Exchange Server, è necessario iniziare configurando l'autenticazione da server a server tra Skype for Business Server ed Exchange Server. Dopo aver effettuato l'autenticazione da server a server, è possibile eseguire le attività seguenti in Skype for Business Server (si noti che, a seconda della configurazione e delle configurazioni, potrebbe non essere necessario completare tutte queste attività):

1. Abilitare l'archiviazione di Exchange modificando le impostazioni di configurazione dell'archiviazione di Skype for Business Server. Questo passaggio è necessario per tutte le distribuzioni.

2. Abilitare l'archiviazione per le comunicazioni interne e/o esterne per gli utenti. Questo passaggio è necessario per tutte le distribuzioni.

3. Configurare la proprietà ExchangeArchivingPolicy per ogni utente. Questo passaggio è obbligatorio solo se Skype for Business Server e Exchange Server si trovano in foreste diverse.

## <a name="step-1-enabling-exchange-archiving"></a>Passaggio 1: abilitazione dell'archiviazione di Exchange

L'archiviazione in Skype for Business Server viene gestita principalmente con le impostazioni di configurazione dell'archiviazione. Quando si installa Skype for Business Server viene automaticamente assegnata una singola raccolta globale di queste impostazioni. Gli amministratori possono facoltativamente creare nuove raccolte di impostazioni di archiviazione nell'ambito del sito. Per impostazione predefinita, l'archiviazione non è abilitata nelle impostazioni globali, né l'archiviazione di Exchange è abilitata in queste impostazioni. Per usare l'archiviazione di Exchange, gli amministratori devono configurare le proprietà EnableArchiving e EnableExchangeArchiving in queste impostazioni di configurazione. La proprietà EnableArchiving può essere impostata su uno dei tre valori possibili:

- **Nessuno**. L'archiviazione è disabilitata. Questo è il valore predefinito. Se EnableArchiving è impostato su None, non verrà archiviato nel database di archiviazione di Skype for Business Server o in Exchange Server.

- **ImOnly**. Vengono archiviati solo le trascrizioni di messaggi istantanei. Se l'archiviazione di Exchange è abilitata, queste trascrizioni verranno archiviate in Exchange Server. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Skype for Business Server.

- **ImAndWebConf**. Vengono archiviate sia le trascrizioni di messaggistica istantanea che le trascrizioni di conferenza Web. Se è abilitata l'archiviazione di Exchange, queste trascrizioni verranno archiviate in Exchange Server. Se l'archiviazione di Exchange è disabilitata, queste trascrizioni verranno archiviate in Skype for Business Server.

La proprietà EnableExchangeArchiving è un valore booleano: imposta EnableExchangeArchiving su true ($True) per abilitare l'archiviazione di Exchange o impostare EnableExchangeArchiving su false ($False) per disabilitare l'archiviazione di Exchange. Ad esempio, questo comando consente l'archiviazione delle trascrizioni di messaggistica istantanea e consente inoltre l'archiviazione di Exchange:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Per disabilitare l'archiviazione di Exchange, usare un comando simile al seguente, che consente l'archiviazione di messaggistica istantanea, ma disabilita l'archiviazione in Exchange (in altre parole, le trascrizioni verranno archiviate in Skype for Business Server):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se la proprietà EnableArchiving è impostata su None, Skype for Business Server non archivierà affatto le trascrizioni di messaggistica istantanea e Web Conferencing. In questo caso, il server ignorerà semplicemente il valore configurato per EnableExchangeArchiving.

L'archiviazione di Exchange può essere abilitata o disabilitata anche tramite Skype for Business Server. Per eseguire questa operazione, eseguire la procedura seguente:

1. Nel pannello di controllo fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

2. Nella scheda **Configurazione archiviazione** fare doppio clic sulla raccolta di impostazioni di archiviazione da modificare, ad esempio la raccolta **globale** .

3. Nel riquadro **Modifica impostazioni archiviazione** fare clic sull'elenco a discesa **Impostazioni archiviazione** e selezionare **sessioni** di messaggistica istantanea (per archiviare solo le sessioni di Instant Messaging) o sessioni di messaggistica istantanea **e conferenze Web** (per archiviare sia sessioni di messaggistica istantanea e conferenze Web).

4. Dopo aver scelto gli elementi da archiviare, selezionare la casella di controllo **integrazione di Exchange Server** per abilitare l'archiviazione di Exchange. Per disabilitare l'archiviazione di Exchange, deselezionare questa casella di controllo.

> [!NOTE]
> La casella di controllo **integrazione di Exchange Server** non sarà disponibile se l' **impostazione di archiviazione** è impostata per **disabilitare l'archiviazione**. Prima di tutto, è necessario abilitare l'archiviazione e quindi abilitare l'archiviazione di Exchange.

Se Skype for Business Server e Exchange Server si trovano nella stessa foresta, l'archiviazione per singoli utenti (o almeno per gli utenti con account di posta elettronica su Exchange Server) viene gestita usando i criteri di blocco sul posto di Exchange. Se si hanno utenti ospitati in una versione precedente di Exchange, l'archiviazione per tali utenti verrà gestita usando i criteri di archiviazione di Skype for Business Server. Tieni presente che solo gli utenti con account su Exchange Server 2016 o Exchange Server 2013 possono eseguire l'archiviazione delle trascrizioni Skype for business in Exchange.

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, l'archiviazione per singoli utenti viene gestita configurando la proprietà ExchangeArchivingPolicy per ogni singolo account utente. Per altre informazioni, vedere passaggio 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Passaggio 2: abilitazione dell'archiviazione delle comunicazioni interne e/o esterne

Dopo aver abilitato l'archiviazione e l'archiviazione di Exchange, è necessario modificare i criteri di archiviazione appropriati per verificare che le sessioni utente vengano effettivamente archiviate. Tieni presente che l'abilitazione dell'archiviazione (passaggio 1) non fa sì che Skype for Business Server inizi a archiviare le trascrizioni di messaggistica istantanea e Web Conferencing. Devi invece usare i criteri di archiviazione per abilitare l'archiviazione interna e/o esterna. Quando si installa Skype for Business Server si installa anche un singolo criterio di archiviazione globale che contiene due proprietà:

- **ArchiveInternal**. Quando impostato su true ($True) indica che verranno archiviate sessioni di comunicazione interne che coinvolgono solo gli utenti che hanno account di Active Directory nell'organizzazione.

- **ArchiveExternal**. Se impostato su true ($True) indica che verranno archiviate le sessioni di comunicazione interne (sessioni che coinvolgono almeno un utente che non ha un account di Active Directory nell'organizzazione).

Per impostazione predefinita, entrambi i valori di proprietà sono impostati su false, quindi non vengono archiviati né sessioni di comunicazione interne né esterne. Per modificare il criterio globale, è possibile usare Skype for Business Server Management Shell e il cmdlet Set-CsArchivingPolicy. Questo comando consente l'archiviazione di sessioni di comunicazione interne ed esterne:

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

In alternativa, puoi usare il nuovo-CsArchivingPolicy per creare un nuovo criterio nell'ambito del sito o dell'ambito per utente. Ad esempio, questo comando crea un nuovo criterio di archiviazione per utente denominato RedmondArchivingPolicy:

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Se si crea un criterio per utente, sarà necessario assegnare i criteri agli utenti appropriati. Ad esempio:

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

I criteri di archiviazione possono essere gestiti anche tramite il pannello di controllo di Skype for Business Server. Nel pannello di controllo fare clic su **monitoraggio e archiviazione** e quindi su **criteri di archiviazione**. Per modificare un criterio esistente, fare doppio clic sul criterio (ad esempio, globale) e quindi nel riquadro **modifica criteri di archiviazione** selezionare o deselezionare le caselle di controllo **Archivia comunicazioni interne** e **Archivia comunicazioni esterne** in base alle esigenze. Per creare un nuovo criterio di archiviazione, fare clic su **nuovo** e quindi selezionare criteri **sito** o **criteri utente**. Se crei un nuovo criterio utente, devi accedere agli account utente appropriati (dalla scheda **utenti** ) e assegnare agli utenti il nuovo criterio.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Passaggio 3: configurazione della proprietà ExchangeArchivingPolicy

Se Skype for Business Server e Exchange Server si trovano in foreste diverse, non è sufficiente abilitare semplicemente l'archiviazione di Exchange nelle impostazioni di configurazione dell'archiviazione; Ciò non comporterà l'archiviazione di trascrizioni di messaggistica istantanea e Web Conferencing in Exchange. Devi invece configurare anche la proprietà ExchangeArchivingPolicy in ognuno degli account utente di Skype for Business Server pertinenti. Questa proprietà può essere impostata su uno dei quattro valori possibili:

1. **** Non inizializzato. Indica che l'archiviazione sarà basata sulle impostazioni di blocco sul posto configurate per la cassetta postale di Exchange dell'utente; Se il blocco sul posto non è stato abilitato nella cassetta postale dell'utente, l'utente avrà le sue trascrizioni di messaggistica e Web Conferencing archiviate in Skype for Business Server.

2. **UseLyncArchivingPolicy**. Indica che le trascrizioni di messaggistica istantanea e web conferenza dell'utente devono essere archiviate in Skype for Business Server anziché in Exchange.

3. **** Noarchiving. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente non devono essere archiviate affatto. Tieni presente che questa impostazione sostituisce tutti i criteri di archiviazione di Skype for Business Server assegnati all'utente.

4. **ArchivingToExchange**. Indica che le trascrizioni di messaggistica istantanea e Web Conferencing dell'utente devono essere archiviate in Exchange indipendentemente dalle impostazioni di blocco sul posto che hanno o non sono state assegnate alla cassetta postale dell'utente.

Ad esempio, per configurare un account utente in modo che le trascrizioni di messaggistica istantanea e Web Conferencing vengano sempre archiviate in Exchange, è possibile usare un comando simile a quello di Skype for Business Server Management Shell:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Se si vogliono impostare gli stessi criteri di archiviazione per un gruppo di utenti, ad esempio tutti gli utenti ospitati in un pool di registrar specificato, è possibile usare un comando simile al seguente:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Tieni presente che devi usare Skype for Business Server Management Shell e Windows PowerShell per configurare il valore della proprietà ExchangeArchivingPolicy. Questa proprietà non viene esposta agli amministratori di Skype for Business Server.

Se si vuole visualizzare un elenco di tutti gli utenti a cui è stato assegnato un criterio di archiviazione specifico, è possibile usare un comando simile al seguente, che restituisce il nome visualizzato di Active Directory di tutti gli utenti che hanno il set di proprietà ExchangeArchivingPolicy per non inizializzare:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Analogamente, questo comando restituisce il nome visualizzato degli utenti che non hanno la proprietà ExchangeArchivingPolicy impostata su UseLyncArchivingPolicy:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


