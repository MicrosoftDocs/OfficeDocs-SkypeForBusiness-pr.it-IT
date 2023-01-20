---
title: App Walkie-talkie in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app Walkie-talkie in Microsoft Teams, dal punto di vista dell'amministratore IT.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: c4184e82e99fa4f3169fea14c62f3a892750bf8c
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845893"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>App Walkie-talkie in Microsoft Teams

L'app Walkie-talkie in Teams fornisce comunicazioni push-to-talk istantanee per il team ed è disponibile su Android e iOS. Walkie-talkie consente agli utenti di connettersi con il proprio team usando gli stessi canali sottostanti di cui sono membri.

Solo gli utenti che si connettono a Walkie-talkie in un canale diventano partecipanti e possono comunicare tra loro tramite PTT. Gli utenti continueranno a ricevere trasmissioni fino a quando non toccano  **Disconnetti**.

Con Walkie-talkie in Teams, gli utenti possono comunicare in modo sicuro con un'esperienza PTT familiare senza dover trasportare radio ingombranti e Walkie Talkie funziona ovunque con wi-fi o connettività Internet cellulare.

> [!NOTE]
> Walkie-talkie attualmente non è disponibile in Cina.

## <a name="license-requirements"></a>Requisiti di licenza

Walkie-talkie è incluso in tutte le licenze a pagamento di Teams in [Microsoft 365 e negli abbonamenti Office 365](/office365/servicedescriptions/teams-service-description). Per altre informazioni su come ottenere Teams, vedere [Ricerca per categorie ottenere Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>Distribuzione di Walkie-talkie

Walkie-talkie è supportato su dispositivi Android con Google Mobile Services (GMS) e dispositivi iOS.

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>Passaggio 1: Verificare che Walkie-talkie sia abilitato nell'organizzazione

Per impostazione predefinita, l'app Walkie-talkie è abilitata per tutti gli utenti di Teams nell'organizzazione.

Puoi controllare se l'app è disponibile a livello di organizzazione nella pagina [Gestisci app](manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams. Per verificare che l'app sia abilitata nell'organizzazione:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare alle **App di Teams** > **Gestisci app**.
2. Nell'elenco delle app cerca l'app Walkie-talkie, selezionala e quindi assicurati che **l'interruttore Stato** sia impostato su **Consentito**.

Se si vuole consentire o bloccare l'uso di Walkie-talkie da parte di utenti specifici dell'organizzazione, verificare che Walkie-talkie sia abilitato per l'organizzazione nella pagina [Gestisci app](manage-apps.md) . Creare quindi un criterio personalizzato per le autorizzazioni delle app e assegnarlo a tali utenti. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="step-2-pin-walkie-talkie-to-teams"></a>Passaggio 2: Aggiungere Walkie-talkie a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usare l'esperienza dell'app in prima linea personalizzata per aggiungere Walkie-talkie e altre app a Teams

L'esperienza personalizzata per le app in prima linea in Teams aggiunge le app più rilevanti in Teams per gli utenti che hanno una [licenza F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Le app aggiunte includono Walkie-talkie, turni, attività e approvazioni. Per impostazione predefinita, questa funzionalità è attivata e offre ai dipendenti in prima linea un'esperienza personalizzata in base alle loro esigenze.

Le app vengono aggiunte all'area di notifica nella parte inferiore dei client mobili di Teams, dove gli utenti possono accedervi rapidamente e facilmente.

Per altre informazioni, incluso il funzionamento dell'esperienza con i criteri delle app impostati, vedere [Personalizzare le app di Teams per i dipendenti in prima linea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usare i criteri di configurazione dell'app per aggiungere Walkie-talkie a Teams

I criteri di configurazione delle app consentono di personalizzare Teams per aggiungere app più importanti per gli utenti degli utenti.

Per aggiungere l'app Walkie-talkie per gli utenti, è possibile modificare il criterio globale (predefinito a livello di organizzazione) o creare e assegnare criteri personalizzati nei criteri di configurazione delle app. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Screenshot che mostra l'aggiunta di Walkie-talkie all'elenco di app aggiunte nel riquadro Aggiungi app aggiunte." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Documentazione di rete

Walkie-talkie in Teams richiede la connettività Internet. Per un'esperienza ottimale, sono necessarie le condizioni di rete seguenti.

|Metrica | Obbligatorio |
|---|---|
|Latenza (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perdita pacchetti |< 1% |

Come già accennato, la qualità dei supporti in tempo reale su una rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:

- **Latenza** : il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e alla velocità della luce, tra cui un maggiore sovraccarico da parte dei vari router in mezzo. La latenza viene misurata come tempo di round trip (RTT).
- **Instabilità tra arrivi** : variazione media del ritardo tra pacchetti successivi.
- **Perdita di pacchetti** : la perdita di pacchetti viene spesso definita come percentuale di pacchetti persi in un determinato intervallo di tempo. La perdita di pacchetti influisce direttamente sulla qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto, a perdite burst di tipo "back-to-back" che causano l'interruzione completa dell'audio.

Il consumo di dati previsto da Walkie-talkie è di circa 20 KB/s quando si invia o si riceve audio. In caso di inattività, l'utilizzo previsto dei dati da Walkie-talkie è trascurabile.

## <a name="walkie-talkie-devices"></a>Dispositivi Walkie-talkie

Gli operatori in prima linea spesso devono parlare e ricevere chiamate Walkie-talkie anche quando i loro telefoni sono bloccati. Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.

#### <a name="headsets"></a>Cuffie

- Cuffie wireless (iOS e Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Cuffie cablate (solo Android)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Telefoni Android robusti

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) e [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Configurazione manuale: con Teams installato, vai a **Pulsanti** **impostazioni** > . Sul pulsante Dedicato (1 o 2), selezionare **Pressione lunga** e quindi scegliere **App PTT**. Selezionare la rotellina blu accanto a **Personalizzato** e selezionare **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) e [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Configurazione manuale: con Teams installato, passare a **Impostazioni** > **Tasti programmabili**. Scegli **il tasto PTT** o **Tieni premuto** (a seconda del dispositivo) e seleziona **Teams**.
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer), [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer), [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp), [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer), [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer), [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer), 
  - Configurazione manuale: con Teams installato, il pulsante PTT dedicato funziona con Walkie-talkie per impostazione predefinita.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Configurazione manuale: con Teams installato, passare a **Impostazioni** > **Funzionalità** >  avanzate **XCover/Tasto attivo**. Attivare **ctrl tasto XCover con l'app** e selezionare **Teams**.
  - [Configurazione di MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Configurazione manuale: con Teams installato, vai a **Impostazioni** > **Tasti programmabili**. Scegliere **Select PTT Key app** e selezionare **Teams**.
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Configurazione manuale: con Teams installato, il pulsante PTT dedicato (LEFT_TRIGGER_2) funziona con Walkie-talkie per impostazione predefinita.

> [!NOTE]
> Questi dispositivi non sono certificati da Teams. Sono stati convalidati per funzionare con Teams Walkie-talkie.

## <a name="bluetooth-devices"></a>Dispositivi Bluetooth

> [!NOTE]
> Se gli utenti usano accessori Bluetooth, assicurati che la soluzione di gestione dei dispositivi mobili (MDM) non blocchi i dispositivi Bluetooth.

Nei dispositivi che eseguono Android OS versione 12 o successiva, sono necessarie le autorizzazioni Bluetooth e non sono più necessarie le autorizzazioni di posizione per connettersi usando lo stack BLE. Se le "autorizzazioni nelle vicinanze" non vengono concesse a livello di Teams, un utente riceverà una richiesta di autorizzazioni Bluetooth. Viene visualizzata questa richiesta, indipendentemente dal fatto che un accessorio Bluetooth, ad esempio un auricolare, sia collegato al suo dispositivo. Se è collegato un accessorio Bluetooth, tocca **Consenti** connessione Walkie-talkie all'accessorio Bluetooth.

## <a name="get-insight-into-walkie-talkie-usage-and-performance"></a>Ottenere informazioni dettagliate sull'utilizzo e le prestazioni di Walkie-talkie

Il [report sull'utilizzo e sulle prestazioni di Walkie-talkie](teams-analytics-and-reports/walkie-talkie-usage-report.md) nell'interfaccia di amministrazione di Teams offre una panoramica delle attività e delle prestazioni di Walkie-talkie nell'organizzazione. Il rapporto fornisce informazioni quali il numero di trasmissioni PTT effettuate e ricevute, l'attività del canale, la durata della trasmissione e i dettagli sul dispositivo e sui partecipanti.

## <a name="more-information"></a>Altre informazioni

- Se gli utenti usano i dati mobili per comunicare tramite Teams, Walkie Talkie userà lo stesso metodo.
- Walkie-talkie dovrebbe funzionare bene in situazioni di bassa larghezza di banda o situazioni in cui lo smartphone è connesso e funzionante. Walkie-talkie non funziona quando non c'è connettività affatto.

Per altre informazioni sull'esperienza utente finale, vedere:

- [Introduzione a Teams Walkie-talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicare con il team con Walkie-talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
