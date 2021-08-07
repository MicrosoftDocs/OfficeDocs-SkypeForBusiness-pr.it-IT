---
title: Gestire i componenti in tempo reale in Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come gestire i componenti in tempo reale in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd65370a000bac3d91ae8f3dbc07a121add62ec1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772737"
---
# <a name="manage-live-components-in-teams"></a>Gestire i componenti in tempo reale in Teams

I componenti in tempo reale Teams chat offrono un nuovo modo per ideare, creare e prendere decisioni insieme. Inviare un componente, ad esempio una tabella, un elenco attività o un paragrafo, in cui tutti gli utenti della chat possono modificare le modifiche in linea e vedere le modifiche non appena vengono apportate. Questo significa che puoi raccogliere idee e feedback dal tuo team tenendo meno riunioni e riducendo al minimo la necessità di lunghi thread di chat.

**È possibile eseguire più velocemente le attività insieme.** È possibile creare un'agenda, tenere traccia delle attività di un gruppo o prendere appunti collettivamente. Questi sono solo alcuni scenari semplificati con i componenti in tempo reale.

**Condividere componenti.** In questa versione è possibile condividere i componenti in tempo reale in Teams chat. I destinatari possono modificare da qualsiasi posizione e visualizzare immediatamente gli aggiornamenti, indipendentemente da dove sono state apportate le modifiche. Nelle versioni future, i componenti in tempo reale saranno supportati Teams note e canali delle riunioni, Outlook e infine in tutte Microsoft 365 applicazioni.

**Inizia in chat, crea da lì.** Ogni componente creato da Teams chat viene salvato automaticamente in un file in OneDrive. Quindi, potresti iniziare a collaborare in chat e poi passare al file, dove hai uno spazio visivo più ampio per la modifica e puoi aggiungere tutti i componenti che vuoi.

## <a name="clients-and-platforms"></a>Client e piattaforme

Disponibile nelle app Teams su Windows, Mac, Linux, iOS e Android.

A partire dall'inizio di settembre, i componenti in tempo reale saranno disponibili a livello globale. A fine settembre sarà disponibile per Government Community Cloud Mod (GCC).

## <a name="settings-management"></a>Impostazioni gestione

I componenti in tempo reale sono Microsoft Fluid Framework supportati in Microsoft 365 suite e controllati da SharePoint Online e non dall'Teams di amministrazione.

È necessaria la versione più recente del modulo [di PowerShell SharePoint Online](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) per abilitare o disabilitare tutte le esperienze fluide nel tenant Office 365 online. Microsoft Fluid Framework'impostazione predefinita è **ON** per tutti i tenant di rilascio mirati. Poiché i componenti in tempo reale sono progettati per la collaborazione, i componenti vengono sempre condivisi come modificabili da altri utenti, anche se il tenant è impostato per impostazione predefinita su sola visualizzazione per altri tipi di file. Per altre **informazioni,** vedere il collegamento Altre informazioni accanto all'impostazione.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Verificare se il Fluid Framework è abilitato tramite il cmdlet di PowerShell SharePoint Online

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Verificare se Fluid Framework è abilitato eseguendo il cmdlet Get-SPOTenant senza argomenti.

3. Verificare che il valore di IsFluidEnabled sia **true.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Abilitazione del Fluid Framework tramite il cmdlet di PowerShell SharePoint Online 

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Abilitare Fluid usando il cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   L'applicazione della modifica all'interno della tenancy sarà breve. 

La funzionalità sarà disponibile in Teams Windows Desktop, Mac, iOS, Android. Se questa opzione è abilitata, gli utenti visualizzano una nuova opzione per l'inserimento di componenti in tempo reale nell'esperienza di composizione del messaggio per questi client.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Disabilitazione Fluid Framework tramite il cmdlet di PowerShell SharePoint Online

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Disabilitare Fluid usando il cmdlet Set-SPOTenant Set-SPOTenant -IsFluidEnabled $false. 

   L'applicazione della modifica all'interno della tenancy sarà breve. 

Se è necessario abilitare di nuovo questa funzionalità, è possibile usare SharePoint cmdlet di PowerShell online.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitazioni note

- La creazione di una tabella o di un elenco attività come primo componente dopo il riavvio dell Teams app potrebbe richiedere del tempo aggiuntivo.

- Gli altri membri della chat riceveranno una notifica tramite posta elettronica quando vengono menzionati con un simbolo di @. Le notifiche at-mentions nel feed Teams attività saranno disponibili a breve.

- La ricerca di componenti in tempo reale Teams ricerca restituirà un collegamento al componente in office.com, non al messaggio di chat stesso.

- I componenti in tempo reale vengono disabilitati nelle chat federate e abilitati per le normali chat con un account Guest con Azure B2B.

- Anche se è possibile condividere un componente nei canali Teams e in altre app Microsoft 365, i destinatari ottengono un collegamento nella maggior parte delle posizioni al momento. La modifica in linea è pianificata per altre esperienze in futuro.

## <a name="storage-of-fluid-files"></a>Archiviazione di `.fluid` file

**Come `.fluid` vengono archiviati?**

I componenti in tempo reale creati in Teams sono supportati da `.fluid` un file archiviato nella cartella OneDrive for Business. Essere un file in OneDrive for Business significa che gli utenti possono creare, individuare e gestire facilmente i componenti attivi (file) come qualsiasi `.fluid` Office documento.

Gli utenti possono cercare contenuti nei `.fluid` file da Office.com e OneDrive for Business.
`.fluid` I file funzionano con caratteristiche di governance dei dati come eDiscovery, controllo, creazione di report e blocco legale.

`.fluid`i file verranno ora visualizzati in Office.com e OneDrive for Business, ad esempio nelle aree Recenti e Consigliate.
`.fluid`i file possono essere ripristinati alle versioni precedenti OneDrive for Business.

I partecipanti alla chat devono avere un account OneDrive per creare componenti in tempo reale. Senza un account OneDrive valido, i partecipanti alla chat potrebbero comunque essere in grado di collaborare a un componente creato da altri utenti che hanno un account OneDrive valido, ma non possono crearne uno personalizzato.

[Se](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) si sposta un file da OneDrive a un sito SharePoint, il caricamento del componente in tempo reale non viene Teams `.fluid` chat.

**Cosa succede se il proprietario del file lascia la società?**

[OneDrive criteri di conservazione](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) applicati ai file come ad `.fluid` altri contenuti creati dall'utente.

**Come vengono `.fluid` condivisi i file?**

I componenti in tempo reale possono essere inseriti Teams chat o copiati da una chat a un'altra. I componenti in tempo reale non sono ancora supportati nei canali. Per impostazione predefinita, vengono assegnate le autorizzazioni esistenti del tenant, ma gli utenti possono modificare le autorizzazioni prima dell'invio per assicurarsi che tutti possano accedere.

L'apertura di componenti Teams chat in Office.com offre funzionalità di condivisione nella parte superiore della finestra, in modo analogo alle opzioni di condivisione offerte per altri Office documenti.

**Cosa succede se `.fluid` un file viene danneggiato o danneggiato?**

Cronologia versioni consente di rivedere e copiare da versioni precedenti del file.

**Quali app possono aprire e modificare `.fluid` i file?**

`.fluid`I file possono essere aperti solo come collegamenti nel browser, ad esempio Office.com, e come componenti in tempo reale in Teams chat. Se scaricati, non possono essere riaperti senza prima caricarli di nuovo in OneDrive for Business o SharePoint Online.
