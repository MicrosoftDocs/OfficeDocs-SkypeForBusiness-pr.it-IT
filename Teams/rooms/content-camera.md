---
title: Informazioni su come configurare le fotocamere dei contenuti - Microsoft Teams
author: CarolynRowe
ms.author: crowe
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Usare una fotocamera contenuto in una sala riunioni di Microsoft Teams, che interagisce con il software di elaborazione delle immagini per consentire ai relatori di disegnare su una lavagna analogica.
ms.openlocfilehash: a06dc6b5ebd9dae969a888067146afaccbaaa7e6
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794134"
---
# <a name="content-cameras"></a>Videocamere di contenuto

Ora è possibile usare una fotocamera del contenuto con un sistema Room di Microsoft Teams. Una fotocamera del contenuto interagisce con un software speciale di elaborazione delle immagini e una lavagna per consentire a un relatore di disegnare su una lavagna analogica e condividere il contenuto con i partecipanti remoti.

Guarda il video seguente per esempi di funzionalità della fotocamera contenuto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurare una fotocamera del contenuto

> [!NOTE]
> Attenersi sempre al codice dell'edificio del proprio paese o area, che può definire una distanza minima dal pavimento o l'obbligo che le attrezzature montate a soffitto siano fissati a una trave o ad altre strutture. Segui le istruzioni di montaggio per l'hardware fornito con la fotocamera selezionata. I kit di montaggio per fotocamere OEM includono una fotocamera, extender USB 2.0 e cavi necessari.

Le dimensioni della lavagna utilizzata per la condivisione influiscono sul posizionamento della fotocamera. I suggerimenti per le dimensioni della bacheca sono:

- Larghezza di 0,9-1,8 m (3-6 piedi) - Supportata
- Larghezza di 1,8-2,7 m (1,8-2,7 m) - Scelta consigliata
- Larghezza di 2,7-3,6 m (9-12 piedi) - Supportata
- Oltre i 3,6 m di larghezza , la fotocamera copre 9-12 piedi (2,7-3,6 m) e ritaglia il resto.

## <a name="camera-location"></a>Posizione della fotocamera

La posizione ideale di una fotocamera del contenuto è centrata verticalmente e orizzontalmente sulla lavagna. I codici dell'edificio locale possono avere restrizioni di altezza che richiedono che la fotocamera sia elevata più in alto rispetto alla parte superiore della lavagna.

Puoi installare la fotocamera fino a 6 pollici. (152 mm) superiore alla parte superiore della lavagna e centrata sulla lavagna, come illustrato. Assicurati che l'immagine della fotocamera includa almeno 6 pollici. bordo (152 mm) su entrambi i lati orizzontalmente. Puoi usare l'anteprima della fotocamera nell'app Microsoft Teams Rooms per determinare il posizionamento finale della fotocamera.

