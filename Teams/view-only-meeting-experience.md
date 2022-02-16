---
title: Esperienza di solo visualizzazione nelle riunioni
author: SerdarSoysal
ms.author: serdars
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sull'esperienza di sola visualizzazione di Teams per amministratori, relatori e partecipanti
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 104540c047f499f8b82139e0c76c93e4b4625f62
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401140"
---
# <a name="teams-view-only-meeting-experience"></a>Esperienza di sola visualizzazione nelle riunioni di Teams

> [!Note]
> Le trasmissioni nella modalità di sola visualizzazione sono disponibili in Microsoft 365 E3/E5 e Microsoft 365 A3/A5. Questa caratteristica sarà introdotta il 1° marzo 2021, ma risulterà disattivata per impostazione predefinita. La distribuzione di questa funzionalità in Microsoft 365 Government Community Cloud (GCC) inizierà alla fine di marzo 2021. Government Community Cloud High (GCCH) e Department of Defense (DoD) saranno distribuiti in seguito. È necessario modificare i criteri predefiniti dopo tale data se si attivare la funzionalità. Usare PowerShell per abilitare i criteri `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.

> [!Note]
> Se la riunione o il webinar raggiunge piena capacità, Teams si ridimensionerà senza problemi per offrire un'esperienza di trasmissione in modalità di sola visualizzazione per 10.000 persone. Inoltre, durate questo periodo di maggiore telelavoro, si possono organizzare trasmissioni ancora più grandi, per 20.000 persone, fino alla fine di quest'anno. I webinar attualmente non supportano l'esperienza di trasmissione di sola visualizzazione.

Microsoft Teams consente fino a 10.000 partecipanti alle riunioni. Una volta raggiunta la piena capacità della riunione principale (ovvero quando vi accedono 1000 utenti), il resto dei partecipanti potrà accedere a un'esperienza di sola visualizzazione.

Gli utenti che accedono per primi alla riunione, fino alla sua capacità massima, otterranno un esperienza di riunione completa di Teams. Possono condividere audio e video, visualizzare i video condivisi e partecipare alla chat delle riunioni.

Gli utenti che accedono dopo il superamento della capacità della riunione accederanno a un'esperienza di sola visualizzazione.  

I partecipanti potranno unirsi all'esperienza di sola visualizzazione tramite la versione desktop, Web e Teams per dispositivi mobili (Android e iOS).

> [!Note]
> Il limite attuale di capacità delle "riunioni principali", ovvero il numero di utenti pienamente interattivi, è di 1000 e include GCC e webinar.

## <a name="teams-view-only-experience-controls"></a>Controlli dell'esperienza di sola visualizzazione di Teams

È possibile abilitare l'esperienza di sola visualizzazione usando il [`Set-CsTeamsMeetingPolicy`](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet dal [modulo PowerShell di SkypeForBusiness](/powershell/module/skype/?view=skype-ps) o dalla versione 2.0.0 del [ modulo MicrosoftTeams](https://www.powershellgallery.com/packages/MicrosoftTeams).

Per usare il modulo `MicrosoftTeams` consigliato:

```PowerShell
Install-Module -Name "MicrosoftTeams" -MinimumVersion 2.0.0
Connect-MicrosoftTeams
```

Per abilitare l'esperienza di sola visualizzazione, è possibile usare il seguente frammento PowerShell:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

Anche per disabilitare l'esperienza di sola visualizzazione, è possibile usare PowerShell.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

In futuro sarà possibile abilitare o disabilitare l'esperienza di sola visualizzazione dall'interfaccia di amministrazione di Teams.

## <a name="impact-to-users"></a>Impatto sugli utenti

L'esperienza d'uso varia a seconda di numerosi fattori.

Quando il limite di partecipati della riunione principale viene raggiunto, i partecipanti non possono accedere alla riunione se una qualsiasi delle seguenti condizioni è vera: 

- Un amministratore ha disabilitato l'esperienza di sola visualizzazione di Teams dell'organizzatore o dell'intero tenant.
- Il partecipante in sola visualizzazione non può evitare la sala di attesa. Ad esempio, se l’organizzatore di una riunione sceglie di avere solo **persone dell'organizzazione** eviterà la sala di attesa e se un utente esterno all'organizzazione tenterà di accedere come partecipante di sola visualizzazione, non potrà farlo.

Una volta raggiunta la piena capacità della riunione principale, l'organizzatore e i relatori della riunione visualizzeranno un banner che li informa che i nuovi partecipanti avranno accesso in sola visualizzazione.

  ![il client di Teams e il banner di notifica per gli organizzatori e i relatori.](media/chat-and-banner-message.png)

Quando viene raggiunto il limite di partecipanti della riunione principale, i partecipanti vengono informati nella schermata preliminare di accesso che stanno accedendo a un'esperienza di sola visualizzazione. 

  ![la schermata preliminare di accesso di Teams e il messaggio di notifica ai partecipanti per l’accesso in modalità di sola visualizzazione.](media/view-only-pre-join-screen.png)

Se lo spazio è sufficiente, i nuovi utenti accedono sempre alla riunione principale. Se il limite della riunione principale viene raggiunto e uno o più utenti abbandonano la riunione, la riunione principale ha una capacità sufficiente. I partecipanti che accedono (o riaccedono) alla riunione entreranno nella sala principale fino al raggiungimento del limite di utenti. I partecipanti che accedono all'esperienza di sola visualizzazione non potranno essere promossi alla riunione principale né automaticamente né manualmente.

Se i ruoli di relatore e di partecipante sono già stati impostati e il relatore tenta di partecipare a una riunione dopo che la riunione principale ha raggiunto la piena capacità, potrà accedervi come partecipante di sola visualizzazione e avrà le stesse limitazioni dei partecipanti di sola visualizzazione. Supporto per garantire che tutti i relatori partecipino alla riunione principale in una data successiva. L’organizzatore avrà sempre uno spazio garantito nella riunione principale.

## <a name="impact-to-meeting-presenters-and-organizers"></a>Impatto sui relatori e gli organizzatori della riunione

Le limitazioni per i relatori e gli organizzatori della riunione includono:

- Non sono disponibili informazioi sui partecipanti in modalità di sola visualizzazione. I processi e-discovery non sono supportati per i partecipanti in modalità di sola visualizzazione.
- Gli utenti della riunione principale non possono visualizzare i partecipanti di sola visualizzazione.
- Non è possibile rimuovere i partecipanti in modalità di sola visualizzazione dalle riunioni.

> [!Note]
> Il numero di partecipanti rifletterà solo le persone della riunione principale e non le persone nella sala di sola visualizzazione. Pertanto, i presentatori non possono conoscere esattamente il numero degli utenti nella sala di sola visualizzazione.

## <a name="experience-for-view-only-attendees"></a>Esperienza per gli in modalità nella sala di sola visualizzazione

L'esperienza di sola visualizzazione consente ai partecipanti di:

- Ascoltare i partecipanti alla riunione principale di Teams.
- Vedere il feed video del relatore attivo (se il relatore sta condividendo il video).
- Visualizzare il contenuto condiviso usando la funzionalità di condivisione del desktop o dello schermo.

I partecipanti nella sala di sola visualizzazione non potranno usare le seguenti opzioni delle riunioni:

- Partecipare alle riunioni se il partecipante non è autorizzato a ignorare la sala di attesa in base ai criteri o alle opzioni configurati della sala di attesa.
- Accedere alla sala di solo visualizzazione usando la funzionalità di audioconferenza.
- Partecipare alla sala di sola visualizzazione usando il sistema Microsoft Teams Rooms o i servizi Cloud Video Interop (CVI).
- Condividere l'audio o il video.
- Leggere o partecipare alla chat della riunione.
- Visualizzare il video trasmesso dai partecipanti alla riunione, se non sono i relatori attivi.
- Vedere i file di PowerPoint condivisi usando la funzionalità PowerPoint Live o specifiche applicazioni di condivisione (diverse dalla condivisione desktop o schermo).
- Alzare la mano durante la riunione.
- Inviare o vedere reazioni.
- Interagire con qualsiasi app 3P integrata nella riunione di Teams, inclusi i sondaggi.

## <a name="view-only-feature-limitations"></a>Limitazioni della funzionalità di sola visualizzazione

- I partecipanti di sola visualizzazione potranno visualizzare i sottotitoli in tempo reale solo sulla versione desktop o Web. Al momento sono supportati solo i sottotitoli in inglese.
- I partecipanti di sola visualizzazione non possono registrarsi ai webinar.
- I partecipanti nella sala di sola visualizzazione saranno supportati dalla tecnologia di streaming.
- I partecipanti nella sala di sola visualizzazione non vengono inclusi nel report sui partecipanti.
- I partecipanti nella sala di sola visualizzazione hanno un'esperienza video singola. Possono accedere l'altoparlante attivo o i contenuti che vengono condivisi, ma non entrambi.
- Al momento non supportiamo i layout **Galleria**, **Galleria estesa**, o **Modalità Insieme** per gli utenti nella sala di sola visualizzazione.
- I partecipanti in sola visualizzazione sono supportati esclusivamente dai criteri seguenti di sala di attesa: "Persone nella mia organizzazione e utenti guest", "Persone nella mia organizzazione, organizzazioni attendibili e utenti guest" e "Tutti". Se si usano criteri di sala di attesa che non supportano i partecipanti di sola visualizzazione, ai partecipanti di sola visualizzazione saranno espulsi dalla riunione. 
- I partecipanti nella sala di sola visualizzazione non avranno la stessa latenza dei partecipanti normali. <sup>1</sup>

  <sup>1</sup> I partecipanti nella sala di sola visualizzazione avrannno un ritardo audio e video di 30 secondi durante la riunione.  
