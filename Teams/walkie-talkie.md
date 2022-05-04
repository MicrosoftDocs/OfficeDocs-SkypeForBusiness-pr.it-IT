---
title: Applicazione Walkie-talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app Walkie-talkie in Microsoft Teams, da un punto di vista ITAdmin.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 776f0f31d54788fbffd86bbcbedd44e30ada28a3
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "65186972"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>App Walkie-talkie in Microsoft Teams

L'app Walkie-talkie in Teams fornisce comunicazioni push-to-talk istantanee per il team ed è ora disponibile su Android & iOS. Walkie-talkie consente agli utenti di connettersi con il proprio team usando gli stessi canali sottostanti di cui sono membri. Solo gli utenti che si connettono a Walkie-talkie in un canale diventano partecipanti e possono comunicare tra loro tramite push-to-talk, uno alla volta.

Con Walkie-talkie in Teams, i dipendenti in prima linea possono ora comunicare in modo sicuro con un'esperienza PTT familiare senza dover trasportare radio ingombranti e Walkie Talkie funziona ovunque con wi-fi o connettività Internet cellulare.

## <a name="getting-started"></a>Introduzione

### <a name="deploying-walkie-talkie"></a>Distribuzione di Walkie-talkie

Walkie-talkie è supportato nei dispositivi Android con dispositivi Google Servizi mobili (GMS) e iOS.

### <a name="pin-walkie-talkie-to-teams"></a>Aggiungi Walkie-talkie a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usa l'esperienza app in prima linea personalizzata per aggiungere Walkie-talkie e altre app a Teams

L'esperienza delle app in prima linea personalizzate in Teams aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Le app aggiunte includono Walkie-talkie, turni, attività e Approvazioni. Per impostazione predefinita, questa funzionalità è attivata e offre ai dipendenti in prima linea un'esperienza personalizzata in base alle loro esigenze.

Le app vengono aggiunte alla barra dell'app, ovvero la barra sul lato del client desktop di Teams e nella parte inferiore del Teams client per dispositivi mobili, in cui gli utenti possono accedervi in modo semplice e rapido.

Per altre informazioni, incluso il funzionamento dell'esperienza con i criteri delle app impostati, vedere [Personalizzare le app Teams per i dipendenti in prima linea](pin-teams-apps-based-on-license.md).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usare un criterio di configurazione dell'app per aggiungere Walkie-talkie a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per aggiungere app più importanti per gli utenti.

Per aggiungere l'app Walkie-talkie per gli utenti, è possibile modificare il criterio globale (impostazione predefinita a livello di organizzazione) o creare e assegnare criteri di configurazione delle app personalizzati. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Screenshot che mostra l'aggiunta di Walkie-talkie all'elenco di app aggiunte nel riquadro Aggiungi app aggiunte." lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>Documentazione di rete

Walkie-talkie in Teams richiede la connettività Internet e al di sotto delle condizioni di rete sono necessarie per un'esperienza ottimale.

|Metrica | Obbligatorio |
|---|---|
|Latenza (RTT) | < 300ms |
|Jitter |< 30ms |
|Perdita pacchetti |< 1% |

Come già accennato, la qualità dei supporti in tempo reale su una rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:

- **Latenza** : il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e alla velocità della luce, tra cui un maggiore sovraccarico da parte dei vari router in mezzo. La latenza viene misurata come tempo di round trip (RTT).
- **Instabilità tra** arrivi: rappresenta la variazione media del ritardo tra pacchetti successivi.
- **Perdita pacchetti** : spesso viene definita come percentuale di pacchetti persi in un determinato intervallo di tempo. La perdita di pacchetti influisce direttamente sulla qualità audio: da pacchetti piccoli e singoli persi che non hanno quasi alcun impatto, a perdite burst back-to-back che causano l'interruzione completa dell'audio.

Il consumo di dati previsto da Walkie-talkie è di circa 20 KB/s quando si invia o si riceve audio. In caso di inattività, l'utilizzo previsto dei dati da Walkie-talkie è trascurabile.

### <a name="walkie-talkie-devices"></a>Dispositivi Walkie-talkie

Gli operatori in prima linea spesso devono parlare e ricevere chiamate Walkie-talkie anche quando i loro telefoni sono bloccati. Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.

- **Cuffie**
  - Cuffie wireless (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Cuffie cablate (solo Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Telefoni Android robusti**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Configurazione manuale: con Teams installato, passare a Impostazioni > Funzioni avanzate > chiave XCover/Active. Attiva 'Ctrl tasto XCover con app' e selezionare 'Teams'
    - [Configurazione di MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Configurazione manuale - Con Teams installato, il pulsante PTT dedicato (LEFT_TRIGGER_2) funziona per impostazione predefinita con Walkie-talkie
    
> [!NOTE]
> Questi dispositivi non sono Teams certificati. Sono stati convalidati per funzionare con Teams Walkie-talkie.

### <a name="license-requirements"></a>Requisiti di licenza

L'app Walkie-talkie è inclusa in tutte le licenze a pagamento di Teams negli [abbonamenti Office 365](/office365/servicedescriptions/teams-service-description). Per altre informazioni su come ottenere Teams, vedere  [Ricerca per categorie accedere a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="further-information"></a>Ulteriori informazioni

- Gli ITAdmin possono mantenere il controllo su chi usa Walkie-talkie tramite i criteri delle app.
- Se il frontline worker usa i dati mobili per comunicare tramite Teams, Walkie-talkie userà lo stesso metodo.
- Walkie-talkie dovrebbe funzionare bene in situazioni di bassa larghezza di banda o situazioni in cui lo smartphone è connesso e funzionante. Walkie-talkie non funziona quando non c'è connettività affatto.

Per ulteriori informazioni sull'esperienza utente finale, vedere:

- [Attività iniziali con walkie-talkie Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicare con il team con Walkie-talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
