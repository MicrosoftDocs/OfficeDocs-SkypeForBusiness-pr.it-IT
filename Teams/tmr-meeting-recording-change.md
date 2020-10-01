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
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269640"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usare OneDrive for business e SharePoint o Stream per le registrazioni delle riunioni

> [!Note]
> Il passaggio dall’uso di Microsoft Stream all’uso di OneDrive for Business e SharePoint per le registrazioni delle riunioni avverrà in modo graduale. All'avvio, gli amministratori del tenant possono scegliere questa nuova opzione per il flusso di lavoro oggi e inizieranno a vedere le registrazioni caricate automaticamente in OneDrive for business e SharePoint nel 2020 ottobre. In novembre è necessario rifiutare l'opt-out se si vuole continuare a usare Stream e un po' di tempo all'inizio di 2021 è necessario che tutti i clienti usino OneDrive for business e SharePoint per le nuove registrazioni delle riunioni.

Microsoft Teams ha un nuovo metodo per il salvataggio delle registrazioni delle riunioni. Come partenza da Stream, il metodo usa Microsoft OneDrive e SharePoint in Microsoft 365 e offre numerosi vantaggi.

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

Anche se un criterio dice che è già impostato su **Stream**, potrebbe non essere impostato. Se è impostato su Nothing, il valore predefinito è Stream. Se si vuole rifiutare l'opt-out, è **necessario** reimpostare i criteri in **Stream** per assicurarsi che Stream sia l'impostazione predefinita.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove verrà archiviata la registrazione della riunione?**

- Per le riunioni non di canale, la registrazione viene archiviata in una cartella denominata. Registrazioni * * che si trova al primo livello del OneDrive che appartiene alla persona che ha avviato la registrazione della riunione. Esempio

  <i>OneDrive for business</i> / del registratore **Registrazioni**

- Per le riunioni di canale, la registrazione viene archiviata nella raccolta documentazione sito teams in una cartella denominata **registrazioni**. Esempio

  <i>Nome teams-nome canale</i> / **Documenti** / **Registrazioni**

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