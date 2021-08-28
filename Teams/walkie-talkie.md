---
title: Applicazione Walkie Talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app Walkie Talkie in Microsoft Teams, dal punto di vista dell'ITAdmin.
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
ms.openlocfilehash: 80aedfd0c1bb4f4a20ecdfcd977ce74d667cad43
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602071"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>App Walkie Talkie in Microsoft Teams

L'app Walkie Talkie in Teams fornisce comunicazioni push-to-talk istantanee (PTT) per il team ed è ora disponibile su Android. Walkie Talkie consente agli utenti di connettersi con il team usando gli stessi canali sottostanti di cui sono membri. Solo gli utenti che si connettono a Walkie Talkie in un canale diventano partecipanti e possono comunicare tra loro usando push-to-talk, uno alla volta.

Con Walkie Talkie in Teams, i lavoratori in prima linea possono ora comunicare in modo sicuro con un'esperienza PTT familiare senza dover portare radio ingombrante e Walkie Talkie funziona ovunque con wifi o connettività Internet cellulare.

## <a name="getting-started"></a>Introduzione

### <a name="deploying-walkie-talkie"></a>Distribuzione di Walkie Talkie

Attualmente, Walkie Talkie è disponibile per i dispositivi Android con Google Servizi mobili (GMS) e non è preinstallato. Per abilitare questa funzionalità per gli utenti dell'organizzazione, è necessario aggiungere Walkie Talkie ai criteri di configurazione delle [app](teams-app-setup-policies.md)assegnati agli utenti dall'interfaccia di amministrazione   di [Teams.](https://admin.teams.microsoft.com/) Una volta abilitata, Walkie Talkie sarà disponibile nell'app Android entro 48 ore.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Aggiunta di Walkie Talkie all'elenco delle app

Nell'Microsoft Teams di amministrazione, in Teams criteri di configurazione **dell'app,** l'opzione Consenti blocco utente dovrebbe essere  >  impostata su  **Su**. Quindi, nella sezione App aggiunte fare clic su **+Aggiungi app.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

Nel riquadro **Aggiungi app** aggiunte visualizzato a destra  usare la casella di testo Cerca per cercare Walkie Talkie. Se il risultato è un risultato della ricerca, selezionare il **pulsante Aggiungi** a destra del nome per aggiungerlo all'elenco.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app aggiunte con Walkie immesso nel riquadro di ricerca e l'app Walkie Talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

L'app Walkie Talkie dovrebbe ora essere visualizzata nell'elenco App aggiunte ed essere disponibile per l'uso dopo aver fatto clic sul **pulsante** Salva.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco delle app aggiunte con l'app Walkie Talkie aggiunta e il pulsante Salva sotto l'elenco.":::

### <a name="network-documentation"></a>Documentazione di rete

Walkie Talkie in Teams la connettività Internet e al di sotto delle condizioni di rete sono necessarie per un'esperienza ottimale.

|Metrica | Obbligatorio |
|---|---|
|Latenza (RTT) | < 300 ms |
|Jitter |< 30 ms |
|Perdita pacchetti |< 1% |

Come indicato in precedenza, la qualità dei supporti multimediali in tempo reale su una rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma in particolare dalla quantità di:

- **Latenza:** tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e alla velocità della luce, incluso il sovraccarico dei vari router in mezzo. La latenza viene misurata come tempo di round trip (RTT).
- **Instabilità tra gli arrivi:** questa è la variazione media del ritardo tra pacchetti successivi.
- **Perdita di pacchetti:** spesso viene definita come percentuale di pacchetti persi in un determinato intervallo di tempo. La perdita di pacchetti influisce direttamente sulla qualità audio, da piccoli pacchetti persi individuali che non hanno quasi alcun impatto, a perdite di burst back-to-back che causano il cut-out audio completo.

L'utilizzo previsto dei dati da Walkie Talkie è di circa 20 Kb/s quando si invia o si riceve l'audio. Quando si è inattivi, l'utilizzo previsto dei dati da Walkie Talkie è trascurabile.

### <a name="walkie-talkie-devices"></a>Dispositivi Walkie Talkie

I lavoratori in prima linea spesso devono parlare e ricevere chiamate Walkie Talkie anche quando i loro telefoni sono bloccati. Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.

- **Cuffie**
  - Cuffie wireless 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Cuffie cablate 
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Telefoni robusti**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), Galaxy [XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    -  Configurazione manuale: con Teams installato, passare Impostazioni > funzionalità avanzate > XCover/Active. Attiva "Controlla il tasto XCover con l'app" e seleziona "Teams"
    -  [Configurazione MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Questi dispositivi non sono Teams certificati. Sono stati convalidati per funzionare con Teams Walkie Talkie.

### <a name="license-requirements"></a>Requisiti di licenza

L'app Walkie Talkie è inclusa in tutte le licenze a pagamento Teams in [Office 365 abbonamenti.](/office365/servicedescriptions/teams-service-description) Per altre informazioni su come ottenere Teams, vedere Come si ottiene l'accesso a [Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Alcune funzionalità avanzate possono richiedere licenze aggiuntive. Ad esempio, l'integrazione con Samsung Galaxy XCover Pro richiede una licenza Knox.

## <a name="further-information"></a>Altre informazioni

- Gli amministratori IT possono mantenere il controllo su chi usa Walkie Talkie tramite i criteri delle app.
- Se il tuo frontline worker usa i dati mobili per comunicare tramite Teams, Walkie Talkie userà lo stesso metodo.
- Walkie Talkie dovrebbe funzionare bene in situazioni con larghezza di banda ridotta o in situazioni in cui lo smartphone è connesso e funzionante. Walkie Talkie non funzionerà quando non c'è connettività.

Per altre informazioni sull'esperienza utente finale, vedere:

- [Introduzione a Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicare con il team con Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
