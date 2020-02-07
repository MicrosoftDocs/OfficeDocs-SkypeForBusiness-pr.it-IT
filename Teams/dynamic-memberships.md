---
title: Panoramica sull'appartenenza dinamica per i team
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni sull'appartenenza a un team dinamico basato su AAD.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04ac33bdd87b8bd7566e7588a3353a2f49920286
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836846"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Panoramica sull'appartenenza dinamica per i team

Microsoft teams supporta i team associati ai gruppi di Office 365 tramite *l'appartenenza dinamica*. L'appartenenza dinamica consente di definire l'appartenenza a un team da una o più regole che controllano alcuni attributi utente in Azure Active Directory (Azure AD). Gli utenti vengono aggiunti o rimossi automaticamente ai team corretti quando gli attributi dell'utente cambiano o gli utenti partecipano e lasciano il tenant.

Con l'appartenenza dinamica puoi configurare Team per alcuni coorti di utenti dell'organizzazione. Possibili scenari includono:
- Un ospedale può creare team distinti per infermieri, medici e chirurghi per trasmettere comunicazioni. Questo aspetto è particolarmente importante se l'ospedale si basa su dipendenti temporanei.
- Un'università può creare un team per tutti i docenti all'interno di un determinato collegio, tra cui una facoltà aggiuntiva che cambia spesso.
- Una compagnia aerea vuole creare un team per ogni volo (ad esempio un martedì pomeriggio non-stop da Chicago ad Atlanta) e avere un equipaggio di volo che cambia spesso automaticamente assegnato o rimosso in base alle esigenze.

Usando questa funzionalità, i membri di un determinato team vengono aggiornati automaticamente in base a un set di criteri specifico, invece di gestire manualmente l'appartenenza. In questo modo, le licenze Azure AD Premium P1 e l'appartenenza al team possono essere [assegnate da un amministratore del tenant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) alle proprietà di Azure ad di qualsiasi utente, purché si disponga di un tenant e di un account di amministratore.

Microsoft teams può richiedere in qualsiasi momento da pochi minuti a un massimo di 2 ore per riflettere le modifiche dinamiche dell'appartenenza dopo avere avuto effetto nel gruppo Office 365 per un team.

> [!NOTE]
> - Le regole possono definire chi è un membro del team, ma non chi è il proprietario del team.
> - Vedere [limiti e specifiche per Microsoft teams](limits-specifications-teams.md) per i limiti correnti sulle dimensioni del team e del canale.
> - I proprietari non saranno in grado di aggiungere o rimuovere utenti come membri del team, poiché i membri sono definiti da regole di gruppo dinamiche.
> - I membri non saranno in grado di abbandonare i team da gruppi dinamici.


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>Creazione e gestione di un gruppo di Office 365 con appartenenza dinamica
Durante l'accesso come amministratore del tenant, seguire le istruzioni in [creare un gruppo dinamico e verificare lo stato](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule). Se necessario, fare riferimento alle [regole di appartenenza dinamiche per i gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).

## <a name="create-a-new-team-with-your-o365-group"></a>Creare un nuovo team con il gruppo di Office 365

Ora consente di rendere effettive le modifiche apportate all'appartenenza e creare un nuovo team come descritto in [migliorare i gruppi di Office 365 esistenti con Microsoft teams](enhance-office-365-groups.md).

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Applicare l'appartenenza dinamica a un team esistente

Puoi anche prendere un team esistente e modificarlo in modo che abbia un abbonamento dinamico, come descritto in [modificare l'appartenenza a gruppi statici in Dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).

## <a name="changes-in-client-behavior"></a>Modifiche al comportamento del client

Una volta abilitata l'appartenenza dinamica per un team, i client di teams non consentiranno più la gestione dei membri per il team. Le opzioni per aggiungere membri, modificare i ruoli dei membri, inviare e approvare le richieste di join e uscire dal team sono tutte nascoste.
