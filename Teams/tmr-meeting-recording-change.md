---
title: Usare OneDrive for Business e SharePoint per le registrazioni delle riunioni
author: CarolynRowe
ms.author: crowe
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for Business e allo spazio di archiviazione per la registrazione delle riunioni di SharePoint in Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc315353e1ece0b4d455937c1677e35e3c18d152
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794154"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for Business e SharePoint o Stream per le registrazioni delle riunioni

> [!NOTE]
> La modifica dell'archiviazione delle registrazioni delle riunioni di Teams da Classic Stream a OneDrive e SharePoint (ODSP) è stata completata a partire dal 30 agosto 2021. Tutte le registrazioni sono ora archiviate in ODSP. Questa modifica sostituisce il criterio RecordingStorageMode e la modifica dell'impostazione in PowerShell non ha più alcun impatto.

|Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 ottobre 2020<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| È possibile abilitare i criteri riunione di Teams in modo che le registrazioni delle riunioni siano salvate in OneDrive for Business e SharePoint invece di Microsoft Stream (versione classica)|
|Implementazione a partire dal giorno 7 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le nuove registrazioni delle riunioni di Teams verranno salvate in OneDrive for Business e SharePoint a meno che questa modifica non venga ritardata modificando i criteri delle riunioni di Teams dell'organizzazione e impostandole esplicitamente su **Stream**. La visualizzazione dei report dei criteri come Stream non è sufficiente. È necessario impostare in modo esplicito il valore dei criteri su **Stream**.|
|Implementazione a partire dal giorno 11 gennaio 2021<br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Anche se i clienti GCC possono rifiutare esplicitamente tale opzione, a partire dal 5 ottobre, non è possibile acconsentire esplicitamente. Questa funzionalità verrà distribuita a tutti i clienti GCC a partire dall'11 gennaio 2021, a meno che non sia stata rifiutata esplicitamente.<br>  <br>A partire dall'11 gennaio 2021, tutte le nuove registrazioni delle riunioni di Teams per i clienti GCC verranno salvate in OneDrive for Business e SharePoint a meno che questa modifica non venga ritardata modificando i criteri delle riunioni di Teams dell'organizzazione e impostandoli esplicitamente su **Stream**. <br><br>Se tale funzionalità è stata rifiutata esplicitamente, ma si vuole attivarla, è possibile impostare i criteri delle riunioni di Teams in modo esplicito su **OneDrive for Business**. |
|Implementazione a partire dal giorno 1 marzo 2021<br> *(Completata)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC-High e DoD**<br> I clienti ora possono abilitare le registrazioni delle riunioni cloud in Microsoft Teams per la prima volta. Queste registrazioni verranno archiviate e riprodotte in OneDrive e SharePoint per impostazione predefinita. |
|Implementazione incrementale a partire dal giorno 16 agosto 2021 <br> *(Completata)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Tutti i clienti (Enterprise, Education e GCC)**<br>Non è possibile salvare registrazioni di nuove riunioni in Microsoft Stream (versione classica); tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for Business e SharePoint anche se hanno modificato i criteri delle riunioni di Teams in Stream.<br><br> È consigliabile che i clienti, in modo da controllare meglio il cambiamento nell'organizzazione, acconsentano esplicitamente ogni volta che si ha familiarità con la modifica anziché attendere che venga eseguita. |

Microsoft Teams offre un nuovo metodo per salvare le registrazioni delle riunioni. Come prima fase di una transizione dalla Microsoft Stream classica al [nuovo Stream](/stream/streamnew/new-stream), questo metodo archivia le registrazioni in Microsoft OneDrive for Business e SharePoint in Microsoft 365 e offre numerosi vantaggi.

> [!NOTE]
> Se la registrazione di una riunione di Teams non viene caricata correttamente in OneDrive/SharePoint, verrà visualizzato un messaggio di errore "La registrazione è terminata in modo imprevisto" e la registrazione verrà invece salvata temporaneamente in Servizi multimediali di Azure (AMS). Una volta archiviata in AMS, non vengono eseguiti tentativi di caricamento automatico della registrazione in OneDrive/SharePoint o Stream.

Le registrazioni delle riunioni archiviate in AMS sono disponibili per 21 giorni prima che vengano eliminate automaticamente. Gli utenti possono scaricare il video da AMS se devono conservarne una copia.

I vantaggi dell'uso di OneDrive for Business e SharePoint per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per la registrazione delle riunioni di Teams (TMR) (etichette di autoretenzione S+C E5)
- Trarre vantaggio dalla governance delle informazioni di OneDrive for Business e SharePoint
- Autorizzazioni e condivisioni facili da impostare
- Condividere registrazioni con gli utenti guest (utenti esterni) solo con condivisione esplicita
- Richiedere flusso di accesso
- Fornire collegamenti condivisi OneDrive for Business e SharePoint
- Le registrazioni delle riunioni sono disponibili più velocemente
- Supporto del tenant in **locale**
- Supporto multi-geografico: le registrazioni vengono archiviate in un'area specifica dell'utente
- Supporto BYOK (Bring Your Own Key)

