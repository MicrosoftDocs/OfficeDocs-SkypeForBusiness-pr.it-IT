---
title: 'App pazienti per amministratori Teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: App pazienti per amministratori Teams
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749558"
---
# <a name="patients-app-overview"></a>Panoramica delle app pazienti

L'applicazione patients è un'app Store di Microsoft teams disponibile per tutti gli utenti di teams. L'app consente ai team di assistenza paziente costituiti da operatori clinici (ad esempio infermieri, medici, assistenti sociali) di curare e rivedere elenchi di pazienti per scenari che spaziano da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.   

L'app ha due modalità: 

- La modalità connessa EMR che si connette a EMR tramite FHIR. L'app modalità connessa EMR rimane in anteprima privata e i clienti interessati o gli amministratori possono richiedere l'accesso all'app eliminando Microsoft un messaggio di posta elettronica su teamsforhealthcare@service.microsoft.com con le informazioni sul tenant di Office 365. 
- La modalità manuale che consente ai team di assistenza di aggiungere/apportare manualmente le informazioni sul paziente. L'applicazione è disponibile nell'app teams Store per gli utenti finali da scaricare per impostazione predefinita ed è in anteprima pubblica. L'app può essere limitata a determinate sezioni di utenti che usano [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md)



## <a name="usage-example"></a>Esempio di utilizzo

Durante le sessioni di arrotondamento su ogni turno in reparto medico, i clinici si radunano presso la stazione di cura per discutere gli ultimi aggiornamenti sullo stato di avanzamento dei pazienti nel reparto.  Evidenziano le metriche chiave critiche (non necessariamente mediche o che esplicitano sulle cartelle cliniche dei pazienti) e assicurano che il paziente sia sul percorso di scorrimento a destra per il discarico in base alla diagnosi. Per aggirare questi pazienti, l'infermiera di carica configura l'app paziente in un team in cui vengono aggiunti tutti i clinici e aggiunge i pazienti a un elenco di pazienti. Durante i turni, gli infermieri e gli altri responsabili della cura per il paziente accedono a Microsoft teams e l'app patients sui loro dispositivi mobili e aggiornano le informazioni pertinenti sul paziente nel dispositivo e quindi tutti gli altri membri del team di assistenza possono vedere gli aggiornamenti e le note e rimanere sincronizzati. Due volte al giorno, all'inizio e alla fine di un turno, hanno anche riunioni di Team displicinary per passare all'elenco dei pazienti e usare l'app pazienti per mettere a terra se stessi e condividere informazioni su ogni paziente usando l'app pazienti in uno schermo di grandi dimensioni. Spesso, alcuni clinici possono anche accedere a queste riunioni di team in remoto ed essere ancora parte della discussione. 

## <a name="configure-patients-app"></a>Configurare l'app pazienti

Per informazioni su come preparare l'ambiente per l'uso dell'app pazienti in modalità EMR, vedere [integrazione di record sanitari elettronici in Microsoft teams](patients-app.md). Dovrai anche vedere gestire i [criteri di configurazione delle app in Microsoft teams](../../teams-app-setup-policies.md) per abilitare l'app patients per l'organizzazione.

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a>Argomenti correlati

[Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
