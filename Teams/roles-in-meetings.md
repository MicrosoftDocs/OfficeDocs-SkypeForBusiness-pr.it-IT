---
title: Funzionalità per relatori e partecipanti in una riunione di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sulle funzionalità disponibili per relatori e partecipanti una riunione di Teams.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321735"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a>Funzionalità per relatori e partecipanti in una riunione di Teams
======================================================

Le riunioni di Microsoft Teams supportano molti tipi di partecipanti. I partecipanti possono accedere a varie funzionalità per le riunioni in base ai ruoli che rivestono all'interno o all'esterno dell'organizzazione.

Le funzionalità per riunioni disponibili sono:

- Chat (include foto e adesivi)
- Note riunione
- Lavagna
- Registrazione
- File
- Pianificare una riunione (solo per le riunioni)

Questo articolo descrive le funzionalità per i partecipanti e il rispettivo accesso alle funzionalità per le riunioni.

## <a name="presenters-and-organizers"></a>Relatori e organizzatori

Relatori e organizzatori includono:

- Relatori dell'organizzazione
- Relatori di altre organizzazioni, inclusi i partecipanti anonimi ed esterni. I relatori sono designati dall'organizzatore e hanno bisogno di un invito personale da parte dell'organizzatore.

Relatori e organizzatori hanno accesso a tutte le funzionalità di una riunione o di un evento live.

## <a name="participants"></a>Partecipanti

I partecipanti alla riunione possono essere di diversi tipi:

- [Partecipante interno al tenant](#in-tenant-participant)
- [Partecipante guest](#guest-participant)
- [Partecipante esterno (federato)](#external-federated-participant)
- [Partecipante anonimo](#anonymous-participant)

### <a name="in-tenant-participant"></a>Partecipante interno al tenant

Il partecipante interno al tenant appartiene all'organizzazione e ha le credenziali per il tenant. Per altre informazioni su questo partecipante, vedere [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

|Riunione  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | Sì | Sì | Sì |
| Note riunione | Sì | Sì |Sì |
| Lavagna | Sì | Sì |Sì |
| Registrazione | N/D |Sì | Sì |
| File | Sì | Sì | Sì |
| Pianificare una riunione | Sì | N/D | N/D |
|||||||

### <a name="guest-participant"></a>Partecipante guest

Un partecipante guest è una persona di un'altra organizzazione che è stata invitata ad accedere a Teams o ad altre risorse nel tenant dell'organizzazione in base alla piattaforma B2B di Azure Active Directory. Gli utenti guest possono essere invitati a partecipare alle normali riunioni e alle riunioni di canale. Per altre informazioni sui partecipanti guest, vedere [Com'è l'esperienza guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

| Riunione |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | Sì | Sì | Sì |
| Note riunione | Sì | Sì | Sì |
| Lavagna | No | No |No |
| Registrazione | N/D |No | No |
| File | Sì | Sì | Sì |
| Pianificare una riunione | No | N/D | N/D |
|||||||

### <a name="external-federated-participant"></a>Partecipante esterno (federato)

Un partecipante esterno è un utente che usa Teams in un'altra organizzazione, che è stato invitato a partecipare a una riunione, ma che non ha accesso ad altre risorse condivise dell'organizzazione. I partecipanti esterni vengono visualizzati nell'elenco dei partecipanti alla riunione con il nome identità che usano nella propria organizzazione. Per altre informazioni sui partecipanti esterni, vedere [Comunicare con utenti di altre organizzazioni](communicate-with-users-from-other-organizations.md#external-access).

| Riunione (può essere aggiunto a un team solo come guest) ||
|-|-|-|
| **Funzionalità** |||
| Chat | N/D |
| Note riunione | N/D |  
| Lavagna | N/D |
| Registrazione | N/D |  
| File | N/D |
| Pianificare una riunione | N/D |
|||

### <a name="anonymous-participant"></a>Partecipante anonimo

Il partecipante anonimo è simile a un utente esterno, ma la sua identità non viene propagata nella riunione. Nel momento in cui entra nella riunione, immette manualmente un nickname. Per altre informazioni sui partecipanti anonimi, vedere [Sicurezza e Microsoft Teams](teams-security-guide.md#participant-types).

| Riunione  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| **Funzionalità**        | Prima della riunione | Durante la riunione | Dopo la riunione |
| Chat | N/D | No | N/D |
| Note riunione | N/D | No | N/D |
| Lavagna | N/D | No | N/D |
| Registrazione | N/D | No | N/D |
| File | N/D | No | N/D |
| Pianificare una riunione | N/D | N/D | N/D |
|||||||

## <a name="related-topics"></a>Argomenti correlati

[Sicurezza e Microsoft Teams](teams-security-guide.md)

[Accesso guest in Teams](guest-access.md)
