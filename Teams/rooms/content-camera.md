---
title: Informazioni su come configurare le fotocamere dei contenuti - Microsoft Teams
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
description: Usare una fotocamera del contenuto in una sala di Microsoft Teams, che interagisce con il software di elaborazione delle immagini per consentire ai relatori di disegnare su una lavagna analogica.
ms.openlocfilehash: ced0a65c0c1fab25bd1b244aea7301d654c44a9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508313"
---
# <a name="content-cameras"></a>Videocamere di contenuto

È ora possibile usare una fotocamera del contenuto con un sistema Room di Microsoft Teams. Una videocamera del contenuto interagisce con un software speciale di elaborazione delle immagini e con una lavagna per consentire a un relatore di disegnare su una lavagna analogica e condividere il contenuto con i partecipanti remoti.

Guarda il video seguente per esempi di funzionalità della fotocamera del contenuto.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurare una fotocamera del contenuto

> [!NOTE]
> Attenersi sempre al codice dell'edificio del paese o dell'area geografica, che può definire una distanza minima dal piano o un requisito che l'attrezzatura montata su soffitto sia protetta a un aviatore o a un'altra struttura. Seguire le istruzioni di montaggio per l'hardware fornito con la videocamera selezionata. I kit di montaggio per fotocamera OEM includono una fotocamera, estenditori USB 2.0 e cavi necessari.

Le dimensioni della lavagna usata per la condivisione influiscono sul posizionamento della fotocamera. Le raccomandazioni relative alle dimensioni della bacheca sono:

- Larghezza: 0,9 -1,8 m, supportata
- Larghezza: 1,8 -2,7 metri (1,8 - 2,7 m) - Scelta consigliata
- Larghezza 9-12 metri (2,7 - 3,6 m) - Supportata
- Larga 3,6 metri, la fotocamera copre i 2,7-3,6 metri e ritaglia il resto.

## <a name="camera-location"></a>Posizione fotocamera

Il posizionamento ideale di una fotocamera del contenuto è centrato verticalmente e orizzontalmente sulla lavagna. I codici di edificio locali possono avere restrizioni di altezza che richiedono che la videocamera sia elevata più in alto rispetto alla parte superiore della lavagna.

Puoi installare la fotocamera fino a 6". (152 mm) in più rispetto alla parte superiore della lavagna e centrato sulla lavagna, come illustrato. Assicurarsi che l'immagine della fotocamera includa almeno una parte di almeno 6 in. Bordo (152 mm) su entrambi i lati orizzontalmente. È possibile usare l'anteprima della fotocamera nell'app Sale di Microsoft Teams per determinare il posizionamento finale della fotocamera.

![Diagramma di posizionamento della fotocamera del contenuto](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distanza della fotocamera

Usando gli indicatori tipici della lavagna, l'esperienza utente remota ottimale è la condivisione dei tratti input penna nell'intervallo da 1 a 2 mm per pixel nell'immagine della fotocamera del contenuto e i risultati migliori usano 1,5 mm per pixel. Tutte le fotocamere supportate offrono una risoluzione 1920 x 1080 e alcune possono superare tale risoluzione.

La distanza della fotocamera dalla lavagna si combina con la risoluzione della videocamera e con HFoV per determinare la distanza dalla lavagna. La tabella seguente mostra esempi di distanze per varie dimensioni della lavagna. È possibile usare questi valori come punti di partenza per determinare il posizionamento finale della fotocamera del contenuto.

**Distanza della fotocamera dalla lavagna**

| Fotocamera HFoV |3 ft. (0.91 m)     | 6 ft. (1.8 m)    | 9 ft. (2.74 m)        |12 ft.  (3,65 m)         | Distanza massima da Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1,79 ft. (0,54 m) | 1,58 ft. (1,09 m)  | 1,36 ft. (1,6 m)    |2,15 ft. (2.17 m) |7,51 ft. (2.28 m) |
| 90°         | 1,5 ft. (0,45 m) | 3.00 ft. (0.91 m)   | 4,5 ft. (1,37 m)    |6,0 ft. (1,82 m)    |6,3 ft. (1,92 m) |
| 100°        | 1,26 ft. (0.38 m)| 2,52 ft. (0,77 m)   | 3,78 ft. (1,15 m)   |1,03 ft. (1,53 m)   |1,29 ft. (1,61 m) |
| 110°        | 1,05 ft. (0,32 m)| 2.10 ft. (0.64 m)   | 3,15 ft. (0,96 m)   |4,2 ft. (1,28 m)    |4,41 ft. (1,31 m) |
| 120°        | 0,87 ft. (0,26 m)| 1,73 ft. (0,52 m)   | 2,60 ft. (0,79 m)   |3,46 ft. (1,05 m)   |3,64 ft. (1,10 m) |
|             |               |                  |                  |        |                    |                  |

La distanza tra la fotocamera del contenuto e il muro su cui è montata la lavagna dipende dall'HFoV del modello di videocamera, che varia. Installa fotocamere con HFoV più grande (ad esempio 120 gradi) più vicino alla parete e fotocamere con HFoV più stretto lontano dal muro. Controlla l'HFoV prima di iniziare a installare la videocamera selezionata.

Se sono presenti lavagne di dimensioni superiori a 3,65 m (3,65 m) o nessun angolo (ad esempio lavagne a parete complete), è possibile posizionare la fotocamera in un punto qualsiasi al centro. Il software di miglioramento seleziona un'area al centro se non riesce a trovare gli angoli della lavagna.

> [!NOTE]
> È possibile usare nastro di colore scuro o altri elementi per creare un'area definita della fotocamera su una lavagna a parete intera.
>
> È possibile scegliere di montata la fotocamera su un tripode spostabile invece che su un supporto permanente. Posizionare il trepode centrato sulla lavagna. Questa configurazione può essere temporanea o usata nei casi in cui è poco probabile che l'apparecchiatura venga sotbatteta. Se usi un supporto temporaneo, ricorda che il miglioramento del contenuto avrà un impatto se sposti la videocamera dopo la condivisione iniziale e dovrai condividerla di nuovo per correggere il movimento.
>
> Una lavagna non bianca non è supportata.

## <a name="supported-cameras"></a>Fotocamere supportate

Per determinare se è possibile usare una videocamera come videocamera dei contenuti, consultare le versioni certificate del firmware per [le periferiche audio e video USB.](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)

In caso contrario, consulta Microsoft Teams Devices Marketplace per i kit di fotocamera dei contenuti supportati [all'aka.ms/teamsdevices.](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>Impostazioni fotocamera

Dopo aver installato la videocamera nella sala, configurala sulla console Di Microsoft Teams Rooms della sala:

1. Selezionare **l'icona** ![ ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) Impostazioni, accedere come amministratore e selezionare Impostazioni **dispositivo.**
2. Nella sezione **Impostazioni predefinite videocamera** selezionare la videocamera  dei contenuti e verificare che sia selezionata l'opzione Miglioramenti al contenuto.
3. (Facoltativo) Se la fotocamera è stata installata capovolta perché è stata montata dal soffitto, selezionare l'opzione Ruota fotocamera del contenuto **di 180°.**
4. Selezionare **Salva e esci.**

![Configurazione della fotocamera del contenuto](../media/content-camera.png)

È anche possibile modificare queste impostazioni in remoto usando un [file di configurazione XML.](xml-config-file.md)

## <a name="see-also"></a>Vedere anche

[Gestire le impostazioni della console di Microsoft Teams Rooms in remoto con un file di configurazione XML](xml-config-file.md)

[Requisiti per Microsoft Teams Rooms](requirements.md)


