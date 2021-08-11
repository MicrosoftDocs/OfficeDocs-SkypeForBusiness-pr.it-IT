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
description: Scopri come gestire i componenti in tempo reale in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305018"
---
# <a name="manage-live-components-in-teams"></a>Gestire i componenti in tempo reale in Teams

I componenti in Teams chat offrono un nuovo modo per ideare, creare e prendere decisioni insieme. Invia un componente, ad esempio una tabella, un elenco attività o un paragrafo, in cui tutti gli utenti della chat possono modificare le modifiche in linea e visualizzare le modifiche non appena vengono apportate. Ciò significa che è possibile raccogliere idee e feedback dal team mantenendo un numero minore di riunioni e riducendo al minimo la necessità di lunghi thread di chat.

**Eseguire le attività più velocemente insieme.** Creare una crowd-source per un'agenda, tenere traccia delle azioni di un gruppo o prendere appunti collettivamente. Questi sono solo alcuni scenari semplificati con i componenti in tempo reale.

**Condividere componenti.** In questa versione, è possibile condividere i componenti in tempo reale in Teams chat. I destinatari possono modificare da qualsiasi posizione e visualizzare immediatamente gli aggiornamenti, indipendentemente da dove sono state apportate le modifiche. Nelle versioni future, i componenti in tempo reale saranno supportati in Teams note e canali delle riunioni, Outlook e infine in tutte Microsoft 365 applicazioni.

**Inizia in chat, crea da qui.** Ogni componente creato da Teams chat viene salvato automaticamente in un file in OneDrive. Quindi, potresti iniziare a collaborare in chat e poi passare al file, dove hai uno spazio visivo più ampio per la modifica e puoi aggiungere tutti i componenti che vuoi.

## <a name="clients-and-platforms"></a>Client e piattaforme

Disponibile nelle app Teams su Windows, Mac, Linux, iOS e Android.

A partire dai primi di settembre, i componenti in tempo reale saranno disponibili a livello globale. A fine settembre sarà disponibile per Government Community Cloud Mod (GCC).

## <a name="settings-management"></a>Impostazioni gestione

I componenti live sono creati con Microsoft Fluid Framework supportati Microsoft 365 suite e controllati da SharePoint Online e non dall'Teams di amministrazione.

Per abilitare o disabilitare tutte le esperienze fluide nel tenant SharePoint online, è necessaria la versione più recente Office 365 SharePoint [PowerShell.](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) Microsoft Fluid Framework il valore predefinito è **ON** per tutti i tenant di rilascio di destinazione. Poiché i componenti live sono progettati per la collaborazione, i componenti vengono sempre condivisi come modificabili da altri utenti, anche se il tenant è impostato come predefinito per la sola visualizzazione per altri tipi di file. Per altri **dettagli,** vedi il collegamento Altre informazioni accanto all'impostazione.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Verifica se il Fluid Framework è abilitato tramite il cmdlet powershell SharePoint Online

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Verificare se Fluid Framework è abilitato eseguendo il cmdlet Get-SPOTenant senza argomenti.

3. Verificare che il valore di IsFluidEnabled sia **true.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Abilitazione del Fluid Framework tramite il cmdlet powershell SharePoint Online 

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Abilitare Fluid utilizzando il cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   La modifica avrà un breve periodo di tempo per essere applicata alla tenancy. 

La funzionalità sarà disponibile in Teams Windows Desktop, Mac, iOS, Android. Se abilitati, gli utenti visualizzano una nuova opzione per l'inserimento di componenti attivi nell'esperienza di composizione del messaggio per questi client.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Disabilitazione Fluid Framework tramite il cmdlet powershell SharePoint Online

1. [Connessione per SharePoint PowerShell online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Disabilitare Fluid utilizzando Set-SPOTenant cmdlet Set-SPOTenant -IsFluidEnabled $false. 

   La modifica avrà un breve periodo di tempo per essere applicata alla tenancy. 

Se è necessario abilitare di nuovo questa funzionalità, è possibile usare i cmdlet di PowerShell SharePoint Online.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitazioni note

- La creazione di una tabella o di un elenco attività come primo componente dopo il riavvio dell Teams app potrebbe richiedere più tempo.

- Gli altri membri della chat riceveranno una notifica tramite posta elettronica quando vengono menzionati con il simbolo at (@). Le notifiche di menzione nel feed Teams attività saranno disponibili a breve.

- La ricerca di componenti in tempo reale Teams ricerca restituirà un collegamento al componente in office.com, non al messaggio di chat stesso.

- I componenti live sono disabilitati nelle chat federate e abilitati per le chat regolari con un account Guest con Azure B2B.

- Anche se puoi condividere un componente nei canali Teams e in altre app Microsoft 365, i destinatari ottengono un collegamento nella maggior parte delle posizioni in questo momento. La modifica in linea è pianificata per altre esperienze in futuro.

## <a name="storage-of-fluid-files"></a>Archiviazione di `.fluid` file

**Come `.fluid` vengono archiviati?**

I componenti live creati in Teams sono supportati da un file archiviato nella cartella `.fluid` OneDrive for Business. Essere un file in OneDrive for Business significa che gli utenti possono creare, individuare e gestire i componenti attivi (file) con la facilità di qualsiasi `.fluid` Office documento.

Gli utenti possono cercare contenuto nei `.fluid` file da Office.com e OneDrive for Business.
`.fluid` i file funzionano con funzionalità di governance dei dati come eDiscovery, controllo, creazione di report e conservazione legale.

`.fluid`i file verranno ora visualizzati in Office.com e OneDrive for Business, ad esempio nelle aree Recenti e Consigliate.
`.fluid`i file possono essere ripristinati nelle versioni precedenti da OneDrive for Business.

I partecipanti alla chat devono disporre di un account OneDrive per creare componenti in tempo reale. Senza un account OneDrive valido, i partecipanti alla chat potrebbero comunque essere in grado di collaborare su un componente creato da altri utenti che dispongono di un account OneDrive valido, ma che non possono crearne di propri.

[Lo](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) spostamento di un file da OneDrive a un sito SharePoint comporterà il mancato caricamento del componente in tempo reale `.fluid` nella chat Teams chat.

**Cosa succede se il proprietario del file lascia la società?**

[OneDrive criteri di conservazione](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) si applicano ai file come per altri `.fluid` contenuti creati dall'utente.

**Come vengono `.fluid` condivisi i file?**

I componenti live possono essere inseriti Teams chat o copiati da una chat all'altra. I componenti live non sono ancora supportati nei canali. Per impostazione predefinita, vengono assegnate le autorizzazioni esistenti del tenant, ma gli utenti possono modificare le autorizzazioni prima dell'invio per garantire che tutti gli utenti possano accedervi.

L'apertura di componenti da Teams chat in Office.com offre funzionalità di condivisione nella parte superiore della finestra, in modo analogo alle opzioni di condivisione offerte per altri Office documenti.

**Cosa succede se `.fluid` un file viene danneggiato o danneggiato?**

Cronologia versioni consente di esaminare e copiare da versioni precedenti del file.

**Quali app possono aprire e modificare `.fluid` i file?**

`.fluid`i file possono essere aperti solo come collegamenti nel browser, ad esempio Office.com e come componenti in tempo reale in Teams chat. Se scaricati, non possono essere riaperti senza prima caricarli in OneDrive for Business o SharePoint Online.
