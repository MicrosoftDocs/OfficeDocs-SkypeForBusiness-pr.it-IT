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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "62015016"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>App Walkie-talkie in Microsoft Teams

L'app Walkie-talkie in Teams fornisce comunicazioni push-to-talk istantanee per il team ed è ora disponibile su Android & iOS. Walkie-talkie consente agli utenti di connettersi con il proprio team usando gli stessi canali sottostanti di cui sono membri. Solo gli utenti che si connettono a Walkie-talkie in un canale diventano partecipanti e possono comunicare tra loro tramite push-to-talk, uno alla volta.

Con Walkie-talkie in Teams, i dipendenti in prima linea possono ora comunicare in modo sicuro con un'esperienza PTT familiare senza dover trasportare radio ingombranti e Walkie Talkie funziona ovunque con wi-fi o connettività Internet cellulare.

## <a name="getting-started"></a>Introduzione

### <a name="deploying-walkie-talkie"></a>Distribuzione di Walkie-talkie

Walkie-talkie è supportato nei dispositivi Android con dispositivi Google Servizi mobili (GMS) e iOS. 

Attualmente, Walkie-talkie non è preinstallate. Per abilitare questa caratteristica per gli utenti dell'organizzazione, è necessario aggiungere Walkie-talkie ai criteri di  [installazione](teams-app-setup-policies.md)  dell'appassegnati agli utenti dall'interfaccia di amministrazione [di Teams](https://admin.teams.microsoft.com/). Dopo l'abilitazione, Walkie-talkie diventerà disponibile nell'app entro 48 ore.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Aggiunta di Walkie-talkie all'elenco delle app

Nell'interfaccia di amministrazione di Microsoft Teams, in Teams i **criteri di installazione** **dell'app** > , **l'opzione Consenti aggiunta utente** dovrebbe essere impostata su **Attivato**. Quindi, nella sezione App aggiunte fare clic su **+Aggiungi app**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

Nel **riquadro Aggiungi app aggiunte** visualizzato a destra, usa la casella di testo **Cerca** per cercare Walkie-talkie. Quando viene visualizzato come risultato della ricerca, selezionare il pulsante **Aggiungi** a destra del nome per aggiungerlo all'elenco.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app aggiunte con Walkie immesso nel riquadro di ricerca e l'app Walkie-talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

L'app Walkie-talkie dovrebbe ora essere visualizzata nell'elenco App aggiunte ed essere disponibile per l'uso dopo aver fatto clic sul pulsante **Salva** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco App aggiunte con l'app Walkie-talkie aggiunta e il pulsante Salva sotto l'elenco.":::

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