Consultare l'elenco completo delle [funzionalità disponibili oggi e nel tempo](/stream/streamnew/features-new-version-stream).

Per altre informazioni, guardare il video "What's New for Microsoft Teams Meeting Recordings".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Impostare l'opzione di registrazione della riunione per OneDrive for Business e SharePoint

L'opzione di registrazione della riunione è un'impostazione a livello di criteri di Teams. Nell'esempio seguente viene illustrato come impostare il criterio globale. Assicurarsi di impostare l'opzione di registrazione delle riunioni per il criterio o i criteri assegnati agli utenti.

> [!Note]
> La propagazione delle modifiche ai criteri delle riunioni di Teams richiede qualche tempo. È necessario ricontrollare dopo alcune ore dall'impostazione, quindi disconnettersi e accedere di nuovo all'applicazione desktop di Teams o riavviare semplicemente il computer.

1. Installa Teams PowerShell.

   > [!NOTE]
   > Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente. Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online. Vedere [Gestire Skype for Business Online con PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Avviare PowerShell come amministratore.

3. Installare il [modulo di PowerShell per Teams](./teams-powershell-install.md).

4. Importare il modulo di Microsoft Teams e accedere come amministratore di Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. Usa [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) per impostare un criterio riunione di Teams per la transizione dall'archiviazione di Stream a OneDrive for Business e SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se ad alcuni utenti è stato assegnato un criterio per organizzatore o per utente, è necessario impostare questa impostazione per questo criterio se si vuole che le registrazioni delle riunioni vengano archiviate anche in OneDrive for Business e SharePoint. Per altre informazioni, vedere [Gestire i criteri di riunione in Teams](meeting-policies-overview.md).


## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli

> [!Note]
> È consigliabile che il destinatario sia un utente connesso quando condivide le registrazioni delle riunioni di Teams. Selezionare l'opzione **Persone in (L'organizzazione)** quando si condivide il file come documentato in [SharePoint file o cartelle](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US). La condivisione esterna non è progettata per la distribuzione di file di grandi dimensioni o di un numero elevato di file. Per evitare scenari di frode e abuso, potrebbero verificarsi problemi durante la condivisione di una grande quantità di dati con utenti esterni.

