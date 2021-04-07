---
title: Usare NDI in Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare NDI in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598465"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Usare la tecnologia NDI® in Microsoft Teams

 La tecnologia NewTek NDI® (Network Device Interface) è una soluzione moderna per la connessione di dispositivi multimediali , ad esempio una fotocamera da studio e un mixer. Invece di usare connessioni fisiche, la tecnologia NDI® consente la connettività su una Intranet locale, anche in un computer locale.

La tecnologia NDI® è diventata una soluzione di settore standard per la produzione di contenuti live per i flussi e ha acquisito una notevole consapevolezza e adozione nel mondo della trasmissione professionale.

Skype ha aggiunto in ® funzionalità NDI a Skype alla fine del 2018. Microsoft Teams usa questa funzionalità per migliorare l'esperienza della riunione.

La tecnologia NDI® è limitata a una rete locale e deve essere considerata solo una parte del flusso di lavoro di produzione, non una soluzione broadcast.

## <a name="turn-on-ndi-technology"></a>Attivare la tecnologia NDI®

La tecnologia NDI® richiede due passaggi per essere attivata per un utente.

1. L'amministratore del tenant deve abilitare la proprietà 'AllowNDIStreaming' in CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Dopo aver popolato questa modifica, l'utente finale deve attivare la tecnologia NDI® per il proprio client specifico da **Autorizzazioni**  >  **impostazioni.**

Quando un utente partecipa a una riunione, viene visualizzato un messaggio che informa che la riunione è in fase di trasmissione. Se gli utenti non vogliono essere inclusi nella trasmissione, dovranno rilasciare dalla riunione.

L'immagine seguente mostra il messaggio banner visualizzato da un utente in una riunione di Teams.

![striscione ® tecnologia NDI che viene visualizzato in una riunione di Teams.](media/NDI-disclosure.png)

Il banner contiene un collegamento [all'informativa sulla privacy Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® viene attivato solo per sessione. All'accesso successivo, l'utente deve attivarlo prima di usare NDI®.

## <a name="supported-locales-and-user-types"></a>Impostazioni locali e tipi di utente supportati

La ® NDI è supportata in tutte le impostazioni locali. Gli utenti seguenti sono inclusi in uno stream di tecnologia NDI®, ma non tutti gli utenti possono accedere al flusso della tecnologia NDI®:

- In-tenant: supporto completo, fornito in base a ring/tenantId/userId (controllato dai criteri riunioni)
- Federato: nessun accesso al flusso (anche se ha la tecnologia NDI® su)<sup>1</sup>
- Premium - nessun accesso in streaming
- Anonimo: nessun accesso al flusso
- Guest: nessun accesso in streaming  

<sup>1</sup> I dispositivi hanno un'® NDI attivata per impostazione predefinita. Se un partecipante alla riunione usa un dispositivo con tecnologia NDI®, dovrà attivare la tecnologia NDI® NDI.
