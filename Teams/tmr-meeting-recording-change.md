---
title: Usare OneDrive for business e SharePoint per le registrazioni delle riunioni
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come passare da Stream a OneDrive for business e a SharePoint Meeting recording storage in Microsoft teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea07079a94e2f76f8833e0854fd0161b4ff9ec09
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620711"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> La modifica dell'uso di Microsoft Stream in OneDrive for business e Microsoft SharePoint per le registrazioni delle riunioni sarà un approccio graduale.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 ottobre 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| È possibile abilitare il criterio riunione teams affinché le registrazioni delle riunioni vengano salvate in OneDrive for business e SharePoint anziché Microsoft Stream (classica)|
|Implementazione a partire dal 7 gennaio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Tutte le registrazioni delle riunioni delle nuove squadre verranno salvate in OneDrive for business e SharePoint a meno che non si ritardi la modifica modificando i criteri della riunione dei team dell'organizzazione e impostandone esplicitamente lo stato in **Stream**. La visualizzazione della segnalazione dei criteri come flusso non è sufficiente. Devi impostare in modo esplicito il valore dei criteri in **Stream**.|
|Implementazione a partire dal 11 gennaio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Solo GCC**<br> Mentre i clienti di GCC possono rinunciare a partire dal 5 ottobre, non si riesce ad accettare l'opt-in. Questa funzionalità verrà distribuita a tutti i clienti di GCC a partire dall'11 gennaio 2021, a meno che non sia stato scelto.<br>  <br>A partire dall'11 gennaio 2021, tutte le registrazioni delle riunioni delle nuove squadre per i clienti GCC verranno salvate in OneDrive for business e SharePoint, a meno che non si ritardi la modifica modificando i criteri di riunione dei team dell'organizzazione e impostandone esplicitamente lo stato in **Stream**. <br><br>Se l'opzione è stata disattivata, ma si è pronti per attivare questa funzionalità, è possibile impostare i criteri di riunione del team in modo esplicito in **OneDrive for business**. |
|Implementazione a partire dal 1 ° marzo 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clienti di Enterprise & GCC**<br>**Nessuna registrazione di una nuova riunione può essere salvata in Microsoft Stream (classica); tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for business e SharePoint anche se hanno modificato i criteri di riunione del team in Stream**.<br><br> È consigliabile che i clienti riproducano questa caratteristica prima di questa data in modo che possano controllare l'intervallo del rilascio. |
|Implementazione a partire dal 7 luglio 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clienti per l'istruzione**<br>**Nessuna registrazione di una nuova riunione può essere salvata in Microsoft Stream (classica); tutti i clienti avranno automaticamente le registrazioni delle riunioni salvate in OneDrive for business e SharePoint anche se hanno modificato i criteri di riunione del team in Stream**.<br><br> È consigliabile che i clienti riproducano questa caratteristica prima di questa data in modo che possano controllare l'intervallo del rilascio. Questa pianificazione è stata aggiornata per dare ai clienti dell'istruzione la possibilità di completare i semestri in corso. |

> [!Note]
> È consigliabile che i clienti aziendali e educativi, per controllare meglio la modifica dell'organizzazione, optino quando si è a proprio agio con la modifica invece di aspettare che avvenga.

