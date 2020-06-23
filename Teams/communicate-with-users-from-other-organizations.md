---
title: Comunicare con utenti di altre organizzazioni in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come comunicare con utenti di altre organizzazioni in Microsoft Teams usando l'accesso esterno (federazione) e l'accesso guest.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 8676c45a386a9fb36571e3262a8c70769f45f0a6
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785278"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Comunicare con utenti di altre organizzazioni in Microsoft Teams
======================================================

Se è necessario comunicare e collaborare con persone esterne all'organizzazione, Microsoft Teams offre due modi diversi per farlo. Il primo è l’**accesso esterno** (federazione): consente di trovare, chiamare e chattare con utenti di altri domini, ad esempio contoso.com. Il secondo è l’**accesso guest**: consente di aggiungere singoli utenti al team, come guest, usando il loro indirizzo di posta elettronica. È possibile collaborare con i guest come si farebbe con qualsiasi altro utente dell'organizzazione.

Se si preferisce, si può sia l'accesso esterno che l'accesso guest: uno non preclude l'altro.

A un livello elevato, ecco come scegliere (per un confronto dettagliato, passare a [Confrontare l’accesso esterno e guest](#compare-external-and-guest-access) più in basso):

## <a name="external-access"></a>Accesso esterno

Usare l’**accesso esterno** (federazione) quando è necessaria una soluzione che consenta agli utenti esterni in altri domini di trovare, chiamare, chattare e pianificare riunioni con l’utente. Gli utenti esterni non hanno accesso ai team o alle risorse del team dell'organizzazione. Scegliere l’accesso esterno se si vuole comunicare con utenti esterni che si trovano ancora in Skype for Business (online o locale) o Skype (disponibile all'inizio del 2020). 

L'accesso esterno è attivato per impostazione predefinita in Teams, quindi l'organizzazione può comunicare con tutti i domini esterni. L'amministratore di Teams può disattivarlo o specificare quali domini includere o escludere. Per altre informazioni, vedere [Gestire l’accesso esterno](manage-external-access.md). 

Se si vuole consentire agli utenti esterni di accedere a team e canali, l’[accesso guest](#guest-access) potrebbe essere un’opzione migliore. 


## <a name="guest-access"></a>Accesso guest

Usare l'**accesso guest** per aggiungere un singolo utente, indipendentemente dal dominio, a un team in cui potrà chattare, chiamare, pianificare riunioni e collaborare ai file dell'organizzazione (archiviati in SharePoint o OneDrive for Business), usando le app di Office 365 o Microsoft 365, come Word, Excel o PowerPoint. Un utente guest può usufruire di quasi tutte le stesse funzionalità di Teams di un membro del team nativo. Per altre informazioni, vedere [Accesso guest in Teams](guest-access.md).

- Gli utenti guest vengono aggiunti all'Active Directory Domain Services dell'organizzazione.
- Per comunicare con un guest è necessario che il guest sia connesso a Teams con il proprio account guest. Questo vuol dire che può essere che l’utente si debba disconnettere dal proprio account Teams per accedere all’account Teams dove è guest.
- Gli utenti guest hanno accesso a più risorse in Teams, ad esempio file, team e canali, rispetto agli utenti con accesso esterno (federato).
- L'amministratore di Teams controlla tutto ciò che un guest può o non può fare grazie all'interfaccia di amministrazione di Teams. Per altre informazioni, vedere [Gestire l’accesso guest](manage-guests.md).

Se si vuole attivare l'accesso guest nell'organizzazione, iniziare con l'[Elenco di controllo dell’accesso guest](guest-access-checklist.md).


## <a name="compare-external-and-guest-access"></a>Confrontare l'accesso esterno e guest

| Funzionalità | Utenti con accesso esterno | Utenti con accesso guest |
|---------|-----------------------|--------------------|
| L’utente può chattare con utenti di un'altra società | Sì |Sì |
| L’utente può chiamare utenti di un'altra società | Sì | Sì |
| L’utente può vedere se una persona di un'altra società è disponibile per chiamate o chat | Sì | Sì<sup>1</sup> |
| L’utente può cercare altri utenti in tenant esterni | Sì<sup>2</sup> | No |
| L'utente può condividere file | No | Sì |
| Gli utenti possono accedere alle risorse di Teams | No | Sì |
| L’utente può essere aggiunto a una chat di gruppo | No | Sì |
| Gli utenti possono essere invitati a una riunione | Sì | Sì |
| Altri utenti possono essere aggiunti a una chat con un utente esterno | No<sup>3</sup> | N/D |
| L’utente viene identificato come entità esterna | Sì | Sì |
| La presenza viene visualizzata | Sì | Sì |
| Il messaggio Fuori sede viene visualizzato | No | Sì |
| È possibile bloccare l’utente singolo | No | Sì |
| Le @menzioni sono supportate | Sì<sup>4</sup> | Sì |
| Effettuare chiamate private | Sì | Sì |
| Visualizzare il numero di telefono dei partecipanti alla riunione con accesso esterno | No<sup>5</sup> | Sì |
| Consentire video IP | Sì | Sì |
| Modalità di condivisione dello schermo | Sì<sup>4</sup> | Sì |
| Consentire Riunione immediata | No | Sì |
| Modificare i messaggi inviati | Sì<sup>4</sup> | Sì |
| Eliminare i messaggi inviati | Sì<sup>4</sup> | Sì |
| Usare Giphy in una conversazione | Sì<sup>4</sup> | Sì |
| Usare meme nelle conversazioni | Sì<sup>4</sup> | Sì |
| Usare sticker nelle conversazioni | Sì<sup>4</sup> | Sì |
||||

<sup>1</sup>A condizione che l'utente sia stato aggiunto come guest e che sia stato eseguito l'accesso come guest al tenant guest.<br>
<sup>2</sup>Solo tramite posta elettronica o indirizzo SIP (Session Initiation Protocol).<br>
<sup>3</sup>La chat esterna (federata) è solo 1:1.<br>
<sup>4</sup>Chat 1:1 supportata per utenti Solo Teams a utenti Solo Teams di due organizzazioni diverse. <br>
<sup>5</sup> Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams. Per altre informazioni, vedere [Attivare o disattivare i messaggi di entrata e di uscita per le riunioni in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).

## <a name="related-topics"></a>Argomenti correlati

[Accesso esterno in Teams](manage-external-access.md)

[Accesso guest in Teams](guest-access.md)

