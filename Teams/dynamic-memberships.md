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
description: Scopri come Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120768"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Panoramica sull'appartenenza dinamica per i team

Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando *l'appartenenza dinamica.* L'appartenenza dinamica consente di definire l'appartenenza di un team in base a una o più regole che controllano la presenza di determinati attributi utente in Azure Active Directory (Azure AD). Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi degli utenti cambiano o gli utenti si uniscono e lasciano il tenant.

Con l'appartenenza dinamica è possibile configurare i team per determinate coorti di utenti dell'organizzazione. Gli scenari possibili includono:
- Un ospedale può creare team distinti per infermieri, medici e medici per trasmettere le comunicazioni. Questo è particolarmente importante se l'ospedale si basa sui dipendenti temporanei.
- Un'università può creare un team per tutti i docenti all'interno di un determinato istituto di istruzione, incluso un istituto di istruzione aggiunto che cambia di frequente.
- Una compagnia aerea vuole creare un team per ogni volo (ad esempio un non-stop di martedì pomeriggio da Chicago ad Atlanta) e assegnare o rimuovere automaticamente un membro del personale di volo che cambia spesso in base alle esigenze.

Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set specifico di criteri, invece di gestire manualmente l'appartenenza. Per eseguire questa operazione, è necessario che le licenze P1 Premium di Azure AD e l'appartenenza al team possano essere assegnate da un amministratore [tenant](/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure AD di qualsiasi utente, purché si abbia un tenant e un account di amministratore.

Microsoft Teams può richiedere da qualche minuto a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo che sono state applicate al gruppo Microsoft 365 per un team.

> [!NOTE]
> - Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.
> - Vedere [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md) per i limiti correnti per le dimensioni del team e del canale.
> - I proprietari non potranno aggiungere o rimuovere utenti come membri del team, perché i membri sono definiti da regole di gruppo dinamiche.
> -    I membri non potranno lasciare i team supportati da gruppi dinamici.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Creazione e gestione di un gruppo di Microsoft 365 con appartenenza dinamica

Dopo l'accesso come amministratore del tenant, seguire le istruzioni in [Creare un gruppo dinamico e controllare lo stato.](/azure/active-directory/users-groups-roles/groups-create-rule) Se necessario, vedere [Regole di appartenenza dinamiche per i gruppi in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Creare un nuovo team con il gruppo di Microsoft 365

È ora possibile concedere il tempo necessario per l'applicazione delle modifiche all'appartenenza e creare un nuovo team come descritto in Creare un [team da un gruppo esistente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Applicare l'appartenenza dinamica a un team esistente

È anche possibile usare un team esistente e cambiarlo in modo che abbia un'appartenenza dinamica, come descritto in Cambiare l'appartenenza statica ai gruppi [in dinamica in Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Modifiche al comportamento del client

Una volta abilitata l'appartenenza dinamica per un team, i client di Teams non consentiranno più la gestione dei membri per il team. Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.