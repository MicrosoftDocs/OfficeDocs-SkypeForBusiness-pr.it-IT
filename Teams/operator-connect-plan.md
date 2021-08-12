---
title: Connessione con operatore
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sulle Connessione con operatore, ad esempio i requisiti e la pianificazione della distribuzione.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adc229264513d7ec4ca692dca1731d7390b80dc243b4571757607c1c76b7cacb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323948"
---
# <a name="plan-for-operator-connect"></a>Pianificare l'Connessione con operatore

>[!NOTE]
>Connessione con operatore è attualmente disponibile solo **nell'anteprima pubblica.** L'anteprima pubblica consente di testare le funzionalità imminenti e fornire feedback. Le funzionalità incluse nell'anteprima pubblica potrebbero non essere complete, potrebbero subire modifiche e non sono supportate in Office 365 Government Cloud.

Connessione con operatore è un'altra opzione per fornire connettività PSTN (Public Switched Telephone Network) con Teams e Sistema telefonico.  

Questo articolo descrive i vantaggi e i requisiti ed elenca gli operatori che partecipano al Connessione con operatore programma.  Se si decide Connessione con operatore soluzione giusta per l'organizzazione, dopo aver letto questo articolo, vedere Configurare Connessione con operatore [.](operator-connect-configure.md)  

## <a name="benefits"></a>Vantaggi

Con Connessione con operatore, se l'operatore esistente è un partecipante al programma Microsoft Connessione con operatore, può gestire il servizio per portare le chiamate PSTN in Teams. Il Connessione con operatore offre i vantaggi seguenti:

- **Sfruttare i contratti esistenti o trovare un nuovo operatore.** È possibile mantenere l'operatore e i contratti preferiti oppure sceglierne uno nuovo tra una selezione di operatori partecipanti per soddisfare le esigenze aziendali.

- **Infrastruttura gestita dall'operatore.** L'operatore gestisce i servizi di chiamata PSTN e i session border controller (SBC), consentendo di risparmiare sull'acquisto e la gestione dell'hardware.

- **Distribuzione più rapida e semplice.** È possibile connettersi rapidamente all'operatore e assegnare numeri di telefono agli utenti, tutti dall'Teams di amministrazione.

- **Supporto e affidabilità migliorati.** Gli operatori forniscono supporto tecnico e contratti di servizio condivisi per migliorare il servizio di supporto, mentre il peering diretto basato su Azure crea una connessione di rete uno-a-uno per migliorare l'affidabilità.

## <a name="requirements"></a>Requisiti

 Connessione con operatore potrebbe essere la soluzione giusta per l'organizzazione se:

- Microsoft Calling Plan non è disponibile nella tua posizione geografica.
- L'operatore preferito è un partecipante al programma Microsoft Connessione con operatore microsoft.
- Si vuole trovare un nuovo operatore per abilitare le chiamate in Teams.

Per abilitare le assegnazioni dei numeri di telefono Connessione con operatore, assicurati che gli utenti siano:

- Teams Telefono concesso in licenza. Per altre informazioni, vedere [Che cos'è Sistema telefonico?](what-is-phone-system-in-office-365.md) e Assegnare Teams [licenze per i componenti aggiuntivi agli utenti.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- In modalità TeamsOnly. Per altre informazioni, vedere [Comprendere Microsoft Teams e Skype for Business coesistenza e interoperabilità.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="available-operators"></a>Operatori disponibili

Gli operatori seguenti sono partecipanti al programma Microsoft Connessione con operatore:

| Operatore | Funzionalità | Copertura paese |
| --- | --- | --- |
| `BT`  | Chiamate | Belgio, Danimarca, Finlandia, Francia, Germania, Irlanda, Italia, Lussemburgo, Paesi Bassi, Norvegia, Polonia, Sudafrica, Spagna, Svezia, Svizzera, Regno Unito |
| `Intrado` | Chiamate | Belgio, Canada, Danimarca, Francia, Germania, Irlanda, Lussemburgo, Paesi Bassi, Spagna, Svezia, Regno Unito, Stati Uniti  |
| `NTT`  | Chiamate | Austria, Belgio, Brasile, Canada, Cecoia, Danimarca, Finlandia, Francia, Germania, Irlanda, Italia, Lussemburgo, Messico, Paesi Bassi, Norvegia, Polonia, Portogallo, Portorico, Romania, Sudafrica, Spagna, Svezia, Svizzera, Regno Unito, Stati Uniti |
| `NuWave` | Chiamate | Austria, Belgio, Canada, Danimarca, Francia, Germania, Irlanda, Italia, Paesi Bassi, Portogallo, Spagna, Svezia, Svizzera, Regno Unito, Stati Uniti   |
| `Orange Business Services` | Chiamate | Austria, Belgio, Cecoia, Danimarca, Finlandia, Francia, Guiana francese, Germania, Guadalupa, Irlanda, Italia, Lussemburgo, Martinica, Mayotte, Paesi Bassi, Norvegia, Polonia, Portogallo, Riunione, Saint Barthélemy, Saint Martin, Spagna, Svalbard, Svezia, Svizzera, Regno Unito  |
| `Pure IP` | Chiamate | Australia, Austria, Belgio, Brasile, Bulgaria, Canada, Cile, Colombia, Croazia, Cipro, Cecoslovacchia, Danimarca, Finlandia, Francia, Germania, Grecia, Hong Kong S.A.R., Irlanda, Italia, Giappone, Lituania, Lussemburgo, Malaysia, Messico, Paesi Bassi, Nuova Zelanda, Norvegia, Panama, Polonia, Portogallo, PortoRico, Romania, Singapore, Slovacchia, Slovenia, Sudafrica, Spagna, Svezia, Svizzera, Regno Unito, Stati Uniti  |
| `Rogers Business` | Chiamate | Canada  |
| `TATA Communications` | Chiamate | Australia, Austria, Belgio, Canada, Cecoia, Danimarca, Francia, Germania, Hong Kong S.A.R., Ungheria, Irlanda, Italia, Malaysia, Messico, Paesi Bassi, Nuova Zelanda, Polonia, Portogallo, Romania, Singapore, Corea del Sud, Spagna, Svezia, Svizzera, Thailandia, Regno Unito, Stati Uniti |
| `Telekom Deutschland` | Chiamate | Germania  |
| `Telenor` | Chiamate | Danimarca, Finlandia, Norvegia, Svezia  |
| `Verizon` | Chiamate | Stati Uniti |
