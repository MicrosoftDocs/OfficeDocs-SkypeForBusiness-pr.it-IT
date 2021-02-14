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
description: Informazioni su come Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 usando l'appartenenza dinamica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583925"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Panoramica sull'appartenenza dinamica per i team

Microsoft Teams supporta i team associati ai gruppi di Microsoft 365 tramite *l'appartenenza dinamica.* L'appartenenza dinamica consente di definire l'appartenenza di un team tramite una o più regole che verificano la presenza di determinati attributi utente in Azure Active Directory (Azure AD). Gli utenti vengono automaticamente aggiunti o rimossi dai team corretti quando gli attributi utente cambiano o gli utenti si uniscono e lasciano il tenant.

Con l'appartenenza dinamica è possibile configurare i team per determinati gruppi di utenti dell'organizzazione. Gli scenari possibili includono:
- Un ospedale può creare team distinti per infermieri, medici e personale medico per le comunicazioni trasmesse. Questo è particolarmente importante se l'ospedale si affida ai dipendenti della temp.
- Un'università può creare un team per tutti gli istituti di istruzione all'interno di una particolare università, incluso un istituto di istruzione che cambia di frequente.
- Una compagnia aerea vuole creare un team per ogni volo (ad esempio un martedì pomeriggio non-stop da Chicago ad Atlanta) e assegnare o rimuovere automaticamente una squadra di volo a cambio continuo, se necessario.

Usando questa caratteristica, i membri di un determinato team vengono aggiornati automaticamente in base a un set di criteri specifico, invece che manualmente l'appartenenza. Per eseguire questa operazione sono necessarie licenze Azure AD Premium P1 e l'appartenenza al team può essere assegnata da un amministratore [del tenant alle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) proprietà di Azure AD di qualsiasi utente, purché si abbia un tenant e un account di amministratore.

Microsoft Teams può richiedere da pochi minuti a 2 ore per riflettere le modifiche dinamiche dell'appartenenza una volta applicate nel gruppo di Microsoft 365 per un team.

> [!NOTE]
> - Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.
> - Vedi [i limiti e le specifiche per Microsoft Teams](limits-specifications-teams.md) per i limiti correnti per le dimensioni del team e del canale.
> - I proprietari non potranno aggiungere o rimuovere utenti come membri del team, perché i membri sono definiti da regole di gruppo dinamiche.
> -    I membri non potranno lasciare i team supportati da gruppi dinamici.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Creazione e gestione di un gruppo di Microsoft 365 con appartenenza dinamica

Dopo l'accesso come amministratore del tenant, seguire le istruzioni in [Creare un gruppo dinamico e controllare lo stato.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) Se necessario, vedere [Regole di appartenenza dinamica per i gruppi in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Creare un nuovo team con il gruppo di Microsoft 365

Ora è possibile impostare l'applicazione delle modifiche all'appartenenza e creare un nuovo team come descritto in Creare un [team da un gruppo esistente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Applicare l'appartenenza dinamica a un team esistente

È anche possibile impostare un team esistente e cambiarlo in modo che abbia un'appartenenza dinamica, come descritto in Cambiare l'appartenenza statica ai gruppi [in dinamica in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Modifiche al comportamento client

Una volta abilitata l'appartenenza dinamica per un team, i client di Teams non consentono più la gestione dei membri per il team. Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare richieste di partecipazione e lasciare il team sono tutte nascoste.
