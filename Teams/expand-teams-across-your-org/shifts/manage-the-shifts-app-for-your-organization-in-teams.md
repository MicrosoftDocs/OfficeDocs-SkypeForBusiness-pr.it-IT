---
title: Gestire l'app Turni per l'organizzazione
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Informazioni su come configurare e gestire l'app Turni in Teams per gli operatori in prima linea nell'organizzazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 545c5af7411aa23bac7c7437d79d412914c7ad79
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2022
ms.locfileid: "69130975"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gestire l'app Turni per l'organizzazione in Microsoft Teams

## <a name="overview-of-shifts"></a>Panoramica di Turni

L'app Turni in Microsoft Teams mantiene gli operatori in prima linea connessi e sincronizzati. È progettato per la prima volta come dispositivo mobile per una gestione del tempo e una comunicazione rapide ed efficaci per i team. I turni consentono ai dipendenti in prima linea e ai loro manager di usare i dispositivi mobili per gestire le pianificazioni e tenersi in contatto.

- I manager creano, aggiornano e gestiscono le pianificazioni dei turni per i team. Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriverà tra 20 minuti"). Possono anche inviare documenti con criteri, bollettini di notizie e video.
- I dipendenti visualizzano i propri turni successivi, vedono quali sono gli altri colleghi pianificati per la giornata, possono richiedere o offrire un cambio di turno e richiedere un permesso.

È importante sapere che Turni attualmente non supporta i guest. Ciò significa che gli utenti guest in un team non possono essere aggiunti o usare la programmazione dei turni quando l’accesso guest è attivato in Teams.

> [!Note]
> Per informazioni dettagliate sulle funzionalità di Turni su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilità di Turni

Turni è disponibile in tutte le SKU Enterprise dove Teams è disponibile.

> [!NOTE]
> Turni è disponibile negli ambienti Government Community Cloud (GCC), ma non negli ambienti GCC High o DoD.

## <a name="location-of-shifts-data"></a>Posizione dei dati di Turni

I dati turni sono attualmente archiviati in Azure nei data center in Asia Pacifico (APAC), unione europea (UE) e America del Nord. Per altre informazioni sulla posizione di archiviazione dei dati, vedere [Dove sono i dati?](http://o365datacentermap.azurewebsites.net/)

Per altre informazioni sui dati di Turni, tra cui archiviazione, conservazione, recupero e crittografia dei dati di Turni, vedere [Domande frequenti sui dati di Turni](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Configurare Turni

### <a name="enable-or-disable-shifts-in-your-organization"></a>Abilitare o disabilitare Turni nell'organizzazione

Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams nell’organizzazione. È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Nell'elenco delle app cerca l'app Turni, selezionala e quindi imposta **l'interruttore Stato** su **Bloccato** o **Consentito**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Abilitare o disabilitare Turni per utenti specifici nell'organizzazione

Per consentire o bloccare l'uso di Turni da parte di utenti specifici dell'organizzazione, verificare che Turni sia attivato per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) . Creare quindi un criterio personalizzato per le autorizzazioni per le app e assegnarlo a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).

### <a name="pin-shifts-to-teams"></a>Aggiungere turni a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>Usare l'esperienza delle app in prima linea personalizzate per aggiungere Turni e altre app a Teams

L'esperienza personalizzata per le app in prima linea in Teams aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Le app aggiunte includono Turni, Walkie-talkie, attività e approvazioni. Per impostazione predefinita, questa funzionalità è attivata e offre ai dipendenti in prima linea un'esperienza personalizzata in base alle loro esigenze.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams, dove gli utenti possono accedervi rapidamente e facilmente.

Per altre informazioni, incluso il funzionamento dell'esperienza con i criteri delle app impostati, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Usare i criteri di configurazione delle app per aggiungere Turni a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per aggiungere le app più importanti per gli utenti.

È possibile creare criteri [personalizzati nei criteri di configurazione delle app](../../teams-app-setup-policies.md) aggiungendo l'app Turni e quindi [assegnandoli](../../assign-policies-users-and-groups.md) agli utenti. In alternativa, è possibile usare i criteri di configurazione dell'app che fanno parte dei pacchetti dei criteri Frontline Worker e Frontline Manager.

Un [pacchetto di criteri](../../manage-policy-packages.md) in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione. Il set di criteri nei pacchetti di criteri Frontline Worker e Frontline Manager include un criterio di configurazione dell'app che blocca l'app Turni e altre app che supportano le attività di comunicazione e collaborazione per quel ruolo.

È consigliabile usare i pacchetti di criteri Frontline Worker e Frontline Manager in quanto semplificano, semplificano e aiutano a garantire la coerenza durante la gestione dei criteri per la forza lavoro in prima linea.

### <a name="enable-shift-based-tags-in-teams"></a>Abilitare i tag basati sui turni in Teams

[I tag](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) in Teams consentono agli utenti di connettersi facilmente con un sottoinsieme di persone in un team. Con i tag basati sui turni, agli utenti vengono automaticamente assegnati tag che corrispondono al nome della programmazione e del gruppo di turno in Turni. Il tag può essere usato in @mentions nella riga **A** in una chat o in un post su qualsiasi canale standard del team.

I tag basati sui turni consentono agli utenti di raggiungere le persone in turno in tempo reale. Le notifiche vengono inviate solo alle persone che sono in turno nel momento in cui il tag viene usato in una chat o in un post del canale. Ad esempio:

- Un responsabile dello store usa il tag @Cashiers per pubblicare un annuncio in un canale per tutti i cassieri in turno.
- Un infermiere usa il tag @CardiologistsOnCall per avviare una chat con tutti i cardiologi in chiamata.

È possibile attivare o disattivare la funzionalità nell'interfaccia di amministrazione di Microsoft Teams. Per altre informazioni, vedere [Gestire i tag in Teams](../../manage-tags.md).

## <a name="search-the-audit-log-for-shifts-events"></a>Cercare nel log di controllo gli eventi di Turni

**(In anteprima)**

È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell’organizzazione.  Per altre informazioni su come eseguire ricerche nel log di controllo e vedere un elenco delle [attività di Turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [Cercare nel log di controllo eventi di Teams](../../audit-log-events.md).

Prima di poter eseguire ricerche nel log di audit, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://protection.office.com). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="related-articles"></a>Articoli correlati

- [Turni per Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Domande frequenti su Turni](shifts-data-faq.md)
- [Turni connettori](/microsoft-365/frontline/shifts-connectors)
- [Guida di Turni per gli operatori in prima linea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Assegnare i criteri agli utenti in Teams](../../policy-assignment-overview.md)