|Tipo di riunione                               | Chi ha fatto clic su Registra?| Dove viene salvata la registrazione?                               |Chi può accedere? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chiamata 1:1 con parti interne             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi. <br /><br />Il destinatario della chiamata (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br /> Il destinatario della chiamata (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con parti interne             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi. <br /><br />Il chiamante (se nello stesso tenant) ha accesso in sola lettura. Nessun accesso di condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive for Business del chiamante                        |Il chiamante è proprietario e ha i diritti completi.<br /> <br />Il destinatario della chiamata non ha accesso. Il chiamante deve condividerlo con il destinatario della chiamata.|
|Chiamata 1:1 con una chiamata esterna             |Destinatario della chiamata                 |Account di OneDrive for Business del destinatario della chiamata                        |Il destinatario della chiamata è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha accesso. Il destinatario della chiamata deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Account di OneDrive for Business del membro del gruppo che ha fatto clic su Registra  |Il membro che ha fatto clic su Registra ha diritti completi. <br /><br /> Gli altri membri del gruppo dallo stesso tenant hanno diritti di lettura. <br /><br /> Gli altri membri del gruppo di un tenant diverso non hanno alcun diritto.|
|Riunione ad hoc/pianificata                    |Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione ad hoc/pianificata                    |Altro membro della riunione   |Membro della riunione che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Riunione ad hoc/pianificata con utenti esterni|Organizzatore              |Account di OneDrive for Business dell’organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione ad hoc/pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su Registra                                  |Il membro che ha fatto clic su Registra ha diritti completi sulla registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione dallo stesso tenant dell'organizzatore hanno accesso in lettura. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'Organizzatore deve condividerlo con loro.|
|Riunione di canale                            |Membro del canale         |Posizione di Teams sharepoint per quel canale. **Nota**: il caricamento della registrazione di riunioni di canale in SharePoint non è supportato per restrizioni basate su IP. È [consigliabile usare l'accesso condizionale di Azure](/azure/active-directory/conditional-access/overview). |Il membro che ha fatto clic su Registra ha diritti di modifica per la registrazione. <br /> <br />Le autorizzazioni di ogni altro membro si basano sulle autorizzazioni di SharePoint per canale.|

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata **Registrazioni** al livello principale del OneDrive for Business che appartiene alla persona che ha avviato la registrazione della riunione. Esempio:

  OneDrive for Business /**Recordings** <i>del registratore</i>

- Per le riunioni del canale, la registrazione viene archiviata nella raccolta della documentazione del sito di Teams in una cartella denominata **Registrazioni**. Esempio:

  <i>Nome di Teams - Nome canale</i>/ **Documenti**/ **Registrazioni**

**Quando i file di Stream (ad esempio le registrazioni) vengono archiviati in SharePoint/OneDrive, come si decide dove andare? L'amministratore ha la possibilità di cambiare la posizione in cui si trova?**

Per impostazione predefinita, tutti i file di registrazione passeranno all'account OneDrive dell'utente che ha selezionato **Registra**. Per le riunioni del canale, la registrazione verrà sempre indirizzata al sito di SharePoint del canale. L'amministratore non può modificare la posizione in cui è archiviata la registrazione.

**Ricerca per categorie gestire le registrazioni di ex dipendenti?**

Poiché i video sono come qualsiasi altro file in OneDrive for Business e SharePoint, la gestione della proprietà e della conservazione dopo l'uscita di un dipendente seguirà il normale [processo di OneDrive for Business e SharePoint](/onedrive/retention-and-deletion).

**Chi ha le autorizzazioni per visualizzare la registrazione della riunione?**

- Per le riunioni non di canale, tutti gli invitati alla riunione, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente. Gli utenti esterni dovranno essere aggiunti in modo esplicito all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni di Canale, le autorizzazioni vengono ereditate dall'elenco dei proprietari e dei membri del canale.

> [!NOTE]
> Al termine del salvataggio, non riceverai un messaggio e-mail, ma la registrazione verrà visualizzata nella chat della riunione al termine. Questo problema si verificherà molto più velocemente rispetto a quanto fatto in Stream in precedenza.

**Come si gestiscono i sottotitoli?**

I sottotitoli codificati per le registrazioni delle riunioni di Teams saranno disponibili durante la riproduzione solo se l'utente ha attivato la trascrizione al momento della registrazione. Gli amministratori devono [attivare la trascrizione della registrazione](meetings-policies-recording-and-transcription.md#allow-transcription) per assicurarsi che gli utenti abbiano la possibilità di registrare le riunioni con la trascrizione.

I sottotitoli consentono di creare contenuto inclusivo per i visualizzatori di tutte le capacità. In qualità di proprietario, è possibile nascondere i sottotitoli nella registrazione della riunione, anche se la trascrizione della riunione sarà ancora disponibile in Teams, a meno che non venga eliminata.

I sottotitoli codificati sono supportati per le registrazioni delle riunioni di Teams per 60 giorni dalla registrazione della riunione.

I sottotitoli non sono completamente supportati se la registrazione delle riunioni di Teams viene spostata o copiata dalla posizione originale in OneDrive for Business o SharePoint.

> [!NOTE]
> Saranno presenti sottotitoli codificati solo in inglese (la trascrizione della riunione non è ancora disponibile in GCC).

**Qual è l'impatto sulla quota di archiviazione?**

I file di registrazione delle riunioni di Teams risiedono in OneDrive for Business e SharePoint e sono inclusi nella quota per tali servizi. Vedere [Quota di SharePoint](/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for Business](/onedrive/set-default-storage-space).

Si ottiene più spazio di archiviazione con [OneDrive for Business](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) rispetto a Stream e più spazio di archiviazione fungibile con SharePoint.

**Come si riproduce la registrazione di una riunione di Teams?**

Il video verrà riprodotto nel lettore video di OneDrive for Business o SharePoint a seconda di dove si accede al file.

**Se prevedi di deprecare l'aggiunta a Stream, i video esistenti rimarranno così com'sono e per quanto tempo?**

Lo stream come piattaforma non verrà deprecato nel prossimo futuro. I video attualmente disponibili in Stream rimarranno disponibili fino a quando non inizieremo la migrazione. Dopo la migrazione, questi video verranno migrati anche a OneDrive for Business o SharePoint. Per altre informazioni, vedere [Dettagli sulla migrazione](/stream/streamnew/migration-details) .

**Ricerca per categorie applicare un'etichetta di conservazione alle registrazioni delle riunioni di Microsoft Teams?**

Vedere [Come applicare automaticamente un'etichetta di conservazione](/microsoft-365/compliance/apply-retention-labels-automatically).

**Ricerca per categorie assegnare criteri agli utenti in Microsoft Teams e quali criteri hanno la precedenza?**

Vedere [Quali criteri hanno la precedenza?](./policy-assignment-overview.md#which-policy-takes-precedence).

**Dove va la registrazione se l'utente non ha OneDrive for Business o SharePoint o se la quota di archiviazione è piena?**

La registrazione atterra nella nostra posizione di archiviazione temporanea, dove si terrà per 21 giorni. Durante tale periodo, l'organizzatore deve scaricare la registrazione. Se non viene scaricata entro 21 giorni, la registrazione viene eliminata.
