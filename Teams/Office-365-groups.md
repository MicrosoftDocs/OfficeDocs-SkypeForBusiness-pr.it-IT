---
title: Microsoft 365 Groups e Microsoft Teams
ms.reviewer: Kyle Blevins
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: In questo articolo verranno fornite informazioni sul funzionamento dei gruppi di Microsoft 365 e delle appartenenze di gruppo con Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec2845723ce7f4a593064795f158ddf718d5b6e5
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753896"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Groups e Microsoft Teams
=====================================

> [!Tip]
> Vedere la sessione seguente per informazioni su come i team interagiscono con Azure Active Directory (Azure AD), Microsoft 365 groups, Exchange, SharePoint e OneDrive for business: [fondazioni di Microsoft teams](https://aka.ms/teams-foundations)

Microsoft 365 groups è il servizio di appartenenza tra applicazioni in Office 365. A livello di base, un gruppo Microsoft 365 è un oggetto in Azure Active Directory con un elenco di membri e un accoppiamento allentato a carichi di lavoro correlati, tra cui un sito del team di SharePoint, il gruppo Yammer, le risorse delle cassette postali di Exchange condivise, planner, Power BI e OneNote. È possibile aggiungere o rimuovere persone al gruppo esattamente come si farebbe con qualsiasi altro oggetto di sicurezza basato su gruppo in Active Directory.

Un amministratore di Office 365 può definire un gruppo di Microsoft 365, aggiungere membri e trarre vantaggio da funzionalità quali una cassetta postale condivisa di Exchange, una raccolta documenti di SharePoint, un gruppo di Yammer e così via. Per altre informazioni sui gruppi di Microsoft 365, vedere informazioni [sui gruppi di microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Non perdere i [gruppi di poster in Microsoft 365 per gli architetti it](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-microsoft-365-groups-work"></a>Come funzionano i gruppi di Microsoft 365
--------------------------

Quando si crea un team, nel backend si sta creando un gruppo Microsoft 365 e la raccolta documenti di SharePoint associata e il blocco appunti di OneNote, oltre a collegamenti ad altre applicazioni cloud di Office 365. Se la persona che crea il team è proprietaria di un gruppo di Office 365 pubblico o privato esistente, può aggiungere la funzionalità teams al gruppo se ha meno di 5000 persone e non è mai stato aggiunto a teams. In questo modo viene creato un canale **generale** predefinito in cui risiedono messaggi di chat, documenti, OneNote e altri oggetti. La visualizzazione della raccolta documenti per il canale rivelerà la cartella **generale** che rappresenta il canale nel team. Cosa più importante, se crei una struttura di cartelle personalizzata all'interno di una raccolta documenti, non viene **propagata** ai team come canale; per il momento, scorre solo da team in SharePoint.

> [!NOTE]
> In base al feedback dei clienti, i nuovi gruppi di Microsoft 365 generati come risultato della creazione di un team nel client Microsoft teams non verranno più visualizzati in Outlook per impostazione predefinita. Per attivare o disattivare la visualizzazione dei gruppi in Outlook, usare il cmdlet [set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) con il parametro **HiddenFromExchangeClientsEnabled** . I gruppi creati tramite Outlook e successivamente abilitati per i team continueranno a essere visualizzati sia in Outlook che in teams. 

> [!NOTE]
> L'eliminazione di un gruppo Microsoft 365 rimuoverà l'alias delle cassette postali per le conversazioni persistenti di Outlook/OWA e le riunioni di teams e contrassegnerà il sito di SharePoint per l'eliminazione. Tra la rimozione di un team e il relativo effetto su Outlook occorrono circa 20 minuti. L'eliminazione di un team dal client teams lo rimuove immediatamente dalla visualizzazione a tutti i membri del team. Se si rimuovono i membri di un gruppo di Microsoft 365 in cui è stata abilitata la funzionalità teams, potrebbe essere previsto un ritardo di circa due ore prima che il team venga rimosso dalla visualizzazione nel client teams per le persone interessate che sono state rimosse.
>
>Leggere [questo](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) articolo per informazioni sul ripristino di un gruppo Microsoft 365 eliminato.

<a name="group-membership"></a>Appartenenza al gruppo
----------------

Le caratteristiche e le funzionalità di gruppo per gli utenti dipendono dalla posizione in cui si guida l'appartenenza al gruppo. Se ad esempio si rimuove un membro di un team, questi vengono rimossi anche dal gruppo Microsoft 365. La rimozione dal gruppo rimuove immediatamente il team e i canali dal client teams. Se si rimuove una persona da un gruppo con l'interfaccia di amministrazione di Microsoft 365, non sarà più possibile accedere agli altri aspetti della collaborazione, ad esempio la raccolta documenti di SharePoint Online, il gruppo Yammer o OneNote condiviso. Tuttavia, avranno comunque accesso alla funzionalità di chat del team per circa due ore.

Come procedura consigliata per la gestione dei membri del team, Aggiungi e Rimuovi membri dal client teams per verificare che sia applicato il controllo di accesso a cascata corretto ad altre applicazioni cloud dipendenti. Inoltre, eviterai un'esperienza disarticolata lasciando le persone con l'impressione che abbiano ancora accesso alle risorse a cui hanno usato (fino a quando il ciclo di sincronizzazione successivo aggiunge o revoca l'accesso a un determinato componente del servizio). Se si aggiungono o si rimuovono membri del team all'esterno del client Teams (usando l'interfaccia di amministrazione di Microsoft 365, Azure AD o Exchange Online PowerShell), le modifiche apportate ai team possono richiedere fino a 24 ore (in alcuni casi).

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>Possibilità di aggiungere un gruppo come partecipante durante la pianificazione delle riunioni
----------------------------------------------------------

A partire da maggio 2020, è ora possibile invitare un gruppo a una riunione pianificata, con i seguenti caveat:
1. Tutti i gruppi e i team Microsoft 365 creati da gruppi Microsoft 365 esistenti saranno ricercabili e possono essere aggiunti alla riunione. Tuttavia, i membri riceveranno l'invito alla riunione in base all'abbonamento al gruppo.
2. I team creati da zero prima di maggio 2018 saranno anche ricercabili, ma i membri non riceveranno l'invito alla riunione a causa della loro sottoscrizione di gruppo predefinita, che è "risponde solo a te". Questa operazione può essere modificata da Outlook modificando le impostazioni del gruppo
3. I team creati da zero dopo il 2018 maggio non possono essere ricercati e sono nascosti usando la proprietà "HiddenFromAddressListsEnabled". Si tratta di un'impostazione controllata dall'amministratore che può essere modificata dall'amministratore.
