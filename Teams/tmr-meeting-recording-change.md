---
title: Usare OneDrive for Business e SharePoint Online per registrare le riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for Business e allo spazio di archiviazione per la registrazione delle riunioni di SharePoint in Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbde1b4d5425b0bbcf904528f0ddb232f27a2ba4b15fb0755639ef01b1f5f09f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312444"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint Online o Stream per registrare le riunioni

> [!Note]
> Il passaggio dall’uso di Microsoft Stream all’uso di OneDrive for Business e Microsoft SharePoint Online per le registrazioni delle riunioni avverrà in modo graduale.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 ottobre 2020<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| È possibile abilitare i criteri riunione di Teams per salvare le registrazioni delle riunioni in OneDrive for Business e SharePoint Online anziché in Microsoft Stream (versione classica)|
|Implementazione a partire dal giorno 7 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni di Teams verranno salvate in OneDrive for Business e SharePoint Online, a meno che non si ritardi questa modifica modificando i criteri delle riunioni di Teams dell'organizzazione e impostandoli in modo esplicito su **Stream**. La visualizzazione dei report dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore dei criteri su **Stream**.|
|Implementazione a partire dal giorno 11 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Anche se i clienti GCC possono rifiutare esplicitamente tale opzione, a partire dal 5 ottobre, non è possibile acconsentire esplicitamente. Questa funzionalità verrà distribuita a tutti i clienti GCC a partire dall'11 gennaio 2021, a meno che non sia stata rifiutata esplicitamente.<br>  <br>A partire dal giorno 11 gennaio 2021, tutte le nuove registrazioni delle riunioni di Teams per i clienti GCC verranno salvate in OneDrive for Business e SharePoint Online, a meno che non si ritardi questa modifica modificando i criteri delle riunioni di Teams dell'organizzazione e impostandoli in modo esplicito su **Stream**. <br><br>Se tale funzionalità è stata rifiutata esplicitamente, ma si vuole attivarla, è possibile impostare i criteri delle riunioni di Teams in modo esplicito su **OneDrive for Business**. |
|Implementazione a partire dal giorno 1 marzo 2021<br> *(Completata)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC-High e DoD**<br> I clienti ora possono abilitare le registrazioni delle riunioni cloud in Microsoft Teams per la prima volta. Queste registrazioni verranno archiviate e riprodotte in OneDrive e SharePoint Online per impostazione predefinita. |
|Implementazione a partire dal giorno 7 luglio 2021<br> *(Completata)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br> Per una riunione di Teams registrata in OneDrive e SharePoint Online e trascritta in tempo reale, ora è possibile cercare in Microsoft Search il file di registrazione della riunione in base alla trascrizione. |
|Implementazione incrementale a partire dal giorno 16 agosto 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br>Nessuna nuova registrazione della riunione può essere salvata in Microsoft Stream (versione classica); tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for Business e SharePoint Online anche se hanno modificato i criteri delle riunioni di Teams in Stream.<br><br> È consigliabile che i clienti, in modo da controllare meglio il cambiamento nell'organizzazione, acconsentano esplicitamente ogni volta che si ha familiarità con la modifica anziché attendere che venga eseguita. |

Microsoft Teams offre un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dalla versione classica di Microsoft Stream al [nuovo Stream](/stream/streamnew/new-stream), questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint Online in Microsoft 365 e offre molti vantaggi.

Stream (versione classica) non verrà deprecato per il prossimo futuro. I video che al momento sono live in Stream (versione classica) rimarranno lì fino a quando non sarà disponibile uno strumento di migrazione futuro per spostarli su OneDrive e SharePoint Online. Per altre informazioni sui piani futuri, vedere [Migrazione della versione classica di Stream](/stream/streamnew/classic-migration).

> [!NOTE]
> Se la registrazione di una riunione di Teams non viene caricata correttamente in OneDrive/SharePoint Online, questa verrà salvata temporaneamente nei Servizi multimediali di Azure (AMS). Dopo l'archiviazione in AMS, non viene effettuato alcun tentativo di caricamento automatico della registrazione in OneDrive/SharePoint Online o Stream.

Le registrazioni delle riunioni archiviate in AMS sono disponibili per 21 giorni prima che vengano eliminate automaticamente. Gli utenti possono scaricare il video da AMS se devono conservarne una copia.

I vantaggi dell'uso di OneDrive for Business e SharePoint Online per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per la registrazione delle riunioni di Teams (TMR) (etichette di autoretenzione S+C E5)
- Trarre vantaggio da OneDrive for Business e dalla governance delle informazioni di SharePoint Online
- Autorizzazioni e condivisioni facili da impostare
- Condividere registrazioni con gli utenti guest (utenti esterni) solo con condivisione esplicita
- Richiedere flusso di accesso
- Fornire collegamenti condivisi di OneDrive for Business e SharePoint Online
- Le registrazioni delle riunioni sono disponibili più velocemente
- Trascrizione di base della ricerca registrata nella riunione
- Supporto del tenant in **locale**
- Supporto multi-geografico: le registrazioni vengono archiviate in un'area specifica dell'utente
- Supporto BYOK (Bring Your Own Key)

Consultare l'elenco completo delle [funzionalità disponibili oggi e nel tempo](/stream/streamnew/features-new-version-stream).

Per altre informazioni, guardare il video "What's New for Microsoft Teams Meeting Recordings".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurare l'opzione di registrazione riunione per OneDrive for Business e SharePoint Online

L'opzione di registrazione della riunione è un'impostazione a livello di criteri di Teams. Nell'esempio seguente viene illustrato come impostare il criterio globale. Assicurarsi di impostare l'opzione di registrazione delle riunioni per il criterio o i criteri assegnati agli utenti.

> [!Note]
> La propagazione delle modifiche ai criteri delle riunioni di Teams richiede qualche tempo. È necessario ricontrollare dopo alcune ore dall'impostazione, quindi disconnettersi e accedere di nuovo all'applicazione desktop di Teams o riavviare semplicemente il computer.

1. Installare PowerShell per Teams.

   > [!NOTE]
   > Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online. Vedere [Gestire Skype for Business Online con PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Avviare PowerShell come amministratore.

3. Installare il [modulo di PowerShell per Teams](./teams-powershell-install.md).

4. Importare il modulo di Microsoft Teams e accedere come amministratore di Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Usare [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per impostare un criterio di riunione di Teams per la transizione dall'archiviazione di Stream a OneDrive for Business e SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se degli utenti hanno assegnato un criterio per organizzatore o per utente, è necessario configurare questa impostazione su questo criterio, se si desidera che archivino anche le registrazioni delle riunioni in OneDrive for Business e SharePoint Online. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Ulteriori informazioni

Per altre informazioni sulla registrazione di una riunione cloud di Teams, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md). In questo articolo sono disponibili altre informazioni sulla configurazione, la gestione, la governance, le autorizzazioni e l'archiviazione della registrazione.
