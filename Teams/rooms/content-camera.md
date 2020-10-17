---
title: Informazioni su come configurare le telecamere di contenuto-Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Usare una videocamera di contenuto in una sala Microsoft teams, che interagisce con il software di elaborazione delle immagini per consentire ai relatori di disegnare su una lavagna analogica.
ms.openlocfilehash: ced0a65c0c1fab25bd1b244aea7301d654c44a9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508313"
---
# <a name="content-cameras"></a>Videocamere di contenuto

Ora è possibile usare una videocamera di contenuto con un sistema di chat room Microsoft teams. Una fotocamera soddisfatta interagisce con un software di elaborazione delle immagini speciale e una lavagna per consentire a un relatore di disegnare su una lavagna analogica e condividere il contenuto con partecipanti remoti.

Vedere il video seguente per esempi di funzionalità della fotocamera del contenuto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurare una videocamera di contenuto

> [!NOTE]
> Rispettare sempre il codice edilizio del proprio paese o dell'area geografica, che può definire una distanza minima dal pavimento o un requisito per garantire l'assicurazione di un equipaggiamento montato a soffitto a una trave o a un'altra struttura. Seguire le istruzioni di montaggio per l'hardware fornito con la fotocamera selezionata. I kit di montaggio per la fotocamera OEM includono una fotocamera, una prolunga USB 2,0 e un cablaggio obbligatorio.

La dimensione della lavagna usata per la condivisione influenza la posizione della fotocamera. Le raccomandazioni per le dimensioni del Board sono:

- 3-6 ft (0.9-1.8 m) Wide-supportato
- 6-9 ft (1.8-2,7 m) Wide-consigliato
- 9-12 ft (2,7-3.6 m) Wide-supportato
- Sopra i 12 ft (3,6 m) di larghezza: la fotocamera copre 9-12 ft (2,7-3,6 m) e ritaglia il resto.

## <a name="camera-location"></a>Posizione della fotocamera

La posizione ideale di una fotocamera soddisfatta è centrata verticalmente e orizzontalmente sulla lavagna. I codici edilizi locali possono avere restrizioni di altezza che richiedono una elevata elevazione della videocamera rispetto all'inizio della bacheca bianca.

È possibile installare la fotocamera fino a 6 in. (152 mm) superiore alla parte superiore della lavagna e centrato sulla lavagna bianca come illustrato. Verificare che nell'immagine della fotocamera sia incluso almeno un 6. (152 mm) su entrambi i lati orizzontalmente. Puoi usare l'anteprima della videocamera nell'app Microsoft teams Rooms per determinare il posizionamento finale della videocamera.

![Diagramma di posizionamento del contenuto della videocamera](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distanze della videocamera

L'esperienza utente remota ottimale consente di condividere i tratti input penna nell'intervallo di 1-2 mm per pixel nell'immagine della fotocamera del contenuto e i risultati migliori usano 1,5 mm per pixel. Tutte le fotocamere supportate supportano la risoluzione di 1920 x 1080 e alcune possono superare quella risoluzione.

La distanza della videocamera dalla lavagna si combina con la risoluzione della fotocamera e HFoV per determinare la distanza dalla lavagna. Nella tabella seguente sono illustrati alcuni esempi di distanze per varie dimensioni della lavagna. Puoi usare questi valori come punti di partenza per determinare la posizione finale della videocamera soddisfatta.

**Distanza della fotocamera dalla lavagna**

| Fotocamera HFoV |3 ft (0,91 m)     | 6 ft (1,8 m)    | 9 ft (2,74 m)        |12 ft.  (3,65 m)         | Distanza massima da lavagna  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80 °         | 1,79 ft (0,54 m) | 3,58 ft (1,09 m)  | 5,36 ft (1,6 m)    |7,15 ft (2,17 m) |7,51 ft (2,28 m) |
| 90 °         | 1,5 ft (0,45 m) | 3,00 ft (0,91 m)   | 4,5 ft (1,37 m)    |6,0 ft (1,82 m)    |6,3 ft (1,92 m) |
| 100 °        | 1,26 ft (0,38 m)| 2,52 ft (0,77 m)   | 3,78 ft (1,15 m)   |5,03 ft (1,53 m)   |5,29 ft (1,61 m) |
| 110 °        | 1,05 ft (0,32 m)| 2,10 ft (0,64 m)   | 3,15 ft (0,96 m)   |4,2 ft (1,28 m)    |4,41 ft (1,31 m) |
| 120 °        | 0,87 ft (0,26 m)| 1,73 ft (0,52 m)   | 2,60 ft (0,79 m)   |3,46 ft (1,05 m)   |3,64 ft (1,10 m) |
|             |               |                  |                  |        |                    |                  |

La distanza tra la videocamera di contenuto e il muro su cui è montata la lavagna dipende dal HFoV per il modello di fotocamera, che varia. Installare le telecamere con un HFoV più grande (ad esempio 120 gradi) più vicino al muro e le telecamere con un HFoV più stretto più lontano dal muro. Verificare la HFoV prima di iniziare a installare la fotocamera selezionata.

Se si dispone di lavagne di dimensioni superiori a 12 ft (3,65 m) o senza angoli, ad esempio lavagne a muro piene, è possibile posizionare la videocamera in un punto qualsiasi del centro. Il software di miglioramento seleziona un'area al centro se non riesce a trovare gli angoli della lavagna.

> [!NOTE]
> È possibile usare un nastro di colore scuro o altri elementi per creare un'area della fotocamera del contenuto definita in una bacheca bianca completa.
>
> È possibile scegliere di montare la videocamera su un treppiede mobile anziché su un supporto permanente. Posizionare il treppiede centrato sulla lavagna. Questa configurazione può essere temporanea o usata in presenza di poche possibilità di abbattere l'apparecchiatura. Se si usa un supporto temporaneo, tenere presente che il miglioramento del contenuto sarà influenzato se si sposta la fotocamera dopo la condivisione iniziale e sarà necessario ripartire per correggere il movimento.
>
> Una bacheca di scrittura non bianca non è supportata.

## <a name="supported-cameras"></a>Fotocamere supportate

Per determinare se è possibile usare una fotocamera come videocamera di contenuto, vedere [versioni del firmware certificate per le periferiche audio e video USB](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

In alternativa, fare riferimento al Marketplace di Microsoft teams Devices per i kit di telecamere di contenuto supportati in [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Impostazioni fotocamera

Dopo aver installato la videocamera nella sala, configurarla nella console Microsoft teams rooms della sala:

1. Selezionare **Settings** l' ![ icona impostazioni impostazioni ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) , accedere come amministratore e selezionare **Impostazioni dispositivo**.
2. Nella sezione **impostazioni predefinite fotocamera** selezionare la fotocamera del contenuto e verificare che l'opzione **miglioramenti contenuto** sia selezionata.
3. Opzionale Se la fotocamera è stata installata a testa in giù perché la videocamera è stata montata dal soffitto, selezionare l'opzione **ruota contenuto camera 180 °** .
4. Selezionare **Salva ed esci**.

![Configurazione della videocamera di contenuto](../media/content-camera.png)

Puoi anche modificare queste impostazioni in remoto usando un [file di configurazione XML](xml-config-file.md).

## <a name="see-also"></a>Vedere anche

[Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)


