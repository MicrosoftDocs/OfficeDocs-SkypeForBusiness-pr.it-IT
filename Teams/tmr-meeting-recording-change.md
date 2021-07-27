---
title: Usare OneDrive for Business e SharePoint Online per le registrazioni delle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for Business e SharePoint archiviazione di registrazione delle riunioni online in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e00ccbf9ade9b1fae3dde64033fe82b502e2366b
ms.sourcegitcommit: 79d20fa2c45173d5a990551e79571caff06d7f82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2021
ms.locfileid: "53486136"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint Online o Stream per le registrazioni delle riunioni

> [!Note]
> Il cambiamento dall'uso di Microsoft Stream OneDrive for Business e Microsoft SharePoint Online per le registrazioni delle riunioni sarà un approccio a fasi.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 ottobre 2020<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Si abilita il criterio Teams riunione per salvare le registrazioni delle riunioni OneDrive for Business e SharePoint Online invece di Microsoft Stream (classica)|
|Distribuzione a partire dal 7 gennaio 2021<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni Teams verranno salvate in OneDrive for Business e SharePoint Online, a meno che non si ritagli questa modifica modificando i criteri riunione Teams dell'organizzazione e impostandoli esplicitamente su **Flusso**. La visualizzazione dei report dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore del criterio su **Stream**.|
|Distribuzione a partire dall'11 gennaio 2021<br> *(Completa)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC solo**<br> Anche GCC i clienti possono rifiutare esplicitamente l'accesso a partire dal 5 ottobre, ma non è possibile acconsentire esplicitamente. Questa funzionalità verrà lanciata a tutti GCC clienti a partire dall'11 gennaio 2021, a meno che non si sia scelto di rifiutare esplicitamente l'opzione.<br>  <br>A partire dall'11 gennaio 2021, tutte le nuove registrazioni delle riunioni Teams per i clienti di GCC verranno salvate in OneDrive for Business e SharePoint Online, a meno che non si ritardi questa modifica modificando i criteri riunione Teams dell'organizzazione e impostandoli esplicitamente su **Flusso**. <br><br>Se si è scelto di rifiutare esplicitamente l'opzione ma si è pronti per attivare questa funzionalità, è possibile farlo impostando esplicitamente i criteri riunione di Teams su **OneDrive for Business**. |
|Distribuzione a partire dall'1 marzo 2021<br> *(Completa)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**GCC high e DoD**<br> I clienti possono ora abilitare le registrazioni delle riunioni nel cloud Microsoft Teams per la prima volta. Queste registrazioni verranno archiviate e riprodotte in OneDrive e SharePoint Online per impostazione predefinita. |
|Distribuzione a partire dal 7 luglio 2021<br> *(Completa)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br> Per una riunione di Teams registrata in OneDrive e SharePoint Online ed è stata anche trascritta in tempo reale durante la riunione, è ora possibile eseguire una ricerca in Microsoft Search per trovare il file di registrazione della riunione in base alla trascrizione. |
|Distribuzione incrementale a partire dal 16 agosto 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br>Non è possibile salvare nuove registrazioni delle riunioni in Microsoft Stream (classica); Tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for Business e SharePoint Online, anche se hanno modificato i criteri Teams riunione in Stream.<br><br> È consigliabile che i clienti, per controllare meglio la modifica all'interno dell'organizzazione, acconsentano esplicitamente ogni volta che si è a proprio agio con la modifica, invece di attendere che si ripeta. |

Microsoft Teams ha un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dal classico Microsoft Stream al nuovo [stream,](/stream/streamnew/new-stream)questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint Online in Microsoft 365 e offre molti vantaggi.

Lo stream (classico) come piattaforma non verrà deprecato nel prossimo futuro. I video attualmente in tempo reale in Stream (classico) rimarranno lì fino a quando non sarà disponibile uno strumento di migrazione futuro per spostarli in OneDrive e SharePoint Online. Per [altre informazioni sui piani futuri,](/stream/streamnew/classic-migration) vedere Eseguire la migrazione classica di Stream.

> [!NOTE]
> Se una registrazione Teams riunione non viene caricata correttamente in OneDrive/SharePoint Online, la registrazione verrà salvata temporaneamente in Servizi multimediali di Azure (AMS). Dopo l'archiviazione in AMS, non vengono effettuati tentativi per caricare automaticamente la registrazione in OneDrive/SharePoint Online o Stream.

Le registrazioni delle riunioni archiviate in AMS sono disponibili per 21 giorni prima di essere eliminate automaticamente. Gli utenti possono scaricare il video da AMS se devono conservarne una copia.

I vantaggi dell'uso di OneDrive for Business e SharePoint Online per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per Teams registrazione delle riunioni (TMR) (etichette di autoretenzione S+C E5)
- Trarre vantaggio dalla governance OneDrive for Business e SharePoint online
- Facile impostare le autorizzazioni e la condivisione
- Condividere registrazioni con utenti guest (utenti esterni) solo con condivisione esplicita
- Richiedi flusso di accesso
- Fornire OneDrive for Business e SharePoint condivisi online
- Le registrazioni delle riunioni sono disponibili più velocemente
- Trascrizione della base di ricerca registrata nella riunione
- **Passare al supporto tenant** locale
- Supporto multi-geo: le registrazioni vengono archiviate in un'area geografica specifica dell'utente
- Portare il proprio supporto per la chiave (BYOK)

Vedere l'elenco completo delle [funzionalità disponibili oggi e cosa aspettarsi nel corso del tempo.](/stream/streamnew/features-new-version-stream)

Per altre informazioni, vedere "Novità Microsoft Teams registrazioni delle riunioni".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Configurare l'opzione di registrazione della riunione per OneDrive for Business e SharePoint Online

L'opzione di registrazione della riunione è un'impostazione a Teams livello di criteri. L'esempio seguente mostra come impostare i criteri globali. Assicurarsi di impostare l'opzione di registrazione della riunione per i criteri assegnati agli utenti.

> [!Note]
> Teams la propagazione delle modifiche ai criteri delle riunioni può richiedere del tempo. Controllare di nuovo dopo alcune ore di impostazione, quindi disconnettersi e accedere di nuovo all'app desktop Teams o semplicemente riavviare il computer.

1. Installare Teams PowerShell di PowerShell.

   > [!NOTE]
   > Skype for Business Online Connector fa attualmente parte dell'Teams di PowerShell più recente. Se si usa la versione pubblica più recente Teams PowerShell, non è necessario installare Skype for Business Online Connector. Vedere [Gestire Skype for Business Online con PowerShell.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)

2. Avviare PowerShell come amministratore.

3. Installare [Teams modulo di PowerShell](./teams-powershell-install.md).

4. Importare il modulo MicrosoftTeams e accedere come Teams amministratore.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Usare [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per impostare criteri riunione Teams per la transizione dallo spazio di archiviazione stream a OneDrive for Business e SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se ad alcuni utenti è stato assegnato un criterio per organizzatore o per utente, è necessario impostare questa impostazione su questo criterio se si vuole che archivino anche le registrazioni delle riunioni in OneDrive for Business e SharePoint Online. Per altre informazioni, vedere [Gestire i criteri riunione in Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Altre informazioni

Per altre informazioni sulla registrazione Teams riunione nel cloud, vedere Teams [registrazione delle riunioni cloud.](cloud-recording.md) In questo articolo sono disponibili altre informazioni sulla registrazione della configurazione, della gestione, della governance, delle autorizzazioni e dello spazio di archiviazione.
