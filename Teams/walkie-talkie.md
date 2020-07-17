---
title: Applicazione walkie-talkie in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Come configurare l'app walkie talkie in Microsoft teams, da una prospettiva ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043011"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>App walkie talkie in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L'app walkie talkie in teams fornisce comunicazioni immediate push-to-Talk (PTT) per il team e sarà presto disponibile in anteprima pubblica in Android. Walkie talkie consente agli utenti di connettersi con il proprio team usando gli stessi canali sottostanti di cui sono membri. Solo gli utenti che si connettono a walkie talkie in un canale diventano partecipanti e possono comunicare tra loro tramite push-to-Talk, uno alla volta.

Con walkie-talkie in teams, i lavoratori di i FIRSTLINE possono ora comunicare in modo sicuro con un'esperienza di PTT familiare senza dover trasportare radio ingombranti e il walkie-talkie funziona ovunque con WiFi o connettività Internet cellulare.

## <a name="getting-started"></a>Introduzione

### <a name="deploying-walkie-talkie"></a>Distribuzione di walkie talkie

Durante l'anteprima pubblica, il walkie-talkie non è preinstallato. Per abilitare questa funzionalità per gli utenti dell'organizzazione, è necessario aggiungere walkie talkie ai criteri di [configurazione dell'app](teams-app-setup-policies.md)   assegnati agli utenti dall'interfaccia di [amministrazione di teams](https://admin.teams.microsoft.com/).

Una volta abilitato, walkie talkie sarà disponibile nell'app Android entro 48 ore.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Aggiunta di walkie talkie all'elenco delle app

Nell'interfaccia di amministrazione di Microsoft teams, in criteri di configurazione dell' **app teams**  >  **Setup policies**, è consigliabile consentire **il** **blocco degli utenti** impostato su attivato. Quindi, nella sezione app appuntate, fare clic su **+ Aggiungi app**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Mostra la sezione App aggiunte e il pulsante Aggiungi app da selezionare.":::

Nel riquadro **Aggiungi app Pinned** che viene visualizzato a destra usa la casella di testo **ricerca** per cercare walkie-talkie. Quando si ha un risultato di ricerca, fare clic sul pulsante **Aggiungi** a destra del nome per aggiungerlo all'elenco.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Mostra la barra laterale Aggiungi app Pinned con walkie immessa nel riquadro di ricerca e nell'app walkie talkie nei risultati della ricerca, con il pulsante Aggiungi accanto.":::

L'app walkie-talkie dovrebbe ora essere visualizzata nell'elenco delle app aggiunte ed essere disponibile per l'uso quando si fa clic sul pulsante **Salva** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Mostra l'elenco delle app bloccate con l'app walkie-talkie aggiunta e il pulsante Salva sotto l'elenco.":::

### <a name="network-documentation"></a>Documentazione di rete

Walkie talkie in teams richiede connettività Internet e al di sotto delle condizioni di rete necessarie per un'esperienza ottimale.

Latenza (RTT) < 300ms | Jitter < 30ms | Perdita di pacchetti < 1%

Come indicato in precedenza, la qualità dei contenuti multimediali in tempo reale su una rete IP è fortemente influenzata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:

- **Latenza** : è il tempo necessario per ottenere un pacchetto IP dal punto a al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e la velocità della luce, incluso il sovraccarico aggiuntivo adottato dai vari router in mezzo. La latenza viene misurata come RTT (Round Trip Time).
- **Perdita di pacchetti** : spesso viene definita come percentuale di pacchetti persi in una determinata finestra di tempo. La perdita di pacchetti influenza direttamente la qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto, alle perdite di burst di back-to-back che causano un cut-out audio completo.
- **Jitter** : si tratta della variazione media di ritardo tra i pacchetti successivi.

L'utilizzo dei dati attesi da walkie talkie è di circa 20KB/s durante l'invio o la ricezione di audio. Quando è inattivo, l'utilizzo previsto dei dati da walkie talkie è irrilevante.

### <a name="walkie-talkie-devices"></a>Dispositivi walkie-talkie

I lavoratori I FIRSTLINE spesso devono parlare e ricevere chiamate walkie-talkie anche quando i loro telefoni sono bloccati. Questa esperienza è possibile tramite dispositivi specializzati con un pulsante PTT dedicato.

- Telefoni esistenti
  - Auricolari cablati ([Klein Electronics](https://www.kleinelectronics.com/))
  - Auricolari wireless ([Jabra BlueParrott](https://www.blueparrott.com/))
- Telefoni robusti
  - Samsung Galaxy XCover Pro
    - [Altre info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Guida alla configurazione](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> Questi dispositivi non sono certificati in teams. Sono stati convalidati per collaborare con walkie talkie teams.

### <a name="license-requirements"></a>Requisiti di licenza

L'app walkie talkie è inclusa in tutte le licenze a pagamento dei team in [abbonamenti a Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing). Per altre informazioni su come ottenere teams, vedere [come si accede a Microsoft teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Alcune funzionalità avanzate potrebbero richiedere licenze aggiuntive. Ad esempio, l'integrazione con Samsung Galaxy XCover Pro richiede una licenza Knox.

## <a name="further-information"></a>Altre informazioni

- ITAdmins può mantenere il controllo su chi usa walkie talkie attraverso i criteri per le app.
- Se il lavoratore i FIRSTLINE usa dati mobili per comunicare tramite Team, walkie-talkie userà lo stesso metodo.
- Il walkie-talkie dovrebbe funzionare correttamente in situazioni di larghezza di banda ridotta o in situazioni in cui lo smartphone è connesso e funzionante. Il walkie-talkie non funziona quando non c'è connettività.

Per altre informazioni sull'esperienza utente finale, vedere:

- [Guida introduttiva a teams walkie talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicare con il team con il walkie-talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