Microsoft Teams ha un nuovo metodo per il salvataggio delle registrazioni delle riunioni. Come prima fase di una transizione da Microsoft Stream classico al [nuovo flusso](https://docs.microsoft.com/stream/streamnew/new-stream), questo metodo archivia le registrazioni in Microsoft OneDrive for business e SharePoint in Microsoft 365 e offre numerosi vantaggi.

I vantaggi derivanti dall'uso di OneDrive for business e SharePoint per l'archiviazione delle registrazioni includono:

- Criteri di conservazione per la registrazione di teams Meeting (TMR) (etichette di autoconservazione S + C E5)
- Vantaggi della governance delle informazioni di OneDrive for business e di SharePoint
- Facile impostare le autorizzazioni e la condivisione
- Condividere le registrazioni con Guest (utenti esterni) con solo condivisione esplicita
- Richiedi il flusso di accesso
- Fornisci collegamenti condivisi di OneDrive for business e SharePoint
- Quota aumentata
- Le registrazioni delle riunioni sono disponibili più rapidamente
- Supporto di **go local** tenant
- Supporto multi-geo: le registrazioni vengono archiviate in un'area specifica dell'utente
- Porta il tuo supporto Key (BYOK)
- Qualità della trascrizione migliorata e attribuzione del relatore

Ci sono alcune limitazioni da considerare:

- Ci saranno solo didascalie e trascrizioni chiuse in inglese.
- Non è possibile eseguire ricerche nelle trascrizioni o nel contenuto.
- Non sarà possibile modificare le trascrizioni, ma sarà possibile attivare o disattivare le didascalie.
- È possibile controllare con chi si condivide la registrazione, ma non sarà possibile bloccare le persone con accesso condiviso dal Download della registrazione.
- Non si riceverà un messaggio di posta elettronica quando la registrazione terminerà il salvataggio, ma la registrazione verrà visualizzata nella chat della riunione una volta terminato. Ciò avverrà molto più rapidamente di quanto abbia fatto in Stream in precedenza

Per altre informazioni, vedere "registrazione della riunione".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurare l'opzione di registrazione della riunione per OneDrive for business e SharePoint

L'opzione registrazione riunione è un'impostazione a livello di criteri teams. L'esempio seguente mostra come impostare il criterio globale. Verificare di aver impostato l'opzione di registrazione della riunione per i criteri o i criteri assegnati agli utenti.

> [!Note]
> Le modifiche ai criteri di riunione dei team richiedono un po' di propagazione. Dopo qualche ora di impostazione, eseguire il check-out e quindi effettuare di nuovo l'accesso.

1. Installare PowerShell per Skype for business online.
**Nota**: il connettore di Skype for business online fa attualmente parte del modulo di PowerShell più recente di teams. Se si usa l'ultima versione pubblica di PowerShell per Teams, non è necessario installare il connettore Skype for business online. Vedere [gestire Skype for business online con PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    a. Scaricare [PowerShell per Skype for business online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    b. Seguire le istruzioni per installarlo.

    c. Riavviare il computer.

2. Avviare PowerShell come amministratore

3. Importare il connettore SkypeOnline e accedere come amministratore di teams.

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Usare [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) per impostare un criterio riunione teams per la transizione dallo spazio di archiviazione del flusso a OneDrive for business e SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alcuni utenti hanno assegnato un criterio per ogni organizzazione o per utente, è necessario impostare questa impostazione su questo criterio se si vuole che vengano archiviate anche le registrazioni delle riunioni in OneDrive for business e SharePoint. Per altre informazioni, vedere [gestire i criteri di riunione in teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Rifiutare la disattivazione di OneDrive for business e SharePoint per continuare a usare Stream

Anche se un criterio indica che è impostato su **Stream**, potrebbe non essere impostato. In genere, se il criterio non è impostato, l'impostazione predefinita è **Stream**. Tuttavia, con questa nuova modifica, se si vuole rifiutare l'uso di SharePoint o OneDrive for business, è necessario reimpostare i criteri in **Stream** per assicurarsi che **Stream** sia l'impostazione predefinita.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli

> [!Note]
> È consigliabile che il destinatario sia un utente connesso quando si condividono le registrazioni delle riunioni di teams. Selezionare l'opzione **persone in (organizzazione)** quando si condivide il file come documentato in [condividere file o cartelle di SharePoint](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US). La condivisione esterna non è progettata per la distribuzione di file di grandi dimensioni o di un numero elevato di file. Per evitare scenari di frode e abuso, è possibile che si verifichino problemi durante la condivisione di una grande quantità di dati in utenti esterni.

|Tipo di riunione                               | Chi ha fatto clic su record?| Dove si trova la registrazione?                               |Chi ha accesso? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|chiamata 1:1 con le parti interne             |Chiamante                 |Account di OneDrive for business del chiamante                        |Il chiamante è proprietario e ha i diritti completi. <br /><br />Il chiamato (se nello stesso tenant) ha accesso di sola lettura. Nessun accesso alla condivisione. <br /><br /> Il chiamato (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|chiamata 1:1 con le parti interne             |Chiamato                 |Account di OneDrive for business del destinatario                        |Il chiamato è proprietario e ha i diritti completi. <br /><br />Chiamante (se lo stesso tenant ha accesso in sola lettura. Nessun accesso alla condivisione. <br /><br />Il chiamante (se in un tenant diverso) non ha accesso. Il chiamato deve condividerlo con il chiamante.|
|chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive for business del chiamante                        |Il chiamante è proprietario e ha i diritti completi.<br /> <br />Il chiamato non ha accesso. Il chiamante deve condividerlo con il chiamato.|
|chiamata 1:1 con una chiamata esterna             |Chiamato                 |Account di OneDrive for business del destinatario                        |Il chiamato è proprietario e ha i diritti completi.<br /><br />Il chiamante non ha accesso. Il chiamato deve condividerlo con il chiamante.|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Membro che ha fatto clic sull'account di OneDrive for business di record  |Il membro che ha fatto clic su record ha i diritti completi. <br /><br /> Altri membri dello stesso tenant hanno diritti di lettura. <br /><br /> Altri membri di un tenant diverso non hanno diritti.|
|Adhoc/riunione pianificata                    |Organizzatore              |Account di OneDrive for business dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione. <br /><br /> Tutti gli altri membri della riunione hanno accesso in lettura.|
|Adhoc/riunione pianificata                    |Altro membro della riunione   |Membro che ha fatto clic su record                                  |Il membro che ha fatto clic su record ha i diritti completi per la registrazione. <br /><br />L'organizzatore ha diritti di modifica e può condividere.<br /><br /> Tutti gli altri membri hanno accesso in lettura.|
|Adhoc/riunione pianificata con utenti esterni|Organizzatore              |Account di OneDrive for business dell'organizzatore                     |L'organizzatore ha i diritti completi per la registrazione.<br /> <br /> Tutti gli altri membri della riunione dello stesso tenant dell'Organizzatore hanno accesso in lettura. <br /><br /> Tutti gli altri membri esterni non hanno accesso e l'organizzatore deve condividerlo.|
|Adhoc/riunione pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su record                                  |Il membro che ha fatto clic su record ha i diritti completi per la registrazione. L'organizzatore ha diritti di modifica e può condividere. <br /><br /> Tutti gli altri membri della riunione dello stesso tenant dell'Organizzatore hanno accesso in lettura. <br /><br />Tutti gli altri membri esterni non hanno accesso e l'organizzatore deve condividerlo.|
|Riunione di canale                            |Membro del canale         |Percorso di SharePoint dei team per il canale                   |I membri che hanno fatto clic su record hanno diritti di modifica per la registrazione. <br /> <br />Le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint del canale.|

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata **registrazioni** al primo livello di OneDrive for business che appartiene alla persona che ha avviato la registrazione della riunione. Esempio

  <i>OneDrive for business</i> / del registratore **Registrazioni**

- Per le riunioni di canale, la registrazione viene archiviata nella raccolta documentazione sito teams in una cartella denominata **registrazioni**. Esempio

  <i>Nome teams-nome canale</i> / **Documenti** / **Registrazioni**

**Come si gestiscono le registrazioni da ex dipendenti?**

Dato che i video sono come qualsiasi altro file in OneDrive for business e SharePoint, la gestione della proprietà e la conservazione dopo il congedo da un dipendente seguirà il normale [processo di OneDrive for business e SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**Chi ha le autorizzazioni per visualizzare la registrazione delle riunioni?**

- Per le riunioni non di canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente. Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni di canale, le autorizzazioni vengono ereditate dall'elenco proprietari e membri nel canale.

**Come si gestiscono le trascrizioni?**

I clienti che optano per questa anteprima non avranno le didascalie chiuse disponibili nelle registrazioni delle riunioni del team che vengono migrate in OneDrive for business e SharePoint.Stiamo lavorando per aggiungere didascalie, a partire da didascalie chiuse in inglese, per le registrazioni delle riunioni in Q4 CY2020.

Le didascalie chiuse saranno disponibili nelle registrazioni delle riunioni di teams per i clienti che hanno scelto di consentire le trascrizioni come descritto in [Teams cloud Recordings](cloud-recording.md).

Le didascalie consentono di creare contenuti inclusivi per gli utenti di tutte le abilità. Come proprietario puoi nascondere le didascalie, anche se la trascrizione sarà ancora disponibile in teams a meno che tu non elimini le didascalie da teams. Vedere [come attivare o disattivare le registrazioni delle riunioni](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization).

Le didascalie chiuse sono supportate per le registrazioni delle riunioni di teams per 60 giorni dopo la registrazione della riunione.

Le didascalie chiuse non sono supportate completamente se la registrazione della riunione teams viene spostata o copiata dalla posizione originale in OneDrive for business o SharePoint.

**Come viene influenzata la quota di archiviazione?**

I team che partecipano a una riunione di file Live in OneDrive for business e SharePoint sono inclusi nella quota per tali servizi. Vedere quote di [SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for business](https://docs.microsoft.com/onedrive/set-default-storage-space).

Puoi ottenere più spazio di archiviazione con [OneDrive for business](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) rispetto a Stream e altro spazio di archiviazione fungibili con SharePoint.

**Come si gioca una registrazione di una riunione di Teams?**

Il video verrà riprodotto sul lettore video di OneDrive for business o SharePoint a seconda di dove si accede al file.

**Se si prevede di aggiungere al flusso deprecato, i video esistenti rimarranno così come sono e per quanto tempo?**

Il flusso come piattaforma non sarà deprecato nel prossimo futuro. I video che attualmente vivono in Stream rimarranno lì fino a quando non inizieremo a eseguire la migrazione. Dopo la migrazione, i video verranno migrati anche in OneDrive for business o in SharePoint. Per altre informazioni, controlla la [migrazione classica in Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) .

**Come si applica un'etichetta di conservazione?**

Vedere [come applicare automaticamente un'etichetta di conservazione](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings).

**Come si assegnano I criteri agli utenti di Microsoft teams e quali criteri hanno la precedenza?**

Vedere [quali criteri hanno la precedenza?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence)
