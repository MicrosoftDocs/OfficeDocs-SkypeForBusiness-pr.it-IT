---
title: Usare OneDrive e SharePoint per le registrazioni delle riunioni
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 624dcb4f99bc8ae2b83a1b8f62917ac0a5701888
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486771"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> La modifica dell'uso di Microsoft Stream in OneDrive for business e Microsoft SharePoint per le registrazioni delle riunioni sarà un approccio graduale.


|Data|Evento|
|---|-----------------|
|Inizio Q4 CY20|**Registrazione delle riunioni di teams in OneDrive for business e SharePoint disponibile per opt-in o opt-out.**<br> Gli amministratori del tenant possono optare o rifiutare la disattivazione di OneDrive for business e SharePoint impostando il criterio teams in PowerShell|
|Mid Q4 CY20|**Registrazione delle riunioni di teams in OneDrive for business e SharePoint impostato come predefinito per i tenant che non si dissociano**<br> Questo è il percorso consigliato per la maggior parte dei clienti|
|Q1 CY21|**Salvataggio della registrazione delle riunioni di teams in Stream classico non più consentito**<br>Tutti i tenant salveranno la registrazione delle riunioni di teams in OneDrive for business e SharePoint|


Microsoft Teams ha un nuovo metodo per il salvataggio delle registrazioni delle riunioni. Come prima fase di una transizione da Microsoft Stream classico al [nuovo flusso](https://docs.microsoft.com/stream/streamnew/new-stream), questo metodo archivia le registrazioni in Microsoft OneDrive e SharePoint in Microsoft 365 e offre numerosi vantaggi.

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

1. Installare la console di amministrazione di PowerShell per Skype for business online.

    a. Scaricare [PowerShell per Skype for business online](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).

    b. Seguire le istruzioni per installarlo.

    c. Riavviare il computer.

2. Avviare PowerShell come amministratore

3. Importare il connettore SkypeOnline e accedere come amministratore di teams.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. Usare [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per impostare un criterio per la riunione di teams in transizione dallo spazio di archiviazione del flusso a ODSP.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Rifiutare la disattivazione di OneDrive for business e SharePoint per continuare a usare Stream

Anche se un criterio indica che è impostato su **Stream**, potrebbe non essere impostato. In genere, se il criterio non è impostato, l'impostazione predefinita è **Stream**. Tuttavia, con questa nuova modifica, se si vuole rifiutare l'uso di SharePoint o OneDrive, è necessario reimpostare i criteri in **Stream** per assicurarsi che sia l'impostazione predefinita.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Autorizzazioni o accesso basato sui ruoli


|Tipo di riunione                               | Chi ha fatto clic su record?| Dove si trova la registrazione?                               |Chi ha accesso? R/W, R o condivisione                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|chiamata 1:1 con le parti interne             |Chiamante                 |Account di OneDrive for business del chiamante                        |-Il chiamante è proprietario, ha i diritti completi-chiamato (se nello stesso tenant) ha accesso di sola lettura, nessun accesso di condivisione-chiamato (se in un tenant diverso) non ha accesso. Il chiamante deve condividerlo con il chiamato|
|chiamata 1:1 con le parti interne             |Chiamato                 |Account di OneDrive for business del destinatario                        |-Callee è proprietario, ha i diritti completi-chiamante (se nello stesso tenant ha accesso di sola lettura, nessun accesso alla condivisione-chiamante (se in un tenant diverso) non ha accesso. Il chiamato deve condividerlo con il chiamato|
|chiamata 1:1 con una chiamata esterna             |Chiamante                 |Account di OneDrive for business del chiamante                        |-Il chiamante è proprietario, ha i diritti completi-il chiamato non ha accesso. Il chiamante deve condividerlo con il chiamato|
|chiamata 1:1 con una chiamata esterna             |Chiamato                 |Account di OneDrive for business del chiamante                        |-Callee è proprietario, ha i diritti completi-il chiamante non ha accesso. Il chiamante deve condividerlo con il chiamante|
|Chiamata di gruppo                                 |Qualsiasi membro della chiamata |Membro che ha fatto clic sull'account di OneDrive for business di record  |-I membri che hanno fatto clic su record hanno diritti completi-altri membri dello stesso tenant hanno diritti di lettura-altri membri per i diversi utenti non hanno diritti.|
|Adhoc/riunione pianificata                    |Organizzatore              |Account di OneDrive for business dell'organizzatore                     |-L'organizzatore ha diritti completi per la registrazione-tutti gli altri membri della riunione hanno accesso in lettura|
|Adhoc/riunione pianificata                    |Altro membro della riunione   |Membro che ha fatto clic su record                                  |-Il membro che ha fatto clic su record ha i diritti completi per la registrazione-l'organizzatore ha diritti di modifica e può condividere-tutti gli altri membri hanno accesso in lettura|
|Adhoc/riunione pianificata con utenti esterni|Organizzatore              |Account di OneDrive for business dell'organizzatore                     |-L'organizzatore ha i diritti completi per la registrazione-tutti gli altri membri della riunione dello stesso tenant dell'Organizzatore hanno accesso in lettura-tutti gli altri membri esterni non hanno accesso e l'organizzatore deve condividerlo con loro|
|Adhoc/riunione pianificata con utenti esterni|Altro membro della riunione   |Membro che ha fatto clic su record                                  |-Il membro che ha fatto clic su record ha i diritti completi per l'organizzatore della registrazione ha diritti di modifica e può condividere-tutti gli altri membri della riunione dello stesso tenant dell'Organizzatore hanno accesso in lettura-tutti gli altri membri esterni non hanno accesso e l'organizzatore deve condividerlo|
|Riunione di canale                            |Membro del canale         |Percorso di SharePoint dei team per il canale                   |-I membri che hanno fatto clic su record hanno diritti di modifica per la registrazione: le autorizzazioni di ogni altro membro sono basate sulle autorizzazioni di SharePoint del canale|


## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata **registrazioni** che si trova al primo livello di OneDrive che appartiene alla persona che ha avviato la registrazione della riunione. Esempio

  <i>OneDrive for business</i> / del registratore **Registrazioni**

- Per le riunioni di canale, la registrazione viene archiviata nella raccolta documentazione sito teams in una cartella denominata **registrazioni**. Esempio

  <i>Nome teams-nome canale</i> / **Documenti** / **Registrazioni**

**Come si gestiscono le registrazioni da ex dipendenti?**

Dato che i video sono come qualsiasi altro file in OneDrive e SharePoint, la gestione della proprietà e la conservazione dopo il congedo da parte di un dipendente seguirà il normale [processo di OneDrive e SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

**Chi ha le autorizzazioni per visualizzare la registrazione delle riunioni?**

- Per le riunioni non di canale, tutti gli invitati alle riunioni, ad eccezione degli utenti esterni, riceveranno automaticamente un collegamento condiviso personalmente. Gli utenti esterni dovranno essere aggiunti esplicitamente all'elenco condiviso dall'organizzatore della riunione o dalla persona che ha avviato la registrazione della riunione.

- Per le riunioni di canale, le autorizzazioni vengono ereditate dall'elenco proprietari e membri nel canale.

**Come si gestiscono le trascrizioni?**

I clienti che optano per questa anteprima non avranno le didascalie chiuse disponibili nelle registrazioni delle riunioni del team migrate in OneDrive e SharePoint.Stiamo lavorando per aggiungere didascalie, a partire da didascalie chiuse in inglese, per la riunione delle registrazioni in ottobre 2020.

Le didascalie chiuse saranno disponibili nelle registrazioni delle riunioni di teams per i clienti che hanno scelto di consentire le trascrizioni come descritto in [Teams cloud Recordings](cloud-recording.md)

Le didascalie consentono di creare contenuti inclusivi per gli utenti di tutte le abilità. Come proprietario puoi nascondere le didascalie, anche se la trascrizione sarà ancora disponibile in teams a meno che tu non elimini le didascalie da teams. Vedere [come attivare o disattivare le registrazioni delle riunioni](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

Le didascalie chiuse sono supportate per le registrazioni delle riunioni di teams per 60 giorni dopo la registrazione della riunione.

**Come viene influenzata la quota di archiviazione**

I team che partecipano a una riunione di file Live in OneDrive for business e SharePoint sono inclusi nella quota per tali servizi. Vedere [quota di SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [quota di OneDrive for business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**Come si gioca una registrazione di una riunione di Teams?**

Il video verrà riprodotto sul lettore video di OneDrive for business o SharePoint a seconda di dove si accede al file.

**Se si prevede di aggiungere al flusso deprecato, i video esistenti rimarranno così come sono e per quanto tempo?**

Il flusso come piattaforma non sarà deprecato nel prossimo futuro. I video che attualmente vivono in Stream rimarranno lì fino a quando non inizieremo a eseguire la migrazione. Dopo la migrazione, anche questi video verranno migrati in ODSP. Per altre informazioni, vedere [qui](https://docs.microsoft.com/stream/streamnew/classic-migration) .
