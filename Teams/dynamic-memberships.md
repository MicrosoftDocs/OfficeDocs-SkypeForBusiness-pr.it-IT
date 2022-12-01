---
title: Panoramica sull'appartenenza dinamica per i team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c747fea2b33f2fd18b004e9a16a2302702ec59
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198728"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Panoramica sull'appartenenza dinamica per i team

Microsoft Teams supporta i team associati a Microsoft 365 gruppi usando *l'appartenenza dinamica*. L'appartenenza dinamica consente di definire l'appartenenza di un team in base a una o più regole che verificano la presenza di determinati attributi utente in Azure Active Directory (Azure AD). Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi degli utenti cambiano o gli utenti si aggiungono e lasciano il tenant.

Con l'appartenenza dinamica è possibile configurare team per determinate coorti di utenti dell'organizzazione. Gli scenari possibili includono:
- Un ospedale può creare team distinti per infermieri, medici e chirurghi per trasmettere comunicazioni. Ciò è particolarmente importante se l'ospedale si affida a dipendenti temporanei.
- Un'università può creare un team per tutti i docenti all'interno di un determinato college, incluso un istituto di istruzione associato che cambia di frequente.
- Una compagnia aerea vuole creare una squadra per ogni volo (ad esempio un martedì pomeriggio non-stop da Chicago ad Atlanta) e avere un equipaggio di volo che cambia di frequente automaticamente assegnato o rimosso in base alle esigenze.

Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set di criteri specifico, invece di gestire manualmente l'appartenenza. Per farlo è necessario Azure AD Premium P1 licenze e l'appartenenza al team possono essere [assegnate da un amministratore tenant](/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure AD di qualsiasi utente, a condizione che si disponga di un tenant e di un account amministratore.

Microsoft Teams può richiedere da pochi minuti a 2 ore per riflettere le modifiche dinamiche dell'appartenenza una volta applicate nel gruppo di Microsoft 365 per un team.

Quando si usano team con gruppi dinamici:

- Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.
- I proprietari non potranno aggiungere o rimuovere utenti come membri del team, poiché i membri sono definiti da regole di gruppo dinamiche.
- I client di Teams non consentono la gestione dei membri per il team. Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.

Per creare un team che usa l'appartenenza dinamica, iniziare creando [un gruppo dinamico Microsoft 365](/azure/active-directory/users-groups-roles/groups-create-rule) e quindi [creare un team da tale gruppo](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

È possibile modificare un team esistente in modo che abbia un'appartenenza dinamica. Per informazioni, vedere [Modificare l'appartenenza statica ai gruppi in dinamica in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) .

## <a name="related-topics"></a>Argomenti correlati

[Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md)

[Regole di appartenenza dinamica per i gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