![Diagramma di posizionamento della fotocamera del contenuto.](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distanze della fotocamera

Usando indicatori tipici della lavagna, l'esperienza utente remota ottimale consiste nel condividere i tratti input penna nell'intervallo 1-2 mm per pixel nell'immagine della fotocamera contenuto e i risultati migliori usano 1,5 mm per pixel. Tutte le fotocamere supportate offrono una risoluzione 1920 x 1080 e alcune possono superare tale risoluzione.

La distanza della fotocamera dalla lavagna si combina con la risoluzione della fotocamera e il campo  vista orizzontale (HFoV) per determinare la distanza dalla lavagna. La tabella seguente mostra esempi di distanze per diverse dimensioni della lavagna. È possibile usare questi valori come punti di partenza per determinare il posizionamento finale della fotocamera del contenuto.

**Distanza della fotocamera dalla lavagna**

| Fotocamera HFoV |0,91 m (3 piedi)     | 1,8 m (1,8 m)    | 2,74 m (9 piedi)        |12 ft.  (3,65 m)         | Distanza massima da Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 0,54 m (1,79 piedi) | 1,09 m (3,58 piedi)  | 1,6 m (5,36 piedi)    |2,17 m (7,15 piedi) |2,28 m (7,51 piedi) |
| 90°         | 0,45 m (1,5 piedi) | 0,91 m (3,00 piedi)   | 1,37 m (4,5 piedi)    |1,82 m (1,82 piedi)    |1,92 m (1,92 m) |
| 100°        | 0,38 m (1,26 piedi)| 0,77 m (2,52 piedi)   | 1,15 m (3,78 piedi)   |1,53 m (5,03 piedi)   |1,61 m (5,29 piedi) |
| 110°        | 0,32 m (1,05 piedi)| 0,64 m (2,10 piedi)   | 0,96 m (3,15 piedi)   |1,28 m (4,2 piedi)    |1,31 m (1,41 piedi) |
| 120°        | 0,26 m (0,87 piedi)| 0,52 m (1,73 piedi)   | 0,79 m (2,60 piedi)   |1,05 m (3,46 piedi)   |1,10 m (3,64 piedi) |
             

La distanza tra la fotocamera del contenuto e la parete su cui è montata la lavagna dipende dal HFoV per quel modello di fotocamera, che varia. Installa fotocamere con un HFoV più grande (ad esempio 120 gradi) più vicino al muro e fotocamere con un HFoV più stretto più lontano dal muro. Controlla HFoV prima di iniziare a installare la fotocamera scelta.

Se disponi di lavagne di dimensioni superiori a 3,65 m o senza angoli(come lavagne a parete intera), puoi posizionare la fotocamera in qualsiasi punto del centro. Il software di miglioramento seleziona un'area al centro se non riesce a trovare gli angoli della lavagna.

> [!NOTE]
> Puoi usare nastro di colore scuro o altri elementi per creare un'area della fotocamera con contenuto definito su una lavagna bianca a parete intera. In questo modo i partecipanti della sala potranno sapere quando disegnano in un'area acquisita dalla fotocamera del contenuto.
>
> Puoi scegliere di montarla su un treppiede spostabile invece che su una montatura permanente. Posiziona il treppiede al centro sulla lavagna. Questa configurazione può essere temporanea o usata in caso di poche possibilità di rovesciare l'attrezzatura. Se usi un montaggio temporaneo, ricorda che il miglioramento dei contenuti sarà interessato se sposti la fotocamera dopo la condivisione iniziale e dovrai condividerla di nuovo per correggere il movimento.
>
> Una bacheca che non è bianca non è supportata.

## <a name="supported-cameras"></a>Fotocamere supportate

Per determinare se puoi utilizzare una fotocamera come videocamera contenuto, consulta [Versioni certificate del firmware per le periferiche audio e video USB](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

In alternativa, consulta il marketplace dei dispositivi Microsoft Teams per i kit di fotocamera contenuto supportati in [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Impostazioni della fotocamera

Una volta installata la fotocamera nella stanza, impostala nella console Microsoft Teams Rooms della stanza:

1. Seleziona **Impostazioni** ![Icona Impostazioni,](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) accedi come Amministrazione e seleziona **Periferiche**.
2. Nella sezione **Fotocamera contenuto** seleziona la fotocamera del contenuto e assicurati che l'opzione **Miglioramenti del contenuto** sia selezionata.
3. (Facoltativo) Se la fotocamera è stata installata capovolta perché la fotocamera è stata montata dal soffitto, seleziona l'opzione **Ruota fotocamera contenuto a 180°** .
4. Seleziona **Salva e chiudi**.

![Configurazione della fotocamera contenuto.](../media/content-camera1.png)

È anche possibile modificare queste impostazioni in remoto usando un [file di configurazione XML](xml-config-file.md).

## <a name="see-also"></a>Vedere anche

[Gestire in remoto le impostazioni di una console Microsoft Teams Rooms con un file di configurazione XML](xml-config-file.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)


