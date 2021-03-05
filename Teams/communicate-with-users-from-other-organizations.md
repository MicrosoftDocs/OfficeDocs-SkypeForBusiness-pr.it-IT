---
title: Usare l'accesso guest e l'accesso esterno per collaborare con persone esterne all'organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: Informazioni su come telefonare, chattare, trovare e aggiungere utenti esterni all'organizzazione in Microsoft Teams usando l'accesso esterno (federazione) e l'accesso guest.
ms.openlocfilehash: e3524bfeb7e21e18d0d742c7208bbe307bdd16c8
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421321"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>Usare l'accesso guest e l'accesso esterno per collaborare con persone esterne all'organizzazione

Se è necessario comunicare e collaborare con persone esterne all'organizzazione, è possibile scegliere tra le due opzioni disponibili in Microsoft Teams:

- **Accesso esterno**: tipo di federazione che consente agli utenti di trovare, chiamare e chattare con persone di altre organizzazioni. Queste persone non possono essere aggiunte ai team a meno che non vengano invitate come guest.
- **Accesso guest**: consente di invitare persone esterne all'organizzazione a partecipare a un team. Le persone invitate ottengono un account guest in Azure Active Directory.

Tenere presente che Teams consente di invitare alle riunioni anche persone esterne all'organizzazione. Per questa operazione non è necessario configurare l'accesso esterno o guest.

## <a name="external-access-federation"></a>Accesso esterno (federazione)

Configurare l'accesso esterno se è necessario trovare, chiamare, chattare e configurare riunioni con persone esterne all'organizzazione che usano Teams, Skype for Business (online o in locale) o Skype. 

Per impostazione predefinita, l'accesso esterno è abilitato per tutti i domini. È possibile limitare l'accesso esterno consentendo o bloccando domini specifici o disattivandolo.

![Screenshot delle impostazioni per l'accesso esterno](media/external-access-federation-settings.png)

Per configurare l'accesso esterno, vedere [Gestire l'accesso esterno](manage-external-access.md). 

## <a name="guest-access"></a>Accesso guest

Usare l'accesso guest per aggiungere una persona esterna all'organizzazione a un team, in cui potrà chattare, chiamare, partecipare alle riunioni e collaborare ai file. Un utente guest può usufruire di quasi tutte le stesse funzionalità di Teams di un membro del team nativo.

Gli utenti guest vengono aggiunti all'istanza di Azure Active Directory dell'organizzazione come utenti B2B e devono accedere a Teams usando l'account guest. Questo significa che per accedere all'organizzazione potrebbero doversi disconnettere dalla propria organizzazione.

Per configurare l'accesso guest per Teams, vedere [Collaborare con gli utenti guest in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

## <a name="compare-external-and-guest-access"></a>Confronto tra accesso esterno e accesso guest

Le tabelle seguenti mostrano le differenze nell'uso dell'accesso esterno (federazione) e di quello guest. In entrambi i casi le persone che non fanno parte dell'organizzazione vengono identificate come esterne per gli utenti.

### <a name="things-your-users-can-do"></a>Operazioni eseguibili dagli utenti

| Gli utenti possono | Utenti con accesso esterno | Utenti guest |
|---------|-----------------------|--------------------|
| Chattare con utenti di altre organizzazioni | Sì | Sì |
| Chiamare utenti di altre organizzazioni | Sì | Sì |
| Vedere se una persona di un'altra organizzazione è disponibile per chiamate o chat | Sì | Sì<sup>1</sup> |
| Cercare persone in altre organizzazioni | Sì<sup>2</sup> | No |
| Condividere file | No | Sì |
| Visualizzare il messaggio fuori sede di | No | Sì |
| Bloccare utenti di altre organizzazioni | No | Sì |
| Usare le @menzioni | Sì<sup>3</sup> | Sì |

### <a name="things-people-outside-your-organization-can-do"></a>Operazioni eseguibili da persone esterne all'organizzazione

| Le persone esterne all'organizzazione possono | Utenti con accesso esterno | Utenti guest |
|---------|-----------------------|--------------------|
| Accedere alle risorse di Teams | No | Sì |
| Essere aggiunti a una chat di gruppo | No | Sì |
| Essere invitati a una riunione | Sì | Sì |
| Effettuare chiamate private | Sì | Sì<sup>5</sup> |
| Visualizzare il numero di telefono dei partecipanti alla riunione con accesso tramite telefono | No<sup>4</sup> | Sì |
| Usare il video IP | Sì | Sì<sup>5</sup> |
| Usare la condivisione dello schermo | Sì<sup>3</sup> | Sì<sup>5</sup> |
| Usare Riunione immediata | No | Sì<sup>5</sup> |
| Modificare i messaggi inviati | Sì<sup>3</sup> | Sì<sup>5</sup> |
| Eliminare i messaggi inviati | Sì<sup>3</sup> | Sì<sup>5</sup> |
| Usare Giphy nelle conversazioni | Sì<sup>3</sup> | Sì<sup>5</sup> |
| Usare meme nelle conversazioni | Sì<sup>3</sup> | Sì<sup>5</sup> |
| Usare adesivi nelle conversazioni | Sì<sup>3</sup> | Sì<sup>5</sup> |
| La presenza viene visualizzata | Sì | Sì |
| Usare le @menzioni | Sì<sup>3</sup> | Sì |

<br>

<sup>1</sup> A condizione che l'utente sia stato aggiunto come guest e che sia stato eseguito l'accesso con l'account guest.<br>
<sup>2</sup>Solo tramite posta elettronica o indirizzo SIP (Session Initiation Protocol).<br>
<sup>3</sup> Chat 1:1 supportata per utenti Solo Teams a utenti Solo Teams di due organizzazioni diverse. <br>
<sup>4</sup> Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams. Per altre informazioni, vedere [Attivare o disattivare i messaggi di entrata e di uscita per le riunioni in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> Sono consentiti per impostazione predefinita, ma possono essere disattivati dall'amministratore di Teams

## <a name="related-topics"></a>Argomenti correlati

[Accesso esterno in Teams](manage-external-access.md)

[Accesso guest in Teams](guest-access.md)

