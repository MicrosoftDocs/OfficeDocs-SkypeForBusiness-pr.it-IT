---
title: Panoramica sull'appartenenza dinamica per i team
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Scopri come Microsoft Teams i team associati a Microsoft 365 gruppi usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856325"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Panoramica sull'appartenenza dinamica per i team

Microsoft Teams supporta i team associati a Microsoft 365 gruppi usando *l'appartenenza dinamica.* L'appartenenza dinamica consente di definire l'appartenenza di un team in base a una o più regole che controllano la presenza di determinati attributi utente in Azure Active Directory (Azure AD). Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi degli utenti cambiano o gli utenti si uniscono e lasciano il tenant.

Con l'appartenenza dinamica è possibile configurare i team per determinate coorti di utenti dell'organizzazione. Gli scenari possibili includono:
- Un ospedale può creare team distinti per infermieri, medici e medici per trasmettere le comunicazioni. Questo è particolarmente importante se l'ospedale si basa sui dipendenti temporanei.
- Un'università può creare un team per tutti i docenti all'interno di un determinato istituto di istruzione, incluso un istituto di istruzione aggiunto che cambia di frequente.
- Una compagnia aerea vuole creare un team per ogni volo (ad esempio un non-stop di martedì pomeriggio da Chicago ad Atlanta) e assegnare o rimuovere automaticamente un membro del personale di volo che cambia spesso in base alle esigenze.

Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set specifico di criteri, invece di gestire manualmente l'appartenenza. Per eseguire questa operazione, è necessario che le licenze di Azure AD Premium P1 e l'appartenenza al team possano essere assegnate da un amministratore [tenant](/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure AD di qualsiasi utente, purché si abbia un tenant e un account di amministratore.

Microsoft Teams può richiedere da pochi minuti a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo che sono state applicate nel gruppo Microsoft 365 per un team.

Quando si usano team con gruppi dinamici:

- Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.
- I proprietari non potranno aggiungere o rimuovere utenti come membri del team, perché i membri sono definiti da regole di gruppo dinamiche.
- Teams client non consentono la gestione dei membri per il team. Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.

Per creare un team che usa l'appartenenza dinamica, iniziare [creando](/azure/active-directory/users-groups-roles/groups-create-rule) un gruppo Microsoft 365 e quindi [creare un team da tale gruppo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

È possibile modificare un team esistente in modo che abbia un'appartenenza dinamica. Per informazioni, vedere Modificare l'appartenenza a gruppi [statici in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="related-topics"></a>Argomenti correlati

[Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md)

[Regole di appartenenza dinamiche per i gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
